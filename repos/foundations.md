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
