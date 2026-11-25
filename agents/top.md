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

---

## Pase 2026-11-25 (c8) — la capa agéntica sobre el dato secundario: 398 repos debajo, 2 arriba

Este pase abre el **plano del uso secundario del dato sanitario** (investigación, evidencia de
mundo real, salud poblacional), que la KB no había tocado en siete pases. Todo lo de abajo está
**medido hoy** con `search/repositories` y **toda licencia confirmada abriendo el fichero**.

### El hueco, medido antes de la tabla

| Consulta (corta, regla del ciclo 6) | Resultados |
|---|---|
| `omop agent stars:>=5` | **2** |
| `cohort llm stars:>=10` | 5 |
| `omop mcp` | 17 (sólo uno por encima de 7★) |
| `real world evidence stars:>=20` | 10 |

Dos. Debajo hay **398 repos en `org:OHDSI`**, con razones ★/forks por debajo de 2 casi en bloque
(ver `repos/foundations.md`). Es el **mismo patrón que el ciclo 7 midió en imagen —substrato
enorme, capa agéntica vacía— pero más extremo**: en imagen eran 7/9/2 sobre 9 000★; aquí son 2
sobre un ecosistema con despliegue demostrado y vocabulario regulatorio con fechas en el BOE
europeo (ver `intel/market.md`).

### Agentes y herramientas agénticas sobre OMOP — verificados uno por uno

