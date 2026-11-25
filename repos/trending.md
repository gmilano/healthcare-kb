---
industry: healthcare
region: Global
updated: 2026-11-25
---

# 📈 Repos trending — Healthcare

> **Archivo append-only.** La sección más reciente va arriba; el historial se conserva debajo.

## 2026-11-25 (c10) — 73.399 forks: el repo sanitario más desplegado del mundo, y es AGPL

Cuarto pase del día, plano nuevo: **dispositivo y monitorización remota**. La medición de este pase
obliga a añadir una **tercera banda** a la razón ★/forks del ciclo 6, y es la que mide demanda real.

### La tercera banda de la razón ★/forks — medida hoy

| Repo | ★ | Forks | Forks por ★ | Licencia (bytes) | Push |
|---|---|---|---|---|---|
| [`nightscout/cgm-remote-monitor`](https://github.com/nightscout/cgm-remote-monitor) | 2.867 | **73.399** | **25,6** | AGPL-3.0 (34.521 B) | 2026-11-25 |
| [`LoopKit/LoopWorkspace`](https://github.com/LoopKit/LoopWorkspace) | 316 | **8.859** | **28,0** | **sin fichero de licencia** (por clon) | 2026-11-24 |
| [`nightscout/AndroidAPS`](https://github.com/nightscout/AndroidAPS) | 1.264 | 7.639 | 6,0 | AGPL-3.0 (34.520 B) | 2026-11-25 |
| [`NightscoutFoundation/xDrip`](https://github.com/NightscoutFoundation/xDrip) | 1.828 | 1.331 | 0,7 | GPL-3.0 (35.147 B) | 2026-11-25 |

**Forks ≫ estrellas = usuarios finales autodesplegando**, no desarrolladores contribuyendo: en este
plano el fork *es* la instalación. 73.399 es la cifra más alta de toda esta KB — más que OHDSI,
MONAI, synthea y medplum juntos. Los tres primeros tienen **push de hoy o de ayer**.

### Trending real, por push reciente — la capa de señal se movió esta semana

| Repo | Licencia (bytes) | ★ / forks | Push |
|---|---|---|---|
| [`mne-tools/mne-python`](https://github.com/mne-tools/mne-python) | BSD-3-Clause (1.467 B) | 3.618 / 1.651 | 2026-11-25 |
| [`MIT-LCP/mimic-code`](https://github.com/MIT-LCP/mimic-code) | MIT (1.100 B) | 3.442 / 1.742 | 2026-11-23 |
| [`neuropsychology/NeuroKit`](https://github.com/neuropsychology/NeuroKit) | MIT (1.077 B) | 2.437 / 568 | 2026-11-24 |
| [`MIT-LCP/wfdb-python`](https://github.com/MIT-LCP/wfdb-python) | MIT (1.110 B) | 863 / 333 | 2026-11-25 |
| [`DependencyTrack/dependency-track`](https://github.com/DependencyTrack/dependency-track) | Apache-2.0 (11.357 B) | 4.521 / 881 | 2026-11-25 |

### Lo que la medición descarta de este mismo plano

| Repo | Motivo |
|---|---|
| [`signove/antidote`](https://github.com/signove/antidote) | Implementación de referencia de **IEEE 11073**: LGPL (26.998 B) y **sin push desde 2021-05-14** |
| [`codeforjapan/remote-patient-monitoring-api`](https://github.com/codeforjapan/remote-patient-monitoring-api) | AGPL-3.0 y **sin push desde 2022-01-31**. Precedente institucional APAC, muerto |
| [`innolitics/rdm`](https://github.com/innolitics/rdm) | MIT genuino (1.060 B) pero **sin push desde 2022-10-27** |
| [`paulvangentcom/heartrate_analysis_python`](https://github.com/paulvangentcom/heartrate_analysis_python) | MIT y útil (1.156★) pero último push **2025-12-30** |
| [`antonior92/automatic-ecg-diagnosis`](https://github.com/antonior92/automatic-ecg-diagnosis) | MIT, brasileño (UFMG), 458★ — **sin push desde 2023-03-25**: dato de referencia, no dependencia |

### El tamaño de cada capa, medido

| Consulta (canal `search/repositories`) | Resultados |
|---|---|
| `glucose` | 8.988 |
| `SBOM` | 6.638 |
| `wearable sensor` | 3.253 |
| `ECG deep learning` | 1.443 |
| `remote patient monitoring` | 1.049 |
| `openEHR` | 698 |
| `continuous glucose monitor` | 332 |
| `physiological signal processing` | 196 |
| `medical device cybersecurity` | **58** |
| `IEEE 11073` | **30** |
| `medical device interoperability` | **15** |
| `medical device SBOM` | **12** |

**La interoperabilidad de dispositivo es dos órdenes de magnitud más pequeña que la de dato
clínico**, y su implementación de referencia está abandonada. En cambio el artefacto que la FDA
exige (SBOM, §524B) tiene 6.638 repos detrás — **ninguno sanitario**.

### Notas de canal — del noveno al duodécimo falso negativo de `search`

`search/repositories` falla con **dos síntomas distintos**, y conviene distinguirlos porque el
primero parece un error y el segundo parece un hallazgo: **HTTP 422** para `CycloneDX/cdxgen`,
`openremote/openremote` y `tidepool-org/chrome-uploader`, y **resultado vacío** (que se lee como
«no existe») para `scientisst/BioSPPy`. **Los cuatro existen** por `ls-remote`. Acumulado de esta
KB: **doce falsos negativos**. Donde no hay cifra, se declara ausente en lugar de heredarla. Reconfirmado también que `gh api repos/<slug>` sigue dando **403** para repos no
adjuntos, y que la existencia sólo se decide con `git ls-remote`.

## 2026-11-25 (c9) — 176 repos de substrato de sumisión, y la frontera de licencia cae entre capturar y someter

Tercer pase del día, plano nuevo: **investigación clínica**. La medición de este pase separa el
plano en dos mitades con licencias opuestas, y la línea no es tecnológica: es funcional.

### Tamaño del substrato — canal de precisión (`search/repositories`)

| Organización | Repos | Licencia dominante (verificada por bytes) |
|---|---|---|
| `org:OHDSI` (uso secundario, ya en la KB desde c8) | **398** | Apache-2.0 |
| `org:pharmaverse` | **86** | Apache-2.0 / MIT |
| `org:atorus-research` | **48** | MIT (vía `DESCRIPTION`) |
| `org:cdisc-org` | **42** | MIT |

**176 repos** permisivos en el plano de sumisión regulatoria, mantenidos por GSK, Roche, Atorus
y CDISC. Es el segundo substrato más grande que esta KB ha medido, después de OHDSI.

### Y encima, otra vez, casi nada — séptima medición del mismo patrón

| Consulta | Repos |
|---|---|
| `SDTM agent LLM` | **4** |
| `ADaM automation LLM` | **2** |
| `pharmacovigilance agent LLM` | 22 (ninguno adoptable: máximo 1★) |

### Trending real, por push reciente — cinco piezas del substrato movidas esta semana

| Repo | ★ | Licencia (abierta) | Último push |
|---|---|---|---|
| [senaite/senaite.core](https://github.com/senaite/senaite.core) | 412★ | GPL-2.0 (`LICENSE`) | **2026-11-25** |
| [pharmaverse/teal](https://github.com/pharmaverse/teal) | 268★ | Apache-2.0 (`LICENSE`) | **2026-11-25** |
| [cdisc-org/cdisc-rules-engine](https://github.com/cdisc-org/cdisc-rules-engine) | 126★/50f | MIT (`LICENSE`) | **2026-11-25** |
| [pharmaverse/cards](https://github.com/pharmaverse/cards) | 61★ | Apache-2.0 (`LICENSE.md`) | **2026-11-25** |
| [LabKey/platform](https://github.com/LabKey/platform) | 13★ | Apache-2.0 (`LICENSE`) | **2026-11-25** |
| [pharmaverse/admiral](https://github.com/pharmaverse/admiral) | 328★ | Apache-2.0 (`LICENSE.md`) | 2026-11-24 |

Cinco repos del plano con push **el día del pase**. El plano está vivo; lo que falta es la capa de arriba.

### La regla que sale de la medición

> El plano de **captura** (EDC/LIMS) es copyleft, sin procedencia o parado:
> OpenClinica 519★ **sin fichero de licencia** y 13 meses sin push; LibreClinica GPL;
> senaite GPL-2.0. El plano de **sumisión** es permisivo y lo mantienen las farmacéuticas.
> **No se forkea el EDC: se construye encima, por su interfaz.**

`pharmaverse/sdtm.oak` (Apache-2.0, motor ODM→SDTM **agnóstico de EDC**) es la bisagra que hace
ejecutable esa regla.

### Nota de canal — octavo falso negativo de `search` y una ausencia que sí está medida

`search/repositories` devolvió **nulo** para `krishagni/openspecimen` y `ddRPB/LibreClinica`;
`git ls-remote` confirma que ambos existen (octavo y noveno falso negativo acumulados en esta KB).
Y `FDA/openfda` **no tiene ningún `LICENSE*`**: su licencia (CC0-1.0) está en `COPYING.txt`, que
sólo apareció al **clonar**. Regla: cuando los candidatos `LICENSE*` dan 404 y el repo existe,
la respuesta no es «sin licencia», es «clona y mira».


## 2026-11-25 (c8) — OMOP/OHDSI: el substrato con más forks por estrella que la KB ha medido

Segundo pase del día, plano nuevo: **uso secundario del dato**. Y trae la medición que mejor
valida la regla del ciclo 6 (*la infraestructura real se forkea; el repo promocionado se estrella
y no se forkea*), porque aquí la razón baja de 1 en varios repos a la vez.

### Razón ★/forks del núcleo de OHDSI — medida hoy

| Repo | ★/forks | Razón | Licencia (abierta) | Último push |
|---|---|---|---|---|
| [OHDSI/DatabaseConnector](https://github.com/OHDSI/DatabaseConnector) | 58★/96f | **0,60** | Apache-2.0 (`DESCRIPTION`) | 2026-10-19 |
| [OHDSI/Strategus](https://github.com/OHDSI/Strategus) | 13★/16f | **0,81** | Apache-2.0 (`DESCRIPTION`) | 2026-11-24 |
| [OHDSI/WebAPI](https://github.com/OHDSI/WebAPI) | 154★/185f | **0,83** | Apache-2.0 (11325 B) | 2026-11-23 |
| [OHDSI/SqlRender](https://github.com/OHDSI/SqlRender) | 90★/91f | **0,99** | Apache-2.0 | 2026-10-19 |
| [OHDSI/Achilles](https://github.com/OHDSI/Achilles) | 156★/138f | 1,13 | Apache-2.0 (`DESCRIPTION`) | 2026-10-09 |
| [OHDSI/Broadsea](https://github.com/OHDSI/Broadsea) | 94★/81f | 1,16 | Apache-2.0 (11358 B) | 2026-11-10 |
| [OHDSI/DataQualityDashboard](https://github.com/OHDSI/DataQualityDashboard) | 195★/124f | 1,57 | Apache-2.0 (`DESCRIPTION`) | 2026-11-23 |
| [OHDSI/CommonDataModel](https://github.com/OHDSI/CommonDataModel) | 1 103★/518f | 2,13 | Apache-2.0 (`DESCRIPTION`) | 2026-10-28 |
| [OHDSI/WhiteRabbit](https://github.com/OHDSI/WhiteRabbit) | 230★/103f | 2,23 | Apache-2.0 (11346 B) | 2026-10-13 |

**Cuatro repos por debajo de 1 y nueve por debajo de 2,3.** Para comparar con lo que esta misma
KB ya tenía medido: `medplum` 2,7 y `synthea` 3,6. **El stack de OHDSI está más desplegado que
cualquier otra cosa que la KB de salud haya medido**, y `org:OHDSI` tiene **398 repos**.

### Genómica: el substrato más grande, y con el plazo regulatorio más largo

El EHDS aplaza **dato genético y de ensayos clínicos a 2031-03-26** (el resto, 2029). Es el
plano con **cinco años de margen** y el substrato ya está construido y permisivo:

| Repo | ★/forks | Licencia (fichero abierto) | Último push |
|---|---|---|---|
| [nextflow-io/nextflow](https://github.com/nextflow-io/nextflow) | 3 535★/825f | Apache-2.0 | 2026-11-25 |
| [scverse/scanpy](https://github.com/scverse/scanpy) | 2 622★/810f | BSD-3-Clause | 2026-11-24 |
| [broadinstitute/gatk](https://github.com/broadinstitute/gatk) | 2 013★/632f | Apache-2.0 (`LICENSE.TXT`, 10966 B) | 2026-11-25 |
| [samtools/samtools](https://github.com/samtools/samtools) | 1 983★/629f | **MIT/Expat** (1706 B) | 2026-11-12 |
| [galaxyproject/galaxy](https://github.com/galaxyproject/galaxy) | 1 902★/**1 196f** (1,59) | **MIT** (1590 B) | 2026-11-25 |
| [hail-is/hail](https://github.com/hail-is/hail) | 1 082★/268f | MIT | 2026-11-24 |
| [samtools/htslib](https://github.com/samtools/htslib) | 961★/490f (1,96) | MIT/Expat con excepción acotada en `cram/` (3540 B) | 2026-11-25 |
| [nf-core/sarek](https://github.com/nf-core/sarek) | 623★/564f (**1,11**) | MIT | 2026-11-23 |
| [Illumina/hap.py](https://github.com/Illumina/hap.py) | 474★/136f | BSD + MIT (3507 B) | 2023-12-07 |
| [sigven/pcgr](https://github.com/sigven/pcgr) | 285★/51f | MIT | 2026-11-10 |
| [ga4gh/vrs](https://github.com/ga4gh/vrs) | 101★/43f | Apache-2.0 | 2026-11-24 |
| [ga4gh-beacon/beacon-v2](https://github.com/ga4gh-beacon/beacon-v2) | 36★/21f (1,71) | CC0-1.0 | 2026-11-25 |

**Diez de los doce con push en las últimas dos semanas.** Cuatro venían marcados `NOASSERTION` y
los cuatro son permisivos al abrir el fichero.

### Dos reglas de canal, una nueva y una reconfirmada

- **NUEVA Y LA MÁS ÚTIL DEL PASE: el canal de licencia depende del lenguaje.** `NONE` en el
  metadato de GitHub se produce cuando la licencia vive en un fichero de empaquetado y no en un
  `LICENSE`. Medido: **10 repos nucleares de OHDSI con `NONE` y Apache-2.0 en `DESCRIPTION`**.
  Orden de comprobación: `LICENSE*` → `DESCRIPTION` (R) → `pyproject.toml`/`setup.py` (Python) →
  `pom.xml` (Java) → `package.json` (Node) → `README`. Patrón **P18**.
- **Reconfirmada por la vía contraria, y es la más honesta del pase: un 422 TAMBIÉN puede tener
  razón.** `repo:OHDSI/RabbitInAHat` devolvió **HTTP 422** «the resources do not exist», y esta
  vez `ls-remote` dio **refs=0**: el repo **no existe**. Rabbit-in-a-Hat es un **módulo dentro de
  [OHDSI/WhiteRabbit](https://github.com/OHDSI/WhiteRabbit)** (`rabbitinahat/`), no un repo
  propio. El slug venía **de mi memoria, no de una búsqueda** — exactamente el caso que el pase
  financiero registró con `ultibi`. Lección operativa, que no contradice la regla sino que la
  completa: **`ls-remote` es el árbitro en ambas direcciones**, y un slug recordado hay que
  pasarlo por la puerta igual que uno encontrado. Este pase: **38/38 slugs escritos resuelven**;
  el único que falló fue el único que no salió de una medición.

## 2026-11-25 — entra la imagen médica: el substrato más grande del open source sanitario

### Repos en movimiento — push en las últimas 48 horas, medidos hoy

El plano de imagen no es «nuevo»: es que la KB no lo tenía. Es, medido, **el bloque más grande
de todo el open source sanitario**, y casi todo él está en Apache-2.0 o MIT.

| Repo | Licencia | ★/forks | Último push | Razón ★/f |
|---|---|---|---|---|
| [MIC-DKFZ/nnUNet](https://github.com/MIC-DKFZ/nnUNet) | Apache-2.0 | 9069★/2521f | 2026-11-25 | 3,6 |
| [Project-MONAI/MONAI](https://github.com/Project-MONAI/MONAI) | Apache-2.0 | 8865★/1735f | 2026-11-25 | 5,1 |
| [OHIF/Viewers](https://github.com/OHIF/Viewers) | MIT | 4424★/4395f | 2026-11-24 | **1,006** |
| [wasserth/TotalSegmentator](https://github.com/wasserth/TotalSegmentator) | Apache-2.0 | 3183★/507f | 2026-11-25 | 6,3 |
| [pydicom/pydicom](https://github.com/pydicom/pydicom) | MIT con porciones | 2241★/570f | 2026-11-24 | 3,9 |
| [InsightSoftwareConsortium/ITK](https://github.com/InsightSoftwareConsortium/ITK) | Apache-2.0 | 1677★/763f | 2026-11-25 | 2,2 |
| [cornerstonejs/cornerstone3D](https://github.com/cornerstonejs/cornerstone3D) | MIT | 1174★/542f | 2026-11-25 | 2,2 |
| [Project-MONAI/MONAILabel](https://github.com/Project-MONAI/MONAILabel) | Apache-2.0 | 918★/281f | 2026-11-25 | 3,3 |
| [QIICR/dcmqi](https://github.com/QIICR/dcmqi) | BSD-3-Clause | 282★/69f | 2026-11-16 | 4,1 |

**OHIF/Viewers con razón 1,006** (4 424 estrellas y 4 395 forks) es el caso más limpio de la
regla del ciclo 6 registrado hasta ahora en cualquier industria: un fork por estrella, es decir
casi todo el que lo mira lo despliega.

### Lo que la razón y la licencia descartan de este mismo plano

| Repo | Motivo |
|---|---|
| [jodogne/OrthancMirror](https://github.com/jodogne/OrthancMirror) | **GPL-3.0** confirmado (`COPYING`, 35148 B). Es el PACS ligero de referencia, pero sólo utilizable como proceso separado tras DICOMweb. `orthanc-server/orthanc` **no existe** (refs=0): el proyecto vive en UCLouvain, GitHub es espejo |
| [dcm4che/dcm4che](https://github.com/dcm4che/dcm4che) | **MPL** (`LICENSE.txt`, 25755 B). Copyleft débil por fichero; 1468★/720f, push 2026-11-19 |
| [Slicer/Slicer](https://github.com/Slicer/Slicer) | Licencia **propia** del Brigham, no OSI estándar (10514 B). 2745★/813f |
| [fo-dicom/fo-dicom](https://github.com/fo-dicom/fo-dicom) | **Ningún fichero de licencia** tras probar 9 nombres. 1220★/671f y aun así inutilizable |

### Verticales de salud pública descubiertas este pase

| Repo | Licencia | ★/forks | Razón | Nota |
|---|---|---|---|---|
| [dimagi/commcare-hq](https://github.com/dimagi/commcare-hq) | BSD-3-Clause | 527★/240f | 2,2 | Agentes comunitarios de salud; push de hoy |
| [dhis2/dhis2-core](https://github.com/dhis2/dhis2-core) | BSD-3-Clause | 361★/411f | **0,88** | Ministerios de salud de **más de 80 países** y sólo 361 estrellas |
| [Bahmni/openmrs-module-bahmniapps](https://github.com/Bahmni/openmrs-module-bahmniapps) | MPL-2.0 (18072 B) | 160★/336f | **0,48** | Distribución clínica completa sobre OpenMRS |
| [dhis2/dhis2-android-capture-app](https://github.com/dhis2/dhis2-android-capture-app) | BSD-3-Clause | 66★/142f | **0,46** | Captura sin conexión |

### Tooling oficial de India, recuperado de un falso negativo de `search`

[NHA-ABDM/ABDM-wrapper](https://github.com/NHA-ABDM/ABDM-wrapper) es **Apache-2.0** (11357 B) y
existe con **refs=37**, pero `org:NHA-ABDM` devuelve 7 repos y **no lo incluye**: séptimo falso
negativo de `search` registrado en la KB. El resto de la organización (UHI CC0-1.0 164★,
ABHA-APP MIT, MOCK-HIP MIT, nhcx sin licencia) está **parado desde 2024**.

### Dos reglas de canal reconfirmadas

- **Acortar la consulta antes de concluir que no hay nada.** `berta clinical documentation` → 0
  resultados; `berta scribe` → encuentra el repo. Y `Pl4tt/OpenScribe` + `ClinicianFOCUS/FreeScribe`
  dan `SEARCH_MISS` con `repo:<slug>` pero **existen** por `ls-remote` (refs=2 y refs=36).
- **El metadato de licencia es un mal testigo, cuatro de cuatro veces este pase.** `NOASSERTION`
  en `pydicom`, `Slicer`, `dcm4che` y `Bahmni` resultó ser MIT-con-porciones, acuerdo propio del
  Brigham, MPL 1.1 y MPL-2.0 respectivamente. Abrir el fichero, siempre.

## 2026-11-22 — lo que se forkea, no lo que se estrella

Este pase cambió el criterio de selección de esta lista. Hasta ahora ordenábamos por
estrellas; a partir de hoy se registra también **la razón estrellas/forks**, porque mide algo
distinto: las estrellas miden atención y los forks miden despliegue. En salud la diferencia es
grande, porque la infraestructura sanitaria real tiene pocos usuarios y todos la forkean.

### Repos en movimiento — verificados por `ls-remote` + bytes de licencia

| Nombre | Licencia | Descripción | Stars/Forks | Razón | Push |
|--------|----------|-------------|-------------|-------|------|
| [maziyarpanahi/openmed](https://github.com/maziyarpanahi/openmed) | Apache-2.0 | NER clínico y desidentificación de PII; refs=4613. Cifra idéntica a la de ayer: estable, no inflada | 5833★/773f | 7,5 | 2026-11-21 |
| [openemr/openemr](https://github.com/openemr/openemr) | GPL-3.0 | El EMR open source con más tracción; certificado ONC | 5618 | — | 2026-11 |
| [synthetichealth/synthea](https://github.com/synthetichealth/synthea) | Apache-2.0 | Generador de historiales sintéticos; 975 forks es la señal de que todo el mundo lo despliega | 3477★/975f | 3,6 | 2026-11-20 |
| [medplum/medplum](https://github.com/medplum/medplum) | Apache-2.0 | Backend FHIR-native; **1029 forks**, el núcleo abierto más adoptable de esta KB | 2812★/1029f | 2,7 | 2026-11-22 |
| [thetahealth/mirobody](https://github.com/thetahealth/mirobody) | Apache-2.0 | Registro de salud personal local-first sobre MCP; +27 estrellas en un día, push diario | 1660★/282f | 5,9 | 2026-11-22 |
| [ZainZhao/HIS](https://github.com/ZainZhao/HIS) | Apache-2.0 | Sistema de información hospitalaria completo (China); sin push desde 2025-02 | 1642 | — | 2025-02 |
| [cqframework/clinical-reasoning](https://github.com/cqframework/clinical-reasoning) | Apache-2.0 | Motor CQL; **46 forks sobre 52 estrellas**, refs=1067. Invisible y fundamental | 52★/46f | **1,1** | 2026-11 |
| [hastimal/gemini-healthcare-agentic-platform](https://github.com/hastimal/gemini-healthcare-agentic-platform) | Apache-2.0 | Búsqueda sanitaria agéntica con cita obligatoria; **36 forks sobre 39 estrellas** | 39★/36f | **1,1** | 2026-11-22 |
| [HL7-DaVinci/test-ehr](https://github.com/HL7-DaVinci/test-ehr) | Apache-2.0 | EHR de pruebas para flujos CRD/DTR/PAS; **más forks que estrellas** | 8★/11f | **0,7** | 2025-09 |

### Lo que la razón descarta

| Nombre | Stars/Forks | Razón | Veredicto |
|--------|-------------|-------|-----------|
| [muhammadusamakhan911-bit/fabric-mlv-agent-healthcare-starter](https://github.com/muhammadusamakhan911-bit/fabric-mlv-agent-healthcare-starter) | 149★/1f | **149** | Plantilla de demo de 16 días. Es el **único** repo que pasa el filtro `healthcare agent created:>2026-08-01 stars:>=50`. No usar. |
| [xxPcy/PharmaLLM-Agent](https://github.com/xxPcy/PharmaLLM-Agent) | 205★/5f | 41 | Sin push desde 2026-11-02. MIT verificada, pero sin señal de uso. |
| [mdexa-ai/mdexa-ai-native-database](https://github.com/mdexa-ai/mdexa-ai-native-database) | 201★/11f | 18 | 201 estrellas en 7 días y un solo push. Concepto relevante (procedencia y licencia de datasets médicos), respaldo aún inexistente. |
| [duyunzhoudyz/dyz-med-paper-skills](https://github.com/duyunzhoudyz/dyz-med-paper-skills) | 374★/4f | 94 | 32 *skills* de redacción de artículos médicos, incluida la respuesta a revisores. NOASSERTION. Uso delicado en integridad académica: no recomendable en trabajo de cliente. |

### Verticales descubiertas este pase

| Nombre | Licencia | Bytes | Descripción | Stars | Push | Región |
|--------|----------|-------|-------------|-------|------|--------|
| [DIGI-UW/OpenELIS-Global-2](https://github.com/DIGI-UW/OpenELIS-Global-2) | MPL-2.0 | 16727 | LIS de laboratorio; **slug canónico nuevo**, el anterior redirige. refs=4795 | 294 | 2026-11 | Global |
| [hmislk/hmis](https://github.com/hmislk/hmis) | GPL-3.0 | 35149 | HMIS hospitalario de Sri Lanka, **refs=12900**: uno de los proyectos sanitarios más activos de APAC | 245 | 2026-11 | APAC |
| [open-dicom/awesome-dicom](https://github.com/open-dicom/awesome-dicom) | CC0-1.0 | 7047 | Índice curado del ecosistema DICOM | 415 | 2026-11 | Global |

---

## 2026-11-21 — repos fundacionales con actividad real

Criterio de esta sección: licencia verificada por bytes, existencia por `git ls-remote`, y
**fecha de último push comprobada** (la contra-verificación que detecta cifras infladas).

### Alta actividad — push en las últimas 72 horas

| Repo | Licencia | Descripción | Stars | Push | Región |
|------|----------|-------------|-------|------|--------|
| [medplum/medplum](https://github.com/medplum/medplum) | Apache-2.0 | Backend FHIR-native completo; la base permisiva más adoptable | 2807 | 2026-11-21 | Global |
| [hapifhir/hapi-fhir](https://github.com/hapifhir/hapi-fhir) | Apache-2.0 | Implementación de referencia FHIR en Java | 2448 | 2026-11-21 | Global |
| [microsoft/fhir-server](https://github.com/microsoft/fhir-server) | MIT | Servidor FHIR en .NET | 1396 | 2026-11-21 | North America |
| [maziyarpanahi/openmed](https://github.com/maziyarpanahi/openmed) | Apache-2.0 | NER clínico + de-identificación PII local-first | 5833 | 2026-11-20 | Global |
| [synthetichealth/synthea](https://github.com/synthetichealth/synthea) | Apache-2.0 | Generador de pacientes sintéticos exportable a FHIR | 3472 | 2026-11-20 | Global |
| [pydicom/pydicom](https://github.com/pydicom/pydicom) | MIT (con excepciones) | DICOM en Python puro | 2238 | 2026-11-20 | Global |
| [sunlabuiuc/PyHealth](https://github.com/sunlabuiuc/PyHealth) | MIT | Toolkit de ML sanitario sobre MIMIC/eICU/OMOP | 1703 | 2026-11-20 | North America |
| [openemr/openemr](https://github.com/openemr/openemr) | GPL-3.0 | EMR certificado ONC, completo | 5614 | 2026-11-20 | Global |
| [openmrs/openmrs-core](https://github.com/openmrs/openmrs-core) | MPL-2.0 + disclaimer | Plataforma EMR modular para construir encima | 2002 | 2026-11-20 | Global |
| [Project-MONAI/MONAI](https://github.com/Project-MONAI/MONAI) | Apache-2.0 | Deep learning para imagen médica | 8858 | 2026-11-18 | Global |
| [mims-harvard/ToolUniverse](https://github.com/mims-harvard/ToolUniverse) | Apache-2.0 | Universo de herramientas para agentes biomédicos | 1798 | 2026-11-18 | North America |
| [snap-stanford/Biomni](https://github.com/snap-stanford/Biomni) | Apache-2.0 | Agente de investigación biomédica | 4099 | 2026-11-16 | North America |

### Fuentes oficiales y regionales — el hallazgo de colocación de este pase

| Repo | Licencia | Por qué importa | Stars | Push | Región |
|------|----------|-----------------|-------|------|--------|
| [gematik/api-erp](https://github.com/gematik/api-erp) | Apache-2.0 | Spec **oficial** de e-receta alemana, de la agencia nacional | 116 | 2026-11-20 | EMEA |
| [gematik/api-ePA](https://github.com/gematik/api-ePA) | Apache-2.0 | Spec **oficial** de la historia clínica electrónica alemana | 60 | 2025-11-20 | EMEA |
| [Voa-Health/rnds](https://github.com/Voa-Health/rnds) | Apache-2.0 | RNDS brasileña con **servidor MCP para agentes** (comunitario, no oficial) | 0 | 2026-11-18 | LATAM |
| [Precisa-Saude/fhir-brasil](https://github.com/Precisa-Saude/fhir-brasil) | Apache-2.0 | Toolkit FHIR R4 brasileño con **sandbox local** (sin acreditación DATASUS) | 1 | 2026-11-20 | LATAM |
| [IgMiras/rnds-br-connect](https://github.com/IgMiras/rnds-br-connect) | Apache-2.0 | Constructor/validador FHIR para RNDS en Java | 1 | 2026-11-13 | LATAM |
| [aphp/edsnlp](https://github.com/aphp/edsnlp) | BSD-3-Clause | NLP clínico en francés, de AP-HP París | 168 | 2026-11-20 | EMEA |
| [ohcnetwork/care](https://github.com/ohcnetwork/care) | MIT | Gestión hospitalaria, Digital Public Good de India | 426 | 2026-11-20 | APAC |
| [ma3u/MinimumViableHealthDataspacev2](https://github.com/ma3u/MinimumViableHealthDataspacev2) | Apache-2.0 | Implementación de referencia del EHDS europeo | 11 | 2026-11-20 | EMEA |

> Las dos tablas de arriba contienen **20 repos con 0 defectos**: 51 slugs barridos con
> `git ls-remote` en este pase, **51 resuelven, 0 muertos**.

### Degradados por medición

| Repo | Motivo |
|------|--------|
| [microsoft/hi-ml](https://github.com/microsoft/hi-ml) | **Archivado** 2025-10-06 (la licencia MIT es correcta) |
| [WangRongsheng/CareGPT](https://github.com/WangRongsheng/CareGPT) | **Archivado**; MIT correcto, 995★ |
| [FudanDISC/DISC-MedLLM](https://github.com/FudanDISC/DISC-MedLLM) | Apache-2.0 correcto, pero sin push desde **2023-10-28** |
| [kyriosdata/rnds](https://github.com/kyriosdata/rnds) | Apache-2.0 correcto, sin push desde **2024-08-28**; referencia, no base |
| `OHDSI/CommonDataModel` | **Sin archivo de licencia** (README 200 como control). Un ciclo previo lo dio como Apache-2.0 |
| `LibreHealthIO/lh-ehr` | Sin licencia y sin sección de licencia; upstream vivo está en GitLab |
| `dcm4che/dcm4chee-arc-light` | MPL-1.1 **declarada solo en el README**, sin archivo LICENSE (508★, activo) |

---

# Historial

## 2026-07-02 — ingesta automática (sin filtro de relevancia)

> ⚠️ Conservado como historial. Tabla idéntica byte a byte a la de `agents/trending.md` del mismo
> día: el pipeline escribía el mismo contenido en los dos archivos, de modo que no había
> distinción real entre "agentes" y "repos". Incluye repos de 0 estrellas sin relación con salud.
> No usar como fuente de recomendación.



| Nombre | Licencia | Descripción | Stars |
|--------|----------|-------------|-------|
| [care_fe](https://github.com/ohcnetwork/care_fe) | MIT | Care is a Digital Public Good enabling accelerated healthcare delivery.  | 611 |
| [erpnext](https://github.com/frappe/erpnext) | GPL-3.0 | Free and Open Source Enterprise Resource Planning (ERP) | 36.4k |
| [meditech-cardiomera-decoder](https://github.com/nexatech-ltd/meditech-cardiomera-decoder) | MIT | Open-source decoder & reverse-engineered file-format spec for Meditech CardioMer | 0 |
| [FitYou](https://github.com/Nikhil210206/FitYou) | ? | FitAi redefines fitness with AI-driven personalized plans for workouts and diets | 19 |
| [Relational-Database-Design-MySQL](https://github.com/Nattawut30/Relational-Database-Design-MySQL) | MIT | Designed a relational database schema for resource allocation using E.F. Codd’s  | 0 |
| [diet-log](https://github.com/anwer3712/diet-log) | MIT | Free bilingual (zh-TW/Indonesian) elderly home-care tracking app for family care | 0 |
| [SORT](https://github.com/RSE-Sheffield/SORT) | NOASSERTION | The Self-Assessment of Organisational Readiness Tool is a self-assessment framew | 3 |
| [New-Grad-Healthcare-Jobs-2027](https://github.com/zapplyjobs/New-Grad-Healthcare-Jobs-2027) | NOASSERTION | 2027 entry-level healthcare jobs — nursing, allied health & clinical US roles | 15 |
| [AI-Assisted-decision-support-system-for-physiotherapy-requirement-](https://github.com/Tejaswinikunamalla/AI-Assisted-decision-support-system-for-physiotherapy-requirement-) | MIT | An AI-assisted decision support system that leverages deep learning and medical  | 0 |
| [env-runner](https://github.com/toyonakibirthtrauma50/env-runner) | MIT | Run JavaScript server apps across multiple runtimes with hot-reload, WebSocket p | 0 |

---
*Pipeline automático — se actualiza cada hora.*
