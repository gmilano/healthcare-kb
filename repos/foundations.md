---
industry: healthcare
region: Global
updated: 2026-11-21
---

# 🏗️ Repos fundacionales — Healthcare

> Bases sobre las que construir: interoperabilidad, imagen médica, NLP clínico y datos sintéticos.
> Licencia verificada por bytes; existencia por `git ls-remote`. Última verificación: 2026-11-21.
>
> Este archivo **estaba vacío** en el remoto (una sola fila `| — | — | Por completar | — |`
> desde 2026-07-02). Las 20 filas siguientes son su primer contenido real.

## Interoperabilidad / FHIR — la capa que todo agente clínico necesita

| Repo | Licencia | Descripción | Stars | Último push | Región |
|------|----------|-------------|-------|-------------|--------|
| [medplum/medplum](https://github.com/medplum/medplum) | Apache-2.0 | Backend y plataforma FHIR-native completa (auth, subscripciones, bots); el open core más adoptable para construir encima | 2807 | 2026-11-21 | Global |
| [hapifhir/hapi-fhir](https://github.com/hapifhir/hapi-fhir) | Apache-2.0 | Implementación de referencia de FHIR en Java; el servidor FHIR de facto | 2448 | 2026-11-21 | Global |
| [microsoft/fhir-server](https://github.com/microsoft/fhir-server) | MIT | Servidor FHIR en .NET (base del Azure Health Data Services OSS) | 1396 | 2026-11-21 | North America |
| [gematik/api-erp](https://github.com/gematik/api-erp) | Apache-2.0 | **Especificación oficial** de la API de e-receta alemana, publicada por la agencia nacional de salud digital | 116 | 2026-11-20 | EMEA |
| [gematik/api-ePA](https://github.com/gematik/api-ePA) | Apache-2.0 | **Especificación oficial** de la historia clínica electrónica alemana (ePA) | 60 | 2025-11-20 | EMEA |
| [ma3u/MinimumViableHealthDataspacev2](https://github.com/ma3u/MinimumViableHealthDataspacev2) | Apache-2.0 | Implementación de referencia del European Health Data Space con grafo de conocimiento FHIR R4 | 11 | 2026-11-20 | EMEA |
| [Precisa-Saude/fhir-brasil](https://github.com/Precisa-Saude/fhir-brasil) | Apache-2.0 | Toolkit FHIR R4 brasileño (TypeScript): cliente RNDS con mTLS + **sandbox local de desarrollo** | 1 | 2026-11-20 | LATAM |
| [Voa-Health/rnds](https://github.com/Voa-Health/rnds) | Apache-2.0 | RNDS brasileña: identificadores, códigos y validación FHIR como lib Python, CLI **y servidor MCP para agentes** | 0 | 2026-11-18 | LATAM |
| [IgMiras/rnds-br-connect](https://github.com/IgMiras/rnds-br-connect) | Apache-2.0 | Framework Java que construye y valida documentos FHIR para la RNDS con mapeo de terminología enchufable | 1 | 2026-11-13 | LATAM |
| [kyriosdata/rnds](https://github.com/kyriosdata/rnds) | Apache-2.0 | Utilidades de integración RNDS en Java (sin push desde 2024-08; referencia, no base) | 51 | 2024-08-28 | LATAM |

> ⚠️ Los cuatro repos RNDS son **comunitarios, no oficiales**: cada uno declara explícitamente
> no estar afiliado al Ministério da Saúde ni al DATASUS. La RNDS no publica un paquete FHIR
> versionado, así que los perfiles se capturan de Simplifier. La acreditación DATASUS y el
> certificado ICP-Brasil siguen siendo responsabilidad del integrador.
> Esto contrasta con **gematik**, que sí es la agencia oficial alemana publicando bajo Apache-2.0.

## Imagen médica

| Repo | Licencia | Descripción | Stars | Último push | Región |
|------|----------|-------------|-------|-------------|--------|
| [Project-MONAI/MONAI](https://github.com/Project-MONAI/MONAI) | Apache-2.0 | Framework de deep learning para imagen médica (PyTorch); el estándar del dominio | 8858 | 2026-11-18 | Global |
| [TorchIO-project/torchio](https://github.com/TorchIO-project/torchio) | Apache-2.0 | Preprocesado y augmentation de imágenes médicas volumétricas | 2457 | 2026-11-13 | Global |
| [pydicom/pydicom](https://github.com/pydicom/pydicom) | MIT (con excepciones) | Lectura/escritura DICOM en Python puro. El LICENSE (3140 B) dice *"Except for portions outlined below, pydicom is released under an MIT license"*: GitHub lo reporta como NOASSERTION, pero el cuerpo es MIT con porciones de terceros acotadas | 2238 | 2026-11-20 | Global |

## NLP clínico y modelos médicos

| Repo | Licencia | Descripción | Stars | Último push | Región |
|------|----------|-------------|-------|-------------|--------|
| [maziyarpanahi/openmed](https://github.com/maziyarpanahi/openmed) | Apache-2.0 | NER clínico y **de-identificación de PII** local-first — la pieza que habilita trabajar sin enviar PHI a una API | 5833 | 2026-11-20 | Global |
| [sunlabuiuc/PyHealth](https://github.com/sunlabuiuc/PyHealth) | MIT | Toolkit de ML sanitario (UIUC): pipelines sobre MIMIC/eICU/OMOP | 1703 | 2026-11-20 | North America |
| [medspacy/medspacy](https://github.com/medspacy/medspacy) | MIT | NLP clínico sobre spaCy (negación, contexto, secciones) | 688 | 2026-06-04 | North America |
| [aphp/edsnlp](https://github.com/aphp/edsnlp) | BSD-3-Clause | NLP clínico **en francés**, de Assistance Publique – Hôpitaux de Paris | 168 | 2026-11-20 | EMEA |
| [apache/ctakes](https://github.com/apache/ctakes) | Apache-2.0 | Plataforma de NLP clínico de la Apache Software Foundation (UIMA) | 142 | 2026-11-04 | Global |
| [EPFLiGHT/FullyOpenMeditron](https://github.com/EPFLiGHT/FullyOpenMeditron) | Apache-2.0 | Corpus médico de entrenamiento **auditado por clínicos** y protocolo de evaluación abierta (EPFL LiGHT) | 19 | 2026-11-17 | EMEA |

## Datos sintéticos y modelo común — cómo se prueba sin PHI

| Repo | Licencia | Descripción | Stars | Último push | Región |
|------|----------|-------------|-------|-------------|--------|
| [synthetichealth/synthea](https://github.com/synthetichealth/synthea) | Apache-2.0 | Generador de pacientes sintéticos con historia longitudinal completa, exportable a FHIR. **Resuelve el primer bloqueo de todo engagement clínico: no se puede probar sobre datos reales de paciente** | 3472 | 2026-11-20 | Global |
| [OHDSI/Atlas](https://github.com/OHDSI/Atlas) | Apache-2.0 | UI de cohortes y analítica sobre el modelo común OMOP | 340 | 2026-09-16 | Global |

> `OHDSI/CommonDataModel` **no tiene archivo de licencia** (README 200 como control).
> Un ciclo anterior lo registró como `OMOP-CDM (Apache-2.0)`. La especificación OMOP es
> usable, pero el repo no la otorga por escrito: usar `OHDSI/Atlas` (Apache-2.0 verificado)
> como punto de entrada citable.

---
*Ver también: `verticals/solutions.md` para plataformas verticales completas.*
