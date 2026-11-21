---
industry: healthcare
region: Global
updated: 2026-11-21
---

# 🧩 Patrones de composición — Healthcare

> Recetas concretas: repos nombrados, licencia verificada, y cómo se cablean.
> Cada patrón dice además **qué evidencia produce**, porque en tres regiones la evidencia
> es lo que habilita la venta (ver `intel/market.md`).

## Patrón base

```
[Plataforma vertical open source: OpenEMR / OpenMRS / Medplum]
          ↓  FHIR R4 (nunca SQL directo)
[Servidor MCP sobre FHIR: wso2/fhir-mcp-server | the-momentum/fhir-mcp-server]
          ↓  herramientas tipadas
[De-identificación local: maziyarpanahi/openmed]
          ↓
[Agente(s): Biomni | MedRAX | Hospilot | orquestador propio]
          ↓
[Event log por decisión  →  evidencia de auditoría]
          ↓
[UI conversacional / API para el cliente]
```

La regla que no se negocia: **agente al lado, no fork del EMR.** Con GPL/AGPL además evita que el
entregable herede obligaciones.

---

## P1 — Agente clínico sobre FHIR sin tocar un solo dato de paciente

**El problema que resuelve:** no se puede construir ni demostrar sobre PHI real, y conseguir un
acuerdo de datos tarda semanas. Esto arranca el día uno.

