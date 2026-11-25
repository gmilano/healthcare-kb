---
industry: healthcare
region: Global
updated: 2026-11-25
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

---

## P10 — Agente de autorización previa sobre la especificación Da Vinci

**Cuándo.** Cliente pagador (o proveedor que negocia con pagadores) en EE. UU. con la fecha de
CMS-0057-F encima: **API de autorización previa operativa el 1 de enero de 2027**.

**La disciplina de la segunda pierna, aplicada antes de perderla (ver P9).** La API es
**obligatoria**; la guía Da Vinci PAS es **recomendada** (CMS lista STU 2.0.1 y 2.1.0). Nunca
decirle al cliente «la ley exige Da Vinci»: lo verifica y se cae la credibilidad del resto de
la propuesta. Lo correcto, y además más fuerte: *«la ley exige exponer una API en una fecha; la
única implementación de referencia permisiva que existe es Apache-2.0 y es la que el mercado va
a interoperar»*.

**Piezas, todas Apache-2.0 verificadas por bytes:**

| Pieza | Repo | Papel |
|-------|------|-------|
| Descubrimiento | [HL7-DaVinci/CRD](https://github.com/HL7-DaVinci/CRD) | Decide, en el momento de la orden, si el servicio requiere autorización |
| Documentación | [HL7-DaVinci/dtr](https://github.com/HL7-DaVinci/dtr) | Rellena desde el EHR la documentación que el pagador exige |
| Envío | [HL7-DaVinci/prior-auth](https://github.com/HL7-DaVinci/prior-auth) | Implementación de referencia de PAS |
| Reglas | [cqframework/clinical-reasoning](https://github.com/cqframework/clinical-reasoning) | Motor CQL: **aquí vive el juicio y aquí está el margen** |
| Enganche | [cds-hooks/docs](https://github.com/cds-hooks/docs) | Punto de inserción del agente en el flujo clínico |
| Banco de pruebas | [HL7-DaVinci/test-ehr](https://github.com/HL7-DaVinci/test-ehr) | EHR de pruebas para el ciclo completo |
| Datos | [synthetichealth/synthea](https://github.com/synthetichealth/synthea) | Historiales sintéticos: cero PHI en desarrollo y demo |

**Montaje.**

1. `synthea` genera la cohorte → se carga en `medplum` o HAPI con
   [microsoft/fhir-loader](https://github.com/microsoft/fhir-loader) (MIT).
2. `test-ehr` + `CRD` responden al *hook* `order-sign`: ¿requiere autorización?
3. `dtr` resuelve el cuestionario; **las reglas se escriben en CQL**, no en el prompt.
4. El agente redacta y arma el paquete; `prior-auth` lo envía como PAS.
5. **Una persona aprueba todo lo que tenga consecuencia económica.** No es prudencia
   decorativa: es lo que los análisis de 2026 describen como la única configuración en
   producción, y lo que la obligación de motivar la denegación exige poder justificar.

**El entregable con margen es la biblioteca CQL.** El parser X12 es gratis y el conjunto CPT no
es de nadie que participe en el proyecto; la **regla** sí es del cliente, y es versionable,
auditable y reutilizable entre líneas de negocio. Facturar ahí.

**Lo que este patrón NO debe prometer:** una plataforma de ciclo de ingresos «todo open
source». Su salida se expresa en CPT, propietario de la AMA. Ver P11.

---

## P11 — Puerta de conjuntos de códigos: la licencia del código no es la del contenido

**Extiende P8 con una cuarta categoría.** P8 clasificaba repos en verificada /
declarada-pero-no-depositada / sin licencia. Falta la categoría que más caro sale:
**código permisivo con contenido encumbrado**.

El caso que lo motiva: `IHTSDO/snowstorm` es Apache-2.0 (9939 B verificados) y sirve SNOMED CT,
que exige **Licencia de Afiliado una por país**, gratis en los 54 Miembros y **con cuotas por
banda de renta del Banco Mundial fuera**. La puerta P8 lo aprobaría sin pestañear y el problema
aparecería en la auditoría del cliente.

**Matriz que debe acompañar a todo entregable sanitario:**

| Artefacto | Licencia del CÓDIGO | Licencia del CONTENIDO | Acción en el proyecto |
|-----------|--------------------|------------------------|----------------------|
| ICD-10-CM (`icd10-cm`, `simple_icd_10_CM`) | MIT | **Dominio público** | Libre. Poner aquí los componentes abiertos. |
| CPT | — | **AMA, cuota por usuario** | Registrar el identificador de licencia del cliente. Nunca redistribuir el conjunto. |
| SNOMED CT (`snowstorm`, `snow-owl`) | Apache-2.0 | **Afiliado, por país** | Una licencia por territorio del despliegue. Es partida de coste. |
| LOINC | — | Gratis con registro | Registrar y seguir. |
| X12 (`pyx12`, `stupidedi`, `EDI.Net`) | BSD-3 / MIT | Estructura libre | Adoptar, no reescribir. |

**Regla de CI, añadida a `licence-gate.sh`:** si una ruta de código puede **emitir un código
CPT** y no existe un identificador de licencia AMA registrado en el manifiesto del proyecto,
**el build falla**. Es la única comprobación de esta KB que protege al cliente de una
reclamación de copyright en lugar de protegerlo de un problema de licencia de software.

Y la verificación que este pase añade al método, barata y ya validada 8 de 8:
**`NOASSERTION` en GitHub no significa nada.** Abrir el fichero. `pyx12`, `imsweb/x12-parser`,
`bryand1/icd10-cm` y `crs4/hl7apy` son todas permisivas genuinas y GitHub no lo dice.

---

## P12 — Vigilar la frontera de la especificación (cómo ver venir el próximo hueco)

**El patrón que generaliza el hallazgo del pase.** El open source permisivo no aparece donde
hay demanda; aparece donde hay una **especificación compartida**. Y la frontera entre «juicio»
y «formato» **se mueve por acción regulatoria**, con un adelanto observable.

**Secuencia observada en la autorización previa:**

1. Un regulador declara una obligación (CMS-0057-F, enero de 2024).
2. Un organismo de estándares publica la guía de implementación (Da Vinci CRD/DTR/PAS).
3. **Aparecen implementaciones de referencia permisivas** — y aquí está la señal temprana:
   suben los **forks** antes que las estrellas. `test-ehr` tiene 8★ y 11 forks; `CRD` 45★ y 24.
4. El mandato entra en vigor (2027-01-01) y la capa ya es *commodity*.
5. El margen se desplaza a la capa de juicio inmediatamente superior.

**Qué vigilar, en orden de valor informativo:**

- Calendario de *ballots* de guías de implementación de HL7 y reglas propuestas de CMS. Dan
  entre uno y dos ciclos de ventaja sobre GitHub.
- **La razón estrellas/forks** de los repos del organismo de estándares. Una razón que baja
  hacia 1 indica adopción real en curso.
- Qué tareas de juicio están recibiendo una representación computable. **CQL es el vehículo**:
  cuando una regla de necesidad médica se puede escribir en CQL, deja de ser defendible como
  propiedad intelectual y pasa a ser infraestructura.

**Dos pruebas baratas de autenticidad, ambas gratis en una llamada a `search/repositories`:**

| Firma | Qué indica |
|-------|-----------|
| Una métrica sube mientras `pushed_at` no se mueve | Número inventado (regla del ciclo 5; así se detectó que MDAgents «crecía» de 2,1k a 2,5k★ sin push desde 2024) |
| Razón estrellas/forks por encima de ~50 | Atención sin uso. 149★/1f en una plantilla de 16 días es el caso límite, y es **el único repo** que pasa el filtro de agentes nuevos del sector |

**Predicción falsable para los próximos pases de esta KB**, en el espíritu de la que dejó el
pase financiero: *si* durante 2027 aparece una implementación de referencia permisiva para
**codificación clínica automatizada**, aparecerá **después** de que un regulador o un organismo
de estándares publique una representación computable del criterio de codificación —y **no**
antes, por mucha demanda de mercado que haya. Si aparece antes, esta tesis está mal y hay que
revisarla aquí.

---

## Pase 2026-11-25 — patrones P13 a P16

### P13 · Triaje y segmentación en imagen con la frontera de licencia en el límite HTTP

**Para qué:** un servicio radiológico que quiere pre-segmentación o priorización de estudios
sobre su PACS. Es el hueco mejor colocado del sector: substrato permisivo enorme, 1 230
precedentes 510(k) en radiología y sólo 7-9 repos agénticos encima.

**Receta, con la decisión de licencia incorporada:**

1. **Archivo DICOM — proceso separado, siempre.** [Orthanc](https://github.com/jodogne/OrthancMirror)
   (**GPL-3.0**, 35148 B) como contenedor propio, o el PACS que el cliente ya tenga. Se alcanza
   **exclusivamente por DICOMweb (QIDO-RS / WADO-RS / STOW-RS)**. Nada del producto se enlaza
   contra él, nada lo importa: es un servicio remoto que habla HTTP. Así el GPL-3 **no alcanza**
   al código entregable.
2. **Ingesta y normalización.** [pydicom](https://github.com/pydicom/pydicom) (MIT salvo
   porciones) para leer, y [dcmqi](https://github.com/QIICR/dcmqi) (BSD-3) para convertir la
   salida del modelo en objetos DICOM SEG válidos. Este segundo paso es el que hace que el
   resultado **vuelva al PACS y lo vea el radiólogo en su visor de siempre**, en lugar de morir
   en un panel aparte. Es la diferencia entre un piloto y un servicio.
3. **Inferencia.** [TotalSegmentator](https://github.com/wasserth/TotalSegmentator) (Apache-2.0)
   si las ~120 estructuras cubren el caso —cubren la mayoría de los casos de volumetría—, y
   [nnU-Net](https://github.com/MIC-DKFZ/nnUNet) (Apache-2.0) cuando hay que entrenar sobre
   datos del cliente. Empaquetado con
   [monai-deploy-app-sdk](https://github.com/Project-MONAI/monai-deploy-app-sdk) (Apache-2.0).
4. **Revisión humana.** [OHIF/Viewers](https://github.com/OHIF/Viewers) (MIT) empotrado, con
   [MONAILabel](https://github.com/Project-MONAI/MONAILabel) para que el radiólogo **corrija** la
   segmentación y la corrección vuelva como dato de entrenamiento.
5. **La capa agéntica, que es lo que no existe y por tanto lo vendible:** orquestar
   priorización de la lista de trabajo, comparación con estudios previos del mismo paciente y
   redacción del borrador estructurado. Sobre MCP, en la línea de
   [ChristianHinge/dicom-mcp](https://github.com/ChristianHinge/dicom-mcp) (MIT).

**Reglas de CI que hacen el patrón auditable:**
- Si el manifiesto de dependencias **enlaza** Orthanc o cualquier artefacto GPL-3, **el build
  falla**. Orthanc sólo puede aparecer como imagen de contenedor separada.
- Si un fichero de `dcm4che` aparece **modificado** en el árbol, el build falla (MPL obliga a
  publicar el fichero modificado).
- `fo-dicom` **no entra** mientras no haya fichero de licencia localizable.
- Toda salida de modelo debe pasar por `dcmqi` y validar como DICOM SEG antes de escribirse.

**Lo que no hay que prometer:** que el resultado es un dispositivo aprobado. MONAI, nnU-Net y
TotalSegmentator son **grado investigación y sin autorización regulatoria**. El entregable
honesto es *software de apoyo con validación local documentada*, y si el cliente quiere
indicación clínica, la conversación es 510(k) —donde, eso sí, hay 1 212 precedentes.

### P14 · Scribe ambiental autoalojado con coste conocido

**Para qué:** documentación clínica sin enviar la conversación del paciente a un tercero —el
requisito que aparece en cuanto hay comité de privacidad.

**Receta:** [Berta](https://github.com/phairlab/berta-ai-scribe) (**Apache-2.0**) como esqueleto,
porque ya abstrae el backend de voz (WhisperX, Whisper, Parakeet-MLX, Amazon Transcribe) y el
motor de LLM (Ollama, vLLM, LM Studio). Transcripción local, generación local, y la plantilla de
nota como artefacto versionado del cliente. [OpenScribe](https://github.com/Pl4tt/OpenScribe)
(MIT) como segunda referencia de implementación.

**La abstracción de backend es el entregable con margen**, no el prompt: permite empezar con
Whisper local y cambiar a un servicio gestionado (o al revés) sin tocar el flujo clínico, que es
justo el requisito de arquitectura que Singapur impone por la vía de la responsabilidad
institucional y Corea del Sur por la de la supervisión humana.

**Referencia de coste para el caso de negocio:** los autores de Berta publican **< 30 USD por
médico y mes** de coste operativo, sesión media de 7,6 minutos y 42 % de usuarios
personalizando plantilla. ⚠️ Cifras de los autores (artículo aceptado en JMIR Med Inform): sirven
para encuadrar un build-vs-buy, no para garantizar un número en contrato.

**Exclusión explícita:** [FreeScribe](https://github.com/ClinicianFOCUS/FreeScribe) es
**AGPL-3.0** (confirmado: el fichero dice *GNU AFFERO*, 34522 B). En un SaaS multi-inquilino el
AGPL obliga a ofrecer el fuente a los usuarios del servicio. **No entra en un entregable cerrado**,
y conviene decirlo antes de que alguien lo añada por parecerse a los demás.

### P15 · Vigilancia y analítica de salud pública sobre DHIS2

**Para qué:** ministerios de salud y programas regionales en LATAM y APAC — el comprador
institucional que el patrón «Odoo + IA» prometía y no podía cumplir.

**Receta:** [dhis2/dhis2-core](https://github.com/dhis2/dhis2-core) (**BSD-3-Clause**) como
sistema de registro, que el cliente muy probablemente **ya tiene** (más de 80 ministerios de
salud). Se extiende por su API de aplicaciones **sin bifurcar el núcleo**;
[dhis2-android-capture-app](https://github.com/dhis2/dhis2-android-capture-app) para captura sin
conexión en campo. Encima, la capa agéntica: detección de anomalías en series de notificación,
conciliación de datos de calidad dudosa y resumen narrativo por distrito.

**Por qué el encaje de licencia es el mejor de la sanidad abierta:** BSD-3 **no obliga a liberar**
el módulo que se construye encima. Plataforma permisiva + comprador institucional + capa de IA
sin cubrir, las tres cosas a la vez. Y la razón ★/forks de 0,88 confirma que se despliega.

**Para historia clínica individual, no usar DHIS2:** es agregación y seguimiento de programas.
Lo clínico es [Bahmni](https://github.com/Bahmni/openmrs-module-bahmniapps) (MPL-2.0, razón
0,48) o [medplum](https://github.com/medplum/medplum) (Apache-2.0, 1 034 forks).

### P16 · Puerta de licencia extendida: la quinta categoría

El ciclo 6 dejó la puerta P8/P11 con cuatro categorías (permisiva genuina · `NOASSERTION` que
hay que abrir · copyleft · código permisivo con contenido encumbrado). Este pase añade la que
faltaba y que se cobró cuatro clasificaciones erróneas de cuatro intentos:

| Categoría | Prueba | Veredicto |
|---|---|---|
| Permisiva genuina | Fichero abierto: MIT/Apache/BSD íntegro | Entra |
| `NOASSERTION` en metadato | **Abrir el fichero**; 4 de 4 eran algo distinto de lo que el metadato sugería | Depende del fichero |
| Copyleft fuerte (GPL/AGPL) | Texto del fichero | Sólo como proceso separado; **AGPL ni eso en SaaS** |
| Permisiva con contenido encumbrado | ¿La salida emite CPT, SNOMED CT fuera de país Miembro? | El cliente licencia el contenido |
| **NUEVA · licencia propia «estilo X»** | ¿El fichero es el texto estándar o un acuerdo redactado ad hoc? | **Revisión legal antes de incorporar.** Caso medido: `Slicer/Slicer`, «BSD style» pero es el *Contribution and Software License Agreement v1.0* del Brigham and Women's Hospital, 10514 B de condiciones propias |

Y la sexta situación, que no es categoría sino ausencia: **ningún fichero de licencia encontrado**
tras probar 9 variantes de nombre (`fo-dicom`, y el `NHSDigital/...-FHIR-SCR-IPS` del ciclo 6).
No es permisivo por defecto: es «todos los derechos reservados». No entra.

### Predicción falsable del ciclo 6 — estado al 2026-11-25: **sin refutar y a 37 días de la prueba**

El ciclo 6 registró en P12 que una tarea de juicio recibe oferta open source permisiva **después**
de que un regulador publique su representación computable, y nunca antes. El caso de prueba era
CMS-0057-F. Hoy queda **menos de mes y medio** para su fecha de cumplimiento (1-ene-2027) y el
estado es: los repos de `org:HL7-DaVinci` siguen vivos y **exactamente igual de medidos**
(`prior-auth` 38★/24f, idéntico al 22-nov), `cqframework/clinical-reasoning` idéntico (52★/46f),
y **ningún tracker público de preparación de pagadores** ha aparecido. La predicción no se ha
refutado. Dos precisiones nuevas que cambian el alcance de cualquier propuesta:

- **La API de autorización previa excluye los medicamentos.** Cubre artículos y servicios
  médicos. Un agente que prometa «autorización previa» incluyendo farmacia **está fuera del
  alcance de la norma** y hay que decirlo en la primera reunión.
- La API debe comunicar **aprobación, denegación con motivo específico, o petición de más
  información**: tres salidas, no dos. El «motivo específico» es la que obliga a trazabilidad y
  por tanto la que justifica la biblioteca CQL como entregable.

---

## Pase 2026-11-25 (c8) — patrones P17 a P20

### P17 · Nodo de uso secundario «a prueba de acto de ejecución» (la apuesta de modelo, cubierta)

**Para qué:** un hospital, una red o un ministerio europeo que tiene que estar listo para el
EHDS sin saber todavía qué modelo de datos exigirá su Estado miembro (**2027-03-26** designación
de autoridad de acceso, **2029-03-26** uso secundario). También sirve tal cual para un pagador o
una farmacéutica que quiera evidencia de mundo real.

**La idea que lo hace vendible:** no se promete acertar el modelo. Se promete una arquitectura
donde **cambiar de modelo cuesta una capa, no el sistema**.

**Receta concreta:**

1. **Levantar el nodo.** [OHDSI/Broadsea](https://github.com/OHDSI/Broadsea) (Apache-2.0) —
   `docker compose` con Atlas + WebAPI + HADES + base de datos con el CDM. No montar las piezas
   a mano: Broadsea es el artefacto que la comunidad mantiene y forkea (94★/81f).
2. **Construir contra la pierna firme, sin datos reales.**
   [synthea](https://github.com/synthetichealth/synthea) → [OHDSI/ETL-Synthea](https://github.com/OHDSI/ETL-Synthea)
   (Apache-2.0). Todo el desarrollo y la demo salen de aquí; el dato real entra al final y una vez.
3. **Diseñar el ETL como entregable, no como script.**
   [OHDSI/WhiteRabbit](https://github.com/OHDSI/WhiteRabbit) (Apache-2.0, 11346 B) escanea el
   origen y su módulo **Rabbit-in-a-Hat** produce el **documento de diseño** de ETL. Ese documento
   es lo que el cliente audita, y es lo que sobrevive a un cambio de modelo.
4. **El mapeo terminológico, aislado y versionado.**
   [OHDSI/Usagi](https://github.com/OHDSI/Usagi) para mapear códigos locales a conceptos estándar.
   **Esta capa va en su propio repositorio del cliente, con revisión en PR** — es el activo (P19).
5. **La puerta de calidad es el entregable facturable.**
   [OHDSI/DataQualityDashboard](https://github.com/OHDSI/DataQualityDashboard) (Apache-2.0, en
   `DESCRIPTION`) + [OHDSI/Achilles](https://github.com/OHDSI/Achilles). **Regla de CI: un nodo no
   se declara entregado sin informe DQD verde y caracterización Achilles adjunta.** Esto convierte
   «hemos convertido la base» en un hecho verificable, que es lo que una autoridad de acceso pedirá.
6. **Cohortes como código, no como clics.** [OHDSI/Capr](https://github.com/OHDSI/Capr)
   (Apache-2.0) define cohortes en R versionable; [OHDSI/CirceR](https://github.com/OHDSI/CirceR)
   las traduce. Un agente **genera un borrador de Capr y abre un PR** — nunca ejecuta la cohorte
   contra producción por su cuenta.
7. **Estudios en red:** [OHDSI/Strategus](https://github.com/OHDSI/Strategus) (razón 0,81) como
   orquestador. El agente **invoca** Strategus; no reimplementa la ejecución de estudios.
8. **La capa agéntica, donde está el hueco.**
   [OHNLP/omop_mcp](https://github.com/OHNLP/omop_mcp) (Apache-2.0) para dar acceso tipado al CDM
   por MCP, y [OHDSI/Criteria2Query](https://github.com/OHDSI/Criteria2Query) (Apache-2.0) como
   precedente oficial de «texto libre → cohorte». `omop agent stars:>=5` devuelve **2**: aquí se
   construye, no se compra.
9. **El borde se queda en FHIR.** El dato de origen llega por FHIR (medplum/HAPI, ver P10); OMOP
   es el modelo de **análisis**. La traducción FHIR→OMOP es la capa que se sustituye si el acto de
   ejecución nombra otro modelo. **Es el patrón «MT564 en el borde, seev.031 en el dominio» del
   pase financiero.**

**Qué NO prometer:** que el nodo «cumple el EHDS». A noviembre de 2026 el reglamento no nombra
modelo de datos y los actos de ejecución vencen el 2027-03-26. Se promete **estar listo para
cumplir con coste de cambio acotado**, y eso sí se demuestra con la arquitectura.

### P18 · Puerta de licencia consciente del lenguaje (regla de CI, reutilizable en las 12 industrias)

**El problema, medido:** GitHub reporta **`NONE`** para `OHDSI/CommonDataModel` (1 103★),
`PatientLevelPrediction`, `DataQualityDashboard`, `Achilles`, `CohortMethod`, `DatabaseConnector`,
`FeatureExtraction`, `ETL-Synthea`, `Strategus` y `CirceR`. **Los diez son Apache License 2.0**,
declarada en el `DESCRIPTION` de R. Una puerta que sólo mire `LICENSE` **descarta el substrato de
dato sanitario con más despliegue medido del mundo** por «sin licencia».

**La puerta, en orden:**

| Paso | Dónde mirar | Señal |
|---|---|---|
| 1 | `git ls-remote` | **Existe o no existe.** Árbitro único, en ambas direcciones |
| 2 | `LICENSE`, `LICENSE.md`, `.txt`, `LICENCE`, `COPYING`, `LICENSE-MIT`, `License`, `license.md`, `LICENSE.rst` (rutas **sensibles a mayúsculas**) | Licencia por fichero |
| 3 | **`DESCRIPTION`** (R) → `pyproject.toml`/`setup.py`/`setup.cfg` (Python) → `pom.xml` (Java/Maven) → `package.json` (Node) → `Cargo.toml` (Rust) | **El paso que faltaba.** Campo `License:` |
| 4 | `README` | Declaración débil: utilizable con criterio, **no** equivalente a fichero (caso `OHDSI/Usagi`) |
| 5 | Nada de lo anterior | **No entra.** Caso `OHDSI/Athena`: ni `LICENSE`, ni `DESCRIPTION`, ni bloque `<licenses>` en `pom.xml` |

**Reglas de CI derivadas:**
- Si una dependencia no supera los pasos 2-3, **el build falla**; el paso 4 requiere aprobación
  humana registrada.
- **`NOASSERTION` nunca es motivo de rechazo automático**: obliga a abrir el fichero. Racha
  histórica de esta KB: **10 de 10** resolvieron a permisiva genuina — **6 abiertos en este pase**
  (`gatk` Apache-2.0, `samtools` y `htslib` MIT/Expat, `galaxy` MIT, `hap.py` BSD+MIT, `omop_mcp`
  Apache-2.0) sobre los 4 que acumulaban los ciclos anteriores (`pydicom` entre ellos).
- **Bandas de bytes útiles** (acumuladas): Apache-2.0 íntegra **11325-11358 B**; Apache-2.0 sin
  apéndice **9765-10966 B**; MIT **1069-1078 B**; Unlicense **1210 B**; BSD-3 **1491 B**;
  MIT de Galaxy 1590 B; MPL-2.0 16725-16727 B (18072-18199 con descargo de OpenMRS);
  AGPL-3.0 **34522 B**. Una banda **orienta**; el texto decide.

### P19 · El mapeo terminológico como producto (LATAM, y es el margen del plano)

**El hecho, medido por dos vías independientes:** OHDSI Brasil (CIDACS) nombra la **«escasez de
vocabularios adecuados para el contexto brasileño»** como su principal dificultad; y el ciclo 7
de esta KB midió que **Brasil, México y Colombia no aparecen como Miembros de SNOMED CT**
(Argentina, Chile y Uruguay sí). Mismo problema, dos fuentes, dos ciclos.

**Por qué es oportunidad y no obstáculo:** la **herramienta es Apache-2.0 y gratis**
([Usagi](https://github.com/OHDSI/Usagi), [WhiteRabbit](https://github.com/OHDSI/WhiteRabbit),
[Perseus](https://github.com/OHDSI/Perseus)); **el contenido mapeado no existe**. Y el contenido
mapeado es, por naturaleza, **específico del país y del sistema de origen** — no lo puede
publicar un vendedor global, y no caduca cuando cambia el modelo de datos.

**Receta:**
1. Determinar **primero** la situación de licencia de contenido del país: ¿Miembro de SNOMED CT?
   ¿usa CID-10 (pt-BR) o ICD-10? ¿tablas propias del sistema público (SUS, SIGSS…)?
   **Esto es una partida de coste del proyecto y va en la propuesta, no en el descubrimiento.**
2. Mapear con Usagi contra los vocabularios que el cliente **sí** puede usar; ICD-10-CM y LOINC
   abaratan el camino (dominio público y gratis con registro, respectivamente).
3. Entregar el mapeo como **repositorio del cliente**: versionado, con revisión en PR y conjunto
   de pruebas. **Lo posee, lo audita y lo mantiene él.**
4. Una regla de CI: si el mapeo emite un concepto de un vocabulario cuya licencia no consta en el
   manifiesto del proyecto, **el build falla** (extensión de P11 al plano de investigación).

**Estructuralmente idéntico a la biblioteca CQL del ciclo 6:** el software es abierto y
reemplazable; **el artefacto de conocimiento específico del cliente es el que tiene margen**. Y
cierra el hueco (c) por el lado útil: el NLP clínico en español y el vocabulario OMOP en español
son el mismo trabajo con dos nombres.

### P20 · Genómica clínica con oráculo y cinco años de plazo

**Para qué:** laboratorios, hospitales con oncología de precisión y biobancos. **El plazo:** el
EHDS aplaza dato genético y de ensayos a **2031-03-26** — **1 582 días**. Es el plano con más
margen del sector y el substrato ya está construido.

**Receta:**
1. **Motor:** [nextflow-io/nextflow](https://github.com/nextflow-io/nextflow) (Apache-2.0,
   3 535★). No escribir orquestación propia.
2. **Pipeline:** [nf-core/sarek](https://github.com/nf-core/sarek) (MIT, razón **1,11**) para
   variantes germinales y somáticas. Debajo: [gatk](https://github.com/broadinstitute/gatk)
   (Apache-2.0), [samtools](https://github.com/samtools/samtools) y
   [htslib](https://github.com/samtools/htslib) (MIT/Expat — ⚠️ excepción acotada en `cram/`).
3. **EL ORÁCULO, Y ES EL CORAZÓN DEL PATRÓN:** [Illumina/hap.py](https://github.com/Illumina/hap.py)
   (BSD+MIT) contra *truth sets* públicos de Genome in a Bottle. Da **precisión y sensibilidad
   numéricas** por clase de variante. **El entregable no es «montamos el pipeline»: es el
   benchmark diferencial frente al proceso actual del cliente, con números.** Misma estructura
   que QuantLib/ORE en el pase financiero.
4. **Interpretación clínica:** [sigven/pcgr](https://github.com/sigven/pcgr) (MIT) genera informe
   accionable en cáncer. **Aquí termina lo automático**: el informe lo firma una persona.
5. **Interoperabilidad y federación:** [ga4gh/vrs](https://github.com/ga4gh/vrs) (Apache-2.0) para
   representar variantes de forma estable y
   [ga4gh-beacon/beacon-v2](https://github.com/ga4gh-beacon/beacon-v2) (CC0-1.0) para
   descubrimiento federado **sin mover el dato** — que es exactamente la forma que el EHDS
   favorece. Construir el borde en Beacon desde el principio es la apuesta de menor riesgo.
6. **Escala poblacional:** [hail-is/hail](https://github.com/hail-is/hail) (MIT) si hay cohortes
   grandes. **Interfaz para no programadores:** [galaxy](https://github.com/galaxyproject/galaxy)
   (MIT, razón 1,59).

**Dónde va el agente:** en la interpretación y el informe —resumir evidencia, redactar borrador,
señalar discrepancias con la guía— **nunca en la llamada de variantes**, que es determinista,
está benchmarkeada y no mejora con un LLM. Confundir las dos capas es el error que el oráculo
sirve para hacer evidente.

---

## Pase 2026-11-25 (c9) — patrones P21 a P24

### P21 · Automatización de sumisión regulatoria con el juez ya escrito

**El hueco:** 176 repos permisivos de substrato (pharmaverse 86 + atorus-research 48 +
cdisc-org 42) y **2 repos** en `ADaM automation LLM`. El juez existe y es MIT; la capa que
produce y corrige el entregable, no.

**Las piezas, todas verificadas por bytes:**

| Rol | Repo | Licencia |
|---|---|---|
| Juez / oráculo | [cdisc-org/cdisc-rules-engine](https://github.com/cdisc-org/cdisc-rules-engine) `v1.0.0` | MIT |
| Clave de respuestas | [cdisc-org/cdisc-open-rules](https://github.com/cdisc-org/cdisc-open-rules) | MIT |
| ODM → SDTM | [pharmaverse/sdtm.oak](https://github.com/pharmaverse/sdtm.oak) | Apache-2.0 |
| SDTM → ADaM | [pharmaverse/admiral](https://github.com/pharmaverse/admiral) | Apache-2.0 |
| Especificación legible por máquina | [atorus-research/metacore](https://github.com/atorus-research/metacore) | MIT (`DESCRIPTION`) |
| Escritura conforme XPT / Dataset-JSON | [atorus-research/xportr](https://github.com/atorus-research/xportr) · [atorus-research/datasetjson](https://github.com/atorus-research/datasetjson) | MIT · Apache-2.0 |
| Tablas de seguridad FDA | [pharmaverse/cardinal](https://github.com/pharmaverse/cardinal) | Apache-2.0 |
| Traza de ejecución | [pharmaverse/logrx](https://github.com/pharmaverse/logrx) | MIT (`DESCRIPTION`) |
| Datos de prueba sin PHI | [pharmaverse/pharmaversesdtm](https://github.com/pharmaverse/pharmaversesdtm) · [pharmaverse/pharmaverseadam](https://github.com/pharmaverse/pharmaverseadam) | Apache-2.0 |

**El cableado, y el orden importa:**

1. `metacore` carga la especificación del estudio como metadatos, no como Word.
2. `sdtm.oak` mapea el extracto ODM del EDC del cliente a SDTM. **No se forkea el EDC** (ver P23).
3. `admiral` deriva ADaM.
4. **El agente entra aquí y sólo aquí:** propone los mapeos y las derivaciones que faltan.
5. `cdisc-rules-engine` ejecuta las reglas de `cdisc-open-rules` sobre la salida. **El agente no
   se autoevalúa: lo evalúa el motor del regulador.** Cada hallazgo vuelve al paso 4 como tarea.
6. `xportr` / `datasetjson` escriben el entregable; `logrx` deja la traza.
7. Criterio de parada: **cero hallazgos del motor**, no «el LLM dice que está bien».

**Por qué este patrón se vende:** el cliente no tiene que creerse al agente. El criterio de
aceptación es un ejecutable MIT que publica el propio custodio del estándar, y corre sobre
`pharmaversesdtm` (datos de prueba sin PHI) antes de tocar un dato real.

### P22 · Cuando no hay fixture, el fixture ES el entregable (farmacovigilancia)

Caso inverso de P21, y la aplicación directa de la ley refinada en este pase. En
farmacovigilancia hay fórmula (PRR/ROR/BCPNN), hay formato (ICH E2B(R3)), hay mandato — y la
oferta permisiva máxima es **1★**:

| Repo | Licencia | ★ | Estado |
|---|---|---|---|
| [PrashantRGore/icsr-multi-agent-pipeline](https://github.com/PrashantRGore/icsr-multi-agent-pipeline) | MIT | 1★ | LangGraph + Ollama, export E2B(R3), humano en el bucle |
| [WeDoCareGlobal-CC/pharma-intelligence-os](https://github.com/WeDoCareGlobal-CC/pharma-intelligence-os) | Apache-2.0 | 0★ | Revisión ICSR, PRR/ROR, borradores PSUR/PBRER |
| [InfOmics/TEDAR](https://github.com/InfOmics/TEDAR) | MIT | 0★ | Método de detección de señal; parado desde 2021 |
| [FreeVigilance/E2B](https://github.com/FreeVigilance/E2B) | GPL-3.0 | 1★ | Copyleft; parado desde 2024 |

**La receta:** no empezar por el agente, empezar por **construir y publicar el corpus de
aceptación** — casos ICSR sintéticos con la clasificación correcta acordada, y las señales
esperadas calculadas sobre un extracto de [`FDA/openfda`](https://github.com/FDA/openfda)
(CC0-1.0: redistribuible sin fricción, a diferencia de VigiBase, que es de acceso restringido).
Con ese fixture publicado, PRR/ROR pasa de fórmula a oráculo y el agente se puede medir. **Sin
él, cualquier agente de farmacovigilancia es una demo**, y por eso el plano entero tiene 1★.
Quien publique el fixture define el plano: es P29 del pase financiero, aplicado a salud.

### P23 · Integrar la captura, construir en la sumisión (la línea de licencia)

**La regla:** la frontera de licencia cae entre capturar y someter.

- **No partir de** [OpenClinica/OpenClinica](https://github.com/OpenClinica/OpenClinica): 519★ y
  317 forks, pero **ningún fichero de licencia en el repo** (los seis candidatos dan 404 con
  `README.md` a 200 → ausencia **medida**) y sin push desde 2025-10-28. El README enlaza a una
  página del *vendor*: eso no es procedencia.
- **No forkear** [senaite/senaite.core](https://github.com/senaite/senaite.core) (GPL-2.0, 412★,
  muy activo) ni [ddRPB/LibreClinica](https://github.com/ddRPB/LibreClinica) (GPL): integrarlos
  por interfaz. Un derivado arrastra copyleft a la entrega.
- **Sí partir de** [LabKey/platform](https://github.com/LabKey/platform) (Apache-2.0, push
  2026-11-25) y [krishagni/openspecimen](https://github.com/krishagni/openspecimen) (BSD-3-Clause).
- **No llamar open source a REDCap** en ningún documento: se licencia a instituciones
  consorciadas, no tiene repositorio público.

**La bisagra que lo hace ejecutable:** `pharmaverse/sdtm.oak` es Apache-2.0 y **agnóstico de EDC**.
El contrato de integración es el extracto ODM, no el código del EDC. Así la entrega vive entera
en el lado permisivo aunque el cliente tenga el EDC que tenga.

### P24 · Puerta de licencia, sexta y séptima categoría (regla de CI reutilizable en las 12 industrias)

Extiende P8/P16/P18 con lo aprendido en este pase. Las dos reglas nuevas son de implementación,
no de criterio:

```bash
#!/usr/bin/env bash
# licence-gate v4 — añade: (6) stub de R, (7) clona antes de declarar ausencia,
# y bloqueo explícito de CC-NC-ND presentada como open source.
slug="$1"
raw="https://raw.githubusercontent.com/$slug/HEAD"

# (7) El repo tiene que existir en canal primario. search/repositories da falsos
#     negativos (9 acumulados en esta KB): krishagni/openspecimen, ddRPB/LibreClinica...
git ls-remote -h "https://github.com/$slug" >/dev/null 2>&1 || { echo "NO EXISTE: $slug"; exit 2; }

lic=""
for f in LICENSE LICENSE.md LICENSE.txt COPYING COPYING.txt; do
  body=$(curl -sf "$raw/$f") || continue
  # (6) Stub de R: "YEAR:" + "COPYRIGHT HOLDER:" y NADA de texto legal.
  #     Diez falsos negativos en un solo pase si se omite esta rama.
  if printf '%s' "$body" | grep -q '^COPYRIGHT HOLDER:'; then
    lic=$(curl -sf "$raw/DESCRIPTION" | sed -n 's/^[Ll]icense: *//p' | head -1)
    echo "R-STUB -> DESCRIPTION dice: ${lic:-NADA}"; break
  fi
  lic="$f"; break
done

# (7b) Ningún LICENSE* respondió: NO concluir "sin licencia". FDA/openfda esconde
#      CC0-1.0 en COPYING.txt y sólo aparece al clonar.
if [ -z "$lic" ]; then
  if curl -sf -o /dev/null "$raw/README.md"; then
    tmp=$(mktemp -d); git clone --quiet --depth 1 "https://github.com/$slug" "$tmp/r" 2>/dev/null
    find "$tmp/r" -maxdepth 2 -iname '*licen*' -o -maxdepth 2 -iname '*copying*' | head
    echo "AUSENCIA MEDIDA tras clonar (README=200)"; rm -rf "$tmp"
  else
    echo "INDETERMINADO: ningún fichero de control respondió 200"; exit 3
  fi
fi

# Bloqueos duros. NC y ND no son 'open source' aunque el README lo diga.
for f in LICENSE LICENSE.md COPYING.txt; do
  b=$(curl -sf "$raw/$f") || continue
  printf '%s' "$b" | grep -qi 'NonCommercial'   && { echo "BLOQUEO: NonCommercial"; exit 1; }
  printf '%s' "$b" | grep -qi 'NoDerivatives'   && { echo "BLOQUEO: NoDerivatives"; exit 1; }
  printf '%s' "$b" | grep -qi 'AFFERO'          && { echo "AVISO: AGPL, copyleft de red"; }
done
```

**La prueba de que esta puerta hace falta:** `dfci/matchminer-ai-inference` pasa cualquier
revisión humana que lea el README (*«MatchMiner-AI is open source»*) y el título del paper
(*«An Open-Source Solution»*), y falla en la línea 1 de su `LICENSE`
(`Attribution-NonCommercial-NoDerivatives 4.0 International`). La puerta la habría parado;
la lectura, no.

---

## Pase 2026-11-25 (c10) — patrones P25 a P28

### P25 · Monitorización remota sobre el algoritmo permisivo, nunca sobre la plataforma copyleft

**El problema que resuelve.** Toda propuesta de monitorización remota tropieza con Nightscout:
funciona, lleva una década en producción y tiene **73.399 forks**. Y es **AGPL-3.0**, cuyo alcance
llega al **uso por red**: ofrecerlo modificado como servicio obliga a publicar la fuente de la
modificación a los usuarios del servicio. Forkear y cerrar no es una opción.

**El cableado.** La frontera de licencia de este plano es arquitectónica, así que se construye en
el lado permisivo y se deja el copyleft detrás de una frontera de proceso:

1. **Ingesta de señal** — [`MIT-LCP/wfdb-python`](https://github.com/MIT-LCP/wfdb-python) (MIT) para
   forma de onda y [`neuropsychology/NeuroKit`](https://github.com/neuropsychology/NeuroKit) (MIT)
   para ECG/PPG/EDA. Normalización al esquema de
   [`openmhealth/schemas`](https://github.com/openmhealth/schemas) (Apache-2.0).
2. **Juicio clínico** — [`openaps/oref0`](https://github.com/openaps/oref0) (MIT) o
   [`LoopKit/LoopKit`](https://github.com/LoopKit/LoopKit) (MIT) **como referencia de algoritmo**:
   es la única capa de decisión clínica que esta KB ha encontrado disponible en licencia permisiva
   en diez pases. Las reglas del cliente van en una **biblioteca versionada que el cliente posee**,
   no en el *prompt* (misma regla que la biblioteca CQL de P10).
3. **Persistencia clínica** — `medplum` (Apache-2.0, ya en esta KB) o
   [`tidepool-org/platform`](https://github.com/tidepool-org/platform) (BSD-2-Clause) si el dominio
   es diabetes: Tidepool ya resuelve ingesta desde bombas y medidores con
   [`uploader`](https://github.com/tidepool-org/uploader) (BSD-2).
4. **Integración multi-dispositivo a cabecera** — [`mdpnp/mdpnp`](https://github.com/mdpnp/mdpnp)
   (BSD-2, OpenICE): la única base permisiva **viva** de interoperabilidad de dispositivo.
   **No** `signove/antidote` (LGPL, sin push desde 2021-05-14).
5. **App de paciente** — [`StanfordSpezi/Spezi`](https://github.com/StanfordSpezi/Spezi) +
   [`SpeziLLM`](https://github.com/StanfordSpezi/SpeziLLM) (MIT ambos, push esta semana).
6. **Nightscout, si se usa, como fuente de interoperabilidad detrás de un límite de proceso** —
   se consume su API, no se incorpora su código al artefacto distribuido.
7. **Persona aprueba toda consecuencia terapéutica.** Es dosificación: el humano firma.

**Lo que nunca hay que hacer:** forkear `nightscout/cgm-remote-monitor` o `AndroidAPS` dentro del
producto, ni partir de [`LoopKit/LoopWorkspace`](https://github.com/LoopKit/LoopWorkspace) — que
con 8.859 forks **no tiene fichero de licencia propio** (verificado por clon; la licencia vive un
nivel más abajo, en cada submódulo). Y cuidado con
[`LoopKit/Loop`](https://github.com/LoopKit/Loop): es **MIT con excepciones explícitas para
frameworks y gráficos**, así que los activos visuales no se redistribuyen sin leer la reserva.

**Qué evidencia produce.** Un manifiesto de licencias del artefacto distribuido que demuestra
**cero componentes AGPL/GPL**, generado por la puerta de P28 en cada build. Es también la respuesta
a la pregunta que un cliente con asesoría jurídica hará en la primera reunión.

### P26 · La puerta de SBOM de la §524B como entregable de cliente (no como plataforma)

**El problema que resuelve.** La FDA exige, en la sumisión de todo *cyber device* (510(k), PMA,
De Novo, PDP, HDE), un **SBOM legible por máquina** que cubra componentes comerciales, **open
source** y *off-the-shelf*; si no se aporta, hay que justificar la omisión. Las herramientas que lo
producen son maduras, permisivas y **no son sanitarias**: ahí está el vínculo que falta.

**El cableado**, cinco piezas Apache-2.0, ninguna que haya que escribir:

1. [`CycloneDX/cdxgen`](https://github.com/CycloneDX/cdxgen) o
   [`anchore/syft`](https://github.com/anchore/syft) generan el SBOM en cada build, por lenguaje y
   por imagen.
2. [`CycloneDX/cyclonedx-cli`](https://github.com/CycloneDX/cyclonedx-cli) normaliza, mezcla los
   SBOM de los subsistemas del dispositivo y **valida** el documento.
3. [`DependencyTrack/dependency-track`](https://github.com/DependencyTrack/dependency-track) los
   recibe y mantiene el **inventario continuo** — que es lo que convierte un SBOM de sumisión en
   vigilancia postmercado, la mitad que casi nadie entrega.
4. [`aquasecurity/trivy`](https://github.com/aquasecurity/trivy) aporta el contraste de
   vulnerabilidad sobre el mismo inventario.
5. **VEX** sobre lo anterior: la explotabilidad real en el contexto del dispositivo es lo que
   evita que una CVE irrelevante bloquee una sumisión.

**El vínculo sanitario, que es el margen:** el mapeo del inventario a los apartados de la sumisión
y a la documentación de ciclo de vida. Nadie lo ha publicado —`medical device SBOM` = **12 repos**,
`medical device cybersecurity` = **58**— y no requiere construir herramienta.

**Advertencia de encuadre, regla P9 aplicada:** la obligación de SBOM es **ley** (§524B). El
borrador de la FDA de enero de 2025 sobre *AI-enabled device software functions* **seguía sin
finalizar** en 2026. Se vende el artefacto obligatorio, **no** un formato de IA que aún no existe.
Y no se afirma que la FDA rechace automáticamente por SBOM ausente: eso lo dicen blogs de
proveedores y no está verificado (ver `intel/market.md`, no citable n.º 1).

### P27 · Cruzar la puerta regulatoria con código abierto: la maniobra Tidepool

**Para qué sirve.** Es el único camino **medido** por el que open source sanitario ha obtenido una
autorización regulatoria, y responde a la pregunta que hunde propuestas: *«¿se puede certificar algo
open source?»*. Sí, y el mecanismo tiene cuatro pasos y un dueño.

| Paso | Lo que ocurrió en el caso de referencia |
|---|---|
| 1. Congelar una versión | La autorización cubre **una versión**, no «el proyecto». El enfoque open source en general no queda avalado |
| 2. Una entidad firma y asume el ciclo de vida | **Tidepool**, sin ánimo de lucro, añadió los controles regulatorios sobre código de la comunidad |
| 3. Esperar el ciclo | Sumisión a finales de **2020** → autorización FDA el **2023-01-23**. ~2 años |
| 4. Distribuir con socio comercial | Sequel Med Tech, como *twiist Loop* |

**Estado observable ahora mismo:** Loop 2.0 **sometido en julio de 2026 y en revisión**; Loop 3.0
en desarrollo, no sometido. El ciclo se está repitiendo y se puede seguir.

**Lo que esto prohíbe prometer:** *«lo liberamos y lo certificamos»* como un solo movimiento. Son
dos movimientos, el segundo dura del orden de dos años y **exige un titular que firme**. En una
propuesta, el entregable honesto es el **expediente y el rol de titular**, no la autorización.

**Complementa a P12, no lo sustituye.** P12 dice *dónde* aparecerá oferta permisiva (donde el
regulador convierte un juicio en artefacto computable). P27 dice *cómo se cruza la puerta*: con un
artefacto congelado y un dueño.

### P28 · Puerta de licencia v6 — tres categorías nuevas y un falso positivo propio corregido

Las versiones anteriores (P8, P16, P24) siguen vigentes. Esto añade lo que este pase midió, y la
primera regla corrige un defecto de la propia puerta que esta KB venía recomendando.

```bash
# licence-gate v6 — añade: (8) "noncommercial" aparece UNA VEZ en el texto GPL/AGPL;
# (9) el artefacto que la gente forkea puede ser un manifiesto de submódulos SIN licencia;
# (10) NOASSERTION puede ser NO COMERCIAL (PolyForm) — la racha "10 de 10" quedó rota.

# (8) FALSO POSITIVO MEDIDO Y CORREGIDO. El texto de GPL-3.0 y AGPL-3.0 contiene la palabra
#     "noncommercial" exactamente UNA vez. Un `grep -i noncommercial` para bloquear CC-NC
#     bloquea TODO repo GPL/AGPL. En este pase: 5 falsos positivos (cgm-remote-monitor,
#     AndroidAPS, xDrip, get-based, codeforjapan x2) frente a 2 positivos genuinos.
#     DISCRIMINANTE: anclar en el TITULO (3 primeras lineas) y exigir >=2 apariciones.
nc_count=$(grep -oic 'noncommercial' "$LIC")
title=$(head -3 "$LIC")
if echo "$title" | grep -qiE 'creative commons.*noncommercial|polyform noncommercial' \
   || { [ "$nc_count" -ge 2 ] && echo "$title" | grep -qi 'noncommercial'; }; then
  echo "BLOQUEO: licencia NO COMERCIAL genuina"; exit 1
fi
# 1 aparicion y sin titulo NC => texto GPL incidental. NO bloquear por ese motivo
# (bloquear por copyleft, si aplica, es otra regla).

# (9) MANIFIESTO DE SUBMODULOS SIN LICENCIA. LoopKit/LoopWorkspace: 8859 forks, CERO ficheros
#     de licencia (confirmado por CLON, nunca por 404 de raw: regla 7 de v4). La licencia vive
#     un nivel mas abajo, en cada submodulo. Si existe .gitmodules y no hay LICENSE en la raiz,
#     NO concluir "sin licencia": resolver submodulo por submodulo.
if [ -f .gitmodules ] && [ -z "$LIC" ]; then
  echo "AVISO: manifiesto de submodulos — auditar cada submodulo, no la raiz"
  grep -E '^\s*url' .gitmodules   # y pasar cada uno por esta misma puerta
fi

# (10) NOASSERTION NO IMPLICA PERMISIVA. Contraejemplo medido: thinkwee/HiMe = NOASSERTION en
#      el metadato, PolyForm Noncommercial 1.0.0 en los bytes (linea 3). De NOASSERTION se
#      sigue "SIN MEDIR", no "permisiva". Abrir siempre el fichero.

# (11) PERMISIVA CON RESERVA DE ACTIVOS. LoopKit/Loop: LICENSE.md de 15.235 B que empieza
#      "released under the MIT license (MIT) — With exceptions for frameworks and graphics".
#      Un gate que pregunte solo "es MIT?" contesta SI y se salta la reserva sobre los
#      graficos, que es justo lo que redistribuye un derivado comercial.
#      REGLA: si el LICENSE pesa >3 KB y declara MIT/BSD, buscar "exception|portions|except".
if [ "$(wc -c <"$LIC")" -gt 3072 ] && grep -qi 'mit license\|bsd' "$LIC"; then
  grep -niE 'exception|portions|except for|noted below' "$LIC" | head
fi
```

**Taxonomía de licencia de esta KB, ahora nueve categorías:** permisiva · copyleft · contenido no
libre · ausencia medible · dominio público · CC-NC-ND presentada como open source · manifiesto de
submódulos sin licencia · permisiva con reserva de activos · `NOASSERTION` no comercial.

### Estado de la predicción falsable del ciclo 6 — **a 37 días de la prueba, sin refutar**

CMS-0057-F exige API de autorización previa el **2027-01-01**: faltan **37 días** desde hoy
(2026-11-25). La predicción del ciclo 6 (P12) sigue **sin refutar**. Se comprueba en el pase de
healthcare más cercano a esa fecha.

### Predicción falsable de este pase (c10)

Dos, ambas con fecha y canal de comprobación:

1. **La autorización de Loop 2.0 (sometido en julio de 2026) no exigirá cerrar el repositorio.**
   Si la FDA autoriza Loop 2.0 y `LoopKit/Loop` sigue público y con licencia MIT, P27 queda
   reforzado. Si se autoriza con el código cerrado, **P27 hay que reescribirlo**. Canal:
   comunicados de Tidepool y `ls-remote` + puerta de licencia sobre `LoopKit/Loop`.
2. **La capa agéntica de este plano seguirá por debajo de 50 estrellas en el próximo pase de
   healthcare.** Hoy el techo real es 44★ (`meddev-agent-skills`). Canal: repetir
   `vital signs agent`, `ECG agent` y `medical device agent` ordenados por estrellas.
