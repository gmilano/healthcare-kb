---
industry: healthcare
region: Global
updated: 2026-11-22
---

# 📈 Agentes trending — Healthcare

> **Archivo append-only.** La sección más reciente va arriba; el historial se conserva debajo.
> Reescribir este archivo destruiría la tendencia que existe para registrar.

## 2026-11-22 — la autorización previa cruza de «juicio» a «formato»

El pase anterior (2026-11-21) dejó anotado el hueco más grande de esta KB: **no existe
plataforma agéntica permisiva de ciclo de ingresos ni de denegación de siniestros**, la mayor
partida de presupuesto de IA sanitaria en EE. UU. Este pase fue a medir ese hueco y encontró
algo mejor que una confirmación: encontró **por qué** existe, y que ya se está cerrando por un
lado inesperado.

### Lo nuevo de la semana: Da Vinci y CQL, invisibles y forkeados

Lo que se mueve esta semana no es un agente: es la capa que convierte un juicio clínico en una
API. CMS-0057-F obliga a las aseguradoras a exponer una **API de autorización previa el 1 de
enero de 2027**, y las implementaciones de referencia llevan meses publicadas en Apache-2.0.

| Nombre | Licencia | Qué aporta | Stars/Forks | Push | Región |
|--------|----------|------------|-------------|------|--------|
| [cqframework/clinical-reasoning](https://github.com/cqframework/clinical-reasoning) | Apache-2.0 | Motor CQL: el juicio clínico escrito como especificación ejecutable | 52★/46f | 2026-11 | North America |
| [HL7-DaVinci/CRD](https://github.com/HL7-DaVinci/CRD) | Apache-2.0 | Descubrimiento de requisitos de cobertura en el momento de la orden | 45★/24f | 2026-07 | North America |
| [HL7-DaVinci/prior-auth](https://github.com/HL7-DaVinci/prior-auth) | Apache-2.0 | Implementación de referencia de Da Vinci PAS | 38★/24f | 2026-07 | North America |
| [HL7-DaVinci/dtr](https://github.com/HL7-DaVinci/dtr) | Apache-2.0 | Plantillas y reglas de documentación exigida | 23★/18f | 2026-07 | North America |
| [genomoncology/biomcp](https://github.com/genomoncology/biomcp) | MIT | MCP biomédico: ensayos clínicos, variantes genómicas y literatura | 683 | 2026-11 | North America |
| [hastimal/gemini-healthcare-agentic-platform](https://github.com/hastimal/gemini-healthcare-agentic-platform) | Apache-2.0 | Búsqueda sanitaria agéntica con *grounding* y cita obligatoria; forks ≈ estrellas | 39★/36f | 2026-11 | Global |
| [ChristianHinge/dicom-mcp](https://github.com/ChristianHinge/dicom-mcp) | MIT | Servidor MCP sobre DICOM: consulta de estudios de imagen por un agente | 108 | 2026-10 | EMEA |
| [the-momentum/fhir-mcp-server](https://github.com/the-momentum/fhir-mcp-server) | MIT | Segundo servidor MCP↔FHIR independiente, alternativa a wso2 | 102★/20f | 2025-10 | EMEA |
| [JuneYaooo/open-medical](https://github.com/JuneYaooo/open-medical) | MIT | Agente de escritorio local-first para la consulta médica | 21★/7f | 2026-11 | APAC |

### El contador de agentes verticales no se mueve — cuarta medición

| Consulta | Ciclo 5 (2026-11-21) | Hoy (2026-11-22) |
|----------|----------------------|------------------|
| `healthcare agent created:>2026-08-01 stars:>=50` | 1 | **1** |
| `FHIR mcp stars:>=30` | 11 | **11** |
| `clinical AI agent created:>2026-06-01 stars:>=100` | 0 | no re-medida |

Y el único resultado de la primera consulta es
`muhammadusamakhan911-bit/fabric-mlv-agent-healthcare-starter`: 149 estrellas, **1 fork**, 16
días de vida, una plantilla de demo. **El único indicio de crecimiento del sector en casi
cuatro meses no sobrevive a mirarle los forks.** Lo que un pase añade sigue siendo deuda de
descubrimiento, no crecimiento sectorial.

### Advertencias de este pase

- **`FreedomIntelligence/OpenClaw-Medical-Skills`** aparece en listas de *trending* de
  noviembre con 3120★ y 424 forks: **no tiene fichero de licencia** y no recibe push desde el
  2026-07-21. No usar.
- **`xxPcy/PharmaLLM-Agent`** (205★, 5 forks) y
  **`mdexa-ai/mdexa-ai-native-database`** (201★ en 7 días, 11 forks, sin segundo push) tienen
  la firma de atención comprada o promocionada. El segundo tiene un concepto valioso
  —procedencia y licencia de los datasets que alimentan IA médica— pero no hay aún proyecto
  que respalde la cifra.
- **`soma-intelligence/open-health-sync`** (72★) y **`pacharanero/sct`** (32★) son **AGPL-3.0**
  (34523 B verificados): copyleft de red, fuera del perímetro entregable por defecto.

---

## 2026-11-21 — primer pase verificado; el remoto llevaba 112 días sin tocarse

Contexto: el último commit del remoto era del **2026-08-01**. Los ciclos 2, 3 y 4 de healthcare
(jul–ago 2026) hicieron trabajo que **nunca llegó a pushearse**, así que este es el primer
contenido verificado que entra al repositorio.

### Nuevo esta semana — la capa MCP↔FHIR

| Nombre | Licencia | Qué aporta | Stars | Push | Región |
|--------|----------|------------|-------|------|--------|
| [thetahealth/mirobody](https://github.com/thetahealth/mirobody) | Apache-2.0 | Registro de salud personal local-first consultable por agente vía MCP; el más votado de los hallazgos nuevos | 1633 | 2026-11-20 | Global |
| [healthchainai/HealthChain](https://github.com/healthchainai/HealthChain) | Apache-2.0 | Pipelines Python ↔ APIs FHIR vivas, salida por REST / CDS Hooks / CDA / MCP / LangChain | 232 | 2026-11-20 | Global |
| [healthymind-tech/Taiwan-Health-MCP](https://github.com/healthymind-tech/Taiwan-Health-MCP) | MIT | 73 herramientas: ICD-10-CM/PCS, SNOMED CT, LOINC, TFDA, validación FHIR R4 IG | 171 | 2026-11-18 | APAC |
| [wso2/fhir-mcp-server](https://github.com/wso2/fhir-mcp-server) | Apache-2.0 | MCP sobre FHIR con OAuth 2.0 completo contra Epic | 139 | 2026-11-06 | APAC |
| [Carer-Healthcare-AI/Hospilot](https://github.com/Carer-Healthcare-AI/Hospilot) | MIT | Operaciones hospitalarias agénticas sobre el FHIR de OpenEMR; humano aprueba cada paso consecuente | 18 | 2026-10-19 | Global |
| [Penn-RAIL/MARC-v1](https://github.com/Penn-RAIL/MARC-v1) | MIT | Framework multi-agente de razonamiento clínico (Penn RAIL) | 11 | 2026-08-14 | North America |

### Estructura del mercado, medida el 2026-11-21

`healthcare agent created:>2026-08-01 stars:>=50` → **total_count = 1** en todo el mundo.
`clinical AI agent created:>2026-06-01 stars:>=100` → **0**.
No hay boom de agentes nuevos: lo que esta KB añade es **deuda de descubrimiento**, no crecimiento
del sector. Mismo hallazgo estructural que midieron los pases de *financial* y *legal*.

### Capa de corrección — retiradas esta semana

Estas filas venían recomendadas por los ciclos 2–4 y **no sobrevivieron a la verificación**.
Se registran aquí, no se borran, porque borrarlas invita a readoptarlas.

| Retirada | Motivo medido |
|----------|---------------|
| `MDAgents` (dado como `MIT, ~2.5k★`) | **307★ y sin archivo de licencia**; último push 2024-11-10 |
| `CheXagent` (dado como `Apache-2.0, ~1.4k★`) | **239★ y CC-BY-NC-ND 4.0** — NonCommercial + NoDerivatives |
| `epfl-llm/meditron` (dado como `Apache-2.0, ~5.3k★`) | **el slug no existe**; el sucesor `EPFLiGHT/Meditron` tampoco tiene licencia |
| `BioMedArena` (dado como `Apache-2.0, ~960★`) | real: 30★, **MIT** |
| `MeDxAgent` (dado como `MIT, ~280★`) | real: 5★, **sin licencia** |
| `CareAgent (opencare.ai)` (dado como `Apache-2.0, ~350★`) | **no existe**: total_count = 0 |
| `microsoft/hi-ml` | MIT correcto pero **archivado** desde 2025-10-06 |

**La lección, para el próximo pase:** las estrellas de MDAgents *subían* entre ciclos
(2.1k → 2.3k → 2.5k) mientras el último push del repo seguía congelado en noviembre de 2024.
Un número que crece sobre un repo que no se mueve es la firma de un dato inventado.
Contrastar la cifra con la **fecha de último push** cuesta una llamada y detecta la fabricación.

---

# Historial

## 2026-07-02 — ingesta automática (sin filtro de relevancia)

> ⚠️ Conservado como historial. Esta tabla salió de una ingesta automática sin filtro: incluye
> repos de 0 estrellas, un diseño de esquemas MySQL, una bolsa de empleo y un runner de JavaScript,
> ninguno relacionado con agentes sanitarios. Varias licencias figuran como `?` o `NOASSERTION`.
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