| Agente | Repo | Licencia (fichero abierto) | ★/forks | Último push | Qué hace realmente |
|---|---|---|---|---|---|
| Criteria2Query | [OHDSI/Criteria2Query](https://github.com/OHDSI/Criteria2Query) | Apache-2.0 (11357 B) | 81★/22f | 2026-03-01 | Criterios de elegibilidad en lenguaje natural → cohorte OMOP ejecutable. **Es el precursor agéntico del plano y es del propio OHDSI**: el problema «texto libre → consulta tipada» ya está planteado y licenciado permisivamente |
| omop_mcp | [OHNLP/omop_mcp](https://github.com/OHNLP/omop_mcp) | Apache-2.0 (10566 B) — GitHub decía `NOASSERTION` | 44★/10f | 2026-05-11 | Servidor MCP sobre OMOP del grupo OHNLP (Mayo Clinic). **El activo mejor colocado de la tabla** para construir encima |
| omophub-mcp | [OMOPHub/omophub-mcp](https://github.com/OMOPHub/omophub-mcp) | MIT (1069 B) | 7★/0f | 2026-11-24 | MCP de vocabulario OMOP: resuelve conceptos y jerarquías. Pequeño y vivo (push de ayer) |
| ascent-epi-demo | [Bayer-Group/ascent-epi-demo](https://github.com/Bayer-Group/ascent-epi-demo) | BSD-3-Clause (1491 B) | 2★/1f | 2026-11-23 | Demo de epidemiología agéntica **publicada por una farmacéutica**. 2★ no mide nada; lo que señala es **quién** está construyendo aquí |
| Strategus | [OHDSI/Strategus](https://github.com/OHDSI/Strategus) | Apache-2.0 (en `DESCRIPTION`) | 13★/**16f** | 2026-11-24 | Ejecución de estudios en red como módulos declarativos. Razón **0,81**: más forks que estrellas = se despliega. Es el orquestador que un agente debe invocar, no reimplementar |

**Cinco filas reales, cinco verificadas.** No hay más con licencia permisiva y señal medible en
este plano: los otros 12 resultados de `omop mcp` son de 0-3★ y mayoritariamente sin licencia.

### ⚠️ La trampa de licencia de este pase: `NONE` en GitHub no significa sin licencia

GitHub reporta **`NONE`** para `OHDSI/CommonDataModel` (1 103★), `PatientLevelPrediction`,
`DataQualityDashboard`, `Achilles`, `CohortMethod`, `DatabaseConnector`, `FeatureExtraction`,
`ETL-Synthea`, `Strategus` y `CirceR`. **Los diez son Apache License 2.0**, declarada en el
fichero `DESCRIPTION` de R y no en un `LICENSE`. Una puerta de licencia que sólo mire `LICENSE`
**rechaza el stack HADES completo** —el substrato de dato sanitario con más despliegue medido del
mundo— como «sin licencia». Regla nueva y generalizable a las doce industrias en el patrón **P18**.

Los dos únicos desconocidos genuinos del ecosistema, tras abrir ficheros:

| Repo | Estado real |
|---|---|
| [OHDSI/Athena](https://github.com/OHDSI/Athena) | **Sin licencia localizable**: ni `LICENSE` (5 variantes), ni `DESCRIPTION`, ni bloque `<licenses>` en `pom.xml`. Es el descargador de vocabulario: se usa como servicio, no se redistribuye |
| [OHDSI/Usagi](https://github.com/OHDSI/Usagi) | Apache declarada **sólo en el README**, sin fichero de licencia. Utilizable con criterio; no es lo mismo que un SPDX en el repo |

### El contador de agentes verticales no se mueve — sexta medición consecutiva

```
healthcare agent created:>2026-08-01 stars:>=50   →   total = 1
```

Mismo `fabric-mlv-agent-healthcare-starter`, **149★ y 1 fork**, idéntico a la medición de esta
mañana. Sexta medición consecutiva sin *boom* de agentes verticales permisivos.

---

## Pase 2026-11-25 (c9) — la capa agéntica sobre la investigación clínica: un oráculo con clave de respuestas y otro sin ella

Tercer pase del día, y **plano nuevo que la KB no había abierto en seis pases**: la
investigación clínica (sumisión regulatoria, captura de datos, emparejamiento a ensayo,
farmacovigilancia). Medición de entrada sobre los 3.107 líneas previas: `CDISC` = 0
menciones, `SDTM` = 0, `EDC` = 0, `farmacovigilancia` = 0, `ensayo clínico` = 0.
No era un hueco de profundidad: era un plano entero ausente.

### El hallazgo central: una comparación controlada, misma industria y mismo año

Este plano contiene **dos subplanos con el mismo formato publicado y resultados opuestos**,
lo que permite por primera vez aislar qué propiedad genera oferta permisiva:

| Subplano | Fórmula pública | Formato público | **Clave de respuestas pública** | Oferta permisiva medida |
|---|---|---|---|---|
| Sumisión regulatoria (CDISC) | sí (reglas de conformidad) | sí (SDTM/ADaM/Dataset-JSON) | **SÍ** — [`cdisc-org/cdisc-open-rules`](https://github.com/cdisc-org/cdisc-open-rules) publica *reglas + datos de prueba*, MIT | **176 repos** (pharmaverse 86 + atorus-research 48 + cdisc-org 42) |
| Farmacovigilancia | sí (PRR/ROR, BCPNN) | sí (ICH E2B(R3)) | **NO** — nadie publica la salida esperada | **0 repos adoptables**; el máximo es 1★ |

**Conclusión que corrige la ley del oráculo de esta KB: una FÓRMULA NO ES UN ORÁCULO.**
Hace falta que alguien publique **la salida esperada** — el fixture. Farmacovigilancia tiene
estadístico publicado y formato publicado, y su oferta es de aficionado; CDISC publica
`rules + test data` bajo MIT y tiene el ecosistema permisivo más maduro del sector sanitario
después de OHDSI. Esto **confirma en una segunda industria el patrón P29 del pase financiero
(«el fixture es el entregable»)**: allí se derivó del capital regulatorio, aquí aparece solo,
en salud, por una vía independiente. Deja de ser una observación y pasa a ser ley transversal.

### Agentes y herramientas agénticas del plano — verificados uno por uno

Licencia **abierta por bytes**; existencia por `git ls-remote`; ★/push por `search/repositories`.

| Agente / herramienta | Licencia (por bytes) | ★ | Último push | Qué hace y por qué está aquí |
|---|---|---|---|---|
| [cdisc-org/cdisc-rules-engine](https://github.com/cdisc-org/cdisc-rules-engine) | **MIT** (`LICENSE`) | 126★/50f | **2026-11-25** | CORE: el motor de reglas de conformidad de CDISC. Tag `v1.0.0` confirmado por `ls-remote --tags`. **El oráculo ejecutable del plano.** Push el día del pase |
| [cdisc-org/cdisc-open-rules](https://github.com/cdisc-org/cdisc-open-rules) | **MIT** (`LICENSE`) | 12★ | **2026-11-25** | Reglas **y datos de prueba** procesables por CORE. 12★ no mide nada: es la clave de respuestas |
| [ericporres/trialthread](https://github.com/ericporres/trialthread) | **Apache-2.0** (`LICENSE`) | 8★ | 2026-11-22 | Agente que lee los criterios de elegibilidad y explica cada match; no almacena datos de paciente |
| [cbib/TrialMatchAI](https://github.com/cbib/TrialMatchAI) | **MIT** (`LICENSE`) | 43★ | 2026-11-20 | Emparejamiento paciente-ensayo con LLM abiertos, despliegue local (*Nat Commun* 2026). GitHub lo marcaba `NOASSERTION` |
| [ncbi-nlp/TrialGPT](https://github.com/ncbi-nlp/TrialGPT) | **Dominio público** (NCBI Public Domain Notice) | 185★ | 2025-01-24 | Recuperación + puntuación de elegibilidad del NIH/NCBI. **Obra del Gobierno de EE.UU.: no es copyrightable.** Parado 22 meses |
| [PrashantRGore/icsr-multi-agent-pipeline](https://github.com/PrashantRGore/icsr-multi-agent-pipeline) | **MIT** (`LICENSE`) | 1★ | 2026-10-29 | Pipeline ICSR con LangGraph + Ollama, export E2B(R3), humano en el bucle. **Único permisivo y activo de farmacovigilancia — y tiene 1★** |
| [WeDoCareGlobal-CC/pharma-intelligence-os](https://github.com/WeDoCareGlobal-CC/pharma-intelligence-os) | **Apache-2.0** (`LICENSE`) | 0★ | 2026-10-15 | Workspace de revisión ICSR, E2B(R3), PRR/ROR, borradores PSUR/PBRER |
| [ai-summer2025/clinical-trial-scout-agent](https://github.com/ai-summer2025/clinical-trial-scout-agent) | **MIT** (`LICENSE`) | 0★ | 2026-10-28 | Pipeline de 5 agentes sobre la API v2 de ClinicalTrials.gov. Sin APIs de pago |

Ocho filas reales, verificadas. No se rellena a diez.

### ⛔ Capa de corrección — la trampa de licencia más grave que esta KB ha encontrado

**[dfci/matchminer-ai-inference](https://github.com/dfci/matchminer-ai-inference) — 29★, push
2026-11-20, licencia `CC BY-NC-ND 4.0`. NO ADOPTABLE.**

La contradicción es documental y está en el propio repositorio:

- El **título del paper** es *«MatchMiner-AI: An Open-Source Solution for Cancer Clinical Trial Matching»* (arXiv 2412.17228).
- El **README** afirma literalmente: *«MatchMiner-AI is **open source and uses open-weight models**»*.
- El **LICENSE**, abierto por bytes, dice: `Attribution-NonCommercial-NoDerivatives 4.0 International`.

`NonCommercial` **y** `NoDerivatives` a la vez: Globant no puede usarlo en una entrega de
cliente ni modificarlo. Es el primer caso medido en esta KB en que el proyecto **se
autodescribe como open source en su propio README** y la licencia lo desmiente. Regla que
sale de aquí: *la palabra «open source» en el README y en el título del paper no es un canal
de licencia; el único canal es el fichero.*

**El resto de la familia MatchMiner, medida:**

| Repo | ★ | Licencia (por bytes) | Estado real |
|---|---|---|---|
| [dfci/matchminer](https://github.com/dfci/matchminer) | 54★ | **ninguna** | **Contiene 4 ficheros y ningún código.** `master` sólo aloja el README de portada; el sitio está en la rama `site`. Las 54★ miden una web |
| [dfci/matchminer-ai-inference](https://github.com/dfci/matchminer-ai-inference) | 29★ | **CC BY-NC-ND 4.0** | No adoptable (NC + ND) |
| [dfci/matchminer-ui](https://github.com/dfci/matchminer-ui) | 9★ | **AGPL-3.0** | Copyleft de red |
| [dfci/matchminer-api](https://github.com/dfci/matchminer-api) | 22★ | **ninguna** (ausencia **medida**: `README.md` responde 200) | Parado desde 2023-12-05 |

El emparejador oncológico «open source» de referencia del sector **no tiene una sola pieza
adoptable**. Si un cliente lo nombra en un RFP, ésta es la respuesta, con los cuatro ficheros
de licencia abiertos.

**[ai-summer2025/clinical-trial-matcher-agent](https://github.com/ai-summer2025/clinical-trial-matcher-agent)** — 0★, sin fichero de licencia (ausencia medida). No adoptable aunque el README prometa informe «listo para médico».

### El contador de agentes verticales — séptima medición consecutiva, y sigue clavado

Medición del hueco agéntico sobre el plano de sumisión, con el canal de precisión:

| Consulta | Repos |
|---|---|
| `org:pharmaverse` + `org:atorus-research` + `org:cdisc-org` (substrato) | **176** |
| `SDTM agent LLM` | **4** |
| `ADaM automation LLM` | **2** |

176 repos de substrato permisivo debajo; **2 repos** de automatización agéntica encima del
entregable que la FDA exige. Séptima medición consecutiva del mismo patrón en esta KB
(FHIR, imagen, OMOP, y ahora sumisión regulatoria). Ya no es un hueco: es la forma del sector.

---

## Pase 2026-11-25 (c10) — el plano del dispositivo y la monitorización remota: donde los pacientes construyeron el despliegue y lo licenciaron en copyleft

Cuarto pase del día. **Plano nuevo, y el que más contradice a los nueve anteriores.** Esta KB
llevaba siete mediciones diciendo lo mismo con distinta ropa: *substrato enorme debajo, capa
agéntica vacía encima*. El plano del dispositivo —monitorización remota, señal fisiológica,
administración automatizada de insulina— **invierte el instrumento de medida**, y por eso había
pasado inadvertido en nueve pases: su tamaño no está en las estrellas, está en los **forks**.

### El hallazgo central: el repo sanitario más desplegado del mundo tiene 25 forks por estrella, y es AGPL

| Repo | Licencia (por bytes) | ★ | Forks | Forks/★ | Push |
|---|---|---|---|---|---|
| [`nightscout/cgm-remote-monitor`](https://github.com/nightscout/cgm-remote-monitor) | AGPL-3.0 (`LICENSE`, 34.521 B) | 2.867 | **73.399** | **25,6** | 2026-11-25 |
| [`LoopKit/LoopWorkspace`](https://github.com/LoopKit/LoopWorkspace) | **SIN FICHERO DE LICENCIA** (verificado por clon) | 316 | **8.859** | **28,0** | 2026-11-24 |
| [`nightscout/AndroidAPS`](https://github.com/nightscout/AndroidAPS) | AGPL-3.0 (`LICENSE.txt`, 34.520 B) | 1.264 | 7.639 | 6,0 | 2026-11-25 |
| [`NightscoutFoundation/xDrip`](https://github.com/NightscoutFoundation/xDrip) | GPL-3.0 (`LICENSE`, 35.147 B) | 1.828 | 1.331 | 0,7 | 2026-11-25 |

73.399 forks es, con mucha diferencia, **la cifra más alta de toda esta KB** — OHDSI, MONAI,
synthea y medplum juntos no se acercan. Y no son contribuyentes: son **pacientes desplegando su
propia instancia**. El fork *es* la instalación. Lo mismo en `LoopWorkspace`, que se forkea para
compilar la app propia en GitHub Actions.

**Consecuencia inmediata y no negociable para una propuesta:** el plano sanitario con más
despliegue real del mundo open source es también **el que menos se puede empaquetar en un
producto propietario**. AGPL-3.0 alcanza el límite de red: ofrecer Nightscout como servicio
obliga a publicar la fuente de lo que se ofrece. No es un detalle de cumplimiento, decide la
arquitectura antes de la primera línea de código (ver `compose/patterns.md` P25).

### Y la parte permisiva existe — pero es el ALGORITMO, no la plataforma

Aquí está la inversión fina, y es lo que hace vendible el plano. En los nueve pases anteriores la
capa permisiva era el **formato** y la capa vacía era el **juicio**. Aquí el juicio clínico
—cuánta insulina administrar— **sí es permisivo**, y lo que es copyleft es la **fontanería**:

| Repo | Capa | Licencia (por bytes) | ★ / forks | Push |
|---|---|---|---|---|
| [`openaps/oref0`](https://github.com/openaps/oref0) | Algoritmo de referencia (dosificación) | MIT (`LICENSE.txt`, 1.092 B) | 487 / 406 | 2026-11-23 |
| [`openaps/openaps`](https://github.com/openaps/openaps) | Toolkit original del lazo cerrado | MIT (`LICENSE.txt`, 1.093 B) | 478 / 176 | 2026-11-10 |
| [`LoopKit/LoopKit`](https://github.com/LoopKit/LoopKit) | Framework de dispositivo y dosificación (iOS) | MIT (`LICENSE`, 1.117 B) | 423 / 429 | 2026-11-24 |
| [`LoopKit/Loop`](https://github.com/LoopKit/Loop) | App de lazo cerrado | **MIT con excepciones** (`LICENSE.md`, 15.235 B) | 1.761 / 1.458 | 2026-11-25 |
| [`tidepool-org/platform`](https://github.com/tidepool-org/platform) | Plataforma de datos de diabetes (servidor) | BSD-2-Clause (`LICENSE`, 1.295 B) | 31 / 16 | 2026-11-25 |
| [`tidepool-org/uploader`](https://github.com/tidepool-org/uploader) | Subida desde dispositivos (bombas, medidores) | BSD-2-Clause (`LICENSE`, 1.299 B) | 128 / 84 | 2026-11-24 |
| [`tidepool-org/blip`](https://github.com/tidepool-org/blip) | Visualización clínica de datos de diabetes | BSD-2-Clause (`LICENSE`, 1.295 B) | 112 / 52 | 2026-11-25 |

**La frontera de licencia de este plano no es tecnológica, es arquitectónica:** permisiva en el
algoritmo y en el dato, copyleft en la plataforma de monitorización que el paciente despliega.
Un *engagement* se construye sobre `oref0`/`LoopKit`/Tidepool y **no forkea Nightscout**.

### ⚠️ `LoopKit/Loop` es MIT **con excepciones**, y la excepción es de activos

`LICENSE.md` pesa 15.235 B para una licencia MIT de 1 KB. La línea 1 lo dice: *«Loop is released
under the MIT license (MIT) — With exceptions for frameworks and graphics, noted below»*, y el
fichero enumera 8 frameworks embebidos y los gráficos. GitHub lo reporta como `NOASSERTION`
precisamente por eso. Una puerta de licencia que pregunte *«¿es MIT?»* contesta «sí» y **se salta
la reserva sobre los gráficos**, que es justo lo que un derivado comercial redistribuye.

### Agentes y herramientas agénticas del plano — verificados uno por uno

Lo que hay es pequeño, y por primera vez en esta KB **lo mejor del plano agéntico es un framework
académico mantenido**, no una plantilla de proveedor:

| Repo | Qué hace | Licencia (por bytes) | ★ / forks | Push |
|---|---|---|---|---|
| [`StanfordBDHG/HealthGPT`](https://github.com/StanfordBDHG/HealthGPT) | Consulta en lenguaje natural sobre datos de HealthKit (wearable del paciente) | MIT (`LICENSE.md`, 1.122 B) | 1.964 / 181 | 2026-07-14 |
| [`StanfordSpezi/SpeziLLM`](https://github.com/StanfordSpezi/SpeziLLM) | Módulo LLM (local y remoto) para apps de salud digital | MIT (`LICENSE.md`, 1.121 B) | 290 / 46 | 2026-11-21 |
| [`StanfordSpezi/Spezi`](https://github.com/StanfordSpezi/Spezi) | Framework de apps de salud digital: consentimiento, cuestionarios, dispositivos | MIT (`LICENSE.md`, 1.121 B) | 261 / 27 | 2026-11-22 |
| [`AminAlam/meddev-agent-skills`](https://github.com/AminAlam/meddev-agent-skills) | *Skills* agénticas para trabajo regulatorio de dispositivo médico | MIT (`LICENSE`, 1.066 B) | 44 / 8 | — |
| [`Infinite-Labs-AI/hermes-health-apollo`](https://github.com/Infinite-Labs-AI/hermes-health-apollo) | Agente local-first sobre wearable y calendario | MIT (`LICENSE`, 1.072 B) | 29 / 4 | — |
| [`gustmd0121/ECG-Agent`](https://github.com/gustmd0121/ECG-Agent) | Agente de interpretación de ECG | MIT (`LICENSE`, 1.072 B) | 12 / 1 | — |
| [`bryan-basg/samd-starter-kit`](https://github.com/bryan-basg/samd-starter-kit) | Andamiaje de proyecto SaMD (software como dispositivo médico) | MIT (`LICENSE`, 1.085 B) | 8 / 3 | — |

Siete filas reales. **Las cuatro últimas están entre 8 y 44 estrellas**: se citan porque son
permisivas y existen, no porque estén maduras. `Spezi` + `SpeziLLM` es lo único del bloque con
mantenimiento continuo medido (push esta semana) y respaldo institucional (Stanford).

### ⛔ Capa de corrección — y rompe una racha que esta KB venía acumulando

| Repo | Lo que dice el metadato | Lo que dicen los bytes | Veredicto |
|---|---|---|---|
| [`thinkwee/HiMe`](https://github.com/thinkwee/HiMe) | `NOASSERTION` (74★/11f) | `LICENSE` 4.649 B, línea 3: **`# PolyForm Noncommercial License 1.0.0`**, 5 apariciones de *noncommercial* | **NO ADOPTABLE.** Agente personal de salud, no usable en trabajo de cliente |
| [`elkimek/get-based`](https://github.com/elkimek/get-based) | AGPL-3.0 (168★/34f) | `LICENSE` 34.523 B, línea 1 `GNU AFFERO GENERAL PUBLIC LICENSE` | Copyleft de red. Real y activo, **no incorporable** |
| [`openregulatory/templates`](https://github.com/openregulatory/templates) | `NOASSERTION` (201★/60f, push 2026-10-21) | `LICENSE.md` 19.089 B, título: **`Creative Commons Attribution-NonCommercial-ShareAlike 4.0`** | **NO ADOPTABLE EN ENTREGA DE PAGO.** Ver el aviso de abajo: es la trampa comercial del pase |

**`NOASSERTION` → permisiva genuina ya NO es 10 de 10.** Esta KB venía anotando la racha desde el
ciclo 5 y el pase c8 la cerró en «10 de 10». `thinkwee/HiMe` es el **primer contraejemplo
medido**: `NOASSERTION` que esconde una licencia **no comercial** (PolyForm NC 1.0.0, que no es
OSI). La regla operativa no cambia —*abrir el fichero*— pero la **inferencia optimista sí**: de
`NOASSERTION` no se sigue «permisiva», se sigue «sin medir». Corregido aquí contra la nota de c8.

### ⚠️ La trampa comercial del pase: las plantillas de QMS regulatorio son NonCommercial

Es la trampa más caramente relevante para una consultora, porque es **exactamente el repo al que
uno alargaría la mano**. `openregulatory/templates` (201★, activo) ofrece plantillas de ISO 13485
/ MDR / expediente técnico: justo el entregable de un proyecto de dispositivo. Y es
**CC-BY-NC-SA-4.0**: *NonCommercial*. Usarlas en un proyecto facturado incumple la licencia.

La alternativa permisiva existe pero está parada: [`innolitics/rdm`](https://github.com/innolitics/rdm)
(*Regulatory Documentation Manager*, MIT verificado `LICENSE.txt` 1.060 B, 145★/36f) **sin push
desde 2022-10-27**. Es decir: en documentación regulatoria de dispositivo, **lo permisivo está
abandonado y lo mantenido es no comercial**. Hueco (h), nuevo y colocable.

### El contador de agentes verticales — octava medición consecutiva, y sigue en 1

La consulta de referencia del ciclo 5, repetida sin cambios:

| Consulta (canal `search/repositories`) | c5 | c6 | c10 (hoy) |
|---|---|---|---|
| `healthcare agent created:>2026-08-01 stars:>=50` | 1 | 1 | **1** |

Y la medición propia de este plano, con consultas cortas (la lección de c6: acortar antes de
concluir que no hay nada):

| Consulta | Resultados | Lo más estrellado y su realidad |
|---|---|---|
| `vital signs agent` | 32 | El primero es un falso positivo (`jettbrains/-L-`, GPL-3.0); los tres siguientes genuinos tienen **0 estrellas** |
| `ECG agent` | 80 | 27★ · 12★ · 5★ · 4★ · 4★ — la categoría entera en dígitos simples |
| `medical device agent` | 130 | Primero falso positivo (volcado de referencias, 79★); el mejor real es `meddev-agent-skills` 44★ |
| `telemonitoring AI` | 9 | Nada con tracción |
| `biosignal LLM` | 14 | Nada con tracción |
| `CGM LLM` | 26 | Nada con tracción |

**Octava medición consecutiva**, ahora en el plano con más despliegue del sector: 1.049 repos bajo
`remote patient monitoring` y una capa agéntica cuyo techo real son 44 estrellas. El patrón
atravesó FHIR, imagen, OMOP, sumisión regulatoria y dispositivo. Ya no se reporta como hueco: es
la forma del sector, y la oportunidad está en construir la capa, no en buscarla.

---

## Pase 2026-11-25 (c11) — el plano del medicamento: tres sub-planos, tres resultados, y el discriminante **no** es el regulador

Quinto pase del día, plano nuevo: **medicación — farmacovigilancia, interacción fármaco-fármaco y
farmacogenómica**. Este plano permite algo que los diez pases anteriores no permitían: una
**comparación controlada de tres vías** dentro de la misma industria, el mismo año y la misma
categoría de tarea («juicio clínico»). Los tres resultados son distintos, y el resultado refuta la
lectura ingenua de **P12**.

### El hallazgo central: la presión regulatoria NO predice la oferta permisiva; la licencia del CONTENIDO sí

| Sub-plano | Presión regulatoria | Licencia del contenido de conocimiento | Oferta permisiva medida |
|---|---|---|---|
| **Farmacovigilancia** (ICSR, señal) | **MÁXIMA** — notificación legalmente obligatoria en todas las jurisdicciones | **MedDRA de pago** (escala por ingresos) + **WHODrug** por suscripción de la UMC | `pharmacovigilance stars:>=10` → **12 repos en todo el mundo**; el multiagente académico de referencia **sin fichero de licencia**; el único sistema E2B completo es **GPL-3.0** |
| **Interacción fármaco-fármaco clínica** | MEDIA — es CDS, no hay mandato | **Propietaria** (First Databank, Multum); DrugBank es **CC BY-NC 4.0** | `clinical decision support drug` → 191 repos, y **los diez primeros por estrellas suman ~42★** (máximo 8★), casi ninguno con licencia. El único institucional es `HL7/PDDI-CDS` con **5★** |
| **Farmacogenómica** (dosificación) | **NINGUNA** — el CPIC no es un regulador | **CPIC = CC0 1.0**, dedicación al dominio público (verificado en bytes) | **SANO Y VIVO**: `PharmCAT` MPL-2.0 203★/68f, `pypgx` MIT 99★ con push del 24-nov, `PharMe` MIT del Hasso-Plattner |

Leído en vertical: **el sub-plano con más obligación legal es el que tiene menos software abierto, y
el que no tiene ninguna obligación es el único con herramientas permisivas mantenidas.** La
correlación con la presión regulatoria es *inversa*. La correlación con la licencia del contenido es
perfecta.

**P12 no se cae, se corrige.** La secuencia que el ciclo 6 observó («el regulador declara → el
organismo publica una IG → aparecen implementaciones permisivas») describía la **capa de formato**.
Para la **capa de juicio** hace falta una segunda condición que el ciclo 6 no aisló: *que el cuerpo
de conocimiento con el que se juzga sea libre*. El regulador crea la **obligación**; la licencia del
contenido decide si el código abierto puede **cumplirla**.

Y la ley del pase financiero («el open source permisivo sigue al formato de fichero, no a la
decisión») **se confirma aquí por tercera vez y en el caso más difícil**: el formato ICSR *sí* tiene
implementación abierta —`FreeVigilance/E2B` (GPL-3.0, refs=82) y `Pharma-Intelligence-Os`
(Apache-2.0)— mientras el juicio que viaja dentro de ese formato no tiene ninguna. El sobre está
resuelto; la carta no.

### Consecuencia comercial, dicha sin adornos

Donde la obligación es máxima y el contenido está gravado hay **a la vez** el hueco más grande y la
mayor disposición a pagar — es decir, es donde está el margen. Pero **el entregable no puede
prometerse «todo open source»**, por la misma razón que el ciclo 6 estableció para el CPT. Lo que se
vende es la **capa de juicio sobre contenido que el cliente ya licencia**: un laboratorio que notifica
ya paga MedDRA. Lo que Globant aporta es el triaje, la deduplicación, la narrativa y la trazabilidad,
y el entregable con margen es **la biblioteca de reglas y el banco de pruebas**, que el cliente posee.

En farmacogenómica la postura es la opuesta y hay que decirlo igual de claro: **ahí sí se puede
prometer una pila abierta de punta a punta**, porque el contenido es CC0 y el motor es MPL-2.0.
Es el único sub-plano de toda esta KB del que puede decirse eso sobre una tarea de juicio clínico.

### Agentes y herramientas agénticas del plano — verificados uno por uno

Existencia por `git ls-remote`; licencia por bytes del fichero real (puerta v7, ver P32); ★/forks y
`push` por `search/repositories` en la misma llamada.

| Repo | Licencia (bytes) | ★/forks | Push | Qué es, y por qué está aquí |
|---|---|---|---|---|
| [`snap-stanford/Biomni`](https://github.com/snap-stanford/Biomni) | Apache-2.0 (11.357 B) | 4.111★/751f | 2026-11-23 | Agente biomédico general de Stanford. Ya estaba en la KB; **re-medido este pase** y sigue activo. Razón 5,5 |
| [`ChazY11/medradar`](https://github.com/ChazY11/medradar) | **MIT** (1.328 B) | 428★/27f | **2026-11-25** | 375.378 eventos de **seis fuentes públicas gratuitas**, cobertura 1966–2026, 1.157 pruebas *offline*. Investigación de evidencia sobre cambio tecnológico médico. `search` lo daba como `NOASSERTION`; los bytes dicen MIT |
| [`Shakesbeery/vigipy`](https://github.com/Shakesbeery/vigipy) | MIT (1.068 B) | 20★/6f | 2026-10-21 | **El motor de desproporcionalidad permisivo del plano** (PRR, ROR, BCPNN, GPS) en Python. Pequeño, pero es el único mantenido con licencia usable |
| [`KarelDO/BioDEX`](https://github.com/KarelDO/BioDEX) | MIT (1.075 B) | 69★/8f | 2024-01-29 | **El oráculo**: extracción de ICSR contra informes **reales** de la FDA. Parado desde 2024, pero un banco de pruebas envejece mucho mejor que una plataforma (ver P22) |
| [`pryndor/Lixplore_cli`](https://github.com/pryndor/Lixplore_cli) | MIT (1.078 B) | 36★/7f | 2026-10-25 | Exploración de literatura por CLI: la pata de cribado bibliográfico, que es obligación legal en PV |
| [`JamesANZ/medical-mcp`](https://github.com/JamesANZ/medical-mcp) | MIT (1.071 B) | 122★/39f | 2026-10-15 | MCP sobre RxNorm y fuentes de medicamento. **Razón 3,1** → se despliega, no sólo se estrella |
| [`cyanheads/openfda-mcp-server`](https://github.com/cyanheads/openfda-mcp-server) | Apache-2.0 (10.772 B) | 6★/3f | 2026-11-23 | MCP sobre openFDA. Diminuto en estrellas y **activo**; refs=112 |
| [`alvinhenrick/medirag`](https://github.com/alvinhenrick/medirag) | MIT (1.070 B) | 9★/6f | 2026-05-28 | RAG sobre etiquetado de medicamento (DailyMed). Razón 1,5 |
| [`forever-healthy/evidence-mcp`](https://github.com/forever-healthy/evidence-mcp) | MIT (1.090 B) | 7★/0f | **2026-11-25** | MCP de evidencia de la Forever Healthy Foundation. Push de hoy |
| [`WeDoCareGlobal/Pharma-Intelligence-Os-Production`](https://github.com/WeDoCareGlobal/Pharma-Intelligence-Os-Production) | Apache-2.0 (11.359 B) | **0★/1f** | 2026-11-24 | Revisión de ICSR con verificación humana, E2B(R3), gestión de señal PRR/ROR y borradores de PSUR. **Se tabula con su cifra real: cero estrellas, cuatro días de vida.** Es el único proyecto permisivo que cubre el flujo completo; no es todavía una dependencia, es una lectura de diseño |

### La única pila agéntica de juicio clínico que puede entregarse 100 % abierta

| Repo | Licencia (bytes) | ★/forks | Push | Papel |
|---|---|---|---|---|
| [`PharmGKB/PharmCAT`](https://github.com/PharmGKB/PharmCAT) | **MPL-2.0** (16.725 B, banda canónica) | 203★/68f | 2026-10-17 | Anotador clínico farmacogenómico: VCF → diplotipos → recomendación CPIC. **El motor** |
| [`cpicpgx/cpic-data`](https://github.com/cpicpgx/cpic-data) | **CC0 1.0** declarado en `LICENSE.md` (3.234 B) | 34★/2f | **2026-11-19** | **El contenido**, y es dominio público. Pide atribución, no la exige como condición |
| [`sbslee/pypgx`](https://github.com/sbslee/pypgx) | MIT (1.080 B) | 99★/22f | **2026-11-24** | Llamada de genotipos farmacogenéticos en Python. Activo |
| [`PharmGKB/vcf-parser`](https://github.com/PharmGKB/vcf-parser) | MPL-2.0 | 9★/1f | 2026-08-28 | Pieza de entrada de PharmCAT |
| [`hpi-dhc/PharMe`](https://github.com/hpi-dhc/PharMe) | MIT (1.082 B) | 23★/9f | 2025-08-20 | **EMEA**: app paciente-clínico del Hasso-Plattner-Institut sobre recomendaciones CPIC. refs=298 |
| [`dgidb/dgidb`](https://github.com/dgidb/dgidb) | MIT (1.101 B) | 97★/32f | 2025-08-12 | Interacciones fármaco-gen (Griffith Lab). Razón 3,0 |

**MPL-2.0 es copyleft débil por fichero**: PharmCAT se puede invocar y distribuir junto a código
propietario; lo que no se puede es modificar sus ficheros y cerrarlos. Para una integración es una
restricción sin consecuencia práctica, y hay que decirlo porque «copyleft» suele leerse como bloqueo.

### ⛔ Capa de corrección — seis filas que NO son adoptables, y dos son las que un buscador pondría primero

| Repo | Lo que parece | Lo que miden los bytes |
|---|---|---|
| [`jihyechoi77/malade`](https://github.com/jihyechoi77/malade) | El sistema **multiagente académico de farmacovigilancia** más citado (LLM + openFDA) | **SIN fichero de licencia.** refs=4, 15 variantes de nombre × 2 ramas, todas 404. Sin push desde 2025-02-19. El trabajo de referencia del plano **no se puede usar** |
| [`DavidOsherdiagnostica/israel-drugs-mcp-server`](https://github.com/DavidOsherdiagnostica/israel-drugs-mcp-server) | `NOASSERTION` en la API; 19★/10f, el único activo israelí del plano | **CC BY-NC-SA 4.0** (3.690 B, título en la línea 1): **No Comercial + ShareAlike sobre SOFTWARE**, no sobre datos. Caso raro y bloqueo total en trabajo de cliente |
| [`openpharma-org/drugbank-mcp-server`](https://github.com/openpharma-org/drugbank-mcp-server) | MCP listo sobre DrugBank, 11★/4f | **Doble bloqueo**: sin fichero de licencia **y** el contenido que envuelve es **CC BY-NC 4.0** (comercial requiere licencia pagada de DrugBank) |
| [`PacificBiosciences/pb-StarPhase`](https://github.com/PacificBiosciences/pb-StarPhase) | `NOASSERTION`, 27★/6f, llamador PGx de PacBio | **EULA propietario**: «Pacific Biosciences Software License Agreement» (8.568 B). **Segunda** confirmación de la regla (10) de P28: de `NOASSERTION` se sigue «sin medir», nunca «permisiva» |
| [`HHS/pillbox-engine`](https://github.com/HHS/pillbox-engine) | Repo del **Departamento de Salud de EE.UU.**, refs=64 | **SIN licencia** tras 15 nombres × 2 ramas. Instancia norteamericana del patrón del NHS: agencia nacional que publica sin licenciar |
| [`fabkury/ndc_map`](https://github.com/fabkury/ndc_map) · [`open-pgx/openpgx`](https://github.com/open-pgx/openpgx) | Mapeos NDC y PGx con 104★ y 13★ | Ambos **sin fichero de licencia**; refs=2 cada uno |

### El contador de agentes verticales — novena medición consecutiva, y sigue clavado en 1

| Consulta | Resultado |
|---|---|
| `medication agent stars:>=10` | **total = 1** en todo el mundo, y es `yixinzhang98/otc_med_chat_agent` (199★/32f, **sin licencia**, sin push desde 2025-07-29) |
| `pharmacovigilance stars:>=10` | **total = 12**, el primero parado desde enero de 2024 |
| `WHODrug` | **total = 5** repos en todo GitHub |
| `deprescribing` | **total = 30** |

Novena medición consecutiva (legal, financial, healthcare c5–c11) de que **no hay un boom de agentes
verticales permisivos**. Lo que añade un pase es **deuda de descubrimiento**, no crecimiento del sector.
