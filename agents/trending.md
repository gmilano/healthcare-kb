---
industry: healthcare
region: Global
updated: 2026-11-25
---

# 📈 Agentes trending — Healthcare

> **Archivo append-only.** La sección más reciente va arriba; el historial se conserva debajo.
> Reescribir este archivo destruiría la tendencia que existe para registrar.

## 2026-11-25 (c10) — el plano del dispositivo entra en la KB, y rompe la racha de `NOASSERTION`

Cuarto pase del día. Plano nuevo: **dispositivo, monitorización remota y señal fisiológica**. La
novedad de la semana no es un agente: es que **la capa de juicio clínico de este plano está en MIT**
—algo que no había ocurrido en nueve pases— y que el metadato de licencia de GitHub acaba de fallar
en la dirección contraria a la habitual.

### Nuevo esta semana: lo agéntico del plano, con licencia abierta por bytes

| Repo | Qué hace | Licencia (bytes) | ★ / forks | Push |
|---|---|---|---|---|
| [`StanfordBDHG/HealthGPT`](https://github.com/StanfordBDHG/HealthGPT) | Consulta en lenguaje natural de datos de HealthKit | MIT (1.122 B) | 1.964 / 181 | 2026-07-14 |
| [`StanfordSpezi/SpeziLLM`](https://github.com/StanfordSpezi/SpeziLLM) | Módulo LLM para apps de salud digital | MIT (1.121 B) | 290 / 46 | 2026-11-21 |
| [`StanfordSpezi/Spezi`](https://github.com/StanfordSpezi/Spezi) | Framework de app de salud digital con conexión a dispositivos | MIT (1.121 B) | 261 / 27 | 2026-11-22 |
| [`AminAlam/meddev-agent-skills`](https://github.com/AminAlam/meddev-agent-skills) | *Skills* agénticas de trabajo regulatorio de dispositivo | MIT (1.066 B) | 44 / 8 | — |
| [`Infinite-Labs-AI/hermes-health-apollo`](https://github.com/Infinite-Labs-AI/hermes-health-apollo) | Agente local-first sobre wearable y calendario | MIT (1.072 B) | 29 / 4 | — |
| [`gustmd0121/ECG-Agent`](https://github.com/gustmd0121/ECG-Agent) | Agente de interpretación de ECG | MIT (1.072 B) | 12 / 1 | — |
| [`bryan-basg/samd-starter-kit`](https://github.com/bryan-basg/samd-starter-kit) | Andamiaje de proyecto SaMD | MIT (1.085 B) | 8 / 3 | — |

Siete filas reales, y por primera vez **la mejor pieza permisiva de un plano es un framework
universitario mantenido** (Stanford, push esta semana) en vez de una plantilla de proveedor.

### ⛔ La corrección de la semana: `NOASSERTION` ya no es «10 de 10» permisiva

Esta KB venía anotando la racha desde el ciclo 5, y c8 la cerró en «10 de 10». **Primer
contraejemplo medido:**

| Repo | Metadato GitHub | Bytes del `LICENSE` | Veredicto |
|---|---|---|---|
| [`thinkwee/HiMe`](https://github.com/thinkwee/HiMe) | `NOASSERTION` | 4.649 B, línea 3: **`# PolyForm Noncommercial License 1.0.0`** (5 apariciones de *noncommercial*) | **NO ADOPTABLE** |
| [`LoopKit/Loop`](https://github.com/LoopKit/Loop) | `NOASSERTION` | 15.235 B: *«MIT license — With exceptions for frameworks and graphics»* | **Usable con reserva de activos** |
| [`openregulatory/templates`](https://github.com/openregulatory/templates) | `NOASSERTION` | 19.089 B, título **CC-BY-NC-SA-4.0** | **NO ADOPTABLE en entrega de pago** |

La regla operativa no cambia (*abrir el fichero*), pero **la inferencia optimista sí**: de
`NOASSERTION` no se sigue «permisiva», se sigue **«sin medir»**.

### Tendencia de método: la puerta de licencia de esta KB tenía un falso positivo

**La GPL-3.0 y la AGPL-3.0 contienen la palabra «noncommercial» una vez.** Una puerta que haga
`grep -i noncommercial` bloquea como no comercial a **todo repo GPL/AGPL**: en este pase, **5
falsos positivos** (`cgm-remote-monitor`, `AndroidAPS`, `xDrip`, `get-based`, los dos de
`codeforjapan`) frente a **2 positivos genuinos**. Discriminante: anclar en el título y exigir ≥2
apariciones. Corregido en P28.

### El contador de agentes verticales — octava medición

`healthcare agent created:>2026-08-01 stars:>=50` = **1** (igual que c5 y c6). En el plano propio:
`vital signs agent` = 32 repos con los genuinos del top a **0 estrellas**; `ECG agent` = 80 con
tops de 27★ · 12★ · 5★ · 4★ · 4★; `telemonitoring AI` = 9. Debajo, 1.049 repos de
`remote patient monitoring`.

### Advertencia de disciplina: un *slug* que venía de la memoria

Se buscó un framework de «agente conversacional de salud» recordado como `openCHA/openCHA`:
**`ls-remote` dice que no existe**, y `search` sólo devuelve repos sin relación. Venía de la
memoria, no de una búsqueda — el mismo error que el `ultibi` del pase financiero. **No se escribe.**

## 2026-11-25 (c9) — la investigación clínica entra en la KB, y su emparejador de referencia no es adoptable

Tercer pase del día. Plano nuevo: **investigación clínica**. Lo que trae esta semana no es un
agente nuevo, es una **corrección de licencia que afecta a un nombre que aparece en RFPs**.

### Nuevo esta semana: agentes del plano, con licencia abierta por bytes

| Repo | Licencia (fichero abierto) | ★ | Último push | Señal |
|---|---|---|---|---|
| [cdisc-org/cdisc-rules-engine](https://github.com/cdisc-org/cdisc-rules-engine) | MIT (`LICENSE`) | 126★/50f | **2026-11-25** | CORE. Tag `v1.0.0` confirmado por `ls-remote --tags`. Push el día del pase |
| [cdisc-org/cdisc-open-rules](https://github.com/cdisc-org/cdisc-open-rules) | MIT (`LICENSE`) | 12★ | **2026-11-25** | Reglas **+ datos de prueba**. La clave de respuestas del plano |
| [ericporres/trialthread](https://github.com/ericporres/trialthread) | Apache-2.0 (`LICENSE`) | 8★ | 2026-11-22 | Agente de elegibilidad que explica cada match; no persiste datos de paciente |
| [cbib/TrialMatchAI](https://github.com/cbib/TrialMatchAI) | MIT (`LICENSE`) | 43★ | 2026-11-20 | *Nat Commun* 2026, LLM abiertos, despliegue local. GitHub: `NOASSERTION` |
| [pipeworx-io/mcp-eu-ctis](https://github.com/pipeworx-io/mcp-eu-ctis) | MIT (`LICENSE`) | 0★ | 2026-11-09 | **MCP sobre el CTIS de la UE.** 0★ y es el único del plano regulatorio europeo |
| [PrashantRGore/icsr-multi-agent-pipeline](https://github.com/PrashantRGore/icsr-multi-agent-pipeline) | MIT (`LICENSE`) | 1★ | 2026-10-29 | Único permisivo y activo de farmacovigilancia, con 1★ |

### ⛔ La corrección de la semana: «MatchMiner-AI es open source» lo dice su README, y su licencia dice que no

[dfci/matchminer-ai-inference](https://github.com/dfci/matchminer-ai-inference) — 29★, push
2026-11-20 — lleva **`CC BY-NC-ND 4.0`**: *NonCommercial* **y** *NoDerivatives*. Y sin embargo:

- el paper se titula *«MatchMiner-AI: An Open-Source Solution for Cancer Clinical Trial Matching»*;
- el README dice *«MatchMiner-AI is open source and uses open-weight models»*.

Primera vez que esta KB mide un proyecto que **se autodeclara open source en su propio README**
con una licencia que prohíbe uso comercial y derivados. La familia completa:
`matchminer` 54★ **sin código** (4 ficheros; `master` sólo aloja el README de portada),
`matchminer-ui` **AGPL-3.0**, `matchminer-api` **sin licencia** (ausencia medida, `README.md`=200).
**Ninguna pieza adoptable.**

### Tendencia de método: diez falsos negativos de licencia en un pase, todos del mismo lenguaje

`R` es el lenguaje del ensayo clínico y su convención `License: MIT + file LICENSE` deja un
`LICENSE` de **dos líneas** (`YEAR:` / `COPYRIGHT HOLDER:`) sin texto legal. GitHub devuelve
`NOASSERTION` y un gate que grep-ea `LICENSE` concluye «sin licencia». Afectados y corregidos
este pase: `teal`, `rtables`, `cards`, `cardinal`, `logrx`, `metatools`, `xportr`, `metacore`,
`cdiscdata`, `coreval` — **todos permisivos de verdad**.


## 2026-11-25 (c8) — el uso secundario del dato entra en la KB, y su capa agéntica tiene dos repos

Segundo pase del día. El de la mañana abrió imagen y scribes; este abre **uso secundario del
dato sanitario** (investigación, evidencia de mundo real, salud poblacional) y mide que **la capa
agéntica encima está prácticamente vacía sobre el substrato con más despliegue del sector**.

### Nuevo esta semana: lo poco que hay encima de OMOP, con push reciente

| Repo | Licencia (fichero abierto) | ★/forks | Último push | Señal |
|---|---|---|---|---|
| [OHNLP/omop_mcp](https://github.com/OHNLP/omop_mcp) | Apache-2.0 (10566 B) | 44★/10f | 2026-05-11 | MCP sobre OMOP del grupo OHNLP (Mayo Clinic). **El mejor punto de partida del plano.** GitHub lo marcaba `NOASSERTION` |
| [OMOPHub/omophub-mcp](https://github.com/OMOPHub/omophub-mcp) | MIT (1069 B) | 7★/0f | **2026-11-24** | MCP de vocabulario OMOP, push de ayer |
| [Bayer-Group/ascent-epi-demo](https://github.com/Bayer-Group/ascent-epi-demo) | BSD-3-Clause (1491 B) | 2★/1f | **2026-11-23** | Epidemiología agéntica publicada por **una farmacéutica**. Las 2★ no miden nada: el dato es el emisor |
| [OHDSI/Strategus](https://github.com/OHDSI/Strategus) | Apache-2.0 (`DESCRIPTION`) | 13★/**16f** | **2026-11-24** | Razón **0,81** — más forks que estrellas. Orquestador de estudios en red, en uso |
| [OHDSI/CohortMethod](https://github.com/OHDSI/CohortMethod) | Apache-2.0 (`DESCRIPTION`) | 94★/69f | **2026-11-25** | Push de hoy. Estimación de efectos comparativos |

**El dato que lo convierte en tendencia y no en anécdota:** debajo de esas cinco filas hay
**398 repos en `org:OHDSI`** con razones ★/forks por debajo de 2 en bloque, y arriba
`omop agent stars:>=5` devuelve **2**. Es el patrón de imagen del pase de esta mañana, más
extremo, y con un calendario regulatorio europeo con fechas firmes detrás (`intel/market.md`).

### La trampa de este pase: `NONE` en GitHub ≠ sin licencia

Diez repos nucleares de OHDSI —`CommonDataModel` (1 103★), `PatientLevelPrediction`,
`DataQualityDashboard`, `Achilles`, `CohortMethod`, `DatabaseConnector`, `FeatureExtraction`,
`ETL-Synthea`, `Strategus`, `CirceR`— aparecen como **`NONE`** en el metadato y **los diez son
Apache-2.0 declarada en el `DESCRIPTION` de R**. Una puerta de licencia que sólo lea `LICENSE`
rechaza el stack HADES entero. **La puerta tiene que conocer el lenguaje**: R → `DESCRIPTION`,
Python → `pyproject.toml`, Java/Maven → `pom.xml`, Node → `package.json`. Patrón **P18**.

### Advertencias de nomenclatura: **eHDSI no es EHDS**

[Sundhedsdatastyrelsen/ehdsi](https://github.com/Sundhedsdatastyrelsen/ehdsi) (MIT, 1078 B, 7★/2f,
refs=400, push **2026-11-25**) es el **National Contact Point for eHealth de Dinamarca** para
**MyHealth@EU**: intercambio transfronterizo de datos de asistencia, es decir **uso primario**.
No tiene nada que ver con el **European Health Data Space (EHDS)**, el reglamento de **uso
secundario**. Se diferencian en una letra y son cosas distintas. Es además, medido, **el único
activo permisivo serio que aparece al buscar «EHDS»** — lo bueno del resultado no es EHDS.
Noveno caso registrado en esta KB de nombre/slug que no es lo que parece.

### NOASSERTION → permisiva genuina: **10 de 10**

Racha acumulada de la KB, ampliada hoy con `OHNLP/omop_mcp` (Apache-2.0), `broadinstitute/gatk`
(Apache-2.0, 10966 B), `samtools/samtools` (**MIT/Expat**), `samtools/htslib` (MIT/Expat con
excepción acotada en `cram/`), `galaxyproject/galaxy` (**MIT**, 1590 B — *no* Academic Free
License, como se repite a menudo) e `Illumina/hap.py` (BSD + MIT). **`NOASSERTION` es señal de
parser, no de licencia:** hay que abrir el fichero, y hasta ahora siempre ha sido permisiva.

### El contador de agentes verticales — sexta medición

```
healthcare agent created:>2026-08-01 stars:>=50   →   total = 1   (149★ / 1 fork)
```

## 2026-11-25 — los scribes ambientales son la primera categoría agéntica con oferta permisiva

### Nuevo esta semana: documentación ambiental abierta, con coste publicado

Es la primera vez en siete pases de healthcare que una categoría agéntica aparece con **varias
implementaciones permisivas, vivas y verificables a la vez**. Todas medidas el 2026-11-25:

| Agente | Licencia (fichero abierto) | ★/forks | Último push | Señal |
|---|---|---|---|---|
| [phairlab/berta-ai-scribe](https://github.com/phairlab/berta-ai-scribe) | Apache-2.0 (10726 B) | 31★/9f | 2026-10-14 | Backends de voz y de LLM **abstraídos** (WhisperX/Whisper/Parakeet/Transcribe · Ollama/vLLM/LM Studio). Artículo aceptado en JMIR Med Inform |
| [canvas-medical/canvas-hyperscribe](https://github.com/canvas-medical/canvas-hyperscribe) | MIT | 3★/**7f** | **2026-11-25** | Razón 0,43 y push de hoy: se usa, nadie lo estrella |
| [Pl4tt/OpenScribe](https://github.com/Pl4tt/OpenScribe) | MIT (1069 B) | invisible a `search` | `ls-remote` refs=2 | Ruta 100 % local (Whisper + Ollama) |
| [BirgerMoell/open-medical-scribe](https://github.com/BirgerMoell/open-medical-scribe) | MIT | 13★/2f | 2026-03-16 | Incluye modo de nota en sueco |
| [ClinicianFOCUS/FreeScribe](https://github.com/ClinicianFOCUS/FreeScribe) | ⚠️ **AGPL-3.0** (34522 B) | invisible a `search` | `ls-remote` refs=36 | **Copyleft de red.** Fuera de cualquier SaaS cerrado |

**El dato que convierte esto en tendencia:** los autores de Berta publican un coste operativo
**por debajo de 30 USD por médico y mes**, con sesión media de 7,6 minutos y 42 % de usuarios
personalizando alguna plantilla. Es la primera referencia de coste pública de la categoría, y
convierte «ambiental sí o no» en un build-vs-buy con números. ⚠️ Cifras de los autores.

### Orquestadores: el slug que circula en prensa no existe

[Azure-Samples/healthcare-agent-orchestrator](https://github.com/Azure-Samples/healthcare-agent-orchestrator)
(MIT, 217★/93f, push 2026-10-27) es el orquestador multi-agente de *tumor board* real.
`microsoft/healthcare-agent-orchestrator`, que es como lo nombran varias notas de prensa,
**da refs=0 en `ls-remote`: no existe**. Octavo caso registrado en la KB de un slug citado en
prensa que no resuelve. También nuevo y medido:
[microsoft/healthcareai-examples](https://github.com/microsoft/healthcareai-examples) (MIT,
204★/55f) y [ajhcs/healthcare-agents](https://github.com/ajhcs/healthcare-agents) (Apache-2.0,
55★/15f, push 2026-11-18).

### El contador de agentes verticales no se mueve — quinta medición consecutiva

```
healthcare agent created:>2026-08-01 stars:>=50   →   total = 1
```

Mismo repo que en los ciclos 5 y 6 (`fabric-mlv-agent-healthcare-starter`), ahora **149★ y 1
fork**. Cuatro meses sin un agente sanitario permisivo nuevo con tracción medible.

### Advertencias de este pase

- **«#1 trending» no describe nada.** [pavanbadempet/AI-Healthcare-System](https://github.com/pavanbadempet/AI-Healthcare-System)
  encabezó una lista de *trending* de terceros en noviembre. Medido: **81★/19f y AGPL-3.0**.
  Ni es grande ni es utilizable en un entregable cerrado.
- **Sin licencia, no entra, por bueno que sea el paper.**
  [yhzhu99/HealthFlow](https://github.com/yhzhu99/HealthFlow) (61★/6f) tiene artículo en *npj
  Digital Medicine* y **ningún fichero de licencia**. Igual
  [AgenticHealthAI/Awesome-AI-Agents-for-Healthcare](https://github.com/AgenticHealthAI/Awesome-AI-Agents-for-Healthcare)
  (1292★/173f): excelente índice de búsqueda, no redistribuible.
- **Reconfirmado sin cambios:** [FreedomIntelligence/OpenClaw-Medical-Skills](https://github.com/FreedomIntelligence/OpenClaw-Medical-Skills)
  3128★ (eran 3120), **sigue sin licencia** y sigue sin push desde 2026-07-21.

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
