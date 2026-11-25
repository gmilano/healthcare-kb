---
industry: healthcare
region: Global
updated: 2026-11-25
---

# 📡 Tendencias — Healthcare

> Estado del sector a 2026-11-21, con la evidencia que lo sostiene.

## 1. MCP sobre FHIR es la capa que de verdad se consolidó en 2026

Es el hallazgo estructural del pase. Mientras la consulta
`healthcare agent created:>2026-08-01 stars:>=50` devuelve **1 repo en todo el mundo**,
`FHIR mcp stars:>=30` devuelve **11**, en su mayoría MIT o Apache-2.0 y con push reciente:
[wso2/fhir-mcp-server](https://github.com/wso2/fhir-mcp-server) (139★, con flujo OAuth 2.0
contra Epic), [healthchainai/HealthChain](https://github.com/healthchainai/HealthChain) (232★,
REST + CDS Hooks + CDA + MCP + LangChain), [Taiwan-Health-MCP](https://github.com/healthymind-tech/Taiwan-Health-MCP)
(171★, 73 herramientas de terminología), [the-momentum/fhir-mcp-server](https://github.com/the-momentum/fhir-mcp-server) (102★).
**Dónde construir: aquí.** La escasez no está en los agentes, está en el acceso tipado a datos clínicos,
y eso ya está resuelto con licencia permisiva.

## 2. La documentación ambiental dejó de ser el producto y pasó a ser la puerta de entrada

Es el segmento más grande (46.0% de los agentes de documentación clínica en 2026) y el más
capitalizado: Abridge y Ambience se llevaron el 60% de la financiación declarada de 2025 en la
categoría. Pero el análisis de vendors de septiembre de 2026 describe el giro: la documentación
ambiental se está convirtiendo en **la vía de entrada a la automatización más amplia del flujo
clínico**, y los agentes empiezan a ejecutar workflows de varios pasos. Competir en transcripción
es competir contra $800M de capital; competir en lo que sigue a la nota está abierto.

## 3. Los incumbentes del EHR están cerrando el perímetro

Epic reporta **más del 85%** de sus clientes usando Epic AI, y además de sus propios agentes
(Art, Emmie, Penny) ofrece *Agent Factory* para que el hospital construya los suyos. La señal más
clara del perímetro: la integración de OpenAI con Epic es **solo lectura** — sin notas, sin órdenes,
sin códigos. Implicación de arquitectura: **asumir acceso de solo lectura al EHR del incumbente** y
poner la escritura donde el cliente controla el sistema (OpenEMR, OpenMRS, Medplum).

## 4. La exigencia regulatoria se desplazó de "aprobar el modelo" a "demostrar la traza"

Tres jurisdicciones convergen, por caminos distintos, en pedir evidencia por decisión:

- **Brasil**, CFM 2.454/2026, **en vigor desde el 10 de agosto de 2026**: clasificación de riesgo
  por sistema, auditoría continua, uso de IA documentado en el expediente.
- **EEUU**, discussion paper de la FDA (agosto 2026): monitorización post-market y evaluación
  por competencias para dispositivos con IA generativa, agentic AI incluido.
- **Singapur**, guías MOH/HSA (marzo 2026): el enfoque **asigna responsabilidad** en lugar de
  aprobar producto.

Esto cambia qué se construye primero: el event log por decisión no es una mejora de observabilidad,
es el entregable que habilita la venta.

## 5. El calendario europeo se movió, otra vez

El Reglamento (UE) 2026/1744 desplazó el alto riesgo del Anexo I —los dispositivos MDR/IVDR— a
**2 de agosto de 2028**, y hay una propuesta viva para sacarlos del AI Act por completo
(el Parlamento votó mover MDR/IVDR de anexo el 26 de marzo). A marzo de 2026 los dispositivos con
IA se certifican **solo bajo MDR/IVDR**. Lo único firme: **MDR/IVDR no se movió** y el
**Art. 50 aplica desde el 2 de agosto de 2026**. Una fecha regulatoria no es un hecho durable;
construir sobre MDR, no sobre el calendario del AI Act.

## 6. APAC: el cuello de botella es la validación, no el modelo

IDC proyecta un 33% de los hospitales de primer nivel con agentes desplegados para 2030, pero hoy
solo ~**30% de los pilotos** llega a uso clínico, y la razón declarada es explicabilidad y
validación local. Korea tiene el primer estatuto integral de IA de la región; Vietnam clasifica la
IA sanitaria como alto riesgo con registro premarket. El entregable que mueve presupuesto en la
región es el protocolo de validación local.

## 7. LATAM está mejor instrumentada de lo que su narrativa sugiere

Cuatro repos Apache-2.0 cubren la RNDS brasileña, uno de ellos
([Voa-Health/rnds](https://github.com/Voa-Health/rnds)) **ya con servidor MCP para agentes**, y otro
([Precisa-Saude/fhir-brasil](https://github.com/Precisa-Saude/fhir-brasil)) con sandbox local que
permite desarrollar sin acreditación DATASUS. Es la misma inversión de expectativa que el pase de
*financial* midió en banca. La diferencia con EMEA: estos son **comunitarios**, no oficiales
—lo declaran ellos mismos—, mientras gematik sí es la agencia alemana publicando bajo Apache-2.0.

## 8. Lo que NO está pasando

No hay una explosión de agentes clínicos open source nuevos. `clinical AI agent created:>2026-06-01
stars:>=100` devuelve **0**. Los agentes con tracción real
([Biomni](https://github.com/snap-stanford/Biomni) 4099★,
[ToolUniverse](https://github.com/mims-harvard/ToolUniverse) 1798★,
[MedRAX](https://github.com/bowang-lab/MedRAX) 1257★) son **anteriores** y vienen de laboratorios
académicos, no de startups. Varios de los más citados en listas curadas están estancados o sin
licencia. Leer la actividad del sector en la prensa y en los repos da dos respuestas distintas:
el capital se mueve en producto cerrado, no en commons.

---
*Secciones anteriores de este archivo listaban "repos más activos esta semana" provenientes de una
ingesta automática sin filtro de relevancia (incluía un generador de esquemas MySQL y un bolsa de
empleo). Se reemplazaron por tendencias con evidencia; el historial de repos trending vive, como
corresponde, en `repos/trending.md` y `agents/trending.md`.*

---

## Pase 2026-11-22 — las tendencias que sí tienen fecha

### 1. La autorización previa es la primera tarea de juicio clínico con fecha de corte

No es una previsión de proveedor: es una regla. **CMS-0057-F exige una API de autorización
previa operativa el 1 de enero de 2027** para Medicare Advantage, Medicaid/CHIP FFS estatal, y
—con periodos de tarificación o años de plan que empiecen a partir de esa fecha— Medicaid/CHIP
*managed care* y emisores QHP de los *marketplaces*. Partes del paquete **ya están vigentes
desde 2026**: decisión en 72 horas para solicitudes urgentes, 7 días naturales para las
ordinarias, y obligación de motivar la denegación.

**El matiz que decide una arquitectura:** la API es obligatoria, **la guía de implementación
no**. CMS lista Da Vinci CRD/DTR/PAS STU 2.0.1 **y** 2.1.0 como *recomendadas*. Es la regla de
la segunda pierna del patrón P9 aplicada antes de perder una recomendación: la pierna firme es
«hay que exponer una API el 2027-01-01»; la pierna blanda es «tiene que ser Da Vinci PAS».
Se construye con Da Vinci porque es lo que existe en Apache-2.0 y lo que el mercado va a
interoperar, **no porque la ley lo nombre**.

### 2. El ciclo de ingresos es donde la IA sanitaria tiene el retorno medido más alto

Una encuesta de BVP/Bain citada en prensa sectorial sitúa el retorno de la IA de ciclo de
ingresos en **4× su coste, el más alto de cualquier función**, y la adopción en autorización
previa pasando del **32 % al 46 %**. ⚠️ Cifra de encuesta citada por proveedores, sin
metodología publicada: usarla como dirección, no como número defendible ante un CFO.

Lo que sí es verificable es la forma del mercado: los análisis coinciden en que lo que está en
producción es autorización previa, codificación de media cadena y analítica de denegaciones,
**siempre con revisión humana de lo que tiene consecuencia económica**, y que el ciclo de
ingresos plenamente autónomo es una afirmación de 2027 en adelante.

### 3. La vigilancia agéntica sigue en consulta, no en norma

El documento de debate de la FDA sobre dispositivos con IA generativa es del **18 de agosto de
2026**, con comentarios cerrados el **19 de octubre de 2026** (expediente FDA-2026-N-7874), y
pregunta explícitamente por IA agéntica, modelos fundacionales y vigilancia post-mercado.
Sigue siendo **consulta, no regla**. Un comentario presentado al expediente sostiene que las
trayectorias conversacionales multi-turno deben evaluarse de forma holística.

Corolario sin cambios respecto al ciclo 5, y reforzado: no hay manual de examinador que
heredar, así que **quien escriba ahora un marco de control defendible para agentes fija el
estándar de facto**.

### 4. El contenido se encarece aunque el código sea gratis

Tendencia estructural que esta KB no había registrado: los conjuntos de códigos clínicos
siguen trayectorias de licencia divergentes. ICD-10-CM es dominio público y los CDC lo
publican gratis; **CPT sigue con copyright de la AMA y cuotas por usuario**, con una disputa
viva en 2026 sobre si debería pasar a dominio público —**no resuelta**—; SNOMED CT exige
Licencia de Afiliado incluso donde es gratuita, y cobra por banda de renta del Banco Mundial
fuera de sus 54 Miembros. El efecto práctico: **el coste marginal de un despliegue sanitario
multi-país está cada vez más en el contenido y menos en el software.**

### 5. La métrica de GitHub dejó de informar, y hay un sustituto

Cuarta medición consecutiva: `healthcare agent created:>2026-08-01 stars:>=50` devuelve **1**
resultado en casi cuatro meses, y ese resultado tiene **1 fork**. `FHIR mcp stars:>=30`
devuelve 11, igual que ayer. La tendencia real no está en el recuento de estrellas sino en la
**razón estrellas/forks**: los repos que importan en salud tienen pocas estrellas y casi
tantos forks como estrellas, porque los despliega poca gente y todos los despliegan de verdad.

---

## Pase 2026-11-25 — la tendencia está donde ya hay aprobación, no donde hay titulares

### 1. El plano con aprobación regulatoria real es la imagen, y con mucha diferencia

De las **1 614** entradas de la lista de dispositivos con IA habilitada de la FDA (actualizada
el 2026-09-04), **1 230 tienen radiología como panel principal: el 76 %**. Cardiovascular es
segundo muy lejos, con 154. De esos 1 230 de radiología, **1 212 entraron por 510(k)**, 9 por
De Novo y 9 por PMA. Un análisis distinto, sobre una ventana distinta, da 76,3 % en 2025 y
75,0 % en el primer trimestre de 2026: **la proporción es estable**, lo que la hace fiable como
hecho estructural y no como ruido de un trimestre.

Consecuencia que ordena las prioridades del sector: **la vía regulatoria de la imagen está
trillada** —más de 1 200 precedentes por 510(k)— mientras que para un agente clínico que no es
dispositivo no hay precedente ninguno. ⚠️ Todas estas cifras provienen de análisis de terceros
sobre la lista de la FDA; la propia FDA advierte de que su lista no es exhaustiva. Usar como
estructura, no como censo.

### 2. Y justo ahí la capa agéntica está vacía — la combinación es la tendencia

Substrato permisivo medido hoy: nnU-Net 9 069★, MONAI 8 865★, OHIF 4 424★/4 395f,
TotalSegmentator 3 183★. Capa agéntica sobre ese substrato: `dicom mcp` → **7** resultados,
`radiology agent` → **9**, `monai agent` → **2**.

Es el inverso exacto del hueco que el ciclo 6 encontró en el ciclo de ingresos. Allí la capa de
juicio estaba vacía **porque era imposible licenciarla** (la salida se expresa obligatoriamente
en CPT, propiedad de la AMA). Aquí está vacía **sin impedimento alguno**: el substrato es
Apache-2.0 y MIT, el camino regulatorio tiene 1 200 precedentes y el dato es estándar (DICOM).
**Hueco abierto frente a hueco bloqueado**: la distinción vale para las doce industrias y es la
pregunta que hay que hacerse antes de proponer cualquier capa de juicio.

### 3. Los scribes ambientales son la primera categoría agéntica con oferta permisiva real

Mientras los «agentes sanitarios» genéricos no crecen (quinta medición en total=1), la
documentación ambiental sí tiene oferta abierta y verificable: **Berta** (Apache-2.0, backends
Whisper/Parakeet y LLM local con Ollama o vLLM) y **OpenScribe** (MIT) son permisivos;
**FreeScribe** es **AGPL-3.0** y **canvas-hyperscribe** (MIT) tiene más forks que estrellas y
push de hoy. Las cifras que los autores de Berta publican —sesión media de 7,6 minutos, 42 % de
usuarios personalizando alguna plantilla, **coste operativo por debajo de 30 USD por médico y
mes**— son la primera referencia de coste pública del sector. ⚠️ Son cifras de los autores, con
artículo aceptado en JMIR Med Inform: dirección, no punto.

Por qué cuenta como tendencia y no como anécdota: el coste de un scribe abierto autoalojado es
hoy **conocido y bajo**, lo que convierte la pregunta de «ambiental sí o no» en una de
**build-vs-buy con números**, que es exactamente la conversación en la que Globant es fuerte.

### 4. La razón ★/forks distingue sistema desplegado de librería (no sólo real de promocionado)

Refinamiento de la regla del ciclo 6, con 30 repos medidos: razón **< 1** = sistema que una
institución **opera** (openmrs-core 0,44 · OpenELIS 0,43 · Bahmni 0,48 · dhis2-core 0,88);
**3-6** = librería o modelo de adopción legítima (MONAI 5,1 · nnU-Net 3,6); **> 50** = atención
sin uso (`fabric-mlv-...-starter` 149). La tabla completa está en `repos/foundations.md`.
Implicación de selección: **descartar por pocas estrellas descarta precisamente los sistemas que
los ministerios de salud usan**.

### 5. El contador de agentes verticales sigue clavado — quinta medición

`healthcare agent created:>2026-08-01 stars:>=50` → **total = 1**, el mismo repo, ahora con
149★ y **1 fork**. Cuatro meses sin un agente sanitario permisivo nuevo con tracción. Cuando un
informe de mercado hable de explosión de agentes verticales en sanidad, esta consulta es la
réplica de treinta segundos.

### 6. Dos trampas de licencia de signo opuesto — taxonomía reutilizable

| Trampa | Dónde aparece en sanidad | Se puede evitar | Remedio |
|---|---|---|---|
| **Contenido propietario sobre formato abierto** | CPT de la AMA en ciclo de ingresos (ciclo 6); SNOMED CT fuera de países Miembros | **No** | El cliente licencia el contenido; Globant entrega la capa de juicio (biblioteca CQL) |
| **Infraestructura copyleft bajo modelos permisivos** | Orthanc GPL-3 y dcm4che MPL bajo MONAI/OHIF | **Sí** | Separación de procesos: el componente copyleft se alcanza **sólo por DICOMweb/HTTP** |

La pregunta operativa que se deriva: cuando una capa de juicio está vacía, averiguar **cuál de
las dos trampas la vacía** antes de prometer nada. La primera reubica el negocio; la segunda es
una decisión de arquitectura de media hora.

### 7. Lo que el mercado dice de sí mismo, con la dispersión a la vista

Siete casas de análisis, mismo objeto, 2026: Mordor 1,03 B USD · Towards Healthcare 1,14 B ·
Roots 1,17 B · Future Market Insights 1,2 B · Fortune Business Insights 1,83 B. **Consenso real:
~1-1,2 B USD en 2026 con CAGR del 35-45 %.** Pero los puntos finales no reconcilian: 33,66 B
(2035) frente a 51,29 B (2035, SNS Insider) frente a **262,68 M (2030, GII, CAGR 7,08 %)** —
tres órdenes de divergencia según cómo cada casa define «agéntico». **La dispersión es el dato**:
ante un CFO, citar la dirección y el rango, nunca un punto. La cifra de Towards Healthcare
reproduce exactamente la que el ciclo 3 anotó (1,14 B → 33,66 B, 45,6 %), lo que confirma la
fuente pero no la convierte en verdad.

---

## Pase 2026-11-25 (c8) — un mandato sin artefacto no converge

### 1. La tendencia regulatoria del año en Europa produce fragmentación, no ecosistema

El **EHDS** está en vigor desde 2025-03-26 con fechas firmes (**2027-03-26** autoridades de
acceso, **2029-03-26** uso secundario, **2031-03-26** genómica y ensayos) y **no nombra estándar
técnico**. Medido hoy: `ehds stars:>=5` devuelve **4 repos**, el mayor con **16★** y sin licencia
identificada; seis de los nueve resultados de `ehds health data space` no tienen fichero de
licencia y hay entre ellos una tesis y un hackathon. Compárese con CMS-0057-F, donde el
regulador declaró **y** HL7 publicó una guía de implementación: `org:HL7-DaVinci`, **43 repos
Apache-2.0 con más forks que estrellas**.

**La ley del ciclo 6 queda corregida y es el aporte conceptual del pase:** hacen falta **dos**
condiciones para que aparezca open source permisivo antes del mandato — **(1)** el regulador
declara **y (2)** un organismo publica un **artefacto computable**. El EHDS cumple sólo la
primera. **Condición 1 sin condición 2 = fragmentación nacional.** Vale para las doce industrias.

### 2. Y el substrato que ganaría si lo nombraran ya está construido, maduro y desplegado

`org:OHDSI` son **398 repos**, y la razón ★/forks —la prueba de autenticidad que el ciclo 6
introdujo— da los valores más bajos que esta KB ha medido nunca: `DatabaseConnector` **0,60**,
`Strategus` **0,81**, `WebAPI` **0,83**, `SqlRender` **0,99**. Cuatro repos **con más forks que
estrellas**. Para comparar: `medplum` 2,7 y `synthea` 3,6. **No es un proyecto con atención: es
infraestructura que la gente instala.** De los tres candidatos del EHDS, **OMOP es el único con
un ecosistema de análisis completo y permisivo**; `org:openEHR` son 52 repos y los más grandes
están sin tocar desde 2015-2024.

### 3. Tercera medición del mismo patrón: substrato enorme, capa agéntica vacía

`omop agent stars:>=5` → **2**. Sobre 398 repos. Es el **tercer** plano consecutivo con el mismo
diagnóstico (imagen el pase de esta mañana, ciclo de ingresos en el ciclo 6) y **el más extremo
de los tres**. La tendencia real del sector no es que salgan agentes verticales —el contador de
referencia sigue clavado en **1** por **sexta** medición consecutiva— sino que **la distancia
entre substrato y capa agéntica se ensancha**. Ahí está el trabajo.

### 4. Novedad de método con consecuencia inmediata: la puerta de licencia tiene que conocer el lenguaje

Diez repos nucleares de OHDSI aparecen como **`NONE`** en el metadato de GitHub —incluido
`CommonDataModel`, con **1 103★**— y **los diez son Apache-2.0**, declarada en el `DESCRIPTION`
de R. Una puerta de licencia que sólo lea `LICENSE` **rechaza el stack HADES completo**. En
sentido inverso, `NOASSERTION` volvió a resolver a permisiva en los seis casos abiertos hoy:
**10 de 10** en la historia de la KB. **El metadato de licencia de GitHub es una pista; el
fichero es la prueba, y el fichero no siempre se llama `LICENSE`.** Patrón **P18**.

### 5. La trampa contenido-sobre-formato reaparece, y ahora explica un hueco regional

El ciclo 6 estableció que *la licencia del código no es la licencia del contenido* (CPT sobre
X12). El plano de uso secundario lo repite: `OHDSI/Vocabulary-v5.0` es **Unlicense** —dominio
público— pero eso cubre **el código que construye** el vocabulario, no el vocabulario cargado,
que incorpora SNOMED CT y CPT con sus obligaciones. Y aquí la trampa **explica un hecho
regional medido por dos vías independientes**: OHDSI Brasil nombra la «escasez de vocabularios
adecuados para el contexto brasileño» como su principal dificultad, y el ciclo 7 había medido
que **Brasil, México y Colombia no son Miembros de SNOMED CT**. Mismo problema, dos fuentes.
**El cuello de botella del uso secundario en LATAM es contenido terminológico, no herramienta** —
y la herramienta es Apache-2.0 y gratis. Ver **P19**.

### 6. El plazo más largo del sector está en genómica, y el substrato ya existe

El EHDS aplaza **dato genético y de ensayos a 2031-03-26**: **1 582 días**. El substrato está
construido y es permisivo —`nextflow` 3 535★ Apache-2.0, `scanpy` 2 622★ BSD-3, `gatk` 2 013★
Apache-2.0, `samtools` 1 983★ MIT/Expat, `galaxy` 1 902★ **MIT** (no Academic Free License, como
suele repetirse), `nf-core/sarek` con razón **1,11**— y **existe oráculo**: `Illumina/hap.py` con
*truth sets* públicos da precisión y sensibilidad **numéricas**. Es la misma estructura que el
pase financiero encontró en valoración con QuantLib/ORE: **donde hay oráculo, el entregable
defendible es el benchmark diferencial, no la demo.** Cinco años de plazo y oráculo disponible
es el mejor perfil riesgo/plazo del sector. Ver **P20**.

### 7. Asimetría regional que invierte la del pase de la mañana

En imagen y scribes, Norteamérica y EMEA iban delante. En **uso secundario, APAC va delante de
LATAM con diferencia**: Corea tiene las reclamaciones nacionales de **HIRA** mapeadas al CDM para
**toda la población**, Australia tiene **AHDEN**, y el simposio APAC 2026 se celebró en Seúl el
13-15 de noviembre; **LATAM celebró su PRIMER simposio** en julio de 2026 en Salvador. La lectura
no es que LATAM esté mal posicionada, sino que **el encargo es distinto**: en Corea y Australia se
vende capa analítica sobre un nodo existente; en LATAM se vende **el primer nodo y su vocabulario**.
⚠️ Cifras de material de la propia comunidad OHDSI.

---

## Pase 2026-11-25 (c9) — una fórmula no es un oráculo

### 1. La tendencia estructural del año, vista por fin con un control

Esta KB lleva ocho pases sosteniendo que la oferta permisiva sigue a un «oráculo publicable».
Este pase aporta el primer **experimento controlado** del sector: dos subplanos de la misma
industria, el mismo año, con mandato y formato publicados en ambos, que difieren sólo en si
**alguien publica la salida esperada**. Sumisión CDISC (fixture publicado en
[`cdisc-org/cdisc-open-rules`](https://github.com/cdisc-org/cdisc-open-rules), MIT): 176 repos
permisivos, hasta 328★, push diario. Farmacovigilancia (fórmula PRR/ROR y formato E2B(R3)
publicados, **sin fixture**): cero adoptables, máximo 1★. **Una fórmula no es un oráculo; un
oráculo es una salida esperada publicada.**

### 2. CORE v1.0 es el acontecimiento del plano, y llegó este mes

[`cdisc-org/cdisc-rules-engine`](https://github.com/cdisc-org/cdisc-rules-engine) — MIT, 126★,
50 forks, **push el día del pase** — tiene tag `v1.0.0` (verificado con `ls-remote --tags`).
Un motor de reglas de conformidad regulatoria, open source y versión 1.0, cambia la economía del
plano: deja de hacer falta comprar el validador para saber si una sumisión pasa. Lo que queda
por construir es la capa que **corrige** el dataset, no la que lo juzga. *(El número de reglas
y la fecha exacta del release están marcados NO CITABLES en `intel/market.md`.)*

### 3. El sector sigue publicando «open source» que no lo es — y ahora con autodeclaración

[`dfci/matchminer-ai-inference`](https://github.com/dfci/matchminer-ai-inference) (29★, push
2026-11-20) lleva `CC BY-NC-ND 4.0` mientras su paper se titula *«An Open-Source Solution»* y su
README afirma *«MatchMiner-AI is open source»*. Es la primera vez en nueve pases que la KB mide
un proyecto que **se contradice dentro de su propio repositorio**. La tendencia que esto marca no
es jurídica, es de método: **el vocabulario de marketing del open source sanitario se ha
desacoplado de los ficheros de licencia**, y el único canal fiable sigue siendo abrir el fichero.

### 4. Novedad de método con efecto inmediato: el stub de licencia de R

`R` es el lenguaje del ensayo clínico, y su convención `License: MIT + file LICENSE` produce un
`LICENSE` de dos líneas sin texto legal. Resultado: **diez falsos negativos de licencia en un
solo pase** (`teal`, `rtables`, `cards`, `cardinal`, `logrx`, `metatools`, `xportr`, `metacore`,
`cdiscdata`, `coreval`), todos permisivos de verdad, todos marcados `NOASSERTION` por la API de
GitHub. La puerta de licencia de P18 queda extendida con la regla de R. Y aparece una segunda:
cuando todos los `LICENSE*` dan 404, la conclusión no es «sin licencia» sino «clona y mira»
— así se encontró el `COPYING.txt` con CC0-1.0 de [`FDA/openfda`](https://github.com/FDA/openfda).

### 5. El dominio público entra como categoría propia

Dos activos del plano no son permisivos **ni** copyleft: no tienen copyright.
[`ncbi-nlp/TrialGPT`](https://github.com/ncbi-nlp/TrialGPT) (NCBI Public Domain Notice, obra del
Gobierno de EE.UU.) y [`FDA/openfda`](https://github.com/FDA/openfda) (CC0-1.0, 720★). Uso máximo
y **cero garantía**: la tendencia útil aquí es que el aseguramiento sobre activos públicos es un
entregable en sí mismo. Taxonomía de licencia de esta KB: **seis categorías**.

### 6. La línea captura/sumisión, y por qué es una tendencia y no un detalle

El plano de captura de datos clínicos está copyleft, sin procedencia o parado — OpenClinica
519★/317f **sin fichero de licencia** y sin push en 13 meses; senaite GPL-2.0; REDCap
directamente no es open source. El plano de sumisión es permisivo, corporativo y activo.
La tendencia: **el dinero de las farmacéuticas se ha ido al lado del regulador**, no al lado del
investigador. GSK, Roche, Atorus y Bayer mantienen el substrato de sumisión; nadie mantiene el EDC.

### 7. Asimetría regional, y la primera ausencia LATAM con mecanismo

APAC y LATAM dan **0 repos** en el canal de precisión para su propio tooling de sumisión
(`PMDA CDISC submission`, `NMPA clinical data`, y cuatro consultas ANVISA/español). EMEA da **3**
para todo CTIS, y el único activo tiene 0★. Pero por primera vez en esta KB **la ausencia LATAM
no indica retraso**: ANVISA no publica una clave de respuestas ejecutable, y por la ley refinada
de este pase la ausencia de oferta es *lo que el modelo predice*. Como los sponsors de la región
someten a FDA y EMA, el producto vendible es el mismo que en Norteamérica. Segunda ausencia
LATAM consecutiva sin penalización regional.

---

## Pase 2026-11-25 (c10) — el plano donde los pacientes se adelantaron al mercado

### 1. La tendencia estructural de este plano es que la demanda ya está contada, no estimada

Nueve pases de esta KB han tenido que argumentar demanda a partir de regulación y de encuestas de
consultora. El plano del dispositivo trae la primera cifra de demanda que es un **recuento**:
**73.399 forks** de [`nightscout/cgm-remote-monitor`](https://github.com/nightscout/cgm-remote-monitor),
con 2.867 estrellas. En este plano el fork es la instalación —cada paciente despliega su instancia—
así que la cifra no mide atención, mide **despliegues**. Ninguna otra cosa medida en esta KB se
acerca: es el repo sanitario más desplegado que hemos visto, y lo construyeron los pacientes.

La lectura correcta no es «hay un mercado enorme sin atender». Es más específica y más útil:
**el mercado se autoabasteció porque la industria no le dio un producto, y al hacerlo fijó la
licencia en AGPL-3.0.** La oportunidad no está en validar la demanda, está en ofrecer lo que la
comunidad no puede darse: licencia utilizable y un titular regulatorio.

### 2. Y por eso la segunda tendencia es una inversión de la ley del ciclo 6

La ley del pase financiero y del ciclo 6 —*el open source permisivo sigue al formato de fichero,
no a la decisión*— **se cumple en la capa de señal** (ocho repos permisivos verificados, cuatro con
push esta semana: `mne-python` BSD-3, `NeuroKit` MIT, `wfdb-python` MIT, `mimic-code` MIT…) **y se
invierte en la capa de producto**:

| Capa | En los nueve pases anteriores | En el plano del dispositivo |
|---|---|---|
| Juicio / decisión | Vacía o encumbrada | **Permisiva**: `oref0` MIT, `LoopKit` MIT — el algoritmo de dosificación es abierto |
| Plataforma / fontanería | Permisiva y madura | **Copyleft**: Nightscout y AndroidAPS AGPL-3.0, xDrip GPL-3.0 |

**La frontera de licencia de este plano es arquitectónica, no funcional**, y eso la hace
accionable: se construye sobre el algoritmo permisivo y se evita forkear la plataforma copyleft.
Es la primera vez en diez pases que la capa de juicio clínico está disponible en MIT.

### 3. El acontecimiento del plano tiene tres años, y sigue siendo único

**La autorización de Tidepool Loop por la FDA (2023-01-23) sigue siendo el único caso de open
source sanitario que cruza una puerta regulatoria** en todo lo que esta KB ha medido en diez pases
y seis industrias colindantes. Y el mecanismo es reproducible: una entidad (sin ánimo de lucro, en
este caso) **congela una versión, firma la sumisión y asume el ciclo de vida**; la distribución
comercial va por un socio (Sequel Med Tech, *twiist Loop*). Ciclo observado: sumisión a finales de
2020 → autorización en enero de 2023. **Loop 2.0 se sometió en julio de 2026 y sigue en revisión**
— es decir, el ciclo de ~2 años se está repitiendo ahora mismo y es observable.

Tendencia, no anécdota: lo que escasea en el open source clínico **no es código ni especificación,
es alguien que firme**.

### 4. Octava medición consecutiva del hueco agéntico, ahora en el plano más desplegado

`healthcare agent created:>2026-08-01 stars:>=50` sigue devolviendo **1** (igual que en c5 y c6, y
ese único resultado ya se descartó por razón ★/forks: 149★/1f). En el plano propio:
`vital signs agent` = **32 repos** y los genuinos del top tienen **0 estrellas**; `ECG agent` = 80
con tops de 27★ · 12★ · 5★ · 4★ · 4★; `telemonitoring AI` = **9**. Enfrente, el substrato:
`glucose` 8.988, `wearable sensor` 3.253, `ECG deep learning` 1.443, `remote patient monitoring`
1.049.

Octavo plano consecutivo con la misma forma (FHIR, imagen, OMOP, sumisión regulatoria, dispositivo).
A estas alturas la conclusión operativa ya no es «hay un hueco»: es que **la capa agéntica vertical
hay que construirla en todos los planos del sector, y el diferencial competitivo está en el
substrato que se elija debajo, no en encontrar el agente.**

### 5. Lo único permisivo, mantenido y agéntico del plano es académico

`StanfordBDHG/HealthGPT` (MIT, 1.964★) consulta datos de HealthKit en lenguaje natural;
`StanfordSpezi/Spezi` + `SpeziLLM` (MIT, 261★ y 290★, **push esta semana**) son el framework de app
de salud digital con módulo LLM. Es la primera vez en esta KB que **la mejor pieza agéntica
permisiva de un plano no es una plantilla de proveedor** (como los aceleradores de autorización
previa del ciclo 6) sino un framework universitario con mantenimiento continuo. Para un
*engagement* patient-facing, es la base por defecto.

### 6. Novedad de método con efecto inmediato: la puerta de licencia de esta KB tenía un falso positivo

**El texto de la GPL-3.0 y de la AGPL-3.0 contiene la palabra «noncommercial» una vez.** La puerta
de CI que esta KB recomienda desde P8 bloquearía por tanto **todo repo GPL/AGPL como si fuera
CC-NC**. En este pase: **5 falsos positivos** frente a **2 positivos genuinos**. El discriminante
es anclar en el título (tres primeras líneas) y exigir ≥2 apariciones.

Y una corrección de racha, que importa porque era una generalización heredada: **`NOASSERTION` →
permisiva genuina ya no es «10 de 10»**. `thinkwee/HiMe` es `NOASSERTION` y es **PolyForm
Noncommercial 1.0.0**. De `NOASSERTION` no se sigue «permisiva»; se sigue «sin medir». Es
exactamente el error que esta KB comete cuando **hereda** en lugar de **medir** (ley del ciclo 6).

### 7. El artefacto obligatorio del plano es genérico, y eso cambia de dónde viene la oferta

La FDA exige SBOM legible por máquina en la sumisión de todo *cyber device* (§524B). Por P12,
debería haber aparecido oferta permisiva — y apareció, pero **de fuera del sector**: `trivy`
(39.740★), `syft` (9.967★), `dependency-track` (4.521★), `cyclonedx-cli`, `cdxgen`, **las cinco
Apache-2.0 y ninguna sanitaria**. Mientras `medical device SBOM` = **12 repos** y
`medical device cybersecurity` = **58**.

**Refinamiento de P12, generalizable a las doce industrias:** cuando el artefacto que el regulador
exige es **genérico**, la oferta permisiva existe ya y viene de fuera; el hueco no es de
herramienta sino de **vínculo con la sumisión**. Cuando el artefacto es **específico del dominio**
(una biblioteca CQL, un *fixture* de farmacovigilancia), hay que construirlo. Saber en cuál de los
dos casos se está decide si el entregable es integración o desarrollo.

### 8. Asimetría regional: por una vez el plazo que se mueve es el americano a favor

Norteamérica acaba de pasar hospital a domicilio de «riesgo de expiración cada pocos meses» a
**horizonte asegurado hasta 2030-09-30** (Consolidated Appropriations Act 2026), tras expirar en el
cierre de 43 días. Europa, en cambio, movió su plazo de alto riesgo integrado en producto a
**2028-08-02** por **acuerdo político sin confirmar en el Diario Oficial**, con una propuesta de DG
SANTE que podría excluir del todo a los dispositivos con IA: **plazo más largo pero menos firme**.
APAC añadió un país con ley vigente (**Corea, 2026-01-22**, dispositivos médicos como alto impacto)
**sin autoridad supervisora única**. Y LATAM aporta la única **negativa oficial fechada** del pase:
ANVISA, agosto de 2026, no hay software regularizado basado solo en anillos inteligentes ni
equipos de glucosa/oximetría no invasiva.

Las cuatro regiones apuntan al mismo entregable por caminos distintos: **el expediente del ciclo de
vida**. En NA porque la ley lo exige y la guía no lo formatea; en EMEA porque MDR/IVDR tiene
precedencia; en APAC porque nadie ha fijado el criterio; en LATAM porque ANVISA pide justificación
técnica del método. Es la convergencia regional más clara que esta KB ha registrado.

---

## Pase 2026-11-25 (c11) — tendencias del plano del medicamento

### T1 · La obligación legal no genera software libre; la licencia del contenido lo decide

Es la tendencia estructural del pase y es **reutilizable en las doce industrias**. Tres sub-planos
del medicamento, misma industria, mismo año, misma categoría de tarea (*juicio clínico*):

| Sub-plano | Obligación | Contenido | Resultado |
|---|---|---|---|
| Farmacovigilancia | notificación **legalmente obligatoria** en todas las jurisdicciones | **MedDRA de pago**, WHODrug por suscripción | 12 repos con ≥10★ **en todo el mundo** |
| Interacción clínica fármaco-fármaco | ninguna (es CDS) | **propietario** (FDB/Multum); DrugBank CC BY-NC 4.0 | **vacío**: 191 repos y los diez primeros suman ~42★ |
| Farmacogenómica | **ninguna** | **CPIC = CC0 1.0** | **sano**: PharmCAT MPL-2.0 203★ activo, pypgx MIT con push de ayer |

La correlación con la presión regulatoria es **inversa**; con la licencia del contenido, perfecta.
**Qué vigilar, por tanto:** no el calendario del regulador, sino **la política de licencia del
organismo que publica el cuerpo de conocimiento**. Un cambio de licencia de MedDRA movería más
software abierto en seis meses que diez años de mandatos de notificación.

### T2 · El sobre está resuelto, la carta no — tercera confirmación de la ley del pase financiero

«El open source permisivo sigue al formato de fichero, no a la decisión». En este plano el formato
ICSR **sí** tiene implementación abierta: `FreeVigilance/E2B` (GPL-3.0, refs=82) y
`Pharma-Intelligence-Os` (Apache-2.0). El juicio que viaja dentro de ese sobre no tiene ninguna.
**Tercera industria-plano consecutiva en que la frontera cae exactamente en el mismo sitio.**

### T3 · La capa de dato federal estadounidense es la mejor del mundo en este plano, y es dominio público

`FDA/openfda` (CC0-1.0, 721★/173f) y `FDA/open.fda.gov` (MIT, 178★/76f, **push de hoy**) exponen
FAERS, etiquetado y retiradas sin fricción de licencia. Es el equivalente del hallazgo de gematik en
EMEA del ciclo 5, con una diferencia: **gematik publica especificaciones, la FDA publica el dato
operativo completo.** Para una propuesta eso significa que el *fixture* del plano no hay que
fabricarlo —a diferencia del clínico, donde `synthea` resolvía ese problema—: **el dato real de
seguridad ya es público.**

Y el contraste interno de la propia administración estadounidense: `HHS/pillbox-engine` (refs=64)
**no tiene fichero de licencia**. Mismo gobierno, dos posturas. **El patrón «agencia nacional que
publica sin licenciar» ya tiene tres instancias en esta KB: NHS (Reino Unido), NHA (India, parcial),
HHS (EE.UU.).** Frente a una sola que lo hace bien y lo mantiene: gematik.

### T4 · Regulación — lo nuevo o más preciso que en los pases c5–c10

**North America.** La **hoja de ruta de «Clinical Super Intelligence» de CMS se publicó el
2026-11-13**: ocho páginas, iniciativas conjuntas de CMS, HHS y FDA, con énfasis en despliegue por
fases, generación de evidencia y monitorización continua. **Doce días de antigüedad, nuevo respecto
de todos los pases anteriores.** Además: la **QMSR de la FDA sustituyó a la QSR el 2026-02-02**;
guía de CDS de enero de 2026 que aligera el control previo de parte de las herramientas de apoyo;
**1.430 dispositivos con IA autorizados** a marzo de 2026; **177 proyectos de ley en 31 estados**;
**TRAIGA (Texas) y AB 489 (California) en vigor desde 2026-01-01**. Sobre WISeR, registrado en los
ciclos 5 y 6: hay un **intento del Congreso de bloquearlo tras un hallazgo de la GAO** — se registra
como *movimiento legislativo*, no como derogación.

**EMEA.** Nueva fuente **institucional y de primera mano**: la EMA y la FDA publicaron
**diez principios comunes de buenas prácticas de IA en el ciclo de vida del medicamento el
2026-01-14** (ema.europa.eu). Es exactamente la clase de fuente que esta KB prefiere frente a los
blogs jurídicos, y es **directamente aplicable a este plano**. El *Digital Omnibus* ahora se puede
citar con **las dos fechas separadas**: alto riesgo **diciembre de 2027** para sistemas autónomos y
**agosto de 2028** para IA integrada en productos regulados (dispositivos). La **pierna firme sigue
siendo MDR/IVDR** más el art. 50 vigente desde agosto de 2026 — cuarta vez que esta KB lo repite y
sigue siendo el consejo correcto. **NHS England espera que las ICB y los proveedores adopten
tecnología de voz ambiental desde abril de 2026** (refuerza lo que c7 registró sobre scribes).

**APAC.** Japón **añadió análisis de riesgo para agentes de IA a sus directrices empresariales en
marzo de 2026**, bajo la Ley de Promoción de la IA de 2025 — primera mención específica de *agentes*
en una directriz APAC que esta KB registra. China hace de la *healthtech* prioridad estratégica en
su **15.º plan quinquenal**, con el efecto ya medido en el ciclo 6: la adopción la decide el precio
provincial y la compra hospitalaria, no la aprobación.

**LATAM.** El dato del pase, y es un hueco con nombre: **la farmacovigilancia en LATAM no tiene
todavía reglas específicas de IA.** ARCSA, ANVISA y COFEPRIS tienen **expectativas**, no normas. Eso
significa que la venta aquí **no puede apoyarse en cumplimiento** —no hay qué cumplir— sino en coste
por caso y trazabilidad. **Perú** aparece como el país de la región con **marco general de IA y
reglamento aprobado en 2025**. Brasil sigue con **CFM 2.454/2026** como norma profesional en vigor.

### T5 · Estructura de la oferta — quinta medición del mismo patrón

El embudo del plano: **1.807** repos dicen `pharmacovigilance`, **12** tienen ≥10 estrellas, **1** es
un agente (y sin licencia). La caída no es gradual: **ocurre justo donde empieza la obligación legal.**
Novena medición consecutiva de que no hay un boom de agentes verticales permisivos.

La razón ★/forks vuelve a separar poblaciones: `FDA/open.fda.gov` **2,3** y `coderxio/sagerx` **3,6**
son infraestructura que se despliega; `LalanaChami/Pharmacy-Mangment-System` con **675★/290f** parece
adopción pero es un proyecto académico de 2024 y sus forks son entregas de clase — **primer caso
medido en que una razón «buena» (2,3) *no* indica despliegue**, lo que añade un matiz a la regla:
hay que leer la razón **junto a** `push` y la naturaleza del repo, nunca sola.

### T6 · Tamaño de mercado: la dispersión sigue siendo el dato

| Segmento | 2026 | Horizonte |
|---|---|---|
| Externalización de farmacovigilancia | **5,79–9,15 mil M USD** según cuatro firmas distintas | 16,09 mil M (2030) a 22,99 mil M (2035) |
| Farmacovigilancia global | **9,3–13,71 mil M USD** | 15,7 mil M (2033) a 34,17 mil M (2032) |
| Procesamiento de casos | **4,25 mil M USD** | CAGR 13,1 % a 2035; los **servicios** fueron el **46 %** en 2025 |

**La horquilla de la externalización es del 58 % entre la estimación más baja y la más alta para el
mismo año.** Esa dispersión *es* la información: ante un CFO se cita **dirección y rango con la
fuente**, nunca un punto. Lo que sí es sólido y relevante para una propuesta: el **46 % en servicios**
de procesamiento de casos describe un mercado que **hoy se resuelve con personas**, que es
precisamente la condición de un encargo de automatización.

### T7 · ⚠️ Marcado explícitamente como NO CITABLE en este pase

1. **Cualquier cifra única de mercado de farmacovigilancia.** Cuatro firmas dan 5,79 / 8,51 / 8,7 /
   9,15 mil M para **el mismo año**. Citar el rango y la casa, no el punto.
2. **El precio de WHODrug.** No hay cifra pública localizada. Se afirma que **existe cuota por
   ingresos**, nada más.
3. **«61 % de los líderes sanitarios ya construye IA agéntica» y «85 % aumentará inversión».** Encuesta
   citada en prensa sectorial sin metodología publicada. El contraste útil —y también sin metodología—
   es que otra recopilación sitúa el despliegue **en producción** en el **18 %**: la dirección
   (intención ≫ producción) sí es defendible; los números no.
4. **«1.430 dispositivos con IA autorizados por la FDA».** Procede de un blog de cumplimiento, no del
   recuento oficial de la FDA. Verificar en fda.gov antes de usarlo en una propuesta.
5. **La fecha exacta de entrada en vigor de CFM 2.454/2026.** Discrepancia ya registrada en c10 y no
   resuelta (10-ago frente a septiembre de 2026). Se cita la resolución, no la fecha.
6. **«Las interacciones medicamentosas evitables cuestan X».** Buscado para dimensionar el caso de
   negocio del sub-plano vacío y **no localizado en fuente primaria**. Se deja como hueco, no como cifra.

### T8 · Huecos — estado al 2026-11-25 (c11)

- **(a) CPT / ciclo de ingresos:** sigue reclasificado como imposibilidad de licenciamiento. **Y ahora
  tiene un segundo caso del mismo tipo: MedDRA.** Deja de ser excepción y pasa a ser patrón.
- **(b) NHS publica sin licencia:** abierto. **Tercera instancia del patrón este pase: `HHS/pillbox-engine`.**
- **(c) NLP clínico en español:** **confirmado y ahora cuantificado**. `spanish biomedical model stars:>=10`
  → **total = 1** en todo el mundo, y es `PlanTL-GOB-ES/lm-biomedical-clinical-es` (Apache-2.0, parado
  desde 2022-11). `clinical NLP spanish` → 16 resultados, el resto de 0–1★ y sin licencia. Sigue siendo
  trabajo a medida con pocos competidores.
- **(d) APAC:** **reabierto para este plano**. Japón 3 repos (el mejor con 1★), China 2 repos con 0★,
  India 1 resultado y es un trabajo de curso. **APAC no tiene substrato permisivo de medicamento.**
- **(e) Cuotas de documentación ambiental:** sin fuente. Sin cambios.
- **(f) ABDM (India):** cerrado en c7, **re-verificado hoy**: `org:NHA-ABDM` = 7 repos, `UHI` CC0-1.0
  (164★/43f) confirmado por bytes, y **nada en la organización con push posterior a 2024-09** salvo un
  repo de *hackathon*. Material oficial permisivo sin mantener, igual que se registró.
- **(g) Membresía SNOMED de los grandes países LATAM:** sigue abierto; `snomed.org` no resuelve desde
  este entorno.
- **(h) NUEVO — el coste evitable de la interacción medicamentosa.** El sub-plano clínico de DDI está
  vacío y **no se ha podido dimensionar el daño que evita** con fuente primaria. Importa porque es el
  único argumento que justificaría construir sobre contenido licenciado en un hospital. **Es lo primero
  que debería cerrar un pase futuro de este plano.**
- **(i) NUEVO — tooling permisivo para EudraVigilance.** La notificación a EudraVigilance exige registro
  y **está explícitamente fuera del alcance** del único proyecto permisivo que cubre el flujo
  (`Pharma-Intelligence-Os` lo dice en su propio README). No se localizó ninguna implementación abierta
  de la pasarela. **Hueco informado, no silencio.**
