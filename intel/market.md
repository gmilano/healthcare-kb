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
