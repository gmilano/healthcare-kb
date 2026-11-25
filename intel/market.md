---
industry: healthcare
region: Global
updated: 2026-11-25
---

# 🗺️ Mapa de mercado — Healthcare

> Key players, tamaño de mercado, regulación y oportunidades **colocadas por región**.
> Toda cifra lleva su fuente y su fecha. Donde las fuentes se contradicen, se dice.

## Tamaño de mercado — usar la dirección, no el punto

Las estimaciones de *agentic AI in healthcare* para 2026 difieren por un factor de 2×
entre firmas. Citar una sola como si fuera el dato es un error que un cliente detecta.

| Firma | 2026 | Horizonte | CAGR |
|-------|------|-----------|------|
| Fortune Business Insights | $1.83B | $19.71B (2034) | — |
| Towards Healthcare | $1.14B | $33.66B (2035) | — |
| Grand View Research | ~$1.08B | $17.29B (2033) | 48.6% |
| Globe Market Research | $0.9B | ~$24.8B (2035) | — |

**Lo que sí es consistente:** Norteamérica concentra entre el **45.5% y el 55%** del mercado
según la firma, y la documentación clínica ambiental es el segmento más grande y más disputado.

- Agentes de documentación clínica: **$1.95B en 2026**, CAGR 34.15% a 2035 (Precedence Research).
  Dentro de ese segmento, los agentes de documentación ambiental ya son el **46.0%** en 2026.
- Documentación ambiental en total: ~$2.5B global en 2026 → ~$17.6B en 2036 (Meticulous, vía fuente secundaria).

## Estructura real de la oferta open source — medida, no supuesta

Consulta a `search/repositories` el 2026-11-21:

| Consulta | total_count |
|----------|-------------|
| `healthcare agent created:>2026-08-01 stars:>=50` | **1** en todo el mundo |
| `medical agent created:>2026-08-01 stars:>=50` | 3 (uno de ellos sin licencia clara) |
| `clinical AI agent created:>2026-06-01 stars:>=100` | **0** |
| `FHIR mcp stars:>=30` | 11 |

**Conclusión:** no hay un boom de agentes sanitarios open source nuevos con tracción. Hay
**deuda de descubrimiento**: repos que ya existían y esta KB no tenía. Es exactamente el mismo
hallazgo estructural que los pases de *financial* y *legal* midieron de forma independiente.
Donde sí hay oferta real y permisiva es en la **capa MCP↔FHIR** (11 repos, la mayoría MIT/Apache),
y ahí es donde conviene construir.

## Players globales

| Empresa | Tipo | Fortaleza | Debilidad |
|---------|------|-----------|-----------|
| Epic | Incumbente EHR | >85% de sus clientes usando Epic AI; agentes propios (Art, Emmie, Penny) y *Agent Factory* para que el hospital construya | Riesgo de cierre del ecosistema a terceros; la integración de OpenAI con Epic es **solo lectura** (sin notas, órdenes ni códigos) |
| Microsoft | Plataforma | Dragon Copilot (linaje Nuance DAX) como incumbente en documentación ambiental; publica agentes de referencia bajo MIT | Dependencia de Azure en el discurso de producto |
| Abridge | Documentación ambiental | $550M levantados en 2025 (Series D $250M feb + Series E $300M jun); valuación reportada $5.3–5.71B; seleccionada por el VA junto a Knowtex | Categoría muy disputada; el techo de $775.7M del contrato VA se reparte entre adjudicatarios y **no es ingreso de Abridge** |
| OpenEvidence | Búsqueda clínica | $250M en ene-2026 a valuación de $12B con solo ~$735M levantados en total: de los resultados más capital-eficientes del sector | Las valuaciones reportadas se contradicen ($12B / $15B / $3.93B según fuente) |
| Ambience Healthcare | Documentación ambiental | Series C de $243M (jul-2025) | Estimaciones de valuación entre $1B y $2B, poco fiables |
| AWS | Plataforma | Amazon Connect Health disponible con agentes de documentación y codificación médica; servidor MCP de HealthLake open source | Lock-in de datos en HealthLake |

> **No citable:** una sola fuente de blog da cuotas de documentación ambiental
> (Nuance 33% / Abridge 30% / Ambience 13%). Ninguna otra fuente lo sostiene y no hay
> metodología publicada. **No usar en material de cliente.**

## Regulación por región — el estado medido

### North America
- La FDA había autorizado **1.430 dispositivos con IA** a marzo de 2026; históricamente el **97%**
  entró por la vía 510(k) (856 de 882 a mayo de 2024).
- **Discussion paper de la FDA sobre dispositivos con IA generativa (agosto 2026)**: pide input sobre
  evaluación premarket por competencias, monitorización post-market, foundation models y **agentic AI**.
  Es consulta, no norma: no hay aún un playbook de inspección que heredar.
- FDA y EMA publicaron **principios conjuntos de buenas prácticas de IA el 14 de enero de 2026**.
- No existe estatuto federal único: una función de IA puede caer a la vez bajo dispositivo médico (FDA),
  HIPAA, certificación ONC, FTC, deberes profesionales y leyes estatales.
- Los estados están llenando el vacío. La **Colorado AI Act está impugnada en tribunales por xAI y el DOJ**.
- CMS tiene un modelo de pago para cuidado crónico asistido por IA con **primera cohorte el 5 de julio de 2026**,
  con pagos por paciente muy por debajo del precio de mercado de productos comparables.
- ⚠️ **No verificado:** una fuente de prensa sectorial afirma que la FDA autorizó un dispositivo
  diagnóstico autónomo y que HHS emitió un RFI sobre agentes autónomos en octubre de 2026.
  Ninguna fuente primaria lo confirma. **No citar.**

