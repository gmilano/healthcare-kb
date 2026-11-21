---
industry: healthcare
region: Global
updated: 2026-11-21
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
