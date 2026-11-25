---
industry: healthcare
region: Global
updated: 2026-11-25
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

---

## Pase 2026-11-25 — imagen médica y salud pública: los dos planos que faltaban

Dos capas enteras que la KB no tenía y que son, medidas, **las más grandes del open source
sanitario**. Todas las cifras medidas el 2026-11-25; toda licencia confirmada abriendo el fichero.

### Imagen médica — capa de modelo y de visor: permisiva y enorme

| Repo | Licencia | Bytes lic. | Descripción | ★/forks | Último push |
|---|---|---|---|---|---|
| [MIC-DKFZ/nnUNet](https://github.com/MIC-DKFZ/nnUNet) | Apache-2.0 | 11428 | Segmentación médica auto-configurable; la referencia contra la que se comparan los demás | 9069★/2521f | 2026-11-25 |
| [Project-MONAI/MONAI](https://github.com/Project-MONAI/MONAI) | Apache-2.0 | 11357 | Framework de *deep learning* para imagen médica; estándar de facto del sector | 8865★/1735f | 2026-11-25 |
| [OHIF/Viewers](https://github.com/OHIF/Viewers) | MIT | 1087 | Visor DICOM web *zero-footprint* de la Open Health Imaging Foundation; habla DICOMweb con cualquier archivo | 4424★/**4395f** | 2026-11-24 |
| [wasserth/TotalSegmentator](https://github.com/wasserth/TotalSegmentator) | Apache-2.0 | 11357 | Segmentación de ~120 estructuras anatómicas en TC/RM, lista para usar | 3183★/507f | 2026-11-25 |
| [pydicom/pydicom](https://github.com/pydicom/pydicom) | MIT con porciones (3140 B) | 3140 | Lectura/escritura DICOM en Python. El metadato decía `NOASSERTION`; el fichero dice MIT salvo porciones acotadas | 2241★/570f | 2026-11-24 |
| [InsightSoftwareConsortium/ITK](https://github.com/InsightSoftwareConsortium/ITK) | Apache-2.0 | 11357 | Toolkit de segmentación y registro, base de media industria de imagen | 1677★/763f | 2026-11-25 |
| [Project-MONAI/research-contributions](https://github.com/Project-MONAI/research-contributions) | Apache-2.0 | 11357 | Implementaciones de referencia (Swin UNETR y otras) sobre MONAI | 1227★/389f | 2026-11-01 |
| [cornerstonejs/cornerstone3D](https://github.com/cornerstonejs/cornerstone3D) | MIT | 1083 | Librería de renderizado sobre la que está construido OHIF | 1174★/542f | 2026-11-25 |
| [Project-MONAI/MONAILabel](https://github.com/Project-MONAI/MONAILabel) | Apache-2.0 | 11357 | Etiquetado asistido por IA con *plugin* para OHIF y 3D Slicer | 918★/281f | 2026-11-25 |
| [Project-MONAI/model-zoo](https://github.com/Project-MONAI/model-zoo) | Apache-2.0 | 11357 | Modelos preentrenados empaquetados en formato MONAI *bundle* | 350★/111f | 2026-11-23 |
| [InsightSoftwareConsortium/ITKElastix](https://github.com/InsightSoftwareConsortium/ITKElastix) | Apache-2.0 | 11357 | Registro de imagen (elastix) empaquetado para Python | 293★/30f | 2026-11-20 |
| [QIICR/dcmqi](https://github.com/QIICR/dcmqi) | BSD-3-Clause | 1500 | Convierte resultados de segmentación a objetos DICOM válidos: **la pieza que hace interoperable la salida de un modelo** | 282★/69f | 2026-11-16 |
| [Project-MONAI/monai-deploy-app-sdk](https://github.com/Project-MONAI/monai-deploy-app-sdk) | Apache-2.0 | 11357 | Empaqueta un modelo MONAI como aplicación de inferencia desplegable | 146★/72f | 2026-10-28 |

### ⚠️ Imagen médica — capa de archivo y servidor: **copyleft o sin licencia**

Esta tabla es la razón por la que el plano de imagen necesita una decisión de arquitectura y no
sólo una de modelo. Es el hallazgo central del pase; ver P13 en `compose/patterns.md`.

| Repo | Licencia **confirmada abriendo el fichero** | Qué implica en un entregable de cliente |
|---|---|---|
| [jodogne/OrthancMirror](https://github.com/jodogne/OrthancMirror) | **GPL-3.0** (`COPYING`, 35148 B) | Orthanc es el PACS ligero de referencia, pero es **copyleft fuerte**. Espejo en GitHub del proyecto de UCLouvain (`orthanc-server/orthanc` **no existe**, refs=0). Utilizable **sólo como proceso separado tras DICOMweb**, nunca enlazado ni incorporado |
| [dcm4che/dcm4che](https://github.com/dcm4che/dcm4che) | **Mozilla Public License** (`LICENSE.txt`, 25755 B) | Toolkit DICOM de grado industrial, el de los despliegues grandes. Copyleft débil **por fichero**: compatible con producto comercial si no se modifican sus ficheros. 1468★/720f, push 2026-11-19 |
| [Slicer/Slicer](https://github.com/Slicer/Slicer) | **Licencia propia estilo BSD** (`License.txt`, 10514 B) | «3D Slicer Contribution and Software License Agreement v1.0» del Brigham and Women's Hospital. Es **permisiva en espíritu pero no es una licencia OSI estándar**: requiere lectura legal antes de incorporarla. 2745★/813f |
| [fo-dicom/fo-dicom](https://github.com/fo-dicom/fo-dicom) | ⚠️ **ningún fichero de licencia encontrado** (9 variantes de nombre probadas; metadato `NOASSERTION`) | Librería DICOM de .NET muy usada (1220★/671f). Sin fichero de licencia localizable **no entra en un entregable**; si se necesita .NET, resolver la licencia con el proyecto antes de comprometerla |

### Salud pública y despliegue nacional — el bloque de menos estrellas y más instalaciones

| Repo | Licencia | Bytes lic. | Descripción | ★/forks | Último push |
|---|---|---|---|---|---|
| [dhis2/dhis2-core](https://github.com/dhis2/dhis2-core) | BSD-3-Clause | 1517 | Sistema de información sanitaria de referencia mundial; ministerios de salud de **más de 80 países**. Copyright Universidad de Oslo 2004-2025 | 361★/**411f** | 2026-11-25 |
| [dimagi/commcare-hq](https://github.com/dimagi/commcare-hq) | BSD-3-Clause | 1532 | Plataforma de agentes comunitarios de salud desplegada en países de renta baja y media | 527★/240f | 2026-11-25 |
| [dhis2/dhis2-android-capture-app](https://github.com/dhis2/dhis2-android-capture-app) | BSD-3-Clause | 1517 | Captura de datos DHIS2 en Android, con funcionamiento sin conexión | 66★/**142f** | 2026-11-25 |

### La razón estrellas/forks separa **sistemas desplegados** de **librerías** — refinamiento del ciclo 6

El ciclo 6 estableció que una razón ★/forks cercana a 1 indica gente que despliega y por encima
de ~50 atención sin uso. Este pase, con 30 repos medidos de golpe, muestra que la métrica dice
algo más preciso, y es útil para leer cualquier industria:

| Razón ★/forks | Qué es, medido | Ejemplos de este pase |
|---|---|---|
| **< 1** (más forks que estrellas) | **Sistema que instituciones operan.** Cada fork es un despliegue con parches locales. Pocas estrellas porque su público no son desarrolladores que navegan GitHub | openmrs-core 0,44 · OpenELIS-Global-2 0,43 · Bahmni 0,48 · canvas-hyperscribe 0,43 · dhis2-android 0,46 · dhis2-core 0,88 |
| **≈ 1** | Infraestructura que se despliega y además se mira | **OHIF/Viewers 1,006** (4424★/4395f) · HL7-DaVinci/test-ehr 0,7 |
| **3 – 6** | **Librería o modelo de adopción legítima.** Mucha gente la usa como dependencia, poca la bifurca | nnU-Net 3,6 · MONAI 5,1 · TotalSegmentator 6,3 · synthea 3,6 |
| **> 50** | Atención sin uso | `fabric-mlv-...-starter` **149** (149★/1f) |

La lectura operativa: **una razón baja no es señal de proyecto pequeño, es señal de proyecto
operado.** DHIS2 tiene 361 estrellas y lo usan los ministerios de salud de 80 países. Si se
descarta por número de estrellas, se descarta el sistema sanitario de medio mundo.

### Verificación de lo que ya estaba — la ley del ciclo 5 se confirma por quinta vez

«Medir sale barato, heredar sale caro.» Re-medido hoy contra lo que el ciclo 6 anotó el 22-nov:

| Repo | Ciclo 6 (2026-11-22) | Hoy (2026-11-25) | Veredicto |
|---|---|---|---|
| [cqframework/clinical-reasoning](https://github.com/cqframework/clinical-reasoning) | 52★/46f | 52★/46f | **exacto** |
| [HL7-DaVinci/prior-auth](https://github.com/HL7-DaVinci/prior-auth) | 38★/24f | 38★/24f | **exacto** |
| [IHTSDO/snowstorm](https://github.com/IHTSDO/snowstorm) | 401★ | 401★ | **exacto** |
| [synthetichealth/synthea](https://github.com/synthetichealth/synthea) | 3477★ | 3487★ | +10 en 3 días, coherente |
| [medplum/medplum](https://github.com/medplum/medplum) | 2812★ | 2818★ | +6, coherente |
| [maziyarpanahi/openmed](https://github.com/maziyarpanahi/openmed) | 5833★ | 5845★ | +12, coherente |
| [genomoncology/biomcp](https://github.com/genomoncology/biomcp) | 683★ | 685★ | +2, coherente |
| [FreedomIntelligence/OpenClaw-Medical-Skills](https://github.com/FreedomIntelligence/OpenClaw-Medical-Skills) | 3120★, sin licencia, sin push desde 2026-07-21 | 3128★, **sigue sin licencia**, sigue sin push | reconfirmado: el repo médico con más estrellas de los inutilizables |

Añadidos de contexto medidos hoy: [hapifhir/hapi-fhir](https://github.com/hapifhir/hapi-fhir)
2454★/1515f (Apache-2.0) y [openmrs/openmrs-core](https://github.com/openmrs/openmrs-core)
2002★/**4501f** — la razón 0,44 más extrema de la KB.

### Capa de NLP clínico en español — el hueco (c) **se refina, no se cierra**

El ciclo 6 lo dejó abierto «sin hallazgos nuevos». Hay activos, y medirlos explica por qué el
hueco sigue siendo un hueco:

| Repo / recurso | Licencia | ★/forks | Último push | Estado real |
|---|---|---|---|---|
| [PlanTL-GOB-ES/lm-biomedical-clinical-es](https://github.com/PlanTL-GOB-ES/lm-biomedical-clinical-es) | Apache-2.0 | 28★/2f | **2022-11-16** | Modelos biomédico-clínicos en español del Gobierno de España, corpus >1 000 M de tokens. **Permisivo pero abandonado hace cuatro años**; los pesos siguen vivos en Hugging Face |
| [lcampillos/medspaner](https://github.com/lcampillos/medspaner) | ⚠️ **GPL-3.0** | 8★/1f | 2025-03-03 | NER médico en español con corpus anotado. **Copyleft y diminuto** |

Es decir: lo permisivo está muerto y lo vivo es copyleft y de un solo autor. Para un grupo
hospitalario hispanohablante **sigue siendo trabajo a medida con pocos competidores**, y ahora
se puede decir exactamente por qué. Recursos adicionales localizados pero no verificados aquí
por no ser repos: ClinText-SP y RigoBERTa Clinical (arXiv 2503.18594), y los corpus SPACCC,
MEDDOCAN, CodiEsp y E3C.

### Tooling de ABDM (India) — el hueco (f) era en parte **un artefacto del canal de búsqueda**

El ciclo 6 concluyó que India «tiene pila nacional de salud digital y prácticamente ninguna
herramienta permisiva que la hable», a partir de una consulta que devolvió 1 resultado. Medido
por organización en lugar de por palabras clave, la National Health Authority **sí publica**:

| Repo | Licencia | ★/forks | Último push | Nota |
|---|---|---|---|---|
| [NHA-ABDM/ABDM-wrapper](https://github.com/NHA-ABDM/ABDM-wrapper) | **Apache-2.0** (11357 B) | invisible a `search` | existencia por `ls-remote`: **refs=37** | Envoltorio oficial de las APIs de ABDM. **`org:NHA-ABDM` devuelve 7 repos y este no está entre ellos**: séptimo falso negativo de `search` registrado en la KB |
| [NHA-ABDM/UHI](https://github.com/NHA-ABDM/UHI) | CC0-1.0 | 164★/43f | 2024-09-05 | Unified Health Interface. Dominio público pero **parado desde 2024** |
| [NHA-ABDM/ABDM-ABHA-APP](https://github.com/NHA-ABDM/ABDM-ABHA-APP) | MIT | 8★/8f | 2023-11-03 | App de identidad sanitaria ABHA |
| [NHA-ABDM/ABDM-MOCK-HIP](https://github.com/NHA-ABDM/ABDM-MOCK-HIP) | MIT | 3★/2f | 2023-11-03 | HIP simulado: útil como *fixture* de desarrollo |
| [NHA-ABDM/nhcx](https://github.com/NHA-ABDM/nhcx) | ⚠️ sin licencia | 5★/0f | 2024-09-27 | National Health Claims Exchange |

Conclusión corregida y más útil que la del ciclo 6: **India publica tooling oficial permisivo
—incluido un envoltorio Apache-2.0— pero está mayormente parado desde 2024 y una parte no tiene
licencia.** No es ausencia de material, es material oficial sin mantener. Eso cambia la
propuesta: no hay que construir desde cero, hay que **adoptar y mantener** lo que la NHA ya
publicó, que es un encargo más pequeño y más defendible. Y el contraste con el hueco (b) del
NHS se afina: el NHS publica **sin licencia**; India publica **con licencia y sin mantenimiento**.

---

## Pase 2026-11-25 (c8) — uso secundario del dato: el stack OMOP/OHDSI y el substrato genómico

Plano nuevo en la KB. Dos bloques: el **modelo común de datos observacionales** (OMOP) con su
ecosistema de análisis, y el **substrato genómico**, que el EHDS aplaza a 2031 y por tanto es el
de plazo más largo del sector. Todas las cifras **medidas 2026-11-25**; toda licencia **abierta**.

### Stack OMOP/OHDSI — `org:OHDSI` = **398 repos**

| Repo | Papel en el stack | Licencia (canal) | ★/forks | Último push |
|---|---|---|---|---|
| [OHDSI/CommonDataModel](https://github.com/OHDSI/CommonDataModel) | La especificación del modelo: DDL por dialecto de base de datos | Apache-2.0 (`DESCRIPTION`) | 1 103★/518f | 2026-10-28 |
| [OHDSI/Broadsea](https://github.com/OHDSI/Broadsea) | **Por aquí se empieza**: todo el stack en Docker Compose | Apache-2.0 (11358 B) | 94★/81f | 2026-11-10 |
| [OHDSI/Atlas](https://github.com/OHDSI/Atlas) | Interfaz de cohortes, caracterización y estudios | Apache-2.0 (11358 B) | 340★/155f | 2026-09-16 |
| [OHDSI/WebAPI](https://github.com/OHDSI/WebAPI) | Backend REST de Atlas. **Razón 0,83: más forks que estrellas** | Apache-2.0 (11325 B) | 154★/185f | 2026-11-23 |
| [OHDSI/WhiteRabbit](https://github.com/OHDSI/WhiteRabbit) | Escaneo del origen + **Rabbit-in-a-Hat** (módulo interno) para diseñar el ETL | Apache-2.0 (11346 B) | 230★/103f | 2026-10-13 |
| [OHDSI/Usagi](https://github.com/OHDSI/Usagi) | Mapeo de códigos locales a conceptos estándar. **La herramienta del cuello de botella LATAM** | Apache sólo en README ⚠️ | 122★/35f | 2026-05-26 |
| [OHDSI/Vocabulary-v5.0](https://github.com/OHDSI/Vocabulary-v5.0) | Código que **construye** el vocabulario | **Unlicense** (1210 B, dominio público) ⚠️ ver nota | 276★/76f | 2026-11-23 |
| [OHDSI/Athena](https://github.com/OHDSI/Athena) | Descarga de vocabularios | ⚠️ **sin licencia localizable** | 80★/25f | 2026-09-02 |
| [OHDSI/DataQualityDashboard](https://github.com/OHDSI/DataQualityDashboard) | **El entregable que se factura**: batería sistemática de comprobaciones de calidad sobre el CDM, con informe | Apache-2.0 (`DESCRIPTION`) | 195★/124f | 2026-11-23 |
| [OHDSI/Achilles](https://github.com/OHDSI/Achilles) | Caracterización y perfilado de la base convertida | Apache-2.0 (`DESCRIPTION`) | 156★/138f | 2026-10-09 |
| [OHDSI/ETL-Synthea](https://github.com/OHDSI/ETL-Synthea) | Synthea → OMOP. **La pierna firme para construir sin datos reales** | Apache-2.0 (`DESCRIPTION`) | 131★/80f | 2026-03-23 |
| [OHDSI/PatientLevelPrediction](https://github.com/OHDSI/PatientLevelPrediction) | Modelos predictivos con protocolo estandarizado | Apache-2.0 (`DESCRIPTION`) | 227★/97f | 2026-11-24 |
| [OHDSI/CohortMethod](https://github.com/OHDSI/CohortMethod) | Estimación de efectos comparativos | Apache-2.0 (`DESCRIPTION`) | 94★/69f | 2026-11-25 |
| [OHDSI/Strategus](https://github.com/OHDSI/Strategus) | Ejecución de estudios en red. **Razón 0,81** | Apache-2.0 (`DESCRIPTION`) | 13★/16f | 2026-11-24 |
| [OHDSI/Hades](https://github.com/OHDSI/Hades) | Índice del conjunto de paquetes R del ecosistema | Apache-2.0 | 32★/19f | 2026-10-05 |
| [OHDSI/SqlRender](https://github.com/OHDSI/SqlRender) | Traduce un SQL a 10+ dialectos. **Razón 0,99** | Apache-2.0 | 90★/91f | 2026-10-19 |
| [OHDSI/DatabaseConnector](https://github.com/OHDSI/DatabaseConnector) | Conexión homogénea. **Razón 0,60, la más baja del pase** | Apache-2.0 (`DESCRIPTION`) | 58★/96f | 2026-10-19 |
| [OHDSI/Capr](https://github.com/OHDSI/Capr) | Definición de cohortes **como código** (versionable, revisable en PR) | Apache-2.0 | 24★/20f | 2026-09-23 |
| [OHDSI/OncologyWG](https://github.com/OHDSI/OncologyWG) | Extensión oncológica del CDM | Apache-2.0 | 68★/24f | 2026-10-30 |
| [OHDSI/MIMIC](https://github.com/OHDSI/MIMIC) | ETL de MIMIC a OMOP: dataset de UCI de referencia | Apache-2.0 | 101★/42f | 2026-08-21 |
| [OHDSI/Criteria2Query](https://github.com/OHDSI/Criteria2Query) | Lenguaje natural → cohorte. **Precursor agéntico oficial** | Apache-2.0 (11357 B) | 81★/22f | 2026-03-01 |
| [OHDSI/Perseus](https://github.com/OHDSI/Perseus) | ETL a OMOP por interfaz web | Apache-2.0 | 44★/12f | 2023-11-10 ⚠️ parado |

> ⚠️ **`Vocabulary-v5.0` es Unlicense, y eso es sobre el CÓDIGO, no sobre el CONTENIDO.** El
> vocabulario cargado incorpora SNOMED CT, CPT y otros conjuntos **con sus propias
> obligaciones**. Que los scripts de construcción sean dominio público **no dice nada** sobre
> redistribuir el vocabulario resultante. Es la misma trampa que el ciclo 6 documentó con CPT,
> ahora en el plano de investigación. Ver `compose/patterns.md` P11 y P19.

### Substrato genómico — plazo EHDS: **2031-03-26**

| Repo | Papel | Licencia (fichero abierto) | ★/forks | Último push |
|---|---|---|---|---|
| [nextflow-io/nextflow](https://github.com/nextflow-io/nextflow) | Motor de workflows de facto en bioinformática | Apache-2.0 | 3 535★/825f | 2026-11-25 |
| [nf-core/sarek](https://github.com/nf-core/sarek) | Pipeline de variantes germinales y somáticas listo para producción. **Razón 1,11** | MIT | 623★/564f | 2026-11-23 |
| [broadinstitute/gatk](https://github.com/broadinstitute/gatk) | El estándar de llamada de variantes | Apache-2.0 (`LICENSE.TXT`, 10966 B) | 2 013★/632f | 2026-11-25 |
| [samtools/samtools](https://github.com/samtools/samtools) | Manipulación de alineamientos SAM/BAM/CRAM | **MIT/Expat** (1706 B) | 1 983★/629f | 2026-11-12 |
| [samtools/htslib](https://github.com/samtools/htslib) | La librería C que sostiene todo lo anterior | MIT/Expat, excepción acotada en `cram/` (3540 B) | 961★/490f | 2026-11-25 |
| [galaxyproject/galaxy](https://github.com/galaxyproject/galaxy) | Plataforma de análisis con interfaz para no programadores. **Razón 1,59** | **MIT** (1590 B) | 1 902★/1 196f | 2026-11-25 |
| [hail-is/hail](https://github.com/hail-is/hail) | Genómica a escala poblacional sobre Spark | MIT | 1 082★/268f | 2026-11-24 |
| [scverse/scanpy](https://github.com/scverse/scanpy) | Análisis de célula única | BSD-3-Clause | 2 622★/810f | 2026-11-24 |
| [sigven/pcgr](https://github.com/sigven/pcgr) | **Interpretación clínica** de variantes en cáncer con informe | MIT | 285★/51f | 2026-11-10 |
| [Illumina/hap.py](https://github.com/Illumina/hap.py) | Benchmarking de variantes: **el oráculo** del plano | BSD + MIT (3507 B) | 474★/136f | 2023-12-07 |
| [ga4gh/vrs](https://github.com/ga4gh/vrs) | Especificación GA4GH de representación de variantes | Apache-2.0 | 101★/43f | 2026-11-24 |
| [ga4gh-beacon/beacon-v2](https://github.com/ga4gh-beacon/beacon-v2) | Protocolo de descubrimiento federado de datos genómicos | CC0-1.0 | 36★/21f | 2026-11-25 |

**Por qué importa el oráculo:** `hap.py` con los *truth sets* de GA (Genome in a Bottle) permite
dar precisión/sensibilidad **numéricas** de un pipeline. Es, estructuralmente, lo mismo que el
ciclo financiero encontró con QuantLib/ORE en valoración: **cuando existe oráculo, el entregable
defendible es el benchmark diferencial**, no la demo. Ver `compose/patterns.md` P20.

### Nota de método: el canal de licencia depende del lenguaje

Diez repos de la primera tabla aparecen como **`NONE`** en el metadato de GitHub y **los diez son
Apache-2.0** declarada en el `DESCRIPTION` de R. Una puerta que sólo lea `LICENSE` descarta el
stack HADES completo. Orden correcto: `LICENSE*` → `DESCRIPTION` → `pyproject.toml`/`setup.py` →
`pom.xml` → `package.json` → `README`. Patrón **P18**. Y en sentido inverso, `NOASSERTION` siguió
resolviendo a permisiva genuina: **10 de 10** en la historia de la KB.

---

## Pase 2026-11-25 (c9) — investigación clínica: el substrato de sumisión (permisivo) y el de captura (copyleft)

Plano nuevo. La frontera de licencia de este plano **no cae por tecnología, cae por función**:
lo que se **somete** al regulador es permisivo; lo que **captura** el dato es copyleft o no tiene
licencia medible. Esa línea decide la arquitectura, y se puede dibujar con los bytes.

### Substrato de sumisión regulatoria — permisivo, maduro y activo

| Repo | Licencia (canal abierto) | ★/forks | Último push | Función |
|---|---|---|---|---|
| [pharmaverse/admiral](https://github.com/pharmaverse/admiral) | Apache-2.0 (`LICENSE.md`) | 328★ | 2026-11-24 | ADaM in R Asset Library. **La pieza más estrellada del plano** |
| [pharmaverse/teal](https://github.com/pharmaverse/teal) | Apache-2.0 (`LICENSE`) | 268★ | **2026-11-25** | Apps web exploratorias sobre datos de ensayo. GitHub: `NOASSERTION` |
| [pharmaverse/rtables](https://github.com/pharmaverse/rtables) | **MIT** (`LICENSE`) | 262★ | 2026-10-01 | Tablas de reporte. GitHub: `NOASSERTION` |
| [pharmaverse/tern](https://github.com/pharmaverse/tern) | Apache-2.0 | 108★ | 2026-11-22 | Librería TLG (tablas, listados, gráficos) de ensayo clínico |
| [pharmaverse/sdtm.oak](https://github.com/pharmaverse/sdtm.oak) | Apache-2.0 (`LICENSE.md`) | 79★ | 2025-06-24 | Motor de transformación ODM→SDTM agnóstico de EDC |
| [pharmaverse/cards](https://github.com/pharmaverse/cards) | Apache-2.0 (`LICENSE.md`) | 61★ | **2026-11-25** | CDISC Analysis Results Data |
| [pharmaverse/cardinal](https://github.com/pharmaverse/cardinal) | Apache-2.0 (`LICENSE.md`) | 61★ | 2026-11-22 | **Tablas y figuras de seguridad de la FDA** |
| [cdisc-org/analysis-results-standard](https://github.com/cdisc-org/analysis-results-standard) | MIT (`LICENSE`) | 74★ | 2026-11-04 | Analysis Results Standard (ARS) |
| [cdisc-org/DDF-RA](https://github.com/cdisc-org/DDF-RA) | MIT (`LICENSE`) | 58★ | 2026-11-20 | Digital Data Flow Reference Architecture: **el protocolo como dato estructurado** |
| [cdisc-org/DataExchange-DatasetJson](https://github.com/cdisc-org/DataExchange-DatasetJson) | MIT (`LICENSE`) | 40★ | 2026-03-11 | Dataset-JSON: el sustituto de SAS XPT |
| [cdisc-org/COSMoS](https://github.com/cdisc-org/COSMoS) | MIT (`LICENSE`) | 35★ | 2026-11-11 | Metadatos conceptuales y operacionales de los estándares |
| [cdisc-org/usdm](https://github.com/cdisc-org/usdm) | MIT (`LICENSE`) | 26★ | 2026-07-06 | Unified Study Definitions Model |
| [atorus-research/xportr](https://github.com/atorus-research/xportr) | **MIT** (`DESCRIPTION`) | 56★ | 2026-11-02 | Escritura de XPT conforme a sumisión. GitHub: `NOASSERTION` |
| [atorus-research/metacore](https://github.com/atorus-research/metacore) | **MIT** (`DESCRIPTION`) | 53★ | 2026-08-19 | Metadatos de especificación legibles por máquina |
| [atorus-research/datasetjson](https://github.com/atorus-research/datasetjson) | Apache-2.0 (`LICENSE.md`) | 27★ | 2026-10-22 | Lectura/escritura de Dataset-JSON en R |
| [cdisc-org/cosa](https://github.com/cdisc-org/cosa) | MIT (`LICENSE`) | 19★ | 2026-11-05 | **Directorio de la CDISC Open Source Alliance**: el índice del propio plano |
| [cdisc-org/conformance-rules-editor](https://github.com/cdisc-org/conformance-rules-editor) | MIT (`LICENSE`) | 14★ | 2026-05-11 | Editor de las reglas que ejecuta CORE |

Diecisiete filas, todas con licencia abierta por bytes. **Cinco con push en los últimos seis días.**

### ⚠️ La tercera trampa de licencia del sector, y la peor para automatizar: el stub de R

`R` es **el lenguaje del ensayo clínico**, y su convención de empaquetado rompe cualquier puerta
de licencia que mire el fichero `LICENSE`. En un paquete R con `License: MIT + file LICENSE`, el
fichero `LICENSE` **no contiene texto de licencia**: contiene dos líneas.

```
YEAR: 2021
COPYRIGHT HOLDER: GSK/Atorus JPT
```

Eso es todo el fichero `LICENSE` de `pharmaverse/logrx`. Un gate que haga
`grep -q "MIT License" LICENSE` **devuelve falso en todo paquete R del plano** y lo clasifica
como «sin licencia». El campo autoritativo es `DESCRIPTION:` → `License:`.

Y es exactamente por esto que **la API de GitHub devuelve `NOASSERTION`** en diez repos de este
pase: `teal`, `rtables`, `cards`, `cardinal`, `logrx`, `metatools`, `xportr`, `metacore`,
`cdiscdata` y `coreval`. Todos tienen licencia permisiva real. **Diez falsos negativos de
licencia en un solo pase, todos del mismo lenguaje.**

Esto **extiende P18** (puerta de licencia consciente del lenguaje) con la regla concreta que
faltaba: para R, leer `DESCRIPTION`, y tratar un `LICENSE` de dos líneas como *stub*, no como
ausencia. Verificados con esta regla:

| Repo | API GitHub | `DESCRIPTION` (byte real) |
|---|---|---|
| [pharmaverse/logrx](https://github.com/pharmaverse/logrx) | `NOASSERTION` | `MIT + file LICENSE` → **MIT**, 49★ |
| [pharmaverse/metatools](https://github.com/pharmaverse/metatools) | `NOASSERTION` | `MIT + file LICENSE` → **MIT**, 25★ |
| [humanpred/cdiscdata](https://github.com/humanpred/cdiscdata) | `NOASSERTION` | `MIT + file LICENSE` → **MIT**, terminología CT versionada |
| [hrach-gevorgyan/coreval](https://github.com/hrach-gevorgyan/coreval) | `NOASSERTION` | `MIT + file LICENSE` → **MIT**, 3★, 1.054 reglas |

### Substrato de captura de datos (EDC) — copyleft, sin licencia medible, o parado

| Repo | Licencia (por bytes) | ★/forks | Último push | Lectura |
|---|---|---|---|---|
| [OpenClinica/OpenClinica](https://github.com/OpenClinica/OpenClinica) | **ningún fichero de licencia en el repo** | 519★/317f | 2025-10-28 | El EDC open source de referencia. **No hay LICENSE/COPYING: los seis candidatos dan 404 y el `README.md` da 200, así que la ausencia está MEDIDA.** El README enlaza a una página del *vendor* («GNU LGPL»): eso es una promesa comercial, no un fichero. Y está parado 13 meses |
| [ddRPB/LibreClinica](https://github.com/ddRPB/LibreClinica) | **GPL** (`LICENSE`) | — | — | Fork comunitario de OpenClinica 3.14. Copyleft. `search` lo devuelve nulo; `ls-remote` confirma que existe |
| [LabKey/platform](https://github.com/LabKey/platform) | **Apache-2.0** (`LICENSE`) | 13★ | **2026-11-25** | **La única pieza permisiva y activa del plano de captura.** Push el día del pase |
| [LabKey/labkey-api-python](https://github.com/LabKey/labkey-api-python) | Apache-2.0 (`LICENSE.txt`) | 26★ | 2026-11-02 | Cliente Python de LabKey |
| [senaite/senaite.core](https://github.com/senaite/senaite.core) | **GPL-2.0** (`LICENSE`) | 412★ | **2026-11-25** | LIMS clínico muy activo, copyleft. *Corrección de este pase: una primera clasificación automática lo marcó «LGPL»; el fichero dice `GNU GENERAL PUBLIC LICENSE Version 2`. La API tenía razón y el regex no* |
| [krishagni/openspecimen](https://github.com/krishagni/openspecimen) | **BSD-3-Clause** (`LICENSE.md`) | — | — | Biobanco/biorepositorio (ex caTissue Plus). Permisivo. `search` nulo, `ls-remote` OK |

**REDCap no entra en esta tabla y hay que decirlo en voz alta: no es open source.** Se distribuye
a instituciones consorciadas bajo acuerdo de licencia y se autoaloja; no hay repositorio público.
Aparece en listados de «EDC open source» de terceros, y es un error que conviene no heredar.

### El dominio público como cuarta categoría de licencia

Dos activos de este plano no son ni permisivos ni copyleft: **no tienen copyright**.

| Repo | Instrumento | ★ | Lectura para Globant |
|---|---|---|---|
| [FDA/openfda](https://github.com/FDA/openfda) | **CC0-1.0** (`COPYING.txt`, abierto por bytes) | 720★ | Dedicación al dominio público. *Nota de canal: los cuatro `LICENSE*` dan 404; el fichero se llama `COPYING.txt` y sólo apareció al clonar* |
| [ncbi-nlp/TrialGPT](https://github.com/ncbi-nlp/TrialGPT) | **NCBI Public Domain Notice** (obra del Gobierno de EE.UU., no copyrightable) | 185★ | Uso sin restricción declarada; parado desde 2025-01-24 |

Uso máximo, **y ninguna cláusula de garantía**: para una entrega de cliente hay que envolverlos
en el propio aseguramiento. La taxonomía de licencia de esta KB pasa así a **seis categorías**:
permisiva · copyleft · contenido no libre · ausencia medible · **dominio público** ·
**CC-NC-ND presentada como open source**.

---

## Pase 2026-11-25 (c10) — el plano del dispositivo: señal permisiva, comunicación muerta, y un artefacto obligatorio que se construye con herramientas de fuera del sector

Cuarto plano del día. Tres capas, tres licencias distintas, y la del medio está **abandonada**.

### Capa de señal fisiológica — permisiva, madura y con push de hoy

Es la capa de **formato** de este plano, y la ley del ciclo 6 («el open source permisivo sigue al
formato, no a la decisión») **se confirma por sexta vez**, ahora en la forma de onda:

| Repo | Qué resuelve | Licencia (por bytes) | ★ / forks | Push |
|---|---|---|---|---|
| [`mne-tools/mne-python`](https://github.com/mne-tools/mne-python) | EEG/MEG: lectura, filtrado, análisis. El estándar de facto | BSD-3-Clause (`LICENSE.txt`, 1.467 B) | 3.618 / 1.651 | 2026-11-25 |
| [`MIT-LCP/mimic-code`](https://github.com/MIT-LCP/mimic-code) | Código de referencia sobre MIMIC (UCI, incluida forma de onda) | MIT (`LICENSE`, 1.100 B) | 3.442 / 1.742 | 2026-11-23 |
| [`neuropsychology/NeuroKit`](https://github.com/neuropsychology/NeuroKit) | ECG, PPG, EDA, respiración: procesado neurofisiológico | MIT (`LICENSE`, 1.077 B) | 2.437 / 568 | 2026-11-24 |
| [`paulvangentcom/heartrate_analysis_python`](https://github.com/paulvangentcom/heartrate_analysis_python) | HeartPy: análisis de PPG y frecuencia cardiaca | MIT (`LICENSE`, 1.072 B) | 1.156 / 350 | 2025-12-30 |
| [`MIT-LCP/wfdb-python`](https://github.com/MIT-LCP/wfdb-python) | WFDB: el formato de señal de PhysioNet, leer y escribir | MIT (`LICENSE`, 1.110 B) | 863 / 333 | 2026-11-25 |
| [`PIA-Group/BioSPPy`](https://github.com/PIA-Group/BioSPPy) | Biosignal Processing in Python (repo original) | BSD-3 (`LICENSE`, 1.580 B) | 645 / 289 | 2022-08-02 |
| [`raphaelvallat/yasa`](https://github.com/raphaelvallat/yasa) | Estadificación automática del sueño sobre polisomnografía | BSD-3-Clause (`LICENSE`, 1.521 B) | 602 / 130 | 2026-10-25 |
| [`openmhealth/schemas`](https://github.com/openmhealth/schemas) | Esquemas abiertos de datos de salud móvil (el «FHIR» del wearable) | Apache-2.0 (`LICENSE`, 11.324 B) | 82 / 49 | 2026-08-26 |

Ocho filas, ocho licencias permisivas verificadas por bytes. **Cuatro con push esta semana.** Esta
capa no es un hueco: está resuelta, y es la base sobre la que se construye (P25).

> **Nota de procedencia sobre `BioSPPy`:** existe un segundo *slug* mantenido,
> [`scientisst/BioSPPy`](https://github.com/scientisst/BioSPPy), **BSD-3 verificada por bytes**
> (`LICENSE`, 1.585 B) y existencia confirmada por `ls-remote`. No se citan sus estrellas porque
> `search/repositories` **es ciego a ese repo** (HTTP 422). Se declara la cifra ausente en vez de
> heredarla: ver la nota de canal al final.

### ⚠️ Capa de comunicación con el dispositivo — el hueco más limpio del pase

El estándar de comunicación de dispositivo médico es **IEEE 11073**. Su implementación de
referencia abierta es [`signove/antidote`](https://github.com/signove/antidote):

| Repo | Licencia (por bytes) | ★ / forks | Último push | Veredicto |
|---|---|---|---|---|
| [`signove/antidote`](https://github.com/signove/antidote) | **LGPL** (`LICENSE`, 26.998 B) | 51 / 34 | **2021-05-14** | Copyleft débil **y parado hace 4,5 años** |
| [`mdpnp/mdpnp`](https://github.com/mdpnp/mdpnp) | BSD-2-Clause (`LICENSE`, 1.294 B) | 145 / 79 | 2026-05-07 | **OpenICE**, lo único permisivo y vivo de la capa |

Tamaño medido de la capa: `IEEE 11073` = **30 repos en total**; `medical device interoperability`
= **15 repos**. Para comparar: la capa FHIR que esta KB documentó en el ciclo 5 se cuenta por
millares. **La interoperabilidad de dispositivo es, medida, dos órdenes de magnitud más pequeña
que la interoperabilidad de dato clínico**, y su implementación de referencia está abandonada.

`mdpnp/mdpnp` (OpenICE, del programa MD PnP) es por tanto **la única base permisiva viva** para
integración multi-dispositivo a pie de cama. 145 estrellas: pequeño, pero es lo que hay, y la
razón ★/forks de 1,8 dice que quien lo coge lo despliega.

### La capa que la norma obliga a producir — y que se construye con herramientas de fuera del sector

**Este es el segundo hallazgo del pase.** La FDA, por la sección **524B** de la FD&C Act, exige en
la sumisión de todo *cyber device* (510(k), PMA, De Novo, PDP, HDE) un **SBOM legible por máquina**
que cubra componentes comerciales, **open source** y *off-the-shelf*. Es un artefacto computable y
obligatorio: exactamente la condición que el ciclo 6 (P12) identificó como la que hace aparecer
oferta permisiva. **Y la oferta apareció — pero no es sanitaria:**

| Repo | Qué produce | Licencia (por bytes) | ★ / forks | Push |
|---|---|---|---|---|
| [`aquasecurity/trivy`](https://github.com/aquasecurity/trivy) | Escaneo de vulnerabilidades y SBOM | Apache-2.0 (`LICENSE`, 11.357 B) | 39.740 / 939 | 2026-11-24 |
| [`anchore/syft`](https://github.com/anchore/syft) | Generación de SBOM desde imágenes y árboles de fuentes | Apache-2.0 (`LICENSE`, 11.357 B) | 9.967 / 1.083 | 2026-11-25 |
| [`DependencyTrack/dependency-track`](https://github.com/DependencyTrack/dependency-track) | Plataforma de inventario y vigilancia continua de componentes | Apache-2.0 (`LICENSE.txt`, 11.357 B) | 4.521 / 881 | 2026-11-25 |
| [`CycloneDX/cyclonedx-cli`](https://github.com/CycloneDX/cyclonedx-cli) | Conversión, mezcla y validación de SBOM CycloneDX | Apache-2.0 (`LICENSE`, 11.341 B) | 564 / 90 | 2026-10-19 |
| [`CycloneDX/cdxgen`](https://github.com/CycloneDX/cdxgen) | Generador de SBOM multi-lenguaje | Apache-2.0 (`LICENSE`, 11.357 B) | *no medible* | — |

Cinco herramientas, **todas Apache-2.0, ninguna de salud**. Y la medición que lo cierra:
`medical device cybersecurity` = **58 repos**; `medical device SBOM` = **12 repos**; `SBOM` a
secas = **6.638**.

**La regla nueva, y es generalizable a las doce industrias:** cuando el artefacto que el regulador
exige es **genérico** (un SBOM, no un juicio clínico), la oferta permisiva **ya existe y viene de
fuera del sector**. El hueco no es de herramienta, es de **vínculo**: nadie ha atado esas cinco a
la sumisión sanitaria. Ahí está el margen, y es un entregable, no una plataforma (ver P26).

> `CycloneDX/cdxgen` existe (`ls-remote` OK) y su licencia está verificada por bytes, pero
> `search/repositories` devuelve 422 para ese *slug*: **sin cifra de estrellas, y se dice**.

### Substrato regional de este plano — con las dos regiones que suelen quedar sin colocar

| Repo | Región | Qué es | Licencia (por bytes) | ★ / forks | Push |
|---|---|---|---|---|---|
| [`antonior92/automatic-ecg-diagnosis`](https://github.com/antonior92/automatic-ecg-diagnosis) | LATAM | Diagnóstico automático de ECG de 12 derivaciones (UFMG, Brasil; cohorte CODE) | MIT (`LICENSE`, 1.078 B) | 458 / 142 | 2023-03-25 |
| [`vitaldb/vitalutils`](https://github.com/vitaldb/vitalutils) | APAC | Utilidades para VitalDB: señal intraoperatoria de alta resolución (Seoul National University) | BSD-3-Clause (`LICENSE`, 1.507 B) | 22 / 18 | 2026-07-24 |
| [`ehrbase/ehrbase`](https://github.com/ehrbase/ehrbase) | EMEA | Repositorio clínico openEHR (Alemania); alternativa de arquitectura al dato FHIR | Apache-2.0 (`LICENSE`, 11.357 B) | 390 / 154 | 2026-11-25 |

Las dos primeras son **substrato de dato, no producto**: 458★ y 22★. Pero son permisivas, existen y
están colocadas, y en LATAM y APAC esta KB llevaba varios pases registrando ausencias. El brasileño
**no tiene push desde 2023-03-25**: se cita como dato y modelo de referencia, no como dependencia.

`ehrbase` entra como nota de borde: `openEHR` = **698 repos**, una arquitectura de dato clínico
que esta KB no había medido en diez pases y que en Alemania y el norte de Europa compite con FHIR.
No es plano de dispositivo; se anota aquí para que el próximo pase decida si merece plano propio.

### Nota de método — la puerta de licencia necesita una **versión 6**, y por un falso positivo propio

Este pase encontró un defecto en la propia puerta de CI que esta KB venía recomendando (P8/P16/P24),
y conviene decirlo sin adornos porque habría producido datos erróneos:

**El texto de la GPL-3.0 y de la AGPL-3.0 contiene la palabra «noncommercial» exactamente una vez.**
Una puerta que haga `grep -i noncommercial` para bloquear CC-NC **bloquea como "no comercial" a
todo repo AGPL o GPL**. En este pase produjo **cinco falsos positivos** (`cgm-remote-monitor`,
`AndroidAPS`, `xDrip`, `get-based`, y los dos de `codeforjapan`) frente a **dos positivos
genuinos** (`openregulatory/templates`, CC-BY-NC-SA con 9 apariciones; `thinkwee/HiMe`, PolyForm NC
con 5).

El discriminante medido y barato: **anclar en las tres primeras líneas (el título) y exigir ≥2
apariciones**. 1 aparición sin título = texto GPL incidental. Código en `compose/patterns.md` P28.
La taxonomía de licencia de esta KB pasa a **nueve categorías**: permisiva · copyleft · contenido
no libre · ausencia medible · dominio público · CC-NC-ND como open source · **manifiesto de
submódulos sin licencia** · **permisiva con reserva de activos** · **`NOASSERTION` no comercial**.
