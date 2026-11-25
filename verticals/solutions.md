---
industry: healthcare
region: Global
updated: 2026-11-25
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

---

## Pase 2026-11-25 — dos verticales reales que faltaban: salud pública y PACS

El guion de esta tarea pide «plataformas reales tipo Odoo que se puedan personalizar con IA
encima». El ciclo 6 demostró que **Odoo no se traslada a sanidad** (sus módulos clínicos son de
terceros con licencia propietaria o LGPL por módulo). Este pase aporta los dos sistemas que sí
cumplen ese papel y que la KB no tenía.

### DHIS2 — el equivalente sanitario real del patrón «plataforma personalizable»

| Plataforma | Repo | Licencia | ★/forks | Qué es y por qué encaja |
|---|---|---|---|---|
| DHIS2 | [dhis2/dhis2-core](https://github.com/dhis2/dhis2-core) | **BSD-3-Clause** (1517 B, Univ. de Oslo) | 361★/411f | Sistema de información sanitaria usado por los **ministerios de salud de más de 80 países**. Modelo de datos configurable por metadatos y **API de aplicaciones**: se le añaden módulos sin bifurcar el núcleo — exactamente el patrón que se buscaba en un ERP |
| DHIS2 Android Capture | [dhis2/dhis2-android-capture-app](https://github.com/dhis2/dhis2-android-capture-app) | BSD-3-Clause | 66★/142f | Captura en campo **sin conexión**, con sincronización posterior |
| CommCare HQ | [dimagi/commcare-hq](https://github.com/dimagi/commcare-hq) | BSD-3-Clause (1532 B) | 527★/240f | Plataforma de trabajadores comunitarios de salud; despliegues grandes en Asia del Sur y África |
| Bahmni | [Bahmni/openmrs-module-bahmniapps](https://github.com/Bahmni/openmrs-module-bahmniapps) | **MPL-2.0** (18072 B) | 160★/**336f** | Distribución clínica completa (HIS) sobre OpenMRS: consulta, farmacia, laboratorio, facturación. Razón 0,48 = se despliega de verdad. Copyleft débil por fichero: compatible con trabajo comercial encima |

**Por qué BSD-3 importa aquí más que en otros sitios:** el comprador de DHIS2 es un ministerio,
y la licencia BSD-3 permite entregar un módulo propietario encima sin obligación de liberarlo.
Es la combinación más limpia de toda la sanidad abierta: **plataforma permisiva + comprador
institucional + hueco de IA sin cubrir**. Las cifras de países varían por fuente (>80 en el
registro de Digital Public Goods y en el BID para uso ministerial, >100 en la web del propio
proyecto): usar **«más de 80 países»**, que es la cifra referida a ministerios.

### El *stack* PACS como vertical personalizable

Un servicio de imagen completo se compone hoy con piezas abiertas, pero **la frontera de
licencia cae en medio del stack** y eso decide la arquitectura (ver P13 en `compose/patterns.md`):

| Capa | Pieza | Licencia | ¿Dentro del producto? |
|---|---|---|---|
| Visor | [OHIF/Viewers](https://github.com/OHIF/Viewers) + [cornerstone3D](https://github.com/cornerstonejs/cornerstone3D) | MIT | **Sí** — se puede empotrar y modificar |
| Modelo / inferencia | [MONAI](https://github.com/Project-MONAI/MONAI), [nnU-Net](https://github.com/MIC-DKFZ/nnUNet), [TotalSegmentator](https://github.com/wasserth/TotalSegmentator) | Apache-2.0 | **Sí** |
| Empaquetado de inferencia | [monai-deploy-app-sdk](https://github.com/Project-MONAI/monai-deploy-app-sdk) | Apache-2.0 | **Sí** |
| Normalización de la salida | [QIICR/dcmqi](https://github.com/QIICR/dcmqi) | BSD-3-Clause | **Sí** |
| Etiquetado | [MONAILabel](https://github.com/Project-MONAI/MONAILabel) | Apache-2.0 | **Sí** |
| **Archivo / PACS** | [Orthanc](https://github.com/jodogne/OrthancMirror) | ⚠️ **GPL-3.0** | **No** — sólo como proceso separado tras DICOMweb |
| **Toolkit de grado industrial** | [dcm4che](https://github.com/dcm4che/dcm4che) | ⚠️ MPL | Sólo sin modificar sus ficheros |

### Recordatorio del ciclo 6 que este pase vuelve a confirmar

> Comprobar la licencia **del módulo**, no la del núcleo. Se cumplió otra vez aquí: el metadato
> de GitHub daba `NOASSERTION` para `pydicom`, `Slicer`, `dcm4che` y `Bahmni`, y abrir el fichero
> dio cuatro respuestas distintas — MIT con porciones, acuerdo propio del Brigham, MPL 1.1 y
> MPL-2.0. Cuatro de cuatro habrían sido mal clasificadas confiando en el metadato.

---

## Pase 2026-11-25 (c8) — plataformas de uso secundario del dato, personalizables con IA encima

El criterio de este fichero es el de Odoo/OpenMRS/Moodle: **sistema real, instalable, con
comunidad, que se personaliza y encima del cual se pone IA**. Las tres de abajo cumplen y
ninguna estaba en la KB. Medidas 2026-11-25, licencia abierta por fichero.

| Plataforma | Repo | Licencia | ★/forks | Qué es y por qué entra |
|---|---|---|---|---|
| **OHDSI Broadsea** | [OHDSI/Broadsea](https://github.com/OHDSI/Broadsea) | Apache-2.0 (11358 B) | 94★/81f | **El «Odoo» del dato observacional**: un `docker compose up` levanta Atlas + WebAPI + HADES + base de datos con el CDM. Es el punto de entrada de un nodo de uso secundario y lo que convierte OMOP de especificación en sistema desplegable |
| **Atlas** | [OHDSI/Atlas](https://github.com/OHDSI/Atlas) | Apache-2.0 (11358 B) | 340★/155f | La aplicación con la que un epidemiólogo define cohortes y caracteriza poblaciones sin escribir SQL. Es la superficie donde un copiloto aporta valor inmediato: **Criteria2Query ya hace texto→cohorte y es Apache-2.0** |
| **Galaxy** | [galaxyproject/galaxy](https://github.com/galaxyproject/galaxy) | **MIT** (1590 B) | 1 902★/**1 196f** | Plataforma de análisis bioinformático con interfaz web, gestión de herramientas y trazabilidad de ejecución. Razón **1,59** = se despliega de verdad. ⚠️ Se le atribuye a menudo Academic Free License: **el fichero dice MIT**, verificado |

### Lo que estas tres cambian en una propuesta

Las plataformas que ya tenía este fichero (OpenMRS, Bahmni, OpenELIS, medplum) son de **uso
primario**: atienden al paciente. Las tres de arriba son de **uso secundario**: explotan el dato
ya recogido. La distinción no es académica, porque **el comprador es otro** —dirección médica e
investigación, o un ministerio, no el CIO de operaciones— y **el calendario regulatorio es otro**
(EHDS: 2027-03-26 autoridades de acceso, 2029-03-26 uso secundario, 2031-03-26 genómica).

### Advertencia de licencia que afecta a este fichero

En `verticals/` se instalan sistemas, y ahí la licencia del **contenido** pesa tanto como la del
código. Un nodo Broadsea sin vocabulario cargado no sirve, y **el vocabulario no es Apache-2.0**:
incorpora SNOMED CT (licencia de Afiliado, obligatoria incluso donde es gratis) y, en EEUU, CPT
(propiedad de la AMA, con cuotas). `OHDSI/Vocabulary-v5.0` es **Unlicense en el código que lo
construye**, lo cual no cubre el contenido cargado. **Nunca prometer un nodo OMOP «todo open
source»** sin aclarar en qué país está el cliente y qué conjuntos de códigos usa.

---

## Pase 2026-11-25 (c9) — verticales de investigación clínica: dónde sí se puede poner IA encima

El patrón «plataforma real, personalizable, con IA encima» sí tiene equivalentes en este plano,
pero **la licencia decide si se personaliza o sólo se integra**. Las cuatro reales:

| Plataforma | Licencia (por bytes) | ★ | Push | Qué es | Modelo de personalización |
|---|---|---|---|---|---|
| [LabKey/platform](https://github.com/LabKey/platform) | **Apache-2.0** | 13★ | **2026-11-25** | Plataforma de datos de investigación (estudios, cohortes, ensayos, muestras) | **Personalizable y redistribuible.** Es el «Odoo» real de este plano |
| [krishagni/openspecimen](https://github.com/krishagni/openspecimen) | **BSD-3-Clause** | — | — | Biobanco: participantes, consentimientos, inventario, envíos, API REST | Personalizable; permisivo |
| [senaite/senaite.core](https://github.com/senaite/senaite.core) | **GPL-2.0** | 412★ | **2026-11-25** | LIMS clínico en producción, muy activo | **Integrar, no forkear.** Copyleft: una entrega derivada arrastra GPL-2.0 |
| [OpenClinica/OpenClinica](https://github.com/OpenClinica/OpenClinica) | **sin fichero de licencia** (ausencia medida) | 519★/317f | 2025-10-28 | EDC/CDM de referencia del sector | **No partir de aquí.** Sin fichero no hay procedencia, y lleva 13 meses parado |

### Lo que estas cuatro cambian en una propuesta

La regla arquitectónica de este plano, y es nítida:

> **La frontera de licencia cae entre CAPTURAR y SOMETER.** El plano de captura (EDC/LIMS) es
> copyleft o sin procedencia; el plano de sumisión (CDISC/pharmaverse) es permisivo y está
> mantenido por las propias farmacéuticas (GSK, Roche, Atorus, Bayer).

Consecuencia directa y vendible: **no se construye el EDC, se construye encima del EDC del
cliente.** Se integra la captura por su interfaz (ODM, API REST, Dataset-JSON) y se pone la
capa propia donde la licencia es permisiva y donde además está el entregable que el regulador
exige. `pharmaverse/sdtm.oak` existe precisamente para eso: es un motor ODM→SDTM
**agnóstico de EDC**, Apache-2.0. Es la bisagra entre los dos planos, y es la pieza que hace
que esta regla sea ejecutable y no un consejo.

### Advertencia que este fichero ya tenía y que aquí se repite con un caso nuevo

El ciclo 6 estableció que *la licencia del código no es la licencia del contenido*. En este
plano reaparece en su forma más caras: la **terminología controlada de CDISC** (los *codelists*
de SDTM/ADaM) se publica a través de CDISC Library y del NCI EVS con sus propias condiciones,
distintas del MIT del motor que las consume. [`humanpred/cdiscdata`](https://github.com/humanpred/cdiscdata)
(MIT vía `DESCRIPTION`) empaqueta terminología versionada, y conviene revisar la procedencia del
**contenido** antes de redistribuirlo con un entregable, aunque el **código** sea MIT.

---

## Pase 2026-11-25 (c10) — verticales de dispositivo y monitorización remota: cuatro personalizables y una que no se puede tocar

El modelo de este fichero —partir de algo que ya funciona y poner IA encima— **se cumple en este
plano, pero con una exclusión dura**: la plataforma más desplegada del sector es AGPL-3.0 y no
admite ese modelo si el resultado se ofrece como servicio.

| Plataforma | Qué es, en producción | Licencia (por bytes) | ★ / forks | Push | ¿IA encima? |
|---|---|---|---|---|---|
| [`tidepool-org/platform`](https://github.com/tidepool-org/platform) + [`blip`](https://github.com/tidepool-org/blip) + [`uploader`](https://github.com/tidepool-org/uploader) | Plataforma de datos de diabetes: ingesta desde bombas y medidores, almacenamiento y visualización clínica. Usada por clínicas reales | BSD-2-Clause (1.295 / 1.295 / 1.299 B) | 31 / 112 / 128 | 2026-11-25 | **Sí, sin fricción.** BSD-2 permite producto cerrado encima |
| [`mdpnp/mdpnp`](https://github.com/mdpnp/mdpnp) | **OpenICE**: entorno clínico integrado, agrega varios dispositivos de cabecera en un bus común | BSD-2-Clause (1.294 B) | 145 / 79 | 2026-05-07 | **Sí.** Es la única base permisiva viva de interoperabilidad de dispositivo |
| [`StanfordSpezi/Spezi`](https://github.com/StanfordSpezi/Spezi) | Framework de app de salud digital: consentimiento, cuestionarios, conexión a dispositivos, sincronización | MIT (1.121 B) | 261 / 27 | 2026-11-22 | **Sí**, y trae su propio módulo LLM (`SpeziLLM`, MIT) |
| [`DependencyTrack/dependency-track`](https://github.com/DependencyTrack/dependency-track) | Plataforma de inventario continuo de componentes. Es la vertical de **cumplimiento** del plano, no clínica | Apache-2.0 (11.357 B) | 4.521 / 881 | 2026-11-25 | **Sí**: sostiene el SBOM que la FDA exige (§524B) |
| [`nightscout/cgm-remote-monitor`](https://github.com/nightscout/cgm-remote-monitor) | Monitorización remota de glucosa. **73.399 forks**: la plataforma sanitaria open source más desplegada que esta KB ha medido | **AGPL-3.0** (34.521 B) | 2.867 / 73.399 | 2026-11-25 | **NO en producto propietario.** Ver el aviso de abajo |

### El aviso que decide la arquitectura: AGPL-3.0 y el límite de red

Nightscout es la tentación obvia de cualquier propuesta de monitorización remota: funciona, está
desplegado por decenas de miles de pacientes y lleva una década en producción. Y es **AGPL-3.0**,
que extiende la obligación de publicar fuente **al uso por red**: ofrecerlo modificado como
servicio obliga a entregar la fuente de la modificación a los usuarios de ese servicio.

**No es un «consultar con legal» de trámite, es una decisión de diseño.** Las dos salidas
correctas son: (1) construir sobre Tidepool (BSD-2) u OpenICE (BSD-2) y usar Nightscout sólo como
**fuente de interoperabilidad** detrás de una frontera de proceso, o (2) aceptar el AGPL y vender
servicio y evidencia en vez de licencia. Lo que no se puede es forkear y cerrar. P25 lo cablea.

### Lo que este plano confirma del recordatorio del ciclo 6

El ciclo 6 descubrió que **el patrón «Odoo» no se traslada a salud** (módulos clínicos con licencia
propietaria por módulo). Este plano añade la variante de dispositivo: **el patrón «plataforma
personalizable» sí se traslada, pero hay que comprobar la licencia de la plataforma MÁS el límite
que impone**. BSD-2 y MIT no imponen límite; AGPL-3.0 impone el límite de red; y
`LoopKit/LoopWorkspace`, con 8.859 forks, **no tiene fichero de licencia en absoluto** (verificado
por clon), por lo que no es una vertical de partida: es un manifiesto de submódulos.

### Advertencia nueva de este fichero: la vertical de QMS regulatorio es NonCommercial

Un proyecto de dispositivo médico necesita expediente técnico y sistema de calidad, y existe un
repo activo y conocido que los plantilla: [`openregulatory/templates`](https://github.com/openregulatory/templates)
(201★, push 2026-10-21). Su `LICENSE.md` (19.089 B) es **CC-BY-NC-SA-4.0**: *NonCommercial*.
**No se puede usar en un entregable facturado.** La opción permisiva,
[`innolitics/rdm`](https://github.com/innolitics/rdm) (MIT, 1.060 B, 145★), **no tiene push desde
2022-10-27**. En esta vertical, lo permisivo está parado y lo mantenido es no comercial: el
expediente se construye, no se adopta.

### La vertical regional que existe, es pública y está muerta

[`codeforjapan/remote-patient-monitoring-api`](https://github.com/codeforjapan/remote-patient-monitoring-api)
(AGPL-3.0, 34.504 B, 40★/16f) y su
[`dashboard`](https://github.com/codeforjapan/remote-patient-monitoring-dashboard) (AGPL-3.0,
13★/10f) son el sistema de monitorización domiciliaria que Code for Japan construyó para la
pandemia. **Último push: 2022-01-31.** Es el repo más estrellado que `search` devuelve para
`remote patient monitoring` con contenido genuino, y está abandonado hace casi cinco años:
APAC tiene precedente institucional de monitorización remota abierta, **y no tiene oferta viva**.