- **(2026-11-22) Construir contra la fecha firme de CMS-0057-F.** La API de autorización previa
  es obligatoria el **1 de enero de 2027**; la guía Da Vinci PAS es solo *recomendada* (CMS lista
  STU 2.0.1 y 2.1.0). Vender «hay que cumplir Da Vinci» es frágil y un revisor lo detecta. Vender
  «hay que exponer una API en una fecha, y la única implementación de referencia permisiva que
  existe es Apache-2.0» es exacto y además cierto. Piezas:
  [HL7-DaVinci/prior-auth](https://github.com/HL7-DaVinci/prior-auth),
  [CRD](https://github.com/HL7-DaVinci/CRD), [dtr](https://github.com/HL7-DaVinci/dtr),
  [cqframework/clinical-reasoning](https://github.com/cqframework/clinical-reasoning).
- **(2026-11-22) La biblioteca CQL como activo del cliente.** Las reglas de necesidad médica
  escritas en CQL son el único artefacto del ciclo de ingresos que el cliente puede poseer, versionar
  y auditar sin tocar un conjunto de códigos propietario. Es el entregable con margen: el parser X12
  es gratis y el CPT no es nuestro, pero la regla sí.
- **(2026-11-22) Matiz de alcance sobre el hueco de ciclo de ingresos.** Rebaja la oportunidad de
  arriba: **no se puede entregar una plataforma de ciclo de ingresos «todo open source»**, porque su
  salida se expresa en CPT, propietario de la AMA. Se vende la capa de juicio sobre un conjunto de
  códigos que **el cliente ya licencia** para facturar.

### EMEA
- A marzo de 2026 los dispositivos médicos con IA se certifican **exclusivamente bajo MDR/IVDR**;
  las obligaciones de alto riesgo del AI Act **todavía no aplican** a ellos.
- El **Reglamento (UE) 2026/1744** (Digital Omnibus) desplaza el alto riesgo del **Anexo I**
  —donde caen los dispositivos MDR/IVDR— a **2 de agosto de 2028**. El Anexo III va a 2-dic-2027.
  El **Artículo 50** (transparencia) **ya aplica desde el 2 de agosto de 2026**.
- 🔄 **En movimiento legislativo:** hay una propuesta de la Comisión para sacar los dispositivos
  médicos con IA del AI Act y dejarlos solo bajo MDR/IVDR; el Parlamento votó a favor de mover
  MDR/IVDR de anexo el 26 de marzo por amplia mayoría, pero **faltan pasos del procedimiento**.
  Verificar contra el Diario Oficial antes de construir un argumento comercial sobre esta fecha.
- **EHDS**: es la vía regulada de acceso a datos para uso secundario, incluido entrenamiento y
  validación de algoritmos. **No es un atajo de cumplimiento**, y conviene no venderlo como tal.
- **gematik**, la agencia alemana de salud digital, publica sus especificaciones de API
  (e-receta, ePA, TI-Messenger, VZD) bajo **Apache-2.0**. Es una fuente oficial citable.

- **(2026-11-22) El hueco del NHS empeoró y eso lo hace vendible.** No es que no haya tooling FHIR
  oficial del NHS: **sí lo hay y no tiene licencia.**
  [NHSDigital/NHSEngland-FHIR-SCR-IPS](https://github.com/NHSDigital/NHSEngland-FHIR-SCR-IPS)
  existe (refs=61, push 2026-06) y **no contiene fichero de licencia**, verificado con 9 variantes de
  nombre. Sin licencia no hay derecho de uso, así que es inutilizable aunque sea público. Frente a
  gematik —que publica sus especificaciones en Apache-2.0— el contraste es directo y un cliente
  británico lo entiende en una frase.
- **(2026-11-22) Escalado antes que aprobación.** Solo **Alemania y Francia** tienen vías
  estructuradas de reembolso para escalar herramientas de IA; en España e Italia se aprueban
  herramientas que luego no tienen base presupuestaria. El riesgo real de un proyecto en el sur de
  Europa no es la aprobación regulatoria, es que no haya quien lo pague. Dimensionar en consecuencia.
- **(2026-11-22) Cuello de botella de organismos notificados.** Hay 51 organismos designados bajo MDR,
  pero la designación para AI Act exige competencias de IA adicionales. El calendario de evaluación
  es un riesgo de planificación, no un trámite.

### APAC
- **Singapur**: MOH y HSA publicaron las *AI in Healthcare Guidelines* en **marzo de 2026**. El enfoque
  asigna responsabilidad más que aprobar productos.
- **China**: la NMPA emitió las *Implementation Opinions on AI and Drug Regulation* el **2 de abril de 2026**,
  sobre una base en capas de PIPL, Cyber Security Law, Data Security Law y reglas de IA generativa.
- **Corea del Sur**: la *AI Framework Act* es el **primer estatuto integral de IA de la región**.
- **India**: DPDP Act en vigor desde 2025 con despliegue por fases; hay un proyecto de ley de IA
  (Ethics & Accountability) y guías éticas del ICMR para diagnóstico y tratamiento con IA.
- **Japón**: regulación sectorial, sin estatuto transversal.
- **Vietnam**: clasifica la IA sanitaria como **alto riesgo**, con evaluación y registro premarket.
- Adopción: IDC proyecta que **para 2030 el 33% de los hospitales de primer nivel** de Asia-Pacífico
  desplegarán agentes de IA. Hoy solo ~**30% de los pilotos** llegan a uso clínico, y el cuello de
  botella declarado es explicabilidad y validación local.

- **(2026-11-22) La guía de Singapur tiene nombre y versión: AIHGle 2.0** (MOH + HSA,
  **10 de marzo de 2026**). El ciclo 5 la registró sin nombre. Asigna deberes a desarrollador,
  institución y clínico a lo largo de todo el ciclo de vida: el entregable que la satisface es una
  matriz de responsabilidades por fase, no un informe de precisión del modelo.
- **(2026-11-22) Hueco nuevo y simétrico al del NHS: India.** La consulta
  `ABDM health India stars:>=10` devuelve **1** resultado (11★, 1 fork). India tiene una pila
  nacional de salud digital (ABDM) y prácticamente **ninguna herramienta permisiva** que la hable.
  Con una puerta regulatoria más ligera que Japón o China —sin ley específica de IA, aplicando el
  régimen de dispositivos— es la región donde un cliente llega antes a volumen clínico.
- **(2026-11-22) Diferenciar la puerta por país antes de prometer plazos.** China trata el software
  diagnóstico con IA como **Clase III** vía NMPA, y la adopción la deciden el precio provincial y la
  compra hospitalaria, no la aprobación. Japón se mantiene en principios (Ley de Promoción de la IA
  de 2025) con aprobación de producto por la ley de productos farmacéuticos y dispositivos. Mismo
  producto, tres calendarios.

### LATAM
- **Brasil — el hallazgo accionable de la región.** La **Resolución CFM 2.454/2026** entró en vigor el
  **10 de agosto de 2026** (180 días tras su publicación). Obliga a las instituciones a **clasificar cada
  sistema de IA por nivel de riesgo**, mantener **auditoría continua** y **documentar el uso de IA en el
  expediente del paciente**. Consecuencia comercial directa: la gobernanza de IA a nivel hospitalario
  ya funciona como **filtro de venta** en Brasil. Quien llega sin traza de auditoría no pasa.
- **México**: una reforma a la Ley General de Salud de enero de 2026 añadió un capítulo de salud digital,
  y una iniciativa de febrero de 2026 propone regulación integral, reconociendo que la adopción
  tecnológica superó al marco normativo. IMSS, ISSSTE y hospitales privados ya implementan IA.
- Adopción en Brasil: se cita que **18%** de los establecimientos de salud usan IA (**25%** en la red
  privada frente a **11%** en la pública). ⚠️ No pudo verificarse la fuente primaria de ese dato.
- El estado de **PL 2338/2023** (ley de IA brasileña) se reporta como aprobado en Senado y en trámite
  en Cámara; una fuente lo da como aprobado en 2025. ⚠️ Contradictorio, verificar antes de citar.
- Ningún mercado de la región ha adoptado marcos de **validación clínica específicos para IA**, y los
  despliegues se concentran en instituciones emblemáticas.

## Opportunities by region

### North America
- **Escribir el marco de control que no existe.** La FDA pide input sobre agentic AI pero no ha
  publicado norma; no hay playbook de inspección que heredar. Quien produzca ahora un marco de
  control defendible para agentes clínicos —clasificación de riesgo, traza por decisión,
  monitorización post-market— **fija el estándar de facto**. Es el mismo hueco que el pase de
  *financial* identificó en banca con SR 26-2, y se vende igual.
- **Benchmark honesto como entregable.** [MedAgentBench](https://github.com/stanfordmlgroup/MedAgentBench)
  (MIT) evalúa agentes contra FHIR real. Un informe de evaluación con números reproducibles vale más
  en una conversación clínica que una demo.
- **Ciclo de ingresos / denegación de claims**: la mayor línea de presupuesto de IA sanitaria en EEUU,
  y donde la oferta permisiva está vacía (ver gaps). Build-vs-buy abierto.


- **(2026-11-25) Empezar por imagen, porque es donde la vía regulatoria ya está trillada.** De las
  **1 614** entradas de la lista de dispositivos con IA habilitada de la FDA (actualizada
  2026-09-04), **1 230 son de radiología: el 76 %**, y de ellas **1 212 entraron por 510(k)**
  (9 De Novo, 9 PMA). Cardiovascular, segundo, tiene 154. La proporción es estable (76,3 % en
  2025, 75,0 % en el 1T de 2026), así que es estructura y no ruido. Traducción comercial: para un
  producto de imagen hay **más de 1 200 precedentes** que enseñar al comité clínico; para un
  agente clínico que no es dispositivo no hay ninguno. ⚠️ Cifras de análisis de terceros sobre la
  lista de la FDA, que la propia FDA declara no exhaustiva.
- **(2026-11-25) La demanda ya no es el problema; el gobierno del dato sí.** Una encuesta de la
  AMA de 2026 sitúa en **81 % los médicos que usan herramientas de IA profesionalmente**, más del
  doble que la primera vez que preguntó. Por tipo de organización, la adopción de herramientas
  específicas de dominio va a **27 % en sistemas de salud, 18 % en ambulatorio y 14 % en
  pagadores**. Con 81 % de uso individual y 27 % de adopción institucional, el hueco entre ambos
  **es «shadow AI»**, y el entregable que lo cierra es inventario, política y traza — no un modelo.
  ⚠️ Encuestas de sector; usar como dirección.
- **(2026-11-25) Riesgo de latigazo regulatorio, que hay que decirle al cliente.** La orden
  ejecutiva de diciembre de 2025 empuja un estándar federal «mínimamente gravoso» y crea un grupo
  de litigio del DOJ **contra leyes estatales de IA**, mientras 14 estados legislaron salud-IA en
  2025 y la guía borrador de la FDA de enero de 2025 sobre software de dispositivo con IA **sigue
  sin finalizarse**. Consecuencia de arquitectura: **la traza y la política deben ser
  parametrizables por jurisdicción**, porque el mapa va a cambiar durante la vida del proyecto.
- **(2026-11-25) Canadá, que llevaba varios pases sin material propio.** El scribe ambiental
  permisivo más completo del sector, [Berta](https://github.com/phairlab/berta-ai-scribe)
  (Apache-2.0), se desarrolló y evaluó en el contexto de Alberta Health Services, con artículo en
  JMIR Med Inform y **coste operativo publicado por debajo de 30 USD por médico y mes**. Es una
  referencia canadiense citable y una base técnica a la vez.
- **(2026-11-25 · c8) El nodo de uso secundario es el encargo que el calendario de EEUU no bloquea.**
  La regulación federal de IA sanitaria sigue sin cerrarse —la guía de la FDA sobre software de
  dispositivo con IA **no está finalizada**, y la regla de sistema de gestión de calidad entró en
  vigor el **2026-02-02**— mientras **CMS modela la adopción por la vía del pago**, no de la norma.
  Un nodo OMOP no es dispositivo: no entra en esa cola. Y hay dos anclas de contexto citables:
  Norteamérica fue el **44,5 % del mercado global de IA sanitaria en 2025**, y la brecha de
  adopción entre clínico e institución sigue abierta (**81 %** de médicos usando IA frente a
  **27 %** de sistemas de salud, **18 %** ambulatorio y **14 %** pagadores). ⚠️ Encuesta AMA 2026 y
  cifras Menlo Ventures citadas en prensa sectorial: dirección sí, punto ante un CFO no.
- **(2026-11-25 · c8) El entorno normativo estatal se ha vuelto un riesgo de proyecto, no sólo de
  cumplimiento.** 14 estados legislaron sobre IA sanitaria en 2025 y la orden ejecutiva de
  diciembre de 2025 creó una vía de litigio federal contra leyes estatales de IA. Para un
  entregable multiestado eso significa **que el conjunto de obligaciones puede cambiar durante el
  proyecto**: el diseño defendible es el que **parametriza** la regla por jurisdicción en lugar de
  codificarla. Es el mismo argumento que la biblioteca CQL del ciclo 6, aplicado a jurisdicción.

**[c9 · Investigación clínica] El único regulador del mundo cuyo oráculo es ejecutable y público.**
CORE v1.0 ([`cdisc-org/cdisc-rules-engine`](https://github.com/cdisc-org/cdisc-rules-engine),
MIT, 126★, push 2026-11-25) ejecuta reglas de conformidad **de la FDA** publicadas junto con sus
datos de prueba en [`cdisc-org/cdisc-open-rules`](https://github.com/cdisc-org/cdisc-open-rules)
(MIT). Es el caso más limpio de la ley del oráculo en las doce industrias: el regulador publica
la clave de respuestas, y encima hay 176 repos permisivos. **Oferta:** automatización agéntica
de la sumisión (SDTM/ADaM/Define) con CORE como juez — `SDTM agent LLM` devuelve 4 repos y
`ADaM automation LLM` devuelve 2, así que el hueco es cuantificado, no supuesto.
Activos federales en dominio público utilizables sin fricción: [`FDA/openfda`](https://github.com/FDA/openfda)
(CC0-1.0, 720★) y [`ncbi-nlp/TrialGPT`](https://github.com/ncbi-nlp/TrialGPT) (NCBI Public Domain Notice).
**Contexto de compra:** el 81% de los médicos encuestados por la AMA declara usar IA
profesionalmente (recogido en la guía Chambers *Healthcare AI 2026*), NA concentraba el 44,5%
del mercado global de IA sanitaria en 2025, y la política federal apunta a un estándar nacional
«minimally burdensome» (orden ejecutiva de diciembre de 2025) mientras **los estados legislan por
su cuenta** — es decir, el comprador necesita una arquitectura que sobreviva a 50 regímenes.
### EMEA
- **Anclar el agente en la especificación oficial alemana.** [gematik/api-erp](https://github.com/gematik/api-erp)
  y [gematik/api-ePA](https://github.com/gematik/api-ePA) son Apache-2.0 y oficiales. Generar el cliente
  desde su spec en tiempo de build permite decirle al cliente *"está anclado en la spec de gematik, no
  en nuestra interpretación"*, y él lo verifica en dos minutos. No existe equivalente oficial en NHS.
- **Segunda pierna obligatoria para el discurso regulatorio.** El Anexo I se movió a 2-ago-2028 y hay
  una propuesta viva para sacar los dispositivos del AI Act. Cualquier propuesta cuya urgencia
  dependa de esa fecha es frágil. La pierna estable es **MDR/IVDR, que no se movió**, más el
  **Art. 50 que ya aplica desde ago-2026**.
- **EHDS como vía de datos**: posicionar acceso a datos para validación de algoritmos, siendo
  explícito en que no exime de MDR.


- **(2026-11-25) La intención de adoptar ya es casi universal; el cuello de botella es la
  competencia.** Un estudio de la Comisión publicado en marzo de 2026 recoge que el **94 % de los
  proveedores sanitarios ya usa IA o planea adoptarla**. La OCDE, en su capítulo sobre IA
  sanitaria en la UE, recomienda **consolidar la guía** que hoy se reparte entre GDPR, MDR y AI
  Act, y propone meter alfabetización en IA en los **estándares de acreditación hospitalaria**.
  Eso convierte la formación y el marco de competencias en **partida presupuestable**, no en
  cortesía: es un entregable con comprador.
- **(2026-11-25) El plazo del AI Act para dispositivos, con el mecanismo exacto.** El Digital
  Omnibus (propuesta de la Comisión del 2025-11-19) no fija una fecha nueva sin más: para IA
  **integrada en productos regulados**, como los dispositivos médicos, la aplicabilidad pasa a
  **12 meses después de que se confirmen las medidas de apoyo**, con tope duro en
  **2028-08-02** (la fecha original era 2027-08-02). Confirma además que **MDR/IVDR tiene
  precedencia** en la evaluación de conformidad de IA en dispositivos. ⚠️ Se informó de un acuerdo
  político provisional el 2026-05-07 pendiente de adopción formal, y **no se ha podido confirmar
  su publicación en el Diario Oficial** a fecha de hoy. Por tanto la regla del ciclo 6 sigue
  vigente y reforzada: **la pierna firme es MDR/IVDR más el Art. 50 ya aplicable desde
  ago-2026**; cualquier propuesta cuya urgencia dependa de la fecha del Anexo I es frágil.
- **(2026-11-25) Golfo y Norte de África: vender pilotos con criterio de salida.** La actividad de
  la región se describe como mayoritariamente **piloto**, con la **confianza** como barrera
  principal. Combinado con el 30 % de paso a producción medido en APAC, el entregable que
  desbloquea es el **criterio explícito de promoción de piloto a producción**, acordado antes de
  empezar el piloto.
- **(2026-11-25 · c8) EL ARGUMENTO DE VENTA MÁS FUERTE QUE LA KB HA MEDIDO EN EMEA, Y ES UNA
  FRASE DE LA PROPIA COMISIÓN.** El estudio de la Comisión Europea de marzo de 2026 reporta que
  **el 94 % de los proveedores sanitarios ya usan IA o planean adoptarla** y, en la misma
  página, que los sistemas sanitarios europeos **dependen de soluciones desarrolladas fuera de
  la UE**. Demanda casi universal + dependencia externa reconocida por el regulador = **el
  encargo es la alternativa soberana**, y el comprador ya tiene el argumento escrito por su
  propia Comisión. Es la mejor apertura disponible para el plano de uso secundario.
- **(2026-11-25 · c8) El EHDS da fechas firmes y NO da estándar técnico — ahí está el encargo.**
  Reglamento (UE) 2025/327, en vigor desde **2025-03-26**. Hitos: **2027-03-26** cada Estado
  miembro debe designar su **Health Data Access Body**; **2029-03-26** aplica el grueso del uso
  secundario; **2031-03-26** para **dato genético y de ensayos clínicos**. Pero el EHDS **no
  impone modelo de datos**: FHIR, OMOP CDM y openEHR siguen los tres en discusión y **no se
  espera un mandato formal**. Consecuencia directa y medida (ver sección de este pase más abajo):
  **un mandato sin artefacto no produce convergencia, produce fragmentación nacional**. Lo que se
  vende aquí no es «cumplir el EHDS»: es **el nodo que funciona con el modelo que acabe eligiendo
  tu Estado miembro**, con la capa de mapeo aislada. Vender certeza sobre el modelo sería vender
  una apuesta. ⚠️ Fechas de síntesis de despachos jurídicos; confirmar contra el texto del
  Reglamento antes de ponerlas en contrato.
- **(2026-11-25 · c8) Tres autoridades sanitarias nacionales, tres posturas de licencia — y eso
  decide qué se puede reutilizar.** Argumento de una frase para un cliente europeo, enteramente
  medido por esta KB: **gematik** (Alemania) publica sus especificaciones en **Apache-2.0**
  (ciclo 5); **Sundhedsdatastyrelsen** (Dinamarca) publica su National Contact Point en **MIT**
  ([Sundhedsdatastyrelsen/ehdsi](https://github.com/Sundhedsdatastyrelsen/ehdsi), 1078 B,
  refs=400, push 2026-11-25); el **NHS** publica tooling FHIR **sin fichero de licencia alguno**
  (hueco (b), sigue abierto). La consecuencia es operativa, no retórica: en Alemania y Dinamarca
  se parte del código oficial; en Reino Unido **hay que reimplementar**, y eso es presupuesto.
- **(2026-11-25 · c8) ⚠️ Trampa de nomenclatura que cuesta medio día: eHDSI ≠ EHDS.** El repo
  danés de arriba es **eHDSI** (*eHealth Digital Service Infrastructure*, MyHealth@EU):
  intercambio transfronterizo para **asistencia**, uso **primario**. El **EHDS** es el reglamento
  de uso **secundario**. Una letra de diferencia, dos cosas distintas, y buscar «EHDS» devuelve
  sobre todo el primero. La OCDE, por su parte, pide **guía consolidada** entre GDPR, MDR y AI
  Act — señal de que la carga de interpretación, hoy, la paga el integrador.

**[c9 · Investigación clínica] El plano con mandato y sin herramienta: 3 repos para todo CTIS.**
El EU CTR centralizó la sumisión de ensayos en **CTIS**, y el ecosistema permisivo que lo toca
cabe en una tabla: [`pipeworx-io/mcp-eu-ctis`](https://github.com/pipeworx-io/mcp-eu-ctis)
(MIT, **0★**, push 2026-11-09), [`JulHeg/euclinicaltrials.py`](https://github.com/JulHeg/euclinicaltrials.py)
(MIT, 7★, parado desde 2022) y, para el registro anterior,
[`PaulinCharliquart/eudract-py`](https://github.com/PaulinCharliquart/eudract-py) (MIT, 10★,
push 2026-11-04). Consulta `CTIS clinical trial EU` = **3 repos en total**; `EMA clinical trial
regulation tool` = **0**. **Oferta:** ser quien construya la capa CTIS, porque el mandato existe
y la herramienta no — es el patrón «segunda pierna regulatoria» (P9) con el hueco ya medido.
**Contexto:** un estudio de la Comisión de marzo de 2026 reporta que el 94% de los proveedores
sanitarios usa o planea usar IA; el AI Act impone a los sistemas de alto riesgo supervisión
humana, transparencia y documentación; y la OCDE pide explícitamente guía consolidada entre
GDPR, MDR y AI Act — esa fragmentación es el argumento de venta de una arquitectura única.
### APAC
- **Terminología como columna vertebral.** [Taiwan-Health-MCP](https://github.com/healthymind-tech/Taiwan-Health-MCP)
  (MIT, 73 herramientas) ya resuelve ICD-10-CM/PCS, SNOMED CT, LOINC y fármacos TFDA. Es la base
  más avanzada de la región para un agente que debe codificar correctamente.
- **Vender validación local, no el modelo.** Con ~30% de pilotos llegando a producción y la
  explicabilidad como cuello de botella declarado, el entregable que desbloquea presupuesto es el
  **protocolo de validación local**, no un modelo más.
- **Sustituibilidad de proveedor como requisito.** Donde la responsabilidad recae en la institución
  (Singapur) o la IA sanitaria es alto riesgo (Vietnam), la abstracción de proveedor de modelo es
  requisito de arquitectura y por tanto trabajo presupuestable.


- **(2026-11-25) El número que hay que llevar a toda conversación de APAC: sólo ~30 % de las
  pruebas de concepto llegan a producción clínica.** Y encaja con el resto de lo medido: una
  encuesta de HIMSS a 200 clínicos y responsables de TI en **13 mercados** de la región encuentra
  que el **46 %** empezó su programa de IA en los últimos 12 meses y que el obstáculo principal
  es el **coste (67 %)**; IDC añade que **75 %** de los proveedores de la región cree que lo
  agéntico rinde más que la IA generativa. Un mercado que acaba de empezar, con expectativa alta
  y mortalidad de pilotos del 70 %. **El entregable que se vende aquí es el que sobrevive a esa
  mortalidad: validación local, criterio de promoción y coste por caso**, no un modelo más.
  ⚠️ Encuestas de proveedor y de analista; dirección, no punto.
- **(2026-11-25) Corea del Sur, regulación nueva y concreta que el ciclo 6 no tenía.** La **AI
  Basic Act surtió efecto el 2026-01-22** y nombra explícitamente como alto impacto la
  **operación del sistema sanitario** y el **desarrollo y uso de dispositivos médicos**. El deber
  central del operador de alto impacto es la **supervisión humana**, más transparencia y
  evaluación de impacto; y **aplica extraterritorialmente** a actividades que afecten al mercado
  o a usuarios coreanos aunque ocurran fuera. Para Globant esto es directamente presupuestable:
  el artefacto que la satisface es una **matriz de supervisión humana por fase** —el mismo
  entregable que exige AIHGle 2.0 en Singapur— y no un informe de precisión. ⚠️ Las fuentes
  discrepan sobre el Decreto de Aplicación (enero de 2026 frente a una modificación de julio de
  2026) y la prensa local recoge quejas por vaguedad de los términos: verificar el texto vigente
  antes de comprometer alcance.
- **(2026-11-25) India: el encargo es «adoptar y mantener», no «construir».** Medido por
  organización en lugar de por palabras clave, la National Health Authority **sí publica** tooling
  permisivo —[NHA-ABDM/ABDM-wrapper](https://github.com/NHA-ABDM/ABDM-wrapper) es **Apache-2.0**
  y existe con refs=37, aunque `search` no lo liste— pero el resto de la organización está
  **parado desde 2024** y parte no tiene licencia. Con la puerta regulatoria más ligera de APAC,
  **sigue siendo el mejor par riesgo/recompensa de la región**, y ahora con un alcance más
  pequeño y más defendible que el que el ciclo 6 suponía.
- **(2026-11-25 · c8) APAC está POR DELANTE de LATAM en uso secundario, al contrario que en los
  planos de imagen y scribes — y hay nombres y escalas concretas.** El ecosistema OMOP tiene aquí
  su implantación más profunda: en **Corea** las reclamaciones nacionales de **HIRA** están
  mapeadas al CDM **para toda la población** (serie 2010-2019), **KIDSNet** declara una red de
  **7 hospitales y 1,69 M de pacientes pediátricos** (julio de 2026), y **Australia** tiene
  **AHDEN** para adopción nacional. El **Simposio OHDSI APAC 2026** se celebró el **13-15 de
  noviembre en la Universidad Yonsei, Seúl**. **Japón es el menos maduro de los grandes**: el
  mapeo del vocabulario de fármacos sigue en curso. Lectura comercial: en Corea y Australia se
  vende **capa analítica y agéntica sobre un nodo que ya existe**; en Japón e Indonesia se vende
  todavía **el ETL y el vocabulario**. Preguntar primero si hay nodo, nunca presuponerlo.
  ⚠️ Cifras de material de la propia comunidad OHDSI (slides de community call).
- **(2026-11-25 · c8) Corea añade obligación dura en enero de 2026 — segundo régimen APAC con
  nombre.** La **AI Basic Act** coreana, **en vigor desde enero de 2026**, impone obligaciones de
  gestión de riesgo a sistemas de **alto impacto**, sanidad incluida. Junto a AIHGle 2.0 de
  Singapur (ciclo 7), son los dos marcos de la región que ya exigen **artefactos**, no intenciones.
  Y encaja con el dato que esta KB viene usando para APAC: **sólo ~30 % de las pruebas de concepto
  llegan a producción clínica**. El entregable que desbloquea sigue siendo el **expediente de
  gestión de riesgo y el criterio de promoción**, acordados antes del piloto.
- **(2026-11-25 · c8) El dato que ordena la conversación agéntica en APAC:** IDC reporta que
  **el 75 % de los proveedores sanitarios de Asia-Pacífico espera más ganancia de productividad
  de la IA agéntica que de la GenAI sin agentes**. Es la región donde el discurso agéntico tiene
  mejor recepción declarada, con la barrera de **coste al 67 %** (HIMSS, 13 mercados). Es decir:
  **la objeción no es de concepto, es de precio** — argumentar con coste autoalojado publicado
  (ver el patrón de scribe del pase de la mañana) y con substrato Apache-2.0 que no añade licencia.

**[c9 · Investigación clínica] Mandato CDISC sin tooling regional: 0 repos.**
Las consultas `PMDA CDISC submission` y `NMPA clinical data` devuelven **0 repos** en el canal de
precisión. Japón exige sumisión electrónica en estándares CDISC para registro de nuevos fármacos
(requisito establecido desde la segunda mitad de la década pasada; **el hecho normativo es
conocido, pero esta KB no lo ha verificado en fuente primaria este pase — tratar como pendiente
de verificación, no como cita**), y aun así el tooling abierto específico de la región no existe:
se usa el del plano global (pharmaverse/CDISC), en inglés. **Oferta:** aseguramiento y validación
de sumisión sobre CORE para sponsors regionales, que es exactamente lo que el mercado dice
necesitar: Roche reporta que sólo ~30% de las PoC de IA sanitaria en APAC llegan a producción
clínica, y HIMSS (13 mercados) sitúa el coste como barrera principal para el 67%. IDC añade que
el 75% de los proveedores de la región considera que la IA agéntica rinde más que la generativa.
**Regulación que ayuda a vender aseguramiento:** la guía nacional de Singapur de 2026 está
orientada a **asignar responsabilidad** más que a aprobar producto, y la *AI Basic Act* de Corea
del Sur está en vigor desde enero de 2026 con obligaciones de gestión de riesgo para sistemas de
alto impacto. Donde la norma asigna responsabilidad, el entregable es la evidencia.
### LATAM
- **Convertir CFM 2.454/2026 en producto.** Es la única norma de la región que ya está **en vigor** y
  que exige artefactos concretos: clasificación de riesgo por sistema, auditoría continua y registro
  del uso de IA en el expediente. Un agente con event log por decisión **produce esa evidencia por
  construcción**. Esto no es un argumento de cumplimiento abstracto: es el filtro que decide la venta.
- **Anclar en las especificaciones RNDS.** Cuatro repos Apache-2.0 cubren identificadores, validación
  FHIR y cliente mTLS, y [Voa-Health/rnds](https://github.com/Voa-Health/rnds) **ya expone un servidor
  MCP para agentes**. Siendo honestos con el cliente en que son comunitarios y no oficiales, es la
  base más rápida de la región.
- **Desarrollo sin acreditación DATASUS.** El sandbox local de
  [Precisa-Saude/fhir-brasil](https://github.com/Precisa-Saude/fhir-brasil) permite construir y
  demostrar antes de tener certificado ICP-Brasil: destraba el arranque de un engagement brasileño.
- **Hueco de NLP clínico en español.** No se encontró ninguna librería de NLP clínico en español con
  tracción (ver gaps). Para un grupo hospitalario hispanohablante esto es trabajo a medida con
  pocos competidores.

- **(2026-11-22) Primera cifra de adopción con granularidad de país en la región.** El 18 % de los
  establecimientos de salud brasileños ya usa IA, con **25 % en la red privada frente a 11 % en la
  pública**. Cierra parcialmente el hueco (d) que el ciclo 5 dejó abierto por falta de datos
  granulares, y además orienta la venta: el comprador de LATAM con presupuesto es privado, y el
  argumento al sector público es el programa **SUS Digital**, que integra IA y salud digital en el SUS
  durante 2026. ⚠️ Cifra de informe citado en prensa sectorial; usar como dirección.
- **(2026-11-22) Advertencia de licenciamiento específica de la región.** La membresía de SNOMED
  International determina si el contenido de terminología es gratis o se paga por banda de renta del
  Banco Mundial, **y se licencia por país**. Confirmados como Miembros recientes en la región
  **Costa Rica (mayo de 2026), Belice, El Salvador y Jamaica**. **No se pudo confirmar** el estado de
  Brasil, Argentina, Uruguay, Chile, México ni Colombia: `snomed.org` no resuelve desde este entorno
  (política de red de la sesión), y las fuentes secundarias no lo cubren. **Verificar por país antes
  de presupuestar un despliegue regional de terminología** — es una partida de coste, no un trámite.
- **(2026-11-22) Marcos de telemedicina ya operativos como vía de entrada.** Brasil (CFM 2.314/2022),
  Chile (**Ley 21.541**) y México (**NOM-024-SSA3**) tienen marcos vigentes, y COFEPRIS avanza en
  regulación de software médico y dispositivos con IA. La vía de menor resistencia en la región sigue
  siendo el flujo de telemedicina, no el dispositivo diagnóstico.


- **(2026-11-25) Hueco (g) del ciclo 6 — CERRADO en lo que decide el presupuesto: Brasil y México
  NO son Miembros de SNOMED International.** La lista de Miembros de la región recoge
  **Argentina, Belice, Canadá, Chile, Costa Rica, El Salvador, Jamaica, Estados Unidos y
  Uruguay**; **Brasil, México y Colombia no aparecen**. Para Argentina, Chile y Uruguay hay
  corroboración independiente: la página de distribución publica ubicaciones de descarga como
  territorios Miembros. La consecuencia es de partida presupuestaria y es exactamente la que el
  ciclo 6 pedía cerrar primero: **en los dos mercados sanitarios más grandes de LATAM el
  contenido SNOMED CT es una licencia que se paga** (por banda de renta del Banco Mundial, una
  por país), mientras que en Argentina, Chile y Uruguay es gratuito dentro del país — aunque
  **siga requiriendo Licencia de Afiliado**. ⚠️ Fuentes secundarias: `snomed.org` **no resuelve
  desde este entorno** por la política de red de la sesión (hay que autorizar el dominio para
  verificarlo en origen), y la lista localizada muestra 9 países de la región frente a los 54
  Miembros globales que la propia organización declara, así que **puede ir por detrás**.
  Verificar por país antes de firmar un despliegue regional de terminología.
- **(2026-11-25) La adopción sube despacio y el canal real es WhatsApp.** La proporción de
  *healthtech* de la región que usa IA pasó del **14 % al 20 % entre 2022 y 2024**; un mapeo de
  la región cuenta **41 actores** con Brasil dominante y **19 de 31 proveedores verificados** con
  despliegue documentado en acceso del paciente. Y el dato de arquitectura: **muchas de esas
  herramientas de acceso del paciente corren sobre WhatsApp**. Para un engagement regional eso
  no es un detalle de canal, es un requisito de diseño desde el primer día. ⚠️ Recuentos de
  mapeos sectoriales, no auditados.
- **(2026-11-25) Los proveedores empiezan a construir en casa: la ventana de «vender producto»
  se estrecha y la de «vender capacidad» se abre.** Hapvida tiene scribe de IA **propio**, y
  Telepatía, que era proveedor de documentación, se ha movido a apoyo a la decisión clínica. Los
  fabricantes locales de historia clínica están incrustando IA en los sistemas que los
  proveedores ya usan. La lectura para Globant: en LATAM el comprador grande quiere **capacidad
  propia**, lo que favorece el encargo de construir-con-el-cliente y transferir, no la licencia
  de una plataforma cerrada.
- **(2026-11-25) Infraestructura regional de gobernanza en la que apoyarse.** La OPS está
  ayudando a los países a construir preparación —el taller de **Nicaragua de septiembre de 2026**
  priorizó su marco regulatorio y ético de IA en salud— y existe una **hoja de ruta CLIAS/IECS
  para América Latina y el Caribe (2026)** que cubre gobernanza, regulación y financiación. Son
  anclas citables para una propuesta al sector público, que es donde la norma todavía no existe.
  El Banco Mundial añade el argumento técnico que vende validación local: **los modelos
  entrenados con datos de otras regiones pueden no ajustarse al contexto local**.
- **(2026-11-25) NLP clínico en español: el hueco (c) se refina y mejora como argumento.** Hay
  activos, y medirlos explica por qué sigue abierto: [PlanTL-GOB-ES/lm-biomedical-clinical-es](https://github.com/PlanTL-GOB-ES/lm-biomedical-clinical-es)
  es Apache-2.0 con corpus de más de 1 000 M de tokens pero **sin push desde 2022-11-16** (28★/2f),
  y [lcampillos/medspaner](https://github.com/lcampillos/medspaner) está vivo pero es **GPL-3.0**
  y de 8★/1f. Lo permisivo está abandonado y lo vivo es copyleft: **para un grupo hospitalario
  hispanohablante sigue siendo trabajo a medida con pocos competidores**, y ahora se puede
  justificar con dos mediciones en lugar de con una ausencia.
- **(2026-11-25 · c8) EL HALLAZGO LATAM DEL PASE, Y ESTÁ MEDIDO DOS VECES POR VÍAS
  INDEPENDIENTES: EL CUELLO DE BOTELLA ES EL VOCABULARIO, NO LA HERRAMIENTA.** El equipo de
  OHDSI Brasil (CIDACS, simposio OHDSI 2025) nombra como su principal dificultad la **«escasez de
  vocabularios adecuados para el contexto brasileño»** y la necesidad de formación técnica. De
  forma **independiente**, el ciclo 7 de esta KB midió que **Brasil, México y Colombia no
  aparecen como Miembros de SNOMED CT** (Argentina, Chile y Uruguay sí). Dos fuentes distintas,
  dos ciclos distintos, **la misma causa raíz**: el contenido terminológico. Y la conclusión es
  accionable porque **la herramienta es gratis y la que falta no**:
  [Usagi](https://github.com/OHDSI/Usagi), [WhiteRabbit](https://github.com/OHDSI/WhiteRabbit) y
  [Perseus](https://github.com/OHDSI/Perseus) son Apache-2.0; **el mapeo pt-BR/es no existe**.
  => **El entregable con margen es el conjunto de mapeos terminológicos**, que el cliente posee,
  versiona y audita — estructuralmente idéntico a la biblioteca CQL del ciclo 6. Ver **P19**.
- **(2026-11-25 · c8) Y esto unifica el hueco (c): el NLP clínico en español y el vocabulario OMOP
  en español son el mismo hueco con dos nombres.** Re-medido hoy sin cambios:
  `biomedical spanish stars:>=10` → **2 resultados**, ambos de
  [PlanTL-GOB-ES](https://github.com/PlanTL-GOB-ES/lm-biomedical-clinical-es) (Apache-2.0, 28★/2f)
  y **sin push desde 2022-11-16**. Tercera medición consecutiva del mismo vacío. Lo que cambia
  este pase no es la cifra: es que ahora **hay un comprador identificado** para cerrarlo (el nodo
  OMOP de un hospital o ministerio hispanohablante) en lugar de un hueco abstracto.
- **(2026-11-25 · c8) La región está arrancando en este plano — lo cual es la ventana, no la
  objeción.** El **primer** Simposio OHDSI Latin America se celebró el **30-31 de julio de 2026 en
  Salvador, Brasil**, con el objetivo declarado de ≥100 asistentes; Brasil lidera (CIDACS y el
  **Hospital Israelita Albert Einstein**, que empezó en 2018 y es partner de la comunidad desde
  2022). **Chile y Argentina**: sin presencia formal localizable más allá de trabajo de tesis
  —**hueco informado, no silencio**. Comparado con APAC, que celebra simposios desde hace años y
  tiene una población nacional mapeada, **LATAM está varios años detrás en uso secundario**: el
  encargo aquí es **construir el primer nodo**, no optimizar uno existente.
- **(2026-11-25 · c8) Contexto de mercado y marco regulatorio, con la cautela debida.** IMARC
  sitúa el mercado LATAM de IA sanitaria en **0,59 B USD en 2025** con un **CAGR del 25,06 %
  (2026-2034)** ⚠️ proyección de informe comercial: dirección, no punto. En **Brasil** sigue **sin
  marco legal unificado de IA**: el uso médico corresponde al **CFM**, los sistemas como
  tecnología a **ANVISA** y **ANPD** (vía IBA). Para un nodo de uso secundario eso convierte a la
  **ANPD y la LGPD en el interlocutor principal**, no a ANVISA — un nodo de investigación no es
  dispositivo médico. Los ministerios de Argentina, Brasil, Chile y Colombia tienen iniciativas
  de fomento de IA en salud: puerta de entrada al sector público.

**[c9 · Investigación clínica] Ausencia TOTAL medida, y por primera vez con mecanismo que la explica.**
Cuatro consultas al canal de precisión — `ANVISA ensaio clinico software`, `ANVISA clinical trial
open source`, `ensaios clinicos plataforma open source`, `CDISC SDTM espanol` — devuelven
**0 repos cada una**. No es escasez: es cero. Y a diferencia de los huecos LATAM de pases
anteriores, **aquí hay una explicación causal y no un retraso regional**: ANVISA no publica un
conjunto de reglas de conformidad ejecutable con sus datos de prueba, como sí hace la FDA vía
`cdisc-open-rules`. Por la ley del oráculo refinada en este pase (*una fórmula no es un oráculo;
hace falta la clave de respuestas publicada*), **la ausencia de oferta es lo que el modelo
predice**. El trabajo no es «ponerse al día»: es que el oráculo aplicable es el global.
**Oferta:** los sponsors de la región someten a FDA y EMA, así que el entregable vendible es
sumisión conforme con CORE como juez — el mismo producto que en NA, sin penalización regional,
porque CDISC es un estándar global. El margen local está en el mapeo y en el idioma, que es el
patrón P19 de este KB (*el mapeo terminológico como producto*).
**Contexto de compra:** Brasil no tiene marco unificado de IA y la supervisión está repartida
—el CFM cubre el uso médico, ANVISA y ANPD los sistemas (análisis de la IBA)—; los ministerios
de salud de Argentina, Brasil, Chile y Colombia han lanzado iniciativas de IA; y el mercado
regional de IA sanitaria se estimaba en USD 0,59 bn en 2025 (IMARC, previsión de *vendor*:
**usar la dirección, no el punto**).
## Gaps verificados — por función, no por silencio

- **(a) No hay capa agéntica permisiva para ciclo de ingresos / denegación de claims.** Lo más cercano
  funcionalmente es openIMIS, que es **AGPL-3.0** y está orientado a seguro público, no a RCM de EEUU.
  Es el mayor hueco build-vs-buy de esta KB y el de mayor presupuesto asociado.
- **(b) No hay tooling FHIR agéntico oficial del NHS.** Se consultó `NHS fhir stars:>=30` y
  `org:nhsdigital stars:>=20`: NHS Digital publica marcos de ingeniería y design system
  (software-engineering-quality-framework 201★ sin licencia, rap-community-of-practice 96★ MIT,
  nhsuk-react-components 79★ MIT) pero **ningún servidor FHIR ni capa de agente**. Gap real frente
  a Alemania, y oportunidad si un cliente UK lo necesita.
- **(c) No hay NLP clínico en español con tracción.** edsnlp es francés (AP-HP); medspacy y openmed son
  anglófonos. Buscado desde el ángulo LATAM y no apareció candidato. Hueco genuino.
- **(d) Porcentajes de adopción por país en APAC**: no parecen existir públicamente a esa granularidad.
  La proyección de IDC (33% de hospitales top para 2030) y el ~30% de conversión de pilotos son los
  únicos números con método encontrados. **Gap informado**, no ausencia de búsqueda.
- **(e) Cuotas de mercado de documentación ambiental**: no hay fuente fiable. Ver advertencia arriba.

## Posicionamiento Globant

1. **La traza de auditoría es el producto, no el modelo.** Tres regiones convergen en exigir evidencia
   por decisión: CFM 2.454/2026 ya en vigor en Brasil, monitorización post-market en el discussion
   paper de la FDA, y responsabilidad institucional en Singapur. Un agente con event log por decisión
   satisface las tres a la vez. El trabajo de cumplimiento **se consolida**: no cobrarlo tres veces.
2. **Probar sin PHI es la ventaja de arranque.** synthea + un servidor FHIR + de-identificación local
   con openmed permiten construir y demostrar antes de firmar un acuerdo de datos. Eso adelanta
   semanas el inicio de cualquier engagement clínico.
3. **Anclar en la especificación del regulador donde exista.** gematik en EMEA y los repos RNDS en
   LATAM permiten decir *"anclado en la spec oficial, no en nuestra interpretación"*. Es verificable
   por el cliente y desarma la objeción de interoperabilidad.
4. **No construir el EMR.** Agente al lado vía FHIR/MCP, nunca fork de la plataforma. Con GPL/AGPL
   además evita heredar obligaciones en el entregable.
5. **Higiene de licencias como entregable.** Ver `compose/patterns.md` P8: la auditoría de procedencia
   de licencias con evidencia de bytes es exactamente el artefacto que un hospital brasileño necesita
   para su registro de riesgo bajo CFM 2.454/2026. Se cobra dos veces por el mismo trabajo.

---

## Pase 2026-11-22 — estructura de la oferta, regulación y huecos

### La estructura de la oferta, medida con 15 consultas

La ley del pase financiero —*el open source permisivo sigue al formato de fichero, no a la
decisión*— **se confirma en salud y se refina**. El refinamiento es la parte útil:

| Capa | Qué hay | Evidencia |
|------|---------|-----------|
| **Formato** (X12, HL7 v2, terminología) | Maduro, permisivo, mantenido | EDI.Net 491★ MIT · stupidedi 293★ BSD-3 · hl7apy 284★ MIT · snowstorm 401★ Apache-2.0 · pyx12 190★ BSD-3 |
| **Juicio ya convertido en especificación** | Existe, es Apache-2.0 y **se forkea más que se estrella** | `org:HL7-DaVinci` = 43 repos · CRD 45★/24f · prior-auth 38★/24f · dtr 23★/18f · clinical-reasoning 52★/46f |
| **Juicio sin especificar** | Nada por encima de ~40★; solo aceleradores de proveedor | `claim denial`→12 resultados, líder 12★ · `claims adjudication`→10, líder 4★ · `medical necessity`→78 resultados y **los seis primeros suman 3 estrellas** |

**El mecanismo nuevo: la frontera se mueve, y se ve venir.** Cuando un regulador convierte un
juicio en un artefacto **computable**, aparece open source permisivo para ese juicio —y
aparece **antes** del mandato. La autorización previa es el caso de prueba en curso: la API es
obligatoria el 2027-01-01 por CMS-0057-F y las implementaciones de referencia Da Vinci llevan
meses publicadas. El vehículo técnico de esa conversión tiene nombre, **CQL**, y tiene motor
permisivo, [cqframework/clinical-reasoning](https://github.com/cqframework/clinical-reasoning)
(Apache-2.0, refs=1067).

Consecuencia operable, y es una posición de inversión, no una observación: **las tareas de
juicio que están a punto de recibir una especificación computable son predecibles**, porque la
guía de implementación se publica uno o dos ciclos de estandarización antes del mandato. Se
vigila el calendario de *ballots* de HL7 y las reglas de CMS, no GitHub.

### La capa que explica el hueco: el conjunto de códigos

Hallazgo independiente y, para una propuesta, el más importante del pase. **Un formato abierto
puede transportar contenido propietario**, y la obligación viaja con el contenido:

- **ICD-10-CM**: dominio público (CMS/NCHS; los CDC publican cada actualización gratis).
- **CPT**: copyright de la AMA con cuotas por usuario; incorporarlo o redistribuirlo en un
  producto exige licencia. Disputa viva en 2026 sobre su paso a dominio público, **sin
  resolver** — no construir un caso de negocio sobre ella.
- **SNOMED CT**: Licencia de Afiliado obligatoria incluso donde es gratuita (54 Miembros),
  con cuotas por banda de renta del Banco Mundial fuera, **y una licencia por país**.
- **LOINC**: gratis con registro.

Por tanto **el hueco (a) del ciclo 5 queda reclasificado**: la ausencia de plataforma
agéntica permisiva de ciclo de ingresos **no es un descuido del mercado, es una imposibilidad
de licenciamiento**, porque la salida del proceso se expresa obligatoriamente en CPT. No se
puede comprar abierta ni construir abierta. Lo que sí se puede es construir la capa de juicio
sobre el conjunto de códigos que el cliente ya licencia — y eso es precisamente la forma de un
*engagement*, no un obstáculo.

### Regulación — lo nuevo o más preciso que en el ciclo 5

**North America.** CMS-0057-F: API de autorización previa el **1-ene-2027** (MA y
Medicaid/CHIP FFS estatal; *managed care* y QHP según periodo de tarificación o año de plan).
Ya vigente en 2026: 72 h urgente / 7 días naturales ordinario, y denegación motivada. **La API
es obligatoria; la guía Da Vinci es recomendada** (STU 2.0.1 y 2.1.0). Modelo **WISeR** desde
enero de 2026: autorización previa asistida por IA en Medicare tradicional, seis estados.
Documento de debate de la FDA sobre IA generativa del **18-ago-2026**, comentarios cerrados el
**19-oct-2026**, expediente **FDA-2026-N-7874**: consulta, no norma.

**EMEA.** El *Digital Omnibus* de 2026 habría movido el plazo de alto riesgo para IA integrada
en productos regulados —dispositivos médicos incluidos— de agosto de 2027 a **agosto de 2028**,
coherente con el Reg. (UE) 2026/1744 ya registrado. Las fuentes secundarias se contradicen
entre sí (una sitúa las obligaciones en agosto de 2026, otra la entrada en vigor a finales de
2027): **la pierna firme sigue siendo MDR/IVDR, que no se movió, más el Art. 50 vigente desde
agosto de 2026.** Evaluación de preparación de **WHO/Europe de 2026**
(WHO-EURO-2026-12707) como fuente institucional. Reembolso estructurado para escalar IA: solo
Alemania y Francia.

**APAC.** **AIHGle 2.0** (MOH + HSA de Singapur, **10-mar-2026**): asigna deberes a
desarrollador, institución y clínico en todo el ciclo de vida. Japón: principios bajo la **Ley
de Promoción de la IA de 2025**, con aprobación de producto por la ley de productos
farmacéuticos y dispositivos. China: software diagnóstico con IA como **Clase III** (NMPA);
precio provincial y compra hospitalaria deciden la adopción. India: sin ley específica de IA,
régimen de dispositivos, **puerta más ligera**. Sandboxes ampliándose en Japón, India,
Singapur y Corea.

**LATAM.** CFM 2.454/2026 **en vigor desde el 10-ago-2026** (reconfirmada). **18 % de los
establecimientos brasileños ya usan IA (25 % privada / 11 % pública)**, y **SUS Digital**
integra IA en el SUS en 2026. ANVISA ya tiene marco SaMD que cubre algoritmos de IA
diagnóstica. Telemedicina operativa: Brasil CFM 2.314/2022, Chile **Ley 21.541**, México
**NOM-024-SSA3**; COFEPRIS avanzando en software médico con IA.

### ⚠️ Marcado explícitamente como NO CITABLE

Se añade a la lista que abrió el ciclo 5:

- **Que el PL 2338 brasileño «ya está vigente y en implementación, con multas de hasta el 2 %
  de los ingresos».** Lo afirma un blog; **contradice el estado legislativo conocido** y no se
  confirmó en fuente oficial. No usar en ninguna propuesta. La norma brasileña citable y en
  vigor es **CFM 2.454/2026**, que es de un consejo profesional, no una ley de IA.
- **El retorno «4× el coste» de la IA de ciclo de ingresos y la adopción «32 %→46 %» en
  autorización previa** (encuesta BVP/Bain citada en prensa sectorial): sin metodología
  publicada. Dirección sí, número ante un CFO no.
- **La previsión de que los agentes de autorización previa gestionarán «70-80 %» de las
  solicitudes de forma autónoma**: guía de proveedor, es previsión y no resultado medido.
- Siguen no citables, del ciclo 5: las cuotas de mercado de documentación ambiental
  (Nuance 33 / Abridge 30 / Ambience 13) y la afirmación de que la FDA autorizó un dispositivo
  diagnóstico autónomo con una RFI de HHS en octubre de 2026.

### Huecos — estado actualizado

| Hueco | Estado tras este pase |
|-------|----------------------|
| (a) Plataforma permisiva de ciclo de ingresos / denegaciones | **Reclasificado, no cerrado.** No es un hueco de mercado sino una imposibilidad de licenciamiento (CPT). Lo único permisivo son aceleradores de proveedor: microsoft/RHAIL-Claims-Denial-Navigator (12★, refs=3), autoauth-solution-accelerator (20★). |
| (b) Tooling FHIR oficial del NHS | **Refinado y peor de lo descrito.** [NHSDigital/NHSEngland-FHIR-SCR-IPS](https://github.com/NHSDigital/NHSEngland-FHIR-SCR-IPS) existe (refs=61) **sin fichero de licencia** (9 variantes comprobadas). Público pero inutilizable. |
| (c) NLP clínico en español con tracción | **Sigue abierto.** Sin hallazgos nuevos este pase. |
| (d) Porcentajes de adopción por país en APAC | **Sigue abierto en APAC**, pero **parcialmente cerrado en LATAM**: Brasil 18 % (25 % privada / 11 % pública). |
| (e) Cuotas de mercado de documentación ambiental | **Sigue sin fuente fiable.** |
| (f) **NUEVO** — Tooling permisivo para ABDM (India) | `ABDM health India stars:>=10` → **1** resultado (11★/1f, MIT). Pila nacional sin ecosistema abierto. Simétrico al hueco del NHS. |
| (g) **NUEVO** — Membresía SNOMED de los grandes países LATAM | **Hueco informado, no silencio.** `snomed.org` no resuelve desde este entorno (política de red). Confirmados Costa Rica, Belice, El Salvador y Jamaica; sin confirmar Brasil, México, Argentina, Chile, Uruguay, Colombia. **Importa porque decide si el contenido se paga.** |

---

## Pase 2026-11-25 — dónde está la aprobación, dónde está el substrato y dónde no hay nadie

### El hallazgo central: aprobación concentrada + substrato permisivo + capa agéntica vacía

Tres mediciones independientes que apuntan al mismo sitio:

| Medición | Valor | Fuente del dato |
|---|---|---|
| Autorizaciones de dispositivos con IA de la FDA que son de radiología | **1 230 de 1 614 = 76 %** (1 212 por 510(k)) | análisis de terceros sobre la lista de la FDA de 2026-09-04 |
| Substrato open source permisivo de imagen | nnU-Net 9 069★ · MONAI 8 865★ · OHIF 4 424★/4 395f · TotalSegmentator 3 183★, **todo Apache-2.0 o MIT** | medido 2026-11-25 |
| Capa agéntica sobre ese substrato | `dicom mcp` **7** · `radiology agent` **9** · `monai agent` **2** | medido 2026-11-25 |

**Es el hueco mejor colocado que la KB de salud ha registrado.** Y es cualitativamente distinto
del hueco del ciclo de ingresos que encontró el ciclo 6: aquel estaba vacío **porque no se puede
licenciar** (la salida se expresa obligatoriamente en CPT, propiedad de la AMA); este está vacío
**sin impedimento**: substrato Apache-2.0/MIT, dato estándar (DICOM) y más de 1 200 precedentes
regulatorios por 510(k). La distinción —**hueco bloqueado frente a hueco abierto**— es la
pregunta que conviene hacerse en las doce industrias antes de proponer una capa de juicio.

### Tamaño de mercado: la dispersión es el dato

Siete casas, mismo objeto, 2026: Mordor **1,03 B USD** · Towards Healthcare **1,14 B** · Roots
**1,17 B** · Future Market Insights **1,2 B** · Fortune Business Insights **1,83 B**. Consenso
razonable: **1-1,2 B USD en 2026, CAGR del 35-45 %**. Los puntos finales no reconcilian:
33,66 B (2035) · 32,76 B (2035) · 51,29 B (2035, SNS Insider) · y **262,68 M (2030, GII, CAGR
7,08 %)**, que define «agéntico» mucho más estrecho. Ante un CFO: **rango y dirección, nunca un
punto**, y nombrar la casa. La serie de Towards Healthcare reproduce exactamente la que el ciclo
3 anotó (1,14 B → 33,66 B, 45,6 %): confirma la fuente, no la convierte en verdad.

### La segunda trampa de licencia del sector, de signo opuesto a la primera

El ciclo 6 estableció que **la licencia del código no es la licencia del contenido** (CPT,
SNOMED CT). Este pase añade la simétrica y completa la taxonomía:

| Trampa | Caso medido | ¿Evitable? | Qué hacer |
|---|---|---|---|
| Contenido propietario sobre formato abierto | CPT en ciclo de ingresos · SNOMED CT fuera de país Miembro (**Brasil y México no son Miembros**) | **No** | El cliente licencia el contenido; Globant entrega la capa de juicio |
| **Infraestructura copyleft bajo modelos permisivos** | **Orthanc GPL-3** y **dcm4che MPL** debajo de MONAI/OHIF | **Sí** | Separación de procesos: el copyleft se alcanza sólo por DICOMweb/HTTP |
| **Licencia propia «estilo BSD»** | **`Slicer/Slicer`**: acuerdo del Brigham, 10514 B, no OSI | Sí, con lectura legal | Revisión jurídica antes de incorporar |
| Sin fichero de licencia | `fo-dicom` (1220★) · `NHSDigital/...-FHIR-SCR-IPS` · `OpenClaw-Medical-Skills` (3128★) · `yhzhu99/HealthFlow` | — | **No entra**: es «todos los derechos reservados» |

La primera trampa **reubica el negocio**; la segunda es **media hora de arquitectura**. Confundirlas
cuesta una propuesta.

### Estructura de la oferta: el sector tiene dos poblaciones, y la razón ★/forks las separa

Con 30 repos medidos de golpe, la regla del ciclo 6 se afina: razón **< 1** = **sistema que una
institución opera** (openmrs-core 0,44 · OpenELIS 0,43 · Bahmni 0,48 · canvas-hyperscribe 0,43 ·
dhis2-core 0,88); **≈ 1** = infraestructura desplegada y vista (**OHIF 1,006**); **3-6** =
librería/modelo de adopción legítima (MONAI 5,1 · nnU-Net 3,6); **> 50** = atención sin uso
(`fabric-mlv-...-starter` **149**). Implicación de *sourcing*: **DHIS2 tiene 361 estrellas y lo
usan los ministerios de salud de más de 80 países.** Filtrar por estrellas descarta justo los
sistemas que los compradores institucionales ya operan.

### ⚠️ Marcado explícitamente como NO CITABLE en este pase

Se añade a la lista de los ciclos 5 y 6:

1. **«#1 en trending» de cualquier tracker de terceros.** Caso medido:
   `pavanbadempet/AI-Healthcare-System` encabezó una lista de noviembre y tiene **81★/19f y
   AGPL-3.0**. El ranking no describe tamaño ni usabilidad.
2. **Las cifras de coste de Berta (< 30 USD/médico/mes, 7,6 min, 42 %)** son **de los autores**,
   con artículo aceptado pero no independiente. Sirven para encuadrar un build-vs-buy; no para
   garantizar un número en contrato.
3. **El recuento de países de DHIS2.** >80 (registro de Digital Public Goods, BID; uso
   ministerial) frente a >100 (web del proyecto). Usar **«más de 80 ministerios»**.
4. **La publicación en el Diario Oficial del Digital Omnibus.** Hubo acuerdo político provisional
   el 2026-05-07 pendiente de adopción formal y **no se ha confirmado** su publicación. No
   construir urgencia sobre la fecha del Anexo I.
5. **El Decreto de Aplicación de la AI Basic Act coreana**: las fuentes dan enero de 2026 y una
   modificación de julio de 2026. La **fecha de efecto de la ley (2026-01-22) sí es consistente**.
6. Siguen no citables, sin cambio: las cuotas de documentación ambiental (Nuance/Abridge/Ambience),
   el retorno «4x» del ciclo de ingresos y la previsión de «70-80 %» de autorizaciones autónomas.

### Huecos — estado al 2026-11-25

| Hueco | Estado |
|---|---|
| (a) Plataforma agéntica permisiva de ciclo de ingresos | **Reclasificado y confirmado**: imposibilidad de licenciamiento (CPT), no descuido de mercado |
| (b) Tooling FHIR del NHS sin licencia | **Abierto, sin cambios.** Contrasta ahora con India, que publica **con** licencia pero sin mantenimiento |
| (c) NLP clínico en español | **Refinado, sigue abierto**: lo permisivo está abandonado (PlanTL, sin push desde 2022) y lo vivo es GPL-3 y de un autor |
| (d) Adopción con granularidad de país | **LATAM parcialmente cerrado** (Brasil 18 %; serie regional 14 %→20 %). **APAC cerrado en lo esencial**: HIMSS 46 % en 13 mercados, coste 67 %, y **~30 % de pilotos a producción** |
| (e) Cuotas de documentación ambiental | **Sigue sin fuente citable.** Pero el plano abierto de la categoría **sí** está ahora cubierto (Berta, OpenScribe, canvas-hyperscribe) |
| (f) Tooling permisivo de ABDM (India) | **Mayormente cerrado y reclasificado**: la NHA publica Apache-2.0 (`ABDM-wrapper`, refs=37, oculto a `search`), pero **parado desde 2024**. El encargo es adoptar y mantener |
| (g) Membresía SNOMED de los grandes países LATAM | **Cerrado en lo que decide el presupuesto**: Argentina, Chile y Uruguay son Miembros; **Brasil, México y Colombia no aparecen** en la lista. ⚠️ Fuentes secundarias; `snomed.org` no resuelve desde la sesión |
| (h) **NUEVO** — capa agéntica sobre imagen médica | **Abierto y es el mejor colocado del sector**: 7/9/2 resultados sobre un substrato de 9 000★ con 1 212 precedentes 510(k) |
| (i) **NUEVO** — tracker público de preparación de pagadores para CMS-0057-F | **Abierto, y es un hueco informado**: a 37 días del 1-ene-2027 **no existe ningún recuento público** de qué pagadores llegan. Quien lo tenga, tiene la conversación |

## Pase 2026-11-25 (c8) — un mandato sin artefacto no converge: la ley del ciclo 6, corregida

### El hallazgo central: la frontera de la especificación necesita DOS condiciones, no una

El ciclo 6 dejó formulada una ley (**P12**): *cuando un regulador convierte un juicio en
artefacto computable, aparece open source permisivo para ese juicio, y aparece **antes** del
mandato*. El caso que la sostenía era **CMS-0057-F**: la regla exige API de autorización previa
el 2027-01-01 y `org:HL7-DaVinci` ya tenía **43 repos Apache-2.0** con **más forks que
estrellas**. Este pase trae el **contraejemplo que la corrige**, y es un contraejemplo limpio
porque la variable que cambia es exactamente una.

El **EHDS** (Reglamento (UE) 2025/327) tiene **todo** lo que tenía CMS-0057-F —rango de
reglamento, fechas firmes (**2027-03-26** autoridades de acceso, **2029-03-26** uso secundario,
**2031-03-26** genómica y ensayos), obligaciones sobre los tenedores del dato y sanciones— y le
falta **una sola cosa**: **no nombra estándar técnico**. FHIR, OMOP CDM y openEHR siguen los tres
en discusión y **no se espera mandato formal**. Resultado, medido hoy:

| Consulta | Resultado | Lectura |
|---|---|---|
| `ehds stars:>=5` | **4 repos** | El mayor tiene **16★** y licencia `NOASSERTION` |
| `ehds health data space` | 9 repos | **Seis sin fichero de licencia**; hay una tesis, un hackathon y un trabajo de curso |
| `org:HL7-DaVinci` (CMS-0057-F, ciclo 6) | **43 repos Apache-2.0**, forks > estrellas | Implementaciones que se despliegan |

**A 4 meses de la designación de autoridades de acceso y a 28 del grueso del uso secundario, el
EHDS no ha producido un solo repo permisivo con tracción.** Y no es que el substrato no exista:
`org:OHDSI` tiene **398 repos** con razones ★/forks por debajo de 2 en bloque. Existe y está
maduro — **lo que no existe es la convergencia hacia él**, porque nadie ha dicho que sea él.

> **P12 corregido.** Para que aparezca open source permisivo antes del mandato hacen falta
> **dos** condiciones: **(1)** que el regulador declare la obligación **y (2)** que un organismo
> publique un **artefacto computable** al que implementar. CMS-0057-F cumple ambas (regla + IG de
> Da Vinci + CQL). El EHDS cumple **sólo la primera**. **Condición 1 sin condición 2 no produce
> convergencia: produce fragmentación nacional.** Esto es reutilizable en las doce industrias y
> explica por qué algunos mandatos generan ecosistema y otros generan 27 proyectos distintos.

**Predicción falsable registrada:** los actos de ejecución de la Comisión vencen el
**2027-03-26**. Si nombran un modelo de datos, debe aparecer tooling permisivo específico de
EHDS en **1-2 ciclos de estandarización** tras la publicación, con **forks subiendo antes que
estrellas**. Si no lo nombran, lo que debe crecer son los **mapeadores** entre modelos, no las
implementaciones de EHDS. Las dos ramas son observables con una consulta.

### Qué hacer con una apuesta no resuelta: la arquitectura es la cobertura

No se puede vender certeza sobre qué modelo elegirá cada Estado miembro. Lo que sí se puede
vender —y es más defendible— es **el nodo cuya capa de mapeo está aislada**: OMOP como modelo de
análisis (porque es donde está el tooling), FHIR en el borde (porque es donde está el dato de
origen) y la **traducción como artefacto versionado y propio del cliente**. Si el acto de
ejecución nombra OMOP, el cliente ya está. Si nombra openEHR, se sustituye una capa y no el
sistema. **Es exactamente el patrón «MT564 en el borde, seev.031 en el dominio» del pase
financiero**, con otros nombres. Ver `compose/patterns.md` **P17**.

### Estructura de la oferta: tercera medición del mismo patrón, y el más extremo

| Plano | Substrato permisivo | Capa agéntica | Ratio |
|---|---|---|---|
| Imagen médica (ciclo 7) | MONAI 8 865★, nnU-Net 9 069★, OHIF 4 424★ | `dicom mcp`→7, `radiology agent`→9, `monai agent`→2 | vacía |
| **Uso secundario (este pase)** | **`org:OHDSI` 398 repos**, razones ★/f **por debajo de 1** en cuatro | **`omop agent stars:>=5` → 2** | **la más vacía** |
| Ciclo de ingresos (ciclo 6) | Capa de formato madura (X12, hl7apy…) | `medical necessity`: 6 primeros = 3★ en total | vacía **y bloqueada** |

Tres planos, tres veces el mismo diagnóstico, **y la distinción del ciclo 7 sigue siendo la que
decide dónde invertir**: imagen y uso secundario son **huecos abiertos** (substrato permisivo,
dato estándar, nada que lo impida); ciclo de ingresos es **hueco bloqueado** (el resultado se
expresa obligatoriamente en CPT, que es propiedad de la AMA). **Uso secundario tiene además algo
que imagen no tiene: fechas de obligación legal en el calendario europeo.**

### ⚠️ Marcado explícitamente como NO CITABLE en este pase

1. **Las fechas del EHDS, como dato contractual.** Las de arriba son síntesis de notas de
   despachos jurídicos, muy consistentes entre sí pero **no el Diario Oficial**. Las fuentes
   además **discrepan** sobre qué categorías exactas se aplazan a 2031 (una dice dato genómico,
   otra «factores que afectan a la salud»). Dirección y orden de magnitud sí; **antes de un
   contrato, contra el texto del Reglamento (UE) 2025/327**.
2. **Que «OMOP es el estándar del EHDS».** Es una **propuesta** de la comunidad OHDSI Europa
   (Rijnbeek), no política establecida; el propio resumen de su community call de marzo de 2026
   dice que el EHDS **no impone** modelo. El paper IDERHA de JMIR Formative 2026 recomienda una
   colección de estándares centrada en OMOP **y a la vez** le señala límites en descubribilidad de
   metadatos, identificadores globales, control de acceso y **licenciamiento**. Citar como
   candidata con mejor tooling, nunca como norma.
3. **Las cifras de red de OHDSI (HIRA toda la población, KIDSNet 1,69 M, AHDEN).** Provienen de
   slides de la propia comunidad y **algunas páginas están sin fechar**; las listas de capítulos
   APAC **no coinciden entre sí** (una incluye China, India, Indonesia; otra incluye Vietnam y no
   esas tres). Sirven para dimensionar, no para un anexo.
4. **El 0,59 B USD / CAGR 25,06 % de IMARC para LATAM** y el **44,5 %** de cuota norteamericana:
   informes comerciales sin metodología publicada.
5. **El 94 % de proveedores europeos y la dependencia de soluciones extra-UE**: es de un estudio
   de la Comisión Europea —la fuente institucional más fuerte del pase— pero **no he abierto el
   estudio**, sólo su resumen en la página de la Comisión. Citable con atribución; verificar el
   número en el PDF antes de ponerlo en una portada.
6. **Sigue sin fuente citable** (hueco (e)): las cuotas de mercado de documentación ambiental.

### Huecos — estado al 2026-11-25 (c8)

| Hueco | Estado |
|---|---|
| (a) Capa agéntica de ciclo de ingresos | **Bloqueado, sin cambios** (imposibilidad de licenciamiento CPT) |
| (b) Tooling FHIR del NHS sin licencia | **Abierto, sin cambios.** Ahora con dos contraejemplos nacionales medidos: gematik (Apache-2.0) y Dinamarca (MIT) |
| (c) NLP clínico en español | **Abierto y RE-MEDIDO sin cambios** (2 resultados, sin push desde 2022). **Reclasificado**: es el mismo hueco que el vocabulario OMOP en español/portugués, y ahora tiene comprador identificado |
| (d) Adopción con granularidad de país | **APAC cerrado y ampliado** (Corea, Australia, Japón con nombres y escalas). **LATAM ampliado** (Brasil lidera; Chile y Argentina sin presencia formal) |
| (e) Cuotas de documentación ambiental | **Sigue sin fuente citable** |
| (f) Tooling permisivo de ABDM (India) | **Sin cambios** respecto del ciclo 7 |
| (g) Membresía SNOMED de grandes países LATAM | **Cerrado y ahora CORROBORADO por una segunda vía**: OHDSI Brasil nombra la escasez de vocabulario adecuado como su principal dificultad |
| (h) Capa agéntica sobre imagen médica | **Abierto, sin cambios** (ciclo 7) |
| (i) Tracker público de preparación de pagadores CMS-0057-F | **Abierto**; a **37 días** del 2027-01-01 |
| (j) **NUEVO** — capa agéntica sobre uso secundario / OMOP | **Abierto y es ahora el más extremo de la KB**: `omop agent stars:>=5` → **2** sobre 398 repos de substrato desplegado |
| (k) **NUEVO** — mapeo terminológico OMOP para pt-BR y es | **Abierto, con comprador y con causa raíz identificada.** Herramienta gratis (Usagi/WhiteRabbit, Apache-2.0), contenido ausente. **El entregable con margen del plano en LATAM** |
| (l) **NUEVO** — tooling permisivo específico de EHDS | **Abierto, y es un hueco INFORMADO de los valiosos**: el mayor repo «EHDS» tiene 16★ y `NOASSERTION`. No es descuido: **es consecuencia de que el reglamento no nombre artefacto** (ver arriba) |

---

## Pase 2026-11-25 (c9) — una fórmula no es un oráculo: la ley del ciclo 8, corregida por experimento controlado

### El hallazgo central

El pase c8 (esta mañana) estableció que la frontera de la especificación necesita **dos**
condiciones: mandato **y** artefacto. Este pase, en un plano nuevo, encuentra el caso que
**separa el artefacto en dos cosas distintas** y obliga a refinar la ley una vez más.

La investigación clínica contiene dos subplanos que comparten industria, año, lenguaje y
comunidad, y difieren en **una sola** propiedad:

| | Sumisión regulatoria (CDISC) | Farmacovigilancia |
|---|---|---|
| Fórmula / estadístico público | sí (reglas de conformidad) | sí (PRR, ROR, BCPNN) |
| Formato de intercambio público | sí (SDTM/ADaM, Dataset-JSON) | sí (ICH E2B(R3)) |
| Mandato regulatorio | sí (FDA, EMA, PMDA) | sí (y con responsabilidad penal en algunos regímenes) |
| **Salida esperada publicada (fixture)** | **SÍ** (`cdisc-open-rules`: reglas **+ datos de prueba**, MIT) | **NO** |
| **Oferta permisiva medida** | **176 repos**, hasta 328★, push diario | **0 adoptables**, máximo 1★ |

Todo coincide menos el fixture, y el resultado se invierte por completo.

> **Ley corregida: una FÓRMULA NO ES UN ORÁCULO. Un oráculo es una SALIDA ESPERADA PUBLICADA.**
> Mientras nadie publique la respuesta correcta contra la que medirse, el mandato y el formato
> no generan oferta permisiva: generan consultoría propietaria.

Esto importa porque **confirma en una segunda industria, por vía independiente, el patrón P29
del pase financiero («el fixture es el entregable»)**. Allí se derivó del cálculo de capital
bancario; aquí aparece solo, en salud, desde el lado opuesto. Dos industrias no relacionadas,
misma ley: deja de ser una observación de un plano y pasa a ser **regla transversal a las doce
industrias de esta KB**. Y es inmediatamente operativa: ante un plano nuevo, la primera pregunta
ya no es «¿hay mandato?» ni «¿hay formato?», sino **«¿alguien publica la respuesta correcta?»**.
Si la respuesta es no, el entregable de Globant **es publicar el fixture**.

### Estructura de la oferta: cuarta medición del patrón, y la línea de licencia es funcional

| Organización / consulta | Repos | Lectura |
|---|---|---|
| `org:OHDSI` | 398 | Uso secundario (c8) |
| `org:pharmaverse` | 86 | Sumisión, mantenido por GSK/Roche/Atorus |
| `org:atorus-research` | 48 | Sumisión |
| `org:cdisc-org` | 42 | El estándar y su motor |
| `SDTM agent LLM` | **4** | La capa de arriba |
| `ADaM automation LLM` | **2** | La capa de arriba |

Y el hallazgo arquitectónico del pase, que no es una métrica sino una línea:

> **La frontera de licencia de este plano cae entre CAPTURAR y SOMETER.** Captura (EDC/LIMS):
> OpenClinica 519★ **sin fichero de licencia** y 13 meses parado, LibreClinica GPL, senaite
> GPL-2.0, REDCap **no open source**. Sumisión: Apache-2.0 y MIT, mantenido por las farmacéuticas,
> con push diario. Se integra la captura; se construye en la sumisión.

### ⚠️ Marcado explícitamente como NO CITABLE en este pase

- **El recuento de reglas de CORE v1.0** (se leyó «500 reglas SDTM y 183 reglas FDA» en un
  snippet de buscador). La existencia del release **sí** está verificada en canal primario: el
  tag `v1.0.0` aparece en `git ls-remote --tags`. **El número de reglas, no.** No usar en
  propuesta sin contarlas en `cdisc-open-rules`.
- **La fecha exacta de release de CORE v1.0** (un secundario la da como 4 de noviembre de 2026).
  No verificada: `verisian.com` **no resuelve desde esta sesión** y habría que permitirlo en la
  configuración de red del entorno para comprobarlo.
- **El requisito CDISC de PMDA (Japón)**. Es conocido y casi con seguridad correcto, pero no se
  verificó en fuente primaria en este pase.
- Cifras de mercado de *vendor* usadas sólo por su dirección: USD 0,59 bn LATAM 2025 y 25,06%
  CAGR (IMARC); 44,5% de cuota NA 2025; 94% de proveedores UE (estudio de la Comisión, marzo 2026).
- Encuestas de proveedor/consultora citadas como lo que son: AMA 81% de médicos, HIMSS 46%/67%,
  Roche ~30% de PoC a producción, IDC 75%.

### Huecos — estado al 2026-11-25 (c9)

| Hueco | Estado |
|---|---|
| Capa agéntica sobre sumisión regulatoria (SDTM/ADaM) | **ABIERTO y cuantificado**: 176 repos debajo, 2 encima. El mejor hueco medido del plano |
| Farmacovigilancia agéntica permisiva | **ABIERTO y explicado**: falta el fixture, no el formato. Máximo 1★ |
| Tooling CTIS (EMEA) | **ABIERTO**: 3 repos en total, el único activo tiene 0★ |
| Tooling de sumisión APAC (PMDA/NMPA) | **ABIERTO**: 0 repos |
| Tooling de investigación clínica LATAM | **CERO medido**, con mecanismo: ANVISA no publica clave de respuestas. No implica retraso |
| Emparejamiento paciente-ensayo adoptable | **PARCIAL**: TrialMatchAI (MIT) y trialthread (Apache-2.0) sirven; **toda la familia MatchMiner, no** |

---

## Pase 2026-11-25 (c10) — el plano del dispositivo: la demanda ya está probada, la oferta ya está en copyleft, y la puerta regulatoria se cruzó una vez

### El hallazgo central: la razón ★/forks tiene una tercera banda, y es la que mide demanda

El ciclo 6 estableció la prueba barata de autenticidad: razón **estrellas/forks ≈ 1** = gente que
despliega; **> 50** = atención sin uso. Este plano obliga a añadir el extremo opuesto, y es el más
informativo de los tres para una propuesta:

| Banda | Qué significa | Medido en este plano |
|---|---|---|
| Forks ≫ estrellas (razón ★/f < 0,1) | **Usuarios finales autodesplegando.** El fork es la instalación, no la contribución | `cgm-remote-monitor` 2.867★/**73.399f**; `LoopWorkspace` 316★/**8.859f** |
| Razón ≈ 1 | Desarrolladores que despliegan e integran | `oref0` 487/406; `LoopKit` 423/429; `mdpnp` 145/79 |
| Razón > 50 | Atención sin uso | La capa agéntica del plano: tops de 44★/8f y 12★/1f |

**La consecuencia comercial es directa y poco habitual:** en los nueve pases anteriores esta KB
tenía que *argumentar* que había demanda. Aquí la demanda está **contada**: 73.399 instalaciones
de pacientes que se automontaron su propia monitorización remota porque el mercado no se la dio.
Lo que falta no es validación de mercado, es **un producto con licencia utilizable y un responsable
regulatorio**. Y eso es exactamente lo que el sector ha resuelto **una sola vez**.

### El segundo hallazgo, y el más vendible: cómo se cruzó la puerta regulatoria

**Tidepool Loop es el único caso medido en esta KB de open source sanitario que atraviesa una
autorización regulatoria.** La FDA lo autorizó el **2023-01-23**, descrito en la literatura como
*la primera autorización regulatoria de un algoritmo open source de administración automatizada de
insulina*. Los hechos relevantes, y el mecanismo que se puede repetir:

| Hecho | Dato |
|---|---|
| Autorización | FDA, **2023-01-23** (alguna fuente da el 24: desfase de publicación) |
| Sumisión | finales de **2020** → ~2 años de ciclo |
| Qué se autorizó | **Una versión congelada**, no «el open source de AID». La autorización no avala el enfoque en general |
| Quién firmó | **Tidepool, una organización sin ánimo de lucro**, que añadió los controles regulatorios sobre código construido por la comunidad |
| Distribución comercial | A través de un socio: Sequel Med Tech, como *twiist Loop* |
| Estado hoy | **Loop 2.0 sometido en julio de 2026, en revisión**; Loop 3.0 en desarrollo, no sometido |

**La ley que sale de aquí, y complementa a P12 sin sustituirla:** P12 dice *dónde* aparecerá oferta
permisiva (donde el regulador convierte un juicio en artefacto computable). Este caso dice *cómo se
cruza la puerta*: **no con una licencia ni con una especificación, sino con una entidad dispuesta a
firmar la sumisión de una versión congelada y a sostener su ciclo de vida.** El código abierto no
se autoriza; se autoriza un artefacto con dueño. Patrón P27.

Lo que esto prohíbe prometer en una propuesta: *«lo liberamos y lo certificamos»* como un solo
movimiento. Son dos, el segundo dura unos dos años y exige un titular.

### Regulación de este plano, por región — el estado medido

#### North America

- **FDA §524B (FD&C Act)**: toda sumisión de un *cyber device* (510(k), PMA, De Novo, PDP, HDE)
  debe incluir un **SBOM legible por máquina** que cubra componentes comerciales, **open source** y
  *off-the-shelf*. Si no se puede aportar, hay que **justificar la omisión** en la sumisión.
  Guía final de ciberseguridad premarket de 2023, borrador de *Select Updates* de marzo de 2024.
- **La guía que decidiría el resto sigue sin finalizar:** el borrador de la FDA de **enero de 2025**
  sobre gestión del ciclo de vida y sumisiones de *AI-enabled device software functions*
  —considerado la piedra angular de la regulación de dispositivo con IA— **seguía sin finalizarse**
  a 2026 (guía Chambers Healthcare AI 2026). *El matiz de la regla P9, aplicado otra vez: la
  obligación de SBOM es ley; la guía de IA es borrador. No se dicen con la misma voz.*
- **Hospital a domicilio: plazo resuelto hasta 2030.** El *Acute Hospital Care at Home* expiró
  durante el cierre de gobierno de 43 días, se puenteó hasta el **2026-01-30**, y la **Consolidated
  Appropriations Act de 2026 (H.R. 7148)** lo extendió hasta el **2030-09-30**, con informe del
  Secretario de HHS exigido para el **2029-09-30**. Pasa de riesgo regulatorio a **horizonte de
  inversión de cuatro años**: es el cambio de contexto más favorable del pase.
- Adopción: **81 %** de los médicos encuestados declara uso profesional de herramientas de IA
  (encuesta AMA 2026, más del doble que en la primera medición). Por segmento (Menlo Ventures,
  2025): sistemas de salud **27 %**, ambulatorio **18 %**, pagadores **14 %**. Norteamérica fue el
  **44,5 %** del mercado global de IA en salud en 2025.

#### EMEA

- **La fecha del AI Act para dispositivo tiene por fin mecanismo, y corrige la nota del ciclo 6.**
  El ciclo 6 registró que «las fuentes secundarias se contradicen entre sí» sobre el Digital
  Omnibus. Hoy hay un **acuerdo político del 2026-05-07**: las tecnologías médicas **siguen dentro**
  de los requisitos de alto riesgo del AI Act, y la aplicación para sistemas de alto riesgo
  **integrados en productos** se posterga del **2026-08-02** al **2028-08-02**.
- **Y el punto que decide la arquitectura:** el Omnibus confirma que **la evaluación de conformidad
  sectorial (MDR / IVDR) tiene precedencia** para los sistemas de alto riesgo integrados en
  productos. MedTech Europe pedía que todo se tramitara vía MDR/IVDR y **no lo obtuvo**, así que
  queda duplicidad. *La pierna firme sigue siendo MDR/IVDR, por tercer pase consecutivo.*
- El artículo 60 (ensayo en condiciones reales) se extiende a los productos del anexo I sección A,
  **dispositivos médicos e IVD incluidos**.
- **No resuelto:** una propuesta separada de DG SANTE excluiría del todo a los dispositivos médicos
  con IA del marco de alto riesgo, reintroducibles luego por actos delegados. La interacción entre
  ambas propuestas estaba **sin resolver**, y **ninguna fuente confirma publicación en el Diario
  Oficial**: es acuerdo político, no norma adoptada. No construir el caso sobre la fecha de 2028.
- Adopción: estudio de la Comisión de **marzo de 2026**: **94 %** de los proveedores sanitarios usa
  o planea usar IA, con dependencia declarada de soluciones **desarrolladas fuera de la UE**. La
  OCDE recomienda consolidar la guía de GDPR + MDR + AI Act, hoy dispersa.

#### APAC

- **Nuevo y no estaba en esta KB: Corea del Sur.** La **AI Basic Act** (Ley Marco de IA) entró en
  vigor el **2026-01-22**, junto con su Decreto de Aplicación el mismo día, y es el primer régimen
  integral de Asia. **Los dispositivos médicos son dominio de «alto impacto» nombrado
  explícitamente** (art. 2(1) de la Ley de Dispositivos Médicos, más los dispositivos médicos
  digitales). Obligaciones de aseguramiento: identificación, evaluación y mitigación de riesgo a lo
  largo del ciclo de vida, más deber de transparencia (notificar que hay IA). El MSIT ha publicado
  guías de determinación de alto impacto.
- **El hueco de Corea, dicho explícitamente:** no hay **una autoridad supervisora primaria única**
  bajo ese régimen (DLA Piper), y la prensa local recoge que los términos vagos dejan a las empresas
  sin criterio operativo. **Para un *engagement*, eso es lo contrario de una barrera: el entregable
  que se vende es el expediente que demuestre el ciclo de vida**, porque nadie ha fijado el formato.
- Adopción medida: encuesta HIMSS APAC 2026 (200 clínicos, TI y directivos, **13 mercados**):
  **46 %** arrancó sus programas de IA **en los últimos 12 meses**; **67 %** señala el coste como
  obstáculo principal. Roche: sólo **~30 %** de las pruebas de concepto de IA sanitaria en APAC
  llegan a producción clínica. IDC: **75 %** de los proveedores de Asia-Pacífico dice que la IA
  agéntica da más productividad que la GenAI.
- Substrato propio: `vitaldb/vitalutils` (BSD-3, Seoul National University) para señal
  intraoperatoria. Precedente institucional muerto: los dos repos de Code for Japan (AGPL-3.0,
  sin push desde 2022-01-31).

#### LATAM

- **ANVISA ya regula el software con IA, y lleva haciéndolo desde antes del debate:** **RDC
  657/2022** es la norma específica de *software como dispositivo médico* (en vigor desde el
  **2022-07-01**) y **RDC 751/2022** aplica a todo dispositivo médico, SaMD incluido. Según la
  propia presentación de ANVISA al Congreso, la agencia **ya regula SaMD con IA** y la **revisión de
  la RDC 657 traerá mecanismos específicos** para nuevas tecnologías de IA; el software con IA debe
  aportar **justificación técnica del método** empleado.
- **El dato negativo del pase, oficial y fechado, y mata un atajo que se vende mucho:** en
  **agosto de 2026**, Agência Gov citando a ANVISA, **no existe en Brasil ningún software médico
  regularizado para usar sólo datos de anillos inteligentes**, y los equipos de **medición no
  invasiva de glucosa u oximetría no están regularizados**. El puente «wearable de consumo →
  dispositivo clínico» **está explícitamente cerrado en el mercado más grande de la región**.
- ANVISA abrió en 2026 un **nuevo edital de evaluación regulatoria de dispositivos médicos
  innovadores**: es la vía de entrada correcta para producto nuevo.
- Substrato propio: `antonior92/automatic-ecg-diagnosis` (MIT, UFMG, cohorte CODE), sin push desde
  2023-03-25.
- Marco profesional: **CFM 2.454/2026**. *Discrepancia de fuentes no resuelta:* esta KB registró
  vigencia desde **2026-08-10**; un análisis jurídico de 2026 la da como publicada el **27-02-2026**
  con vigencia prevista en **septiembre de 2026**. Se cita la resolución, **no la fecha**.

### Oportunidades de este plano, por región

#### North America — el encargo es el expediente, y la fecha ya no aprieta

Combinación única: obligación de SBOM **vigente** (§524B), guía de IA **sin finalizar** (nadie
puede exigir un formato que no existe), y hospital a domicilio **asegurado hasta 2030-09-30**.
El entregable con margen es la **puerta de cumplimiento del ciclo de vida del dispositivo**
(P26): SBOM por build con herramienta Apache-2.0, VEX, y la trazabilidad que la sumisión pedirá.
Se vende hoy y sobrevive a la finalización de la guía porque el artefacto obligatorio no cambia.

#### EMEA — vender la pierna firme, nunca la fecha de 2028

El plazo de alto riesgo integrado en producto se movió a **2028-08-02** por acuerdo político **no
confirmado en el Diario Oficial**, y hay una propuesta de DG SANTE que podría excluir el caso.
**Quien construya sobre la fecha se queda sin propuesta si la fecha se mueve otra vez.** Se vende
**MDR/IVDR**, que tiene precedencia reconocida en el propio Omnibus y no se ha movido en tres
pases. Oportunidad concreta: el **94 %** de proveedores que usa o planea IA depende de soluciones
de fuera de la UE — hay espacio para integración con soberanía de dato, y `ehrbase` (Apache-2.0)
es la base openEHR cuando el cliente es alemán o nórdico.

#### APAC — el vacío de criterio es el producto

Corea obliga desde **2026-01-22** con dispositivos médicos como alto impacto **y sin autoridad
supervisora única**; Singapur (AIHGle 2.0, registrado en el ciclo 6) asigna deberes por fase;
y sólo **~30 %** de las pruebas de concepto cruzan a producción. Las tres cosas apuntan al mismo
entregable: **matriz de responsabilidades por fase del ciclo de vida más expediente de riesgo**,
que es lo que convierte un piloto en despliegue. Es el mismo producto que Singapur ya pedía, ahora
con un segundo país que lo exige por ley. Substrato local permisivo disponible (VitalDB, BSD-3).

#### LATAM — vender regularización, no wearable

ANVISA tiene marco SaMD maduro (RDC 657/2022 + 751/2022), exige **justificación técnica del
método** para IA, y ha declarado en agosto de 2026 que **no hay** software regularizado basado solo
en anillos ni equipos de glucosa/oximetría no invasiva. La oportunidad **no** es llevar un wearable
de consumo a la clínica: es **acompañar la regularización** por el edital de dispositivos
innovadores y construir sobre señal con procedencia (el ECG de UFMG es MIT y brasileño). Y el
argumento para el sector público sigue siendo el del ciclo 6: comprador privado con presupuesto
(25 % frente a 11 % público en Brasil), SUS Digital como vía pública.

### ⚠️ Marcado explícitamente como NO CITABLE en este pase

1. Que la FDA ponga en **retención técnica** (*technical hold*) en eSTAR las sumisiones 510(k) con
   SBOM ausente, y que **rechace la aceptación** por SBOM inadecuado: lo afirman blogs de
   proveedores de cumplimiento, **no verificado contra fuente FDA**. La obligación legal de §524B
   sí es citable; el mecanismo operativo de rechazo, no.
2. El estado **final** de la guía premarket de ciberseguridad «2025» alojada en HHS: no se confirmó
   desde una página de la FDA. Citar la final de 2023 y el borrador de marzo de 2024.
3. La fecha del **2028-08-02** del AI Act como norma vigente: es **acuerdo político del
   2026-05-07**, sin confirmación en el Diario Oficial. Dirección sí, obligación no.
4. Las cifras de adopción de IDC (**75 %**), Roche (**~30 %**) y HIMSS (**46 % / 67 %**, n=200):
   son encuestas de proveedor y consultora **sin metodología publicada en la fuente consultada**.
   Dirección sí, punto ante un CFO no. Igual que la cifra AMA del **81 %** y los cortes de Menlo.
5. La fecha de entrada en vigor de **CFM 2.454/2026**: dos fuentes secundarias se contradicen
   (agosto frente a septiembre de 2026). Citar la resolución sin fecha.
6. Siguen no citables, de pases anteriores: las cuotas de documentación ambiental
   (Nuance 33 / Abridge 30 / Ambience 13), el retorno «4x» del ciclo de ingresos, y la afirmación
   de que el PL 2338 brasileño está vigente con multas.

### Huecos — estado al 2026-11-25 (c10)

| Hueco | Estado |
|---|---|
| (a) Plataforma agéntica permisiva de ciclo de ingresos | **RECLASIFICADO** (imposibilidad de licencia: CPT). Sin cambio |
| (b) Tooling FHIR del NHS sin licencia | **ABIERTO**, sin cambio |
| (c) NLP clínico en español | **ABIERTO**, sin hallazgos nuevos este pase |
| (d) Granularidad de adopción LATAM | **PARCIAL**: Brasil 18 % (c6) + negativa oficial de ANVISA sobre anillos y glucosa no invasiva (c10) |
| (e) Cuotas de documentación ambiental | **ABIERTO**, sin fuente |
| (f) Tooling permisivo para ABDM (India) | **PARCIAL** (c7 lo recuperó de un falso negativo de canal) |
| (g) Membresía SNOMED de los grandes países LATAM | **ABIERTO**: `snomed.org` sigue sin resolver desde este entorno |
| (h) **NUEVO** — Documentación regulatoria de dispositivo: permisiva **o** mantenida, no ambas | **ABIERTO y colocable**: `innolitics/rdm` MIT parado desde 2022-10; `openregulatory/templates` activo pero **CC-BY-NC-SA** |
| (i) **NUEVO** — Plataforma RPM permisiva y viva | **ABIERTO**: 1.049 repos en `remote patient monitoring`; el más estrellado con contenido genuino tiene **40★, es AGPL-3.0 y está parado desde 2022-01-31** |
| (j) **NUEVO** — Comunicación de dispositivo (IEEE 11073) | **ABIERTO**: 30 repos; la implementación de referencia (`signove/antidote`) es LGPL y **sin push desde 2021-05-14** |
| (k) **NUEVO** — Vínculo sanitario del SBOM | **ABIERTO, y es el de mejor relación esfuerzo/valor**: las cinco herramientas que producen el artefacto son Apache-2.0 y **ninguna es de salud** (`medical device SBOM` = 12 repos) |

---

## Pase 2026-11-25 (c11) — el plano del medicamento: dónde está el margen y por qué no puede ser «todo abierto»

### El hallazgo central: el hueco más grande del sector coincide con la mayor disposición a pagar, y con la imposibilidad de entregarlo abierto

| Sub-plano | Obligación legal | Licencia del contenido | Oferta permisiva | Lectura comercial |
|---|---|---|---|---|
| **Farmacovigilancia** | **máxima** (notificación obligatoria en todas las jurisdicciones) | MedDRA de pago + WHODrug por suscripción | **12 repos ≥10★ en el mundo** | **Aquí está el margen.** Hueco máximo + pago obligado. Pero el entregable **no puede prometerse abierto** |
| **Interacción clínica fármaco-fármaco** | ninguna (CDS) | propietaria (FDB/Multum); DrugBank CC BY-NC | **vacío** (191 repos, top-10 ≈ 42★) | **No vender todavía**: no hay substrato *ni* cifra de daño evitado (hueco (h)) |
| **Farmacogenómica** | **ninguna** | **CPIC = CC0 1.0** | **sana y activa** | **El único sub-plano entregable 100 % abierto** de una tarea de juicio clínico en toda esta KB |

La conclusión que hay que llevar a una propuesta: **el regulador crea la obligación; la licencia del
contenido decide si el código abierto puede cumplirla.** Donde el contenido está gravado, el
entregable con margen es **la capa de juicio sobre contenido que el cliente ya licencia** —un
laboratorio que notifica ya paga MedDRA— y el activo que se queda el cliente es **la biblioteca de
reglas más el banco de pruebas**, no la plataforma.

### El coste del contenido, con cifra oficial (a diferencia del CPT del ciclo 6)

| Conjunto | Coste |
|---|---|
| **MedDRA** | Reguladores y no lucrativos **0 USD**. Comercial por tramo de ingresos del grupo: **139 USD** (< 1 M) … **37.035 USD** (1–5 mil M). **+3 % en 2027.** Sin tramo publicado por encima de 5 mil M |
| **WHODrug / VigiBase** (UMC) | Suscripción por facturación. **Sin precio público** — se cita la existencia de cuota |
| **DrugBank** | *Datasets* **CC BY-NC 4.0**; comercial exige licencia pagada |
| **CPIC** | **CC0 1.0** — dominio público |
| **RxNorm / NDC / DailyMed / openFDA** | Gratis; RxNorm con licencia UMLS de registro sin coste |

**Mejora metodológica respecto del ciclo 6:** donde las cifras del CPT venían de secundarias en
conflicto, **la escala de MedDRA está publicada por la fuente oficial con tramo y cifra exacta**.
Es la primera partida de coste de contenido de esta KB que se puede poner en un presupuesto.

### Tamaño de mercado: la dispersión es el dato

| Segmento | 2026 | Horizonte | Nota |
|---|---|---|---|
| Externalización de PV | **5,79 / 8,51 / 8,7 / 9,15 mil M USD** (cuatro firmas) | 16,09 mil M (2030) – 22,99 mil M (2035) | **Horquilla del 58 % para el mismo año** |
| PV global | **9,3–13,71 mil M USD** | 15,7 mil M (2033) – 34,17 mil M (2032) | CAGR entre 7,8 % y 16,34 % según definición |
| Procesamiento de casos | **4,25 mil M USD** | CAGR 13,1 % a 2035 | **Los servicios fueron el 46 % en 2025** |

El dato sólido y vendible no es el tamaño: es que **el 46 % del procesamiento de casos se resuelve
hoy con personas**. Eso describe exactamente la condición de un encargo de automatización, y se
puede afirmar sin apoyarse en una previsión.

### Oportunidades por región

#### North America — el substrato ya es público; el encargo es el juicio y la trazabilidad

La mejor dotación de todo el plano y la única con fuentes oficiales en dominio público:
`FDA/openfda` (CC0), `FDA/open.fda.gov` (MIT, push de hoy), `coderxio/sagerx` (Apache-2.0),
`HL7/PDDI-CDS` (CC0), `PharmCAT` (MPL-2.0), `cpic-data` (CC0). **Consecuencia práctica: el *fixture*
no hay que fabricarlo**, a diferencia del plano clínico donde `synthea` resolvía ese problema — el
dato real de seguridad ya es público. Marco de venta: la **hoja de ruta de CMS del 2026-11-13**
(fases, evidencia, monitorización continua) describe literalmente los artefactos que un agente con
registro por decisión produce por construcción. **Canadá** tiene pieza propia y mantenida:
`ReyemTech/mcp-canada` (MIT, 63★/9f). Entregable con margen: **triaje y deduplicación de ICSR con
aprobación humana en todo paso con consecuencia regulatoria**, más la biblioteca de reglas como
activo del cliente.

#### EMEA — vender sobre los diez principios EMA/FDA, no sobre el AI Act

La fuente institucional de primera mano de este plano son los **diez principios comunes de buenas
prácticas de IA en el ciclo de vida del medicamento de EMA y FDA, del 2026-01-14**. Es mejor terreno
de venta que el AI Act, cuyas fechas se han movido dos veces (alto riesgo: **dic-2027** autónomos,
**ago-2028** integrados en producto regulado) — **quien construya sobre la fecha se queda sin
propuesta si la fecha se mueve otra vez**, como esta KB viene repitiendo. Substrato local real pero
**copyleft**: `vigicaen` (CeCILL 2.1, CHU de Caen), `pvm` (GPL-3.0, BIPS Bremen), `FreeVigilance/E2B`
(GPL-3.0). **Única pieza permisiva EMEA: `hpi-dhc/PharMe` (MIT, Hasso-Plattner).** Arquitectura
obligada: desplegar el copyleft **al lado** e integrar por API. Hueco vendible: **no existe
implementación abierta de la pasarela de EudraVigilance** (hueco (i)).

#### APAC — no hay substrato; el encargo es construirlo, y Japón es la puerta

Medido y dicho sin adornos: Japón **3 repos** (el mejor con 1★), China **2 repos con 0★**, India
**1 resultado y es un trabajo de curso**. La única señal viva es `pipeworx-io/mcp-jp-pmda-approvals`
(MIT, **0★**, siete días de vida). Lo que sí cambió en el marco: **Japón añadió análisis de riesgo
para agentes de IA a sus directrices empresariales en marzo de 2026** — primera directriz APAC que
esta KB registra mencionando *agentes* explícitamente. Combinado con la regla del ciclo 6 (India
tiene la puerta regulatoria más ligera y llega antes a volumen clínico), la oportunidad es
**greenfield con marco de responsabilidades ya escrito**: se construye el substrato y se entrega la
matriz de responsabilidades por fase que Singapur (AIHGle 2.0) y ahora Japón piden.

#### LATAM — no vender cumplimiento, vender coste por caso y adopción de lo que ya existe

**Dato decisivo del pase: la farmacovigilancia en LATAM aún no tiene reglas específicas de IA.**
ARCSA, ANVISA y COFEPRIS tienen expectativas, no normas. **Por tanto el argumento regulatorio no
existe aquí** —al contrario que en el ciclo 5, donde CFM 2.454/2026 era la palanca más fuerte de las
cuatro regiones— y la venta tiene que apoyarse en **coste por caso y trazabilidad**. Substrato: el
único asset con masa es `iuryLandin/bulario-api` (MIT, 100★/28f) sobre el **bulário de ANVISA**, y
**está parado desde 2025-02**; activo y diminuto a su lado `Diorgerb/dbulario` (Apache-2.0, 4★).
El encargo correcto es el mismo que c7 definió para India: **adoptar y mantener lo publicado**, no
construir de cero. **Perú** es el país de la región con marco general de IA y reglamento aprobado en
2025 — vía de entrada para un piloto con cobertura normativa. Comprador: sigue siendo **privado**
(25 % frente a 11 % público en Brasil, ciclo 6).

Y la honestidad que el pase obliga a escribir: `farmacovigilancia` en español y portugués devuelve
**69 repos cuyos seis primeros suman 7 estrellas**, con **una sola licencia** entre todos. **Pero no
es retraso regional**: la población mundial del sub-plano son **12 repos con ≥10★**. LATAM no va por
detrás de un sector poblado — el sector no está poblado en ninguna región.

### ⚠️ Marcado explícitamente como NO CITABLE en este pase

Ver la lista completa en `intel/trends.md`, T7. En resumen: ninguna cifra única de mercado de PV
(cuatro firmas, horquilla del 58 %), el precio de WHODrug (no publicado), los porcentajes de
intención de inversión (61 % / 85 % / 18 %, sin metodología), el recuento de 1.430 dispositivos de
la FDA (fuente secundaria), la fecha exacta de CFM 2.454/2026 (discrepancia sin resolver) y
cualquier cifra de coste evitable por interacción medicamentosa (no localizada en fuente primaria).
