---
industry: healthcare
region: Global
updated: 2026-11-22
---

# 🏭 Verticales de partida — Healthcare

> Plataformas verticales reales y en producción, customizables con una capa agéntica arriba.
> Modelo: partir de algo que ya funciona clínicamente, no construir el EMR de cero.
> Licencia verificada por bytes. Última verificación: 2026-11-21.
>
> Este archivo **estaba vacío** en el remoto (`| — | — | — | — | Por completar |`). Primer contenido real.

## Plataformas recomendadas

| Plataforma | Licencia | URL | Stack | Caso de uso | Región |
|------------|----------|-----|-------|-------------|--------|
| OpenEMR | GPL-3.0 | [openemr/openemr](https://github.com/openemr/openemr) | PHP + MySQL | EMR completo **certificado ONC** con gestión de consulta y facturación; 5614★. El más completo funcionalmente | Global |
| OpenMRS | MPL-2.0 + Healthcare Disclaimer | [openmrs/openmrs-core](https://github.com/openmrs/openmrs-core) | Java + React | Plataforma EMR modular pensada para **construir encima**, no para usar tal cual; base de despliegues nacionales | Global |
| Medplum | Apache-2.0 | [medplum/medplum](https://github.com/medplum/medplum) | TypeScript | Backend FHIR-native con auth, bots y subscripciones; **la licencia más permisiva del grupo** | Global |
| Mirth Connect | MPL-2.0 | [nextgenhealthcare/connect](https://github.com/nextgenhealthcare/connect) | Java | Motor de integración HL7v2/FHIR/X12; el bus de mensajería hospitalario de facto; 1220★ | Global |
| dcm4chee Archive 5 | MPL-1.1 | [dcm4che/dcm4chee-arc-light](https://github.com/dcm4che/dcm4chee-arc-light) | Java + WildFly | Archivo DICOM / PACS de grado producción; 508★ | Global |
| Bahmni | MPL-2.0 | [bahmni/bahmni-core](https://github.com/bahmni/bahmni-core) | Java + OpenMRS + Odoo + dcm4chee | Distribución hospitalaria completa (EMR + ERP + PACS) para entornos de recursos limitados | Global |
| OpenELIS Global 2 | MPL-2.0 | [I-TECH-UW/OpenELIS-Global-2](https://github.com/I-TECH-UW/OpenELIS-Global-2) | Java + React | LIS (sistema de información de laboratorio) usado en programas de salud pública | Global |
| CARE | MIT | [ohcnetwork/care](https://github.com/ohcnetwork/care) | Python/Django | Gestión de capacidad hospitalaria y teleconsulta; **Digital Public Good**, nacido en India; 426★ | APAC |
| OHDSI ATLAS | Apache-2.0 | [OHDSI/Atlas](https://github.com/OHDSI/Atlas) | Java + JS | Analítica observacional y definición de cohortes sobre OMOP | Global |
| openIMIS | AGPL-3.0 | [openimis/openimis-be_py](https://github.com/openimis/openimis-be_py) | Python/Django | Gestión de seguros y claims de salud para sistemas públicos; respaldo de cooperación suiza/alemana | Global |
| open-health-sync | AGPL-3.0 | [soma-intelligence/open-health-sync](https://github.com/soma-intelligence/open-health-sync) | TypeScript | Sincronización de datos de salud entre fuentes; 71★, activo | Global |
| Frappe/Marley Health | GPL-3.0 (declarada en README) | [frappe/health](https://github.com/frappe/health) | Python/Frappe | HIS sobre el framework Frappe/ERPNext. **Ojo: el proyecto fue renombrado a "Marley Health"** y no hay archivo LICENSE en la raíz | Global |

### Lectura de licencias para esta tabla

- **Apache-2.0 / MIT (Medplum, CARE, ATLAS)** — se puede vendorizar y entregar al cliente sin fricción.
- **MPL-2.0 (OpenMRS, Mirth, Bahmni, OpenELIS)** — copyleft *por archivo*. Modificar el núcleo obliga a
  publicar esos archivos; **construir módulos al lado no contamina**. Es el patrón de OpenMRS por diseño.
- **GPL-3.0 / AGPL-3.0 (OpenEMR, openIMIS, open-health-sync, Marley)** — AGPL alcanza el uso en red.
  Para estos, la arquitectura sana es *agente al lado, no fork*: hablar con su API FHIR/REST y dejar
  la plataforma intacta. Así el entregable del cliente no hereda la obligación.
- **MPL-1.1 (dcm4chee)** — declarada en el README, **sin archivo LICENSE** en la raíz. Usable como
  servicio; pedir el fix de una línea upstream antes de vendorizar.

### Correcciones de slug y licencia respecto de ciclos anteriores

| Lo que se registró antes | Medición de este pase |
|--------------------------|------------------------|
| `Bahmni (AGPL-3.0)` | El LICENSE de [bahmni/bahmni-core](https://github.com/bahmni/bahmni-core) son 18072 B de **MPL-2.0** + disclaimer sanitario. Los listicles dicen AGPL; el archivo manda |
| `bahmni/openmrs-module-bahmnicore` | Slug muerto (refs=0). El real es `bahmni/bahmni-core` |
| `OpenELIS` (sin slug) | El slug real es `I-TECH-UW/OpenELIS-Global-2`; `OpenELIS-Global/OpenELIS-Global-2` tiene refs=0 |
| `MirthConnect (MPL-2.0)` | **Correcto**, y ahora byte-verificado: el LICENSE abre con *"Copyright (c) NextGen Healthcare. All rights reserved."* seguido del texto completo de MPL 2.0. El encabezado del vendor no cambia la licencia |
| `LibreHealthIO/lh-ehr` | Existe pero **sin archivo de licencia** y sin sección de licencia en el README; el upstream vivo está en GitLab. Degradado, no recomendado |

## Cómo customizar con AI (concreto, no genérico)

El error de arquitectura más común es forkear el EMR. No hace falta y, con GPL/AGPL, es caro.

1. **Hablar FHIR, no SQL.** OpenEMR, OpenMRS y Medplum exponen FHIR R4. El agente nunca toca la base.
2. **Poner un servidor MCP delante del FHIR.** [wso2/fhir-mcp-server](https://github.com/wso2/fhir-mcp-server)
   (Apache-2.0) o [the-momentum/fhir-mcp-server](https://github.com/the-momentum/fhir-mcp-server) (MIT)
   convierten los recursos FHIR en herramientas tipadas. Esto es lo que evita que el agente invente campos.
3. **De-identificar antes de salir del perímetro.** [openmed](https://github.com/maziyarpanahi/openmed)
   (Apache-2.0) corre local: NER clínico + PII de-ID antes de cualquier llamada a un LLM externo.
4. **Desarrollar contra pacientes sintéticos.** [synthea](https://github.com/synthetichealth/synthea)
   carga historias completas en el servidor FHIR: se construye y demuestra sin un solo dato real.
5. **Aprobación humana en todo paso consecuente.** El patrón de
   [Hospilot](https://github.com/Carer-Healthcare-AI/Hospilot) (MIT) sobre el FHIR de OpenEMR es la
   referencia: orquestación multi-agente con humano aprobando cada acción con efecto clínico.
6. **Dejar la traza desde el día uno.** Es requisito regulatorio en al menos tres regiones
   (ver `intel/market.md`), no una mejora opcional.

---

## Pase 2026-11-22 — el patrón «Odoo» no se traslada a salud

El guion de esta KB pide plataformas al estilo de Odoo para ERP: sistemas reales,
personalizables, con IA encima. **En salud ese patrón falla, y conviene decirlo antes de que
alguien lo prometa en una propuesta.**

Odoo *core* es open source, pero los módulos sanitarios de su marketplace **no lo son**: se
distribuyen bajo «Odoo Proprietary License v1.0» o, en el mejor caso, LGPL-3
(`ts_health`). Revisado el catálogo de módulos de salud de las versiones 10 a 19
(`pragtech_medical`, `oehealth`, `healthcare_management`, `abs_hospital_management_community`,
`healthcare_management_system_knk`, `tvs_hms`): son add-ons de terceros con licencia por
módulo, no una base comunitaria. **Un *engagement* que planee «Odoo + IA» para un hospital
hereda una licencia propietaria por cada módulo clínico.**

La alternativa correcta en salud no es un ERP con módulo médico, sino un sistema clínico
dedicado. Los que sí cumplen el criterio:

| Plataforma | Licencia | Bytes | Qué es | Stars / refs | Región |
|-----------|----------|-------|--------|--------------|--------|
| [medplum/medplum](https://github.com/medplum/medplum) | Apache-2.0 | 9765 | Backend FHIR-native con 1029 forks; **la base permisiva más adoptable para construir encima** | 2812★ / refs=9471 | Global |
| [openemr/openemr](https://github.com/openemr/openemr) | GPL-3.0 | — | EMR certificado ONC, el más instalado; consumir su FHIR, **no forkearlo** | 5618★ | Global |
| [DIGI-UW/OpenELIS-Global-2](https://github.com/DIGI-UW/OpenELIS-Global-2) | MPL-2.0 | 16727 | LIS de laboratorio de referencia; slug canónico nuevo | 294★ / refs=4795 | Global |
| [hmislk/hmis](https://github.com/hmislk/hmis) | GPL-3.0 | 35149 | HMIS hospitalario completo de Sri Lanka; **refs=12900**, actividad diaria | 245★ | APAC |
| [ZainZhao/HIS](https://github.com/ZainZhao/HIS) | Apache-2.0 | 11357 | Sistema de información hospitalaria completo, origen China; sin push desde 2025-02 | 1642★ | APAC |
| [IHTSDO/snowstorm](https://github.com/IHTSDO/snowstorm) | Apache-2.0 | 9939 | Servidor de terminología oficial de SNOMED International | 401★ | Global |
| [b2ihealthcare/snow-owl](https://github.com/b2ihealthcare/snow-owl) | Apache-2.0 | 11357 | Servidor de terminología multi-esquema con autoría | 292★ | Global |

### La regla de personalización, por licencia

| Licencia de la plataforma | Cómo se le pone IA encima |
|---------------------------|---------------------------|
| **Apache-2.0 / MIT** (medplum, snowstorm, snow-owl, ZainZhao/HIS) | Fork o dependencia directa. Sin restricción en el entregable. |
| **MPL-2.0** (OpenELIS, OpenMRS, Bahmni, Mirth) | Copyleft **por fichero**: añadir ficheros nuevos es seguro; modificar los suyos obliga a publicar esos ficheros. Arquitectura: módulos nuevos, no parches. |
| **GPL-3.0 / AGPL-3.0** (OpenEMR, hmis, GNU Health, openIMIS) | **No incorporar al entregable.** Consumir su API FHIR/REST desde un proceso separado. Es el patrón P2 y existe precisamente por esto. |
| **Odoo Proprietary v1.0** (módulos de salud de Odoo) | Fuera del perímetro. No hay forma de cumplir y entregar código abierto. |

> Y la advertencia que atraviesa todo lo anterior: la licencia de la plataforma **no cubre el
> contenido de terminología**. Un despliegue de snowstorm es Apache-2.0; el SNOMED CT que
> sirve necesita Licencia de Afiliado, una por país. Ver la tabla de conjuntos de códigos en
> `repos/foundations.md`.
