---
industry: healthcare
region: Global
updated: 2026-11-22
---

# 🏗️ Repos fundacionales — Healthcare

> Bases sobre las que construir: interoperabilidad, imagen médica, NLP clínico y datos sintéticos.
> Licencia verificada por bytes; existencia por `git ls-remote`. Última verificación: 2026-11-21.
>
> Este archivo **estaba vacío** en el remoto (una sola fila `| — | — | Por completar | — |`
> desde 2026-07-02). Las 20 filas siguientes son su primer contenido real.

## Interoperabilidad / FHIR — la capa que todo agente clínico necesita

| Repo | Licencia | Descripción | Stars | Último push | Región |
|------|----------|-------------|-------|-------------|--------|
| [medplum/medplum](https://github.com/medplum/medplum) | Apache-2.0 | Backend y plataforma FHIR-native completa (auth, subscripciones, bots); el open core más adoptable para construir encima | 2807 | 2026-11-21 | Global |
| [hapifhir/hapi-fhir](https://github.com/hapifhir/hapi-fhir) | Apache-2.0 | Implementación de referencia de FHIR en Java; el servidor FHIR de facto | 2448 | 2026-11-21 | Global |
| [microsoft/fhir-server](https://github.com/microsoft/fhir-server) | MIT | Servidor FHIR en .NET (base del Azure Health Data Services OSS) | 1396 | 2026-11-21 | North America |
| [gematik/api-erp](https://github.com/gematik/api-erp) | Apache-2.0 | **Especificación oficial** de la API de e-receta alemana, publicada por la agencia nacional de salud digital | 116 | 2026-11-20 | EMEA |
| [gematik/api-ePA](https://github.com/gematik/api-ePA) | Apache-2.0 | **Especificación oficial** de la historia clínica electrónica alemana (ePA) | 60 | 2025-11-20 | EMEA |
| [ma3u/MinimumViableHealthDataspacev2](https://github.com/ma3u/MinimumViableHealthDataspacev2) | Apache-2.0 | Implementación de referencia del European Health Data Space con grafo de conocimiento FHIR R4 | 11 | 2026-11-20 | EMEA |
| [Precisa-Saude/fhir-brasil](https://github.com/Precisa-Saude/fhir-brasil) | Apache-2.0 | Toolkit FHIR R4 brasileño (TypeScript): cliente RNDS con mTLS + **sandbox local de desarrollo** | 1 | 2026-11-20 | LATAM |
| [Voa-Health/rnds](https://github.com/Voa-Health/rnds) | Apache-2.0 | RNDS brasileña: identificadores, códigos y validación FHIR como lib Python, CLI **y servidor MCP para agentes** | 0 | 2026-11-18 | LATAM |
| [IgMiras/rnds-br-connect](https://github.com/IgMiras/rnds-br-connect) | Apache-2.0 | Framework Java que construye y valida documentos FHIR para la RNDS con mapeo de terminología enchufable | 1 | 2026-11-13 | LATAM |
| [kyriosdata/rnds](https://github.com/kyriosdata/rnds) | Apache-2.0 | Utilidades de integración RNDS en Java (sin push desde 2024-08; referencia, no base) | 51 | 2024-08-28 | LATAM |

> ⚠️ Los cuatro repos RNDS son **comunitarios, no oficiales**: cada uno declara explícitamente
> no estar afiliado al Ministério da Saúde ni al DATASUS. La RNDS no publica un paquete FHIR
> versionado, así que los perfiles se capturan de Simplifier. La acreditación DATASUS y el
> certificado ICP-Brasil siguen siendo responsabilidad del integrador.
> Esto contrasta con **gematik**, que sí es la agencia oficial alemana publicando bajo Apache-2.0.

## Imagen médica

| Repo | Licencia | Descripción | Stars | Último push | Región |
|------|----------|-------------|-------|-------------|--------|
| [Project-MONAI/MONAI](https://github.com/Project-MONAI/MONAI) | Apache-2.0 | Framework de deep learning para imagen médica (PyTorch); el estándar del dominio | 8858 | 2026-11-18 | Global |
| [TorchIO-project/torchio](https://github.com/TorchIO-project/torchio) | Apache-2.0 | Preprocesado y augmentation de imágenes médicas volumétricas | 2457 | 2026-11-13 | Global |
| [pydicom/pydicom](https://github.com/pydicom/pydicom) | MIT (con excepciones) | Lectura/escritura DICOM en Python puro. El LICENSE (3140 B) dice *"Except for portions outlined below, pydicom is released under an MIT license"*: GitHub lo reporta como NOASSERTION, pero el cuerpo es MIT con porciones de terceros acotadas | 2238 | 2026-11-20 | Global |

## NLP clínico y modelos médicos

| Repo | Licencia | Descripción | Stars | Último push | Región |
|------|----------|-------------|-------|-------------|--------|
| [maziyarpanahi/openmed](https://github.com/maziyarpanahi/openmed) | Apache-2.0 | NER clínico y **de-identificación de PII** local-first — la pieza que habilita trabajar sin enviar PHI a una API | 5833 | 2026-11-20 | Global |
| [sunlabuiuc/PyHealth](https://github.com/sunlabuiuc/PyHealth) | MIT | Toolkit de ML sanitario (UIUC): pipelines sobre MIMIC/eICU/OMOP | 1703 | 2026-11-20 | North America |
| [medspacy/medspacy](https://github.com/medspacy/medspacy) | MIT | NLP clínico sobre spaCy (negación, contexto, secciones) | 688 | 2026-06-04 | North America |
| [aphp/edsnlp](https://github.com/aphp/edsnlp) | BSD-3-Clause | NLP clínico **en francés**, de Assistance Publique – Hôpitaux de Paris | 168 | 2026-11-20 | EMEA |
| [apache/ctakes](https://github.com/apache/ctakes) | Apache-2.0 | Plataforma de NLP clínico de la Apache Software Foundation (UIMA) | 142 | 2026-11-04 | Global |
| [EPFLiGHT/FullyOpenMeditron](https://github.com/EPFLiGHT/FullyOpenMeditron) | Apache-2.0 | Corpus médico de entrenamiento **auditado por clínicos** y protocolo de evaluación abierta (EPFL LiGHT) | 19 | 2026-11-17 | EMEA |

## Datos sintéticos y modelo común — cómo se prueba sin PHI

| Repo | Licencia | Descripción | Stars | Último push | Región |
|------|----------|-------------|-------|-------------|--------|
| [synthetichealth/synthea](https://github.com/synthetichealth/synthea) | Apache-2.0 | Generador de pacientes sintéticos con historia longitudinal completa, exportable a FHIR. **Resuelve el primer bloqueo de todo engagement clínico: no se puede probar sobre datos reales de paciente** | 3472 | 2026-11-20 | Global |
| [OHDSI/Atlas](https://github.com/OHDSI/Atlas) | Apache-2.0 | UI de cohortes y analítica sobre el modelo común OMOP | 340 | 2026-09-16 | Global |

> `OHDSI/CommonDataModel` **no tiene archivo de licencia** (README 200 como control).
> Un ciclo anterior lo registró como `OMOP-CDM (Apache-2.0)`. La especificación OMOP es
> usable, pero el repo no la otorga por escrito: usar `OHDSI/Atlas` (Apache-2.0 verificado)
> como punto de entrada citable.

---
*Ver también: `verticals/solutions.md` para plataformas verticales completas.*

---

## Pase 2026-11-22 — la capa de formato de la facturación sanitaria

> Todas las licencias de abajo verificadas por bytes contra
> `raw.githubusercontent.com/<slug>/HEAD/<fichero>`; existencia por `git ls-remote`.
> Los NOASSERTION de GitHub se resolvieron abriendo el fichero: **8 de 8 resultaron
> permisivas genuinas**, acumulando la racha que abrió el ciclo 5.

Esta capa faltaba por completo en la KB. Es la capa de **formato** del ciclo de ingresos: X12,
HL7 v2 y los servidores de terminología. Es madura, permisiva y mantenida, y es exactamente lo
que **no hay que volver a escribir** en un *engagement*.

### X12 / EDI — el sobre de la reclamación sanitaria

| Nombre | Licencia | Bytes | Descripción | Stars | Push |
|--------|----------|-------|-------------|-------|------|
| [indice-co/EDI.Net](https://github.com/indice-co/EDI.Net) | MIT | 1074 | Serializador/deserializador EDI para .NET (X12, EDIFACT, TRADACOMS) | 491 | 2025-12 |
| [kputnam/stupidedi](https://github.com/kputnam/stupidedi) | BSD-3-Clause | 1483 | Parseo, generación y validación de X12 en Ruby; cláusula de *endorsement* presente | 293 | 2026-09 |
| [azoner/pyx12](https://github.com/azoner/pyx12) | BSD-3-Clause | 1426 | Validador y traductor X12↔XML en Python, orientado a 837/835 HIPAA | 190 | 2026-11 |
| [BerryWorksSoftware/edireader](https://github.com/BerryWorksSoftware/edireader) | GPL-3.0 | 35142 | Parser EDI en Java, muy usado para 837; **copyleft: no incorporar al entregable** | 142 | 2026-10 |
| [olmelabs/EdiEngine](https://github.com/olmelabs/EdiEngine) | MIT | 1065 | Motor EDI X12 en .NET con validación de esquemas | 109 | 2023-11 |
| [imsweb/x12-parser](https://github.com/imsweb/x12-parser) | BSD-3-Clause | 1577 | Parser X12 en Java de Information Management Services | 99 | 2026-06 |

### HL7 v2 — el formato que sigue moviendo los hospitales

| Nombre | Licencia | Bytes | Descripción | Stars | Push |
|--------|----------|-------|-------------|-------|------|
| [crs4/hl7apy](https://github.com/crs4/hl7apy) | MIT | 1054 | Librería HL7 v2 en Python del CRS4; GitHub la marcaba NOASSERTION | 284 | 2026-11 |
| [senaranya/HL7](https://github.com/senaranya/HL7) | MIT | 1082 | Parser HL7 v2 ligero en Python | 202 | 2026-10 |
| [Efferent-Health/HL7-V2](https://github.com/Efferent-Health/HL7-V2) | MIT | 1081 | Parser HL7 v2 en .NET, mantenido | 104 | 2026-11 |

### Terminología — servidores permisivos, contenido que **no** lo es

Léase junto a la advertencia de abajo: el **código** de estos servidores es Apache-2.0; el
**contenido** que sirven tiene su propia licencia y su propio coste.

| Nombre | Licencia | Bytes | Descripción | Stars | Push |
|--------|----------|-------|-------------|-------|------|
| [IHTSDO/snowstorm](https://github.com/IHTSDO/snowstorm) | Apache-2.0 | 9939 | Servidor de terminología SNOMED CT **oficial de SNOMED International**; sirve la edición internacional y ~14 nacionales | 401 | 2026-11 |
| [b2ihealthcare/snow-owl](https://github.com/b2ihealthcare/snow-owl) | Apache-2.0 | 11357 | Servidor de terminología multi-esquema (SNOMED, LOINC, ICD) con autoría; refs=2105 | 292 | 2026-07 |
| [StefanoTrv/simple_icd_10_CM](https://github.com/StefanoTrv/simple_icd_10_CM) | MIT | 1078 | Acceso programático al árbol ICD-10-CM completo | 94 | 2026-02 |
| [bryand1/icd10-cm](https://github.com/bryand1/icd10-cm) | MIT | 1052 | ICD-10-CM como librería consultable; texto MIT clásico sin línea de título | 97 | 2023-09 |

### ⚠️ La licencia del CÓDIGO no es la licencia del CONTENIDO

Este es el hallazgo que explica el hueco del ciclo 5 mejor que el propio ciclo 5. Un formato
abierto puede transportar un **conjunto de códigos propietario**, y la obligación de licencia
viaja con el contenido, no con el repositorio:

| Conjunto de códigos | Estado | Qué implica para el entregable |
|---------------------|--------|-------------------------------|
| **ICD-10-CM** | Dominio público (CMS / NCHS; los CDC publican cada actualización en PDF y XML) | Libre. Es donde deben ir los componentes abiertos. |
| **CPT** | **Copyright de la AMA, con cuotas por usuario.** Un calendario de licencias de 2026 cita ~18,50 USD/usuario para «CPT Standard»; otra fuente más antigua da 14 USD. Cifras en conflicto: citar la dirección, no el punto | Incorporar o redistribuir el conjunto CPT en un producto **exige licencia de la AMA**. Teclear un código CPT en una reclamación para facturar no la exige. |
| **SNOMED CT** | Licencia de Afiliado **obligatoria incluso donde es gratis**. Gratis en los 54 países Miembros (y en países de renta baja y proyectos de investigación cualificados); **con cuotas fuera**, calculadas por banda de renta del Banco Mundial. **Una licencia por país** | Un despliegue multi-país necesita una licencia por territorio. Afecta al coste de un *rollout* regional, no solo al legal. |
| **LOINC** | Gratis con registro de licencia | Sin fricción práctica. |

**La consecuencia comercial:** no puede existir una plataforma open source permisiva de ciclo
de ingresos de extremo a extremo en EE. UU., porque **su salida se expresa obligatoriamente en
CPT**, que es propietario. El hueco que el ciclo 5 llamó «la mayor oportunidad de
construir-frente-a-comprar» no es un descuido del mercado: es una **imposibilidad de
licenciamiento** en la capa del conjunto de códigos. No se puede comprar abierto y tampoco se
puede construir abierto sin pasar por la AMA.

Eso no cierra el negocio: lo **reubica**. El cliente licencia el conjunto de códigos (ya lo
hace para facturar) y Globant construye la capa de juicio encima. Lo que no se debe prometer
es un entregable «todo open source» que toque CPT.

> Nota de litigio: en 2026 hay una disputa viva sobre si el CPT debería estar en dominio
> público. **No está resuelta.** No construir un caso de negocio sobre que se resuelva.

### FHIR en volumen y clientes — piezas que faltaban

| Nombre | Licencia | Bytes | Descripción | Stars/Forks | Push |
|--------|----------|-------|-------------|-------------|------|
| [cds-hooks/docs](https://github.com/cds-hooks/docs) | Apache-2.0 | 11357 | Especificación CDS Hooks: el punto de enganche de un agente en el flujo clínico | 180★/67f | 2026-11 |
| [Vermonster/fhir-kit-client](https://github.com/Vermonster/fhir-kit-client) | MIT | 1071 | Cliente FHIR en JS/TS, maduro y mantenido | 188★/42f | 2026-10 |
| [google/bulk_fhir_tools](https://github.com/google/bulk_fhir_tools) | Apache-2.0 | 11358 | Herramientas de Bulk FHIR Export de Google | 68★/10f | 2024-12 |
| [microsoft/fhir-loader](https://github.com/microsoft/fhir-loader) | MIT | 1141 | Carga masiva de recursos FHIR; 43 forks sobre 56 estrellas | 56★/43f | 2025-09 |
| [smart-on-fhir/sample-bulk-fhir-datasets](https://github.com/smart-on-fhir/sample-bulk-fhir-datasets) | Apache-2.0 | 11357 | Datasets Bulk FHIR de muestra de SMART, sin PHI | 48★/5f | 2026-10 |
