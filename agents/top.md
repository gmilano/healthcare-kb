---
industry: healthcare
region: Global
updated: 2026-11-25
---

# 🎯 Agentes AI — Healthcare

> Agentes y frameworks agénticos open source para salud. Foco: MIT / Apache 2.0 / BSD.
> **Toda licencia de esta tabla fue verificada por bytes** contra
> `raw.githubusercontent.com/<slug>/HEAD/LICENSE`, y toda existencia contra
> `git ls-remote`. Stars y `pushed` vía `search/repositories` (canal de precisión).
> Última verificación: 2026-11-21.

## Agentes y frameworks verificados

| Nombre | Licencia | Descripción | Stars | Último push | Región |
|--------|----------|-------------|-------|-------------|--------|
| [snap-stanford/Biomni](https://github.com/snap-stanford/Biomni) | Apache-2.0 | Agente de investigación biomédica de Stanford SNAP Lab; el agente biomédico open source con más tracción | 4099 | 2026-11-16 | North America |
| [mims-harvard/ToolUniverse](https://github.com/mims-harvard/ToolUniverse) | Apache-2.0 | Harvard MIMS: universo de herramientas para agentes científicos biomédicos; 600+ refs, base de TxAgent | 1798 | 2026-11-18 | North America |
| [thetahealth/mirobody](https://github.com/thetahealth/mirobody) | Apache-2.0 | Registro de salud personal local-first (labs, wearables, genética) consultable por un agente vía MCP | 1633 | 2026-11-20 | Global |
| [bowang-lab/MedRAX](https://github.com/bowang-lab/MedRAX) | Apache-2.0 | Agente de razonamiento sobre radiografía de tórax, sin entrenamiento adicional (ICML 2025) | 1257 | 2026-11-05 | North America |
| [mims-harvard/TxAgent](https://github.com/mims-harvard/TxAgent) | MIT | Agente de razonamiento terapéutico que opera sobre ToolUniverse | 656 | 2025-07-30 | North America |
| [SamuelSchmidgall/AgentClinic](https://github.com/SamuelSchmidgall/AgentClinic) | MIT | Benchmark de simulación clínica multimodal en entorno de consulta | 381 | 2026-10-03 | North America |
| [stanfordmlgroup/MedAgentBench](https://github.com/stanfordmlgroup/MedAgentBench) | MIT | Benchmark de agentes clínicos **sobre FHIR real** (Stanford / NEJM AI) | 352 | 2025-11-21 | North America |
| [healthchainai/HealthChain](https://github.com/healthchainai/HealthChain) | Apache-2.0 | Conecta pipelines Python a APIs FHIR vivas y entrega vía REST, CDS Hooks, CDA, MCP o LangChain | 232 | 2026-11-20 | Global |
| [Azure-Samples/healthcare-agent-orchestrator](https://github.com/Azure-Samples/healthcare-agent-orchestrator) | MIT | Orquestador multi-agente estilo *tumor board* sobre datos clínicos | 217 | 2026-10-27 | North America |
| [microsoft/healthcareai-examples](https://github.com/microsoft/healthcareai-examples) | MIT | Ejemplos de referencia de los modelos sanitarios de Microsoft (MedImageInsight y familia) | 204 | 2026-11-20 | North America |
| [healthymind-tech/Taiwan-Health-MCP](https://github.com/healthymind-tech/Taiwan-Health-MCP) | MIT | Servidor MCP con **73 herramientas**: ICD-10-CM/PCS, SNOMED CT, LOINC, fármacos TFDA, validación FHIR R4 IG | 171 | 2026-11-18 | APAC |
| [wso2/fhir-mcp-server](https://github.com/wso2/fhir-mcp-server) | Apache-2.0 | Servidor MCP sobre FHIR con flujo OAuth 2.0 completo contra Epic además de HAPI público | 139 | 2026-11-06 | APAC |
| [the-momentum/fhir-mcp-server](https://github.com/the-momentum/fhir-mcp-server) | MIT | Servidor MCP sobre FHIR; alternativa ligera (sin push desde 2025-10, evaluar antes de adoptar) | 102 | 2025-10-23 | Global |
| [langcare/langcare-mcp-fhir](https://github.com/langcare/langcare-mcp-fhir) | MIT | Puente MCP↔FHIR orientado a LangChain (sin push desde 2026-04, evaluar antes de adoptar) | 75 | 2026-04-14 | Global |
| [microsoft/HealthAgentBench](https://github.com/microsoft/HealthAgentBench) | MIT | Benchmark de tareas de agente sanitario de Microsoft Research | 69 | 2026-11-14 | North America |
| [ajhcs/healthcare-agents](https://github.com/ajhcs/healthcare-agents) | Apache-2.0 | 51 paquetes de prompts/SKILL.md para flujos administrativos sanitarios de EEUU | 54 | 2026-11-18 | North America |
| [Carer-Healthcare-AI/Hospilot](https://github.com/Carer-Healthcare-AI/Hospilot) | MIT | Capa agéntica de operaciones hospitalarias sobre FHIR de OpenEMR (LangGraph + Temporal), con aprobación humana por paso consecuente | 18 | 2026-10-19 | Global |
| [Penn-RAIL/MARC-v1](https://github.com/Penn-RAIL/MARC-v1) | MIT | Framework multi-agente de razonamiento y coordinación clínica (Penn RAIL) | 11 | 2026-08-14 | North America |

**18 filas, todas verificadas.** No hay filas de relleno: si una celda no pudo medirse, no se escribió.

## ⛔ Capa de corrección — filas que esta KB recomendó y NO son adoptables

Los ciclos 2, 3 y 4 de healthcare (jul–ago 2026) registraron las filas siguientes como
hecho establecido. Ninguna sobrevivió a la verificación por bytes de este pase.
Se conservan aquí porque **borrarlas repetiría el error**: alguien volvería a adoptarlas.

| Fila registrada antes | Qué se afirmó | Qué está realmente medido | Veredicto |
|-----------------------|---------------|---------------------------|-----------|
| [mitmedialab/MDAgents](https://github.com/mitmedialab/MDAgents) | `MIT, ~2.1k→2.3k→2.5k★`, agente #1 de la KB | **307★, SIN ARCHIVO DE LICENCIA** (11 variantes de nombre/caso × 3 ramas = 404; README 200 como control; el README tampoco declara licencia), último push **2024-11-10** | No vendorizar. Leer/prototipar sí; sin licencia el default legal es *todos los derechos reservados* |
| [Stanford-AIMI/CheXagent](https://github.com/Stanford-AIMI/CheXagent) | `Apache-2.0, ~1.2k→1.4k★` | **239★, CC-BY-NC-ND 4.0** (17843 B, verificado) | **Inutilizable para trabajo de cliente**: NonCommercial + NoDerivatives |
| `epfl-llm/meditron` | `Apache-2.0, ~4.8k→5.1k→5.3k★`, fundacional | **El slug no existe** (`git ls-remote` refs=0). El proyecto vive en [EPFLiGHT/Meditron](https://github.com/EPFLiGHT/Meditron), que **tampoco tiene archivo de licencia** | Usar [EPFLiGHT/FullyOpenMeditron](https://github.com/EPFLiGHT/FullyOpenMeditron) (Apache-2.0 verificado) |
| `BioMedArena` | `Apache-2.0, ~740→960★` | [AI-in-Health/BioMedArena](https://github.com/AI-in-Health/BioMedArena): **30★, MIT** | Licencia distinta y ~30× menos tracción |
| `MeDxAgent` | `MIT, ~280★` | [microsoft/MeDxAgent](https://github.com/microsoft/MeDxAgent): **5★, sin licencia** | No adoptable |
| `CareAgent (opencare.ai)` | `Apache-2.0, ~350★` | `search/repositories` total_count=**0**; ningún slug candidato resuelve | **No existe** |
| `HealthcareAgent (MIT, 51 especialistas)` | repo propio | Es [ajhcs/healthcare-agents](https://github.com/ajhcs/healthcare-agents): Apache-2.0, 54★ | Nombre y licencia equivocados |
| [gersteinlab/MedAgents](https://github.com/gersteinlab/MedAgents) | citado como adoptable | Existe, **sin archivo de licencia** (README 200 como control) | No vendorizar |
| [microsoft/hi-ml](https://github.com/microsoft/hi-ml) | fundacional activo | MIT verificado pero **ARCHIVADO** (2025-10-06) | Solo lectura |
| `microsoft/healthcare-agent-orchestrator` | slug citado | refs=0. Slug real: [Azure-Samples/healthcare-agent-orchestrator](https://github.com/Azure-Samples/healthcare-agent-orchestrator) | Corregido en la tabla de arriba |

### Lo que esto significa como método

Las cifras de estrellas de los ciclos 2→3→4 **crecían** (2.1k→2.3k→2.5k) para un repo cuyo
último push es de **noviembre de 2024**. Un indicador que sube mientras la fecha de último
push no se mueve es la firma de un número inventado, no de un hallazgo.
La fecha de último push es la contra-verificación más barata que existe: **cuesta una llamada
y detecta la fabricación**. Ninguna cifra de estrellas tomada de una nota de rotación
—o de un listicle— es evidencia.

---
*Verificado a mano con `git ls-remote` + sonda de bytes en `raw.githubusercontent.com`. No generado por el pipeline automático.*

---

## Pase 2026-11-22 — la capa de juicio, medida

> Este pase **no reescribe** la tabla de arriba: la valida y añade una capa que no estaba.
> Validación de las filas heredadas: `synthea` 3472→3477, `medplum` 2807→2812,
> `mirobody` 1633→1660, `HealthChain` 232→232, `openmed` 5833→5833 (exacto),
> `MedAgentBench` MIT/352→MIT/353. **Las cifras que el ciclo 5 midió reprodujeron a un día;
> las que fallaron en su día fueron las que venía arrastrando de listicles.** El método
> aguanta: medir sale barato, heredar sale caro.

### Hallazgo central: la frontera de la especificación se mueve, y se ve venir

La ley que trajo el pase financiero —*el open source sigue al formato de fichero, no a la
decisión*— **se confirma en salud y además se refina**. Medido con 15 consultas a
`search/repositories`, tabuladas abajo. Donde el trabajo es un formato con especificación a
nivel de bytes, el repo líder es maduro y permisivo. Donde es un juicio clínico, no hay nada
por encima de ~40 estrellas.

**Pero el límite no es fijo.** Cuando un regulador convierte un juicio en un artefacto
**computable**, aparece open source permisivo para ese juicio — y aparece **antes** del
mandato, no después. La autorización previa es el caso de prueba: CMS-0057-F exige una API de
prior auth para el **1 de enero de 2027**, y las implementaciones de referencia Da Vinci
(Apache-2.0) ya están publicadas y **se forkean más de lo que se estrellan**.

| Capa | Consulta medida | Resultados | Líder |
|------|-----------------|-----------|-------|
| Formato | `x12 edi stars:>=5` | 62 | indice-co/EDI.Net — 491★, MIT |
| Formato | `edi 837` | 106 | BerryWorksSoftware/edireader — 142★, GPL-3.0 |
| Formato | `HL7 v2 parser stars:>=50` | 4 | crs4/hl7apy — 284★, MIT |
| Formato | `snomed stars:>=30` | 22 | IHTSDO/snowstorm — 401★, Apache-2.0 |
| Formato | `icd10 stars:>=50` | 3 | bryand1/icd10-cm — 97★, MIT |
| Juicio-ya-especificado | `org:HL7-DaVinci` | 43 | HL7-DaVinci/CRD — 45★/24f, Apache-2.0 |
| Juicio-ya-especificado | `cds-hooks stars:>=20` | 7 | cds-hooks/docs — 180★/67f, Apache-2.0 |
| Juicio puro | `claim denial stars:>=3` | 12 | microsoft/RHAIL-Claims-Denial-Navigator — 12★ |
| Juicio puro | `revenue cycle stars:>=3` | 16 | nada propio del sector por encima de 11★ |
| Juicio puro | `claims adjudication stars:>=3` | 10 | top del sector 4★ |
| Juicio puro | `medical necessity` | 78 | **los seis primeros suman 3 estrellas** |

`medical necessity` es el resultado más limpio del pase: 78 repositorios y los seis más
relevantes tienen 0, 2, 0, 1, 0 y 0 estrellas. Es un campo de repos vacíos. Nadie ha
publicado un criterio de necesidad médica reutilizable porque no existe uno compartido que
publicar.

### La capa de juicio ya especificada — Da Vinci y CQL (Apache-2.0, verificada por bytes)

Estos repos tienen pocas estrellas y **muchos forks**: la firma de infraestructura que se
despliega, no que se comenta. Son invisibles en cualquier listicle y son lo único permisivo
que existe para autorización previa.

| Nombre | Licencia | Descripción | Stars/Forks | Último push | Región |
|--------|----------|-------------|-------------|-------------|--------|
| [cqframework/clinical-reasoning](https://github.com/cqframework/clinical-reasoning) | Apache-2.0 | Motor CQL: el vehículo por el que un juicio clínico se vuelve ejecutable; refs=1067 | 52★/46f | 2026-11 | North America |
| [HL7-DaVinci/CRD](https://github.com/HL7-DaVinci/CRD) | Apache-2.0 | Coverage Requirements Discovery: descubre en el acto si un servicio necesita autorización | 45★/24f | 2026-07 | North America |
| [HL7-DaVinci/prior-auth](https://github.com/HL7-DaVinci/prior-auth) | Apache-2.0 | Implementación de referencia de Da Vinci PAS, la API que CMS-0057-F vuelve obligatoria | 38★/24f | 2026-07 | North America |
| [HL7-DaVinci/dtr](https://github.com/HL7-DaVinci/dtr) | Apache-2.0 | Documentation Templates and Rules: rellena la documentación exigida desde el EHR | 23★/18f | 2026-07 | North America |
| [AHRQ-CDS/AHRQ-CDS-Connect-CQL-SERVICES](https://github.com/AHRQ-CDS/AHRQ-CDS-Connect-CQL-SERVICES) | Apache-2.0 | Servicio CQL de la agencia federal AHRQ; fuente oficial, no comunitaria | 27★/12f | 2026-05 | North America |
| [HL7-DaVinci/test-ehr](https://github.com/HL7-DaVinci/test-ehr) | Apache-2.0 | EHR de pruebas para validar un flujo CRD/DTR/PAS; **más forks que estrellas** | 8★/11f | 2025-09 | North America |

### La capa de juicio NO especificada — aceleradores de proveedor, dicho sin adornos

Lo único permisivo que existe aquí son plantillas de proveedor, no plataformas comunitarias.
Sirven como referencia de arquitectura; **no son una base sobre la que construir un producto**.

| Nombre | Licencia | Descripción | Stars | Último push | Región |
|--------|----------|-------------|-------|-------------|--------|
| [microsoft/Prior-Authorization-Multi-Agent-Solution-Accelerator](https://github.com/microsoft/Prior-Authorization-Multi-Agent-Solution-Accelerator) | MIT | Acelerador multi-agente de autorización previa; útil como forma, no como producto | 21 | 2026-08 | North America |
| [Azure-Samples/autoauth-solution-accelerator](https://github.com/Azure-Samples/autoauth-solution-accelerator) | MIT | Acelerador de autorización automatizada sobre Azure | 20 | 2026-11 | North America |
| [microsoft/RHAIL-Claims-Denial-Navigator](https://github.com/microsoft/RHAIL-Claims-Denial-Navigator) | MIT | Navegador de denegaciones de siniestros; **refs=3**, es una demo, no una plataforma | 12 | 2026-02 | North America |

### Agentes nuevos verificados este pase

| Nombre | Licencia | Descripción | Stars/Forks | Último push | Región |
|--------|----------|-------------|-------------|-------------|--------|
| [genomoncology/biomcp](https://github.com/genomoncology/biomcp) | MIT | Servidor MCP biomédico (ensayos, variantes, literatura); el MCP médico más adoptado tras mirobody | 683 | 2026-11 | North America |
| [hastimal/gemini-healthcare-agentic-platform](https://github.com/hastimal/gemini-healthcare-agentic-platform) | Apache-2.0 | Búsqueda sanitaria agéntica con fan-out de consultas, *grounding* y cita obligatoria; **39★ y 36 forks** | 39★/36f | 2026-11 | Global |
| [JuneYaooo/open-medical](https://github.com/JuneYaooo/open-medical) | MIT | Agente de escritorio local-first para médicos: gestión de pacientes y conocimiento acumulado | 21★/7f | 2026-11 | APAC |

### Capa de corrección — añadidos de este pase

No borramos filas erróneas: se corrigen en esta capa explícita, porque suprimirlas invita a
readoptarlas.

- **`FreedomIntelligence/OpenClaw-Medical-Skills` — 3120★, 424 forks, SIN FICHERO DE LICENCIA
  y sin push desde 2026-07-21.** Aparece en listas de *trending* de noviembre de 2026. Es el
  repo médico con más estrellas de los que no se pueden usar. Entra en la categoría «sin
  licencia» de la puerta P8, junto a MDAgents y EPFLiGHT/Meditron.
- **`DIGI-UW/OpenELIS-Global-2` es el slug canónico**; `I-TECH-UW/OpenELIS-Global-2` sigue
  resolviendo (ambos refs=4795, es un renombrado con redirección). MPL-2.0 confirmada por
  bytes: 16727 B, el canónico exacto.
- **`stanfordmlgroup/MedAgentBench`: la fila de esta KB ya era correcta** (MIT, 352→353). El
  error «Apache-2.0, ~780★» vive solo en la nota de rotación heredada del ciclo 4. Se registra
  aquí para que nadie «corrija» una fila que está bien.
- **NOASSERTION → permisiva genuina: ahora 8 de 8.** Añaden a la racha `azoner/pyx12`
  (BSD-3-Clause, 1426 B, cláusula de *endorsement* presente), `imsweb/x12-parser`
  (BSD-3-Clause, 1577 B), `bryand1/icd10-cm` (MIT clásico, 1052 B) y `crs4/hl7apy`
  (MIT, 1054 B). El metadato de GitHub sigue siendo un mal testigo; los bytes no.

### Prueba nueva y barata: la razón estrellas/forks

El ciclo 5 dejó una regla: *una métrica que sube mientras `last_push` no se mueve es la firma
de un número inventado*. Este pase añade una segunda, que viene **gratis en la misma llamada**
a `search/repositories`:

> **La infraestructura real se forkea; el repo promocionado se estrella y no se forkea.**
> Una razón estrellas/forks cercana a 1 indica gente que despliega. Por encima de ~50 indica
> atención sin uso.

Medido: `HL7-DaVinci/test-ehr` 8★/11f (0,7) y `hastimal/gemini-healthcare-agentic-platform`
39★/36f (1,1) son reales y útiles pese a sus cifras pequeñas. En el otro extremo,
`muhammadusamakhan911-bit/fabric-mlv-agent-healthcare-starter` tiene 149★ y **1 fork** (149)
con 16 días de vida, y `xxPcy/PharmaLLM-Agent` 205★ y 5 forks (41) sin push desde el 2 de
noviembre.

**El corolario incomoda y es el dato del pase:** la consulta de referencia del ciclo 5,
`healthcare agent created:>2026-08-01 stars:>=50`, sigue devolviendo **total=1** — y ese único
resultado es precisamente el `fabric-mlv-...-starter` de 149★/1 fork. Es decir: **el único
punto de crecimiento aparente del sector en casi cuatro meses es un artefacto de la métrica.**
Cuarta medición consecutiva —tras legal, financial y el propio ciclo 5— de que no hay *boom*
de agentes verticales permisivos.

---

## Pase 2026-11-25 — la capa agéntica sobre imagen médica y los scribes ambientales

Este pase no reescribe nada: verifica lo anterior y abre **dos planos que la KB no había
tocado nunca** — imagen médica y documentación ambiental. Todas las cifras de abajo están
**medidas** el 2026-11-25 con `search/repositories` (estrellas, forks, push y SPDX en una
sola llamada) y toda licencia está **confirmada abriendo el fichero**, no leyendo el metadato.

### Agentes y orquestadores nuevos — verificados uno por uno

| Agente | Repo | Licencia | ★/forks | Último push | Qué hace realmente |
|---|---|---|---|---|---|
| Healthcare Agent Orchestrator | [Azure-Samples/healthcare-agent-orchestrator](https://github.com/Azure-Samples/healthcare-agent-orchestrator) | MIT (1072 B) | 217★/93f | 2026-10-27 | Orquestador multi-agente para *tumor board*: reparte el caso entre agentes especialistas y consolida. El slug `microsoft/healthcare-agent-orchestrator` que circula en prensa **no existe** (`ls-remote` refs=0) |
| healthcare-agents | [ajhcs/healthcare-agents](https://github.com/ajhcs/healthcare-agents) | Apache-2.0 (10714 B) | 55★/15f | 2026-11-18 | Pack de agentes especialistas para administración sanitaria en EEUU. Es el repo que ciclos anteriores anotaron como «51 especialistas» |
| healthcareai-examples | [microsoft/healthcareai-examples](https://github.com/microsoft/healthcareai-examples) | MIT (1072 B) | 204★/55f | 2026-11-20 | Ejemplos de uso de modelos sanitarios multimodales, imagen incluida. Plantilla de proveedor, no plataforma |
| Berta | [phairlab/berta-ai-scribe](https://github.com/phairlab/berta-ai-scribe) | Apache-2.0 (10726 B) | 31★/9f | 2026-10-14 | **Scribe ambiental modular**: backends WhisperX / Whisper / Parakeet-MLX / Amazon Transcribe y LLM local con Ollama, vLLM o LM Studio. Copyright «Ross Mitchell»; desarrollado y evaluado en contexto de Alberta Health Services, con artículo en JMIR Med Inform |
| canvas-hyperscribe | [canvas-medical/canvas-hyperscribe](https://github.com/canvas-medical/canvas-hyperscribe) | MIT | 3★/7f | 2026-11-25 | Copiloto de documentación acoplado al EMR de Canvas. **Más forks que estrellas y push de hoy**: se usa, no se promociona. El slug `canvas-medical/hyperscribe` no existe |
| OpenScribe | [Pl4tt/OpenScribe](https://github.com/Pl4tt/OpenScribe) | MIT (1069 B) | n/d — invisible a `search` | existencia por `ls-remote` (refs=2) | Graba el encuentro y redacta nota estructurada; ruta local Whisper + ruta LLM alojado |
| open-medical-scribe | [BirgerMoell/open-medical-scribe](https://github.com/BirgerMoell/open-medical-scribe) | MIT | 13★/2f | 2026-03-16 | Scribe web/escritorio/CLI con Whisper ONNX, faster-whisper y whisper.cpp; incluye modo de nota en sueco |
| FreeScribe | [ClinicianFOCUS/FreeScribe](https://github.com/ClinicianFOCUS/FreeScribe) | ⚠️ **AGPL-3.0** (34522 B, texto *GNU AFFERO* confirmado) | n/d — invisible a `search` | existencia por `ls-remote` (refs=36) | Scribe local o contra servidor LLM/Whisper en red. **Copyleft de red: inservible en un SaaS cerrado.** Los autores lo declaran en alfa |
| HealthFlow | [yhzhu99/HealthFlow](https://github.com/yhzhu99/HealthFlow) | ⚠️ **sin fichero de licencia** | 61★/6f | 2026-09-23 | Framework multi-agente para análisis de historia clínica electrónica, con artículo en *npj Digital Medicine*. Sin licencia **no es utilizable en trabajo de cliente**, por bueno que sea el paper |
| Awesome AI Agents for Healthcare | [AgenticHealthAI/Awesome-AI-Agents-for-Healthcare](https://github.com/AgenticHealthAI/Awesome-AI-Agents-for-Healthcare) | ⚠️ **sin licencia** | 1292★/173f | 2026-10-02 | El mejor índice de papers y proyectos del sector. Útil **como pista de búsqueda**; sin licencia no se redistribuye |
| AI-Healthcare-System | [pavanbadempet/AI-Healthcare-System](https://github.com/pavanbadempet/AI-Healthcare-System) | ⚠️ **AGPL-3.0** | 81★/19f | 2026-11-09 | Apareció como «#1 trending» de noviembre en un *tracker* de terceros. Medido: **81 estrellas y AGPL-3.0**. El ranking del tracker no describe ni su tamaño ni su usabilidad |
| fabric-mlv-agent-healthcare-starter | [muhammadusamakhan911-bit/fabric-mlv-agent-healthcare-starter](https://github.com/muhammadusamakhan911-bit/fabric-mlv-agent-healthcare-starter) | MIT | 149★/**1f** | 2026-11-06 | Plantilla de demo. Se lista **sólo** para dejar constancia de que sigue siendo el único resultado de la consulta de referencia del sector (ver abajo) |

### El contador de agentes verticales no se mueve — quinta medición consecutiva

La consulta de referencia que los ciclos 5 y 6 dejaron fijada para poder comparar entre pases:

```
healthcare agent created:>2026-08-01 stars:>=50   →   total = 1
```

**Sigue devolviendo 1**, y sigue siendo el mismo `fabric-mlv-...-starter`, ahora con 149★ y
**1 solo fork**. En casi cuatro meses, el sector no ha producido un agente sanitario permisivo
nuevo con tracción medible. Es la **quinta medición consecutiva** —legal, financial, healthcare
c5, c6 y este pase— de que **no hay *boom* de agentes verticales permisivos**, por mucho que lo
digan los informes. Lo que sí hay es substrato excelente en las capas de abajo.

### El hueco agéntico de imagen, medido

El plano de imagen tiene el substrato permisivo más fuerte de toda la sanidad (ver
`repos/foundations.md`), y encima casi no hay agentes:

| Consulta (corta, como manda la regla del ciclo 6) | Resultados |
|---|---|
| `dicom mcp stars:>=10` | 7 |
| `radiology agent stars:>=10` | 9 |
| `monai agent stars:>=10` | 2 |

Siete, nueve y dos. Sobre una base de MONAI (8 865★), nnU-Net (9 069★) y OHIF (4 424★). **Es el
hueco mejor colocado del sector**: substrato maduro y permisivo, aprobación regulatoria
concentrada justo ahí (el 76 % de las autorizaciones de dispositivos con IA de la FDA son de
radiología) y capa agéntica prácticamente vacía. Ver patrón P13 en `compose/patterns.md`.