- **Datos**: [synthetichealth/synthea](https://github.com/synthetichealth/synthea) (Apache-2.0) genera
  pacientes sintéticos con historia longitudinal y los exporta a FHIR.
- **Servidor**: cargar ese bundle en [hapifhir/hapi-fhir](https://github.com/hapifhir/hapi-fhir)
  (Apache-2.0) o [medplum/medplum](https://github.com/medplum/medplum) (Apache-2.0).
- **Acceso del agente**: [wso2/fhir-mcp-server](https://github.com/wso2/fhir-mcp-server) (Apache-2.0)
  expone los recursos FHIR como herramientas tipadas. Es lo que evita que el agente invente campos.
- **Evaluación**: [stanfordmlgroup/MedAgentBench](https://github.com/stanfordmlgroup/MedAgentBench)
  (MIT) puntúa el agente contra tareas FHIR reales.
- **Cableado**: synthea → `POST /fhir/Bundle` → MCP server apuntando a ese endpoint → agente con el
  MCP registrado → correr MedAgentBench contra el mismo endpoint.

**Evidencia que produce:** una cifra de evaluación reproducible. En una conversación clínica eso
pesa más que una demo, y es citable ante un comité.
**Tiempo estimado:** 1–2 semanas hasta demo evaluada.

---

## P2 — Capa agéntica sobre un EMR ya instalado (sin forkearlo)

**El problema:** el cliente ya tiene OpenEMR u OpenMRS en producción y no va a migrar.

- **Base**: [openemr/openemr](https://github.com/openemr/openemr) (GPL-3.0) — **no se forkea**, se
  consume su API FHIR. Así la GPL no alcanza al entregable.
- **Referencia de arquitectura**: [Carer-Healthcare-AI/Hospilot](https://github.com/Carer-Healthcare-AI/Hospilot)
  (MIT) ya hace exactamente esto: orquestación multi-agente sobre el FHIR de OpenEMR con LangGraph +
  Temporal, y **humano aprobando cada paso consecuente**. Leer su diseño antes de escribir el propio.
- **Durabilidad**: Temporal (o equivalente) da reintentos y estado durable; un workflow clínico que
  se cae a mitad sin traza es un incidente, no un bug.
- **Integración con el resto del hospital**: [nextgenhealthcare/connect](https://github.com/nextgenhealthcare/connect)
  (MPL-2.0) para HL7v2 donde todavía no hay FHIR.

**Evidencia que produce:** cola de aprobación humana con quién aprobó qué y cuándo — el artefacto
que piden Singapur (responsabilidad institucional) y CFM 2.454/2026 (uso de IA en el expediente).
**Tiempo estimado:** 3–5 semanas.

---

## P3 — EMEA: anclar el agente en la especificación oficial de gematik

**Por qué este patrón existe:** la objeción de interoperabilidad en Alemania se gana con
procedencia, no con argumentos.

- **Spec**: [gematik/api-erp](https://github.com/gematik/api-erp) (Apache-2.0, e-receta) y
  [gematik/api-ePA](https://github.com/gematik/api-ePA) (Apache-2.0, historia clínica). Son de la
  **agencia nacional alemana de salud digital**, no de un tercero.
- **Cableado**: generar el cliente **desde la spec en tiempo de build** (paso de CI que descarga la
  versión fijada y corre el generador OpenAPI). **No vendorizar el archivo**: se cita la fuente, no
  se copia, y así la actualización es un bump de versión y no una migración.
- **Datos para desarrollo**: synthea + perfiles alemanes; EHDS como vía de acceso a datos reales de
  uso secundario cuando llegue el momento de validar.
- **Discurso**: *"el cliente está generado desde la spec de gematik, no desde nuestra
  interpretación"* — y el cliente lo verifica en dos minutos.

**Segunda pierna obligatoria:** no construir la urgencia sobre el AI Act. El Anexo I se movió a
**2-ago-2028** y hay una propuesta viva para sacar los dispositivos del AI Act por completo. La
pierna firme es **MDR/IVDR, que no se movió**, más el **Art. 50 vigente desde ago-2026**.

---

## P4 — LATAM: agente RNDS que produce la evidencia de CFM 2.454/2026 por construcción

**El patrón de mayor valor comercial de la KB**, porque la norma **ya está en vigor** (10-ago-2026)
y funciona como filtro de venta en Brasil.

- **Acceso y validación**: [Voa-Health/rnds](https://github.com/Voa-Health/rnds) (Apache-2.0) da
  identificadores, códigos y validación FHIR de la RNDS **y ya expone un servidor MCP**, así que el
  agente obtiene herramientas tipadas sin trabajo de integración.
- **Desarrollo sin acreditación**: el sandbox local de
  [Precisa-Saude/fhir-brasil](https://github.com/Precisa-Saude/fhir-brasil) (Apache-2.0) permite
  construir y demostrar **antes** de tener certificado ICP-Brasil y acreditación DATASUS.
- **Backend Java**: [IgMiras/rnds-br-connect](https://github.com/IgMiras/rnds-br-connect) (Apache-2.0)
  construye y valida los documentos FHIR con mapeo de terminología enchufable.
- **La parte que vende**: event log por decisión, con cada afirmación del agente anclada a un
  `Resource.id` FHIR concreto. Eso satisface los tres requisitos de CFM 2.454/2026 —clasificación
  de riesgo por sistema, auditoría continua y uso de IA documentado en el expediente— **como
  subproducto de la arquitectura**, no como un módulo de cumplimiento aparte.
- **Honestidad obligatoria con el cliente**: los cuatro repos RNDS son **comunitarios y declaran no
  estar afiliados al Ministério da Saúde ni al DATASUS**. La RNDS no publica paquete FHIR versionado,
  así que los perfiles se capturan de Simplifier. Decirlo de entrada evita el problema en auditoría.

**Tiempo estimado:** 2–4 semanas a piloto en sandbox.

---

## P5 — APAC: terminología correcta como columna vertebral

**El problema:** un agente que codifica mal no es un agente útil, y la explicabilidad es el cuello
de botella declarado de la región (solo ~30% de los pilotos llega a clínica).

- **Espina dorsal**: [healthymind-tech/Taiwan-Health-MCP](https://github.com/healthymind-tech/Taiwan-Health-MCP)
  (MIT) trae **73 herramientas** sobre ICD-10-CM/PCS, SNOMED CT, LOINC, fármacos y nutrición TFDA, y
  validación de FHIR R4 IG, construido con el SDK TypeScript oficial de MCP para SaaS de alto volumen.
- **Acceso al EHR**: [wso2/fhir-mcp-server](https://github.com/wso2/fhir-mcp-server) (Apache-2.0),
  que ya trae el flujo OAuth 2.0 completo contra Epic.
- **Plataforma donde no hay EHR comercial**: [ohcnetwork/care](https://github.com/ohcnetwork/care)
  (MIT), Digital Public Good nacido en India.
- **Cableado**: el agente registra los dos servidores MCP; toda salida codificada pasa por la
  herramienta de validación de terminología **antes** de escribirse. La validación no es opcional:
  es el paso que convierte el output en auditable.

**Entregable que mueve presupuesto:** el protocolo de validación local, no un modelo más.

---

## P6 — Agente de imagen médica

- **Framework**: [Project-MONAI/MONAI](https://github.com/Project-MONAI/MONAI) (Apache-2.0).
- **Preprocesado**: [TorchIO-project/torchio](https://github.com/TorchIO-project/torchio) (Apache-2.0)
  para volumétrico; [pydicom/pydicom](https://github.com/pydicom/pydicom) (MIT con excepciones) para I/O DICOM.
- **Agente de razonamiento**: [bowang-lab/MedRAX](https://github.com/bowang-lab/MedRAX) (Apache-2.0,
  ICML 2025) razona sobre radiografía de tórax sin entrenamiento adicional.
- **Archivo/PACS**: [dcm4che/dcm4chee-arc-light](https://github.com/dcm4che/dcm4chee-arc-light)
  (MPL-1.1, declarada en README) como fuente de estudios.
- ⛔ **No usar `Stanford-AIMI/CheXagent`**: es **CC-BY-NC-ND 4.0** (NonCommercial + NoDerivatives),
  verificado por bytes. Tres ciclos de esta KB lo recomendaron como Apache-2.0. Inutilizable en
  trabajo de cliente.

---

## P7 — Investigación biomédica y razonamiento terapéutico

- **Agente generalista**: [snap-stanford/Biomni](https://github.com/snap-stanford/Biomni)
  (Apache-2.0, 4099★) — el agente biomédico open source con más tracción real.
- **Herramientas**: [mims-harvard/ToolUniverse](https://github.com/mims-harvard/ToolUniverse)
  (Apache-2.0) como capa de herramientas; [mims-harvard/TxAgent](https://github.com/mims-harvard/TxAgent)
  (MIT) para razonamiento terapéutico sobre ella.
- **Corpus auditado por clínicos**: [EPFLiGHT/FullyOpenMeditron](https://github.com/EPFLiGHT/FullyOpenMeditron)
  (Apache-2.0) para evaluación abierta de respuesta clínica.
- ⛔ `EPFLiGHT/Meditron` **no tiene archivo de licencia**, y el slug histórico `epfl-llm/meditron`
  **no existe**. Usar FullyOpenMeditron, que sí está verificado.

---

## P8 — Puerta de CI de higiene de licencias (y entregable de cliente)

Este patrón existe porque esta KB ya cometió el error: recomendó durante tres ciclos un repo sin
licencia como MIT, y uno NonCommercial como Apache-2.0. El gate hace que no vuelva a pasar, y
**el informe que produce es exactamente el artefacto de procedencia que un hospital brasileño
necesita para su registro de riesgo bajo CFM 2.454/2026**: se cobra dos veces el mismo trabajo.

```bash
#!/usr/bin/env bash
# licence-gate.sh — verifica procedencia de licencia por BYTES, no por metadato.
# Reglas aprendidas: (1) las rutas raw son CASE-SENSITIVE; (2) la ausencia solo está
# "medida" si un archivo de control responde 200; (3) github.com/<slug>/blob/... es
# ciego detras de un proxy (403/404 siempre) — usar SIEMPRE raw.githubusercontent.com;
# (4) la existencia se decide con git ls-remote, nunca con search/repositories.
set -uo pipefail
for slug in "$@"; do
  refs=$(git ls-remote --heads "https://github.com/$slug" 2>/dev/null | wc -l)
  if [ "$refs" -eq 0 ]; then echo "DEAD      $slug"; continue; fi
  found=""
  for br in HEAD main master; do
    for n in LICENSE LICENSE.md LICENSE.txt license licence COPYING; do
      read -r code bytes < <(curl -s -o /dev/null \
        -w '%{http_code} %{size_download}' "https://raw.githubusercontent.com/$slug/$br/$n")
      [ "$code" = "200" ] && { found="$br/$n:$bytes"; break 2; }
    done
  done
  if [ -n "$found" ]; then
    echo "OK        $slug  $found"
  else
    ctrl=$(curl -s -o /dev/null -w '%{http_code}' \
      "https://raw.githubusercontent.com/$slug/HEAD/README.md")
    [ "$ctrl" = "200" ] && echo "NO-LICENCE $slug (control README=200)" \
                        || echo "UNMEASURED $slug (sin control: no concluir nada)"
  fi
done
```

**Bandas de bytes para interpretar el resultado** (ligeramente por encima = preámbulo de copyright,
benigno; muy por encima = licencia compuesta, leerla; muy por debajo = **puntero** a una licencia,
no la licencia):

| Licencia | Bytes canónicos | Visto en este pase |
|----------|-----------------|---------------------|
| MIT | ~1050–1100 | 1063 PyHealth · 1065 medspacy · 1073 HealthAgentBench · 1162 fhir-server (preámbulo MS) |
| Apache-2.0 | ~11347 | 11357 MONAI/synthea/openmed · 11342 gematik · **9765 medplum y 10714 ajhcs = apéndice recortado, leídos y benignos** |
| BSD-3-Clause | ~1500 | 1485 edsnlp |
| MPL-2.0 | ~16725 | 16727 OpenELIS (exacto) · 16967 Mirth (+preámbulo vendor) · 18199 OpenMRS (+disclaimer sanitario) |
| GPL-3.0 | ~35000 | 35147 OpenEMR |
| AGPL-3.0 | ~34500 | 34523 open-health-sync |
| EUPL-1.2 | ~13700 | 13733 gematik/E-Rezept-App-Android |

**Tres categorías de fila que hay que distinguir** (esta KB confundió las tres):

1. **Licencia verificada** — archivo presente, bytes en banda. Vendorizable.
2. **Declarada pero no archivada** — el README o un badge dicen la licencia y **no hay archivo**
   (aquí: `dcm4che/dcm4chee-arc-light` MPL-1.1, `frappe/health` GPL-3.0). Ni segura ni inutilizable:
   leer y prototipar sí, vendorizar al entregable no, y pedir el fix de una línea upstream.
3. **Sin licencia** — ni archivo ni declaración (aquí: `mitmedialab/MDAgents`,
   `EPFLiGHT/Meditron`, `gersteinlab/MedAgents`, `OHDSI/CommonDataModel`). El default legal es
   *todos los derechos reservados*. **Nunca al entregable.**

---

## P9 — El patrón de la segunda pierna regulatoria

No es un patrón técnico, es una regla de propuesta, y está aquí porque esta familia de KBs ya
perdió una recomendación por ignorarla.

**Regla:** si la urgencia de una propuesta descansa en una fecha regulatoria, necesita una segunda
pierna que no dependa de esa fecha. Las fechas se mueven: el AI Act desplazó el Anexo III a
2-dic-2027 y el Anexo I a 2-ago-2028, y hay una propuesta viva para sacar los dispositivos médicos
del AI Act por completo.

| Región | Pierna frágil (se mueve) | Pierna firme (no se movió) |
|--------|--------------------------|-----------------------------|
| EMEA | Anexo I del AI Act, 2-ago-2028 | **MDR/IVDR** + **Art. 50 vigente desde ago-2026** |
| North America | Lo que la FDA publique tras el discussion paper | **HIPAA** + certificación **ONC** + deberes profesionales |
| APAC | Proyecto de ley de IA en India; plazos de implementación | **DPDP Act** (vigente), **alto riesgo en Vietnam** (vigente) |
| LATAM | **PL 2338/2023** (en trámite, estado contradictorio) | **CFM 2.454/2026, en vigor desde 10-ago-2026** |

En LATAM la pierna firme es además la más fuerte de las cuatro regiones: es la única norma ya
exigible que pide artefactos concretos. Ahí la propuesta no necesita apoyarse en un calendario.
