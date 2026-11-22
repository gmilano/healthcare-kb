---
industry: healthcare
region: Global
updated: 2026-11-22
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
