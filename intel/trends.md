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
