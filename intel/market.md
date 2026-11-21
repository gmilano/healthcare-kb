---
industry: healthcare
region: Global
updated: 2026-11-21
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
