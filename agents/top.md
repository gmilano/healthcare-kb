---
industry: healthcare
region: Global
updated: 2026-11-21
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
