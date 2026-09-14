# Documento de Iniciación y Gestión del Proyecto (PID) — "NuevaMente"
## Marco Metodológico: PRINCE2 / PRINCE2 Agile
**Proyecto:** Sistema Inteligente de Adaptación y Generación de Contenido Educativo  
**Programa:** Hackathon No Country — Oracle Next Education (ONE G10)  
**Versión:** 1.1 (Estado: *Documento Vivo / En Perfeccionamiento Continuo*)  
**Fecha de Emisión:** 14 de Septiembre de 2026  

---

> [!NOTE]
> ### 📜 Declaración de "Documento Vivo" (Living Document Clause)
> El presente Plan de Implementación y Gestión no es un contrato estático ni definitivo. Se concibe bajo la filosofía PRINCE2 Agile como **"letra viva"**: un artefacto dinámico que se revisará, ajustará y perfeccionará formalmente al cierre de cada fase de gestión (Sprint). Cualquier miembro del equipo puede proponer ajustes al Business Case, a las tolerancias o a las alternativas técnicas mediante el proceso de control de cambios acordado con el Project Manager.

---

## 1. Estructura de Organización y Gobernanza del Proyecto (Roles PRINCE2)

```text
┌────────────────────────────────────────────────────────────────────────┐
│                        PROJECT BOARD (JUNTA)                           │
│  ┌──────────────────────────────────────────────────────────────────┐  │
│  │                     EXECUTIVE & PROJECT MANAGER                  │  │
│  │             Martin Morfe (Gobierno, Decisión, Enlaces)           │  │
│  └──────────────────┬────────────────────────────┬──────────────────┘  │
│                     │                            │                     │
│  ┌──────────────────┴─────────────┐    ┌─────────┴──────────────────┐  │
│  │           SENIOR USER          │    │       SENIOR SUPPLIER      │  │
│  │   Cristian Contreras & Diana   │    │  Esteban Guillermo Morales │  │
│  │   Castaño (Voz del Estudiante) │    │  (Arquitecto de Solución)  │  │
│  └────────────────────────────────┘    └────────────────────────────┘  │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
    ┌───────────────────────────────┴───────────────────────────────┐
    │                 EQUIPOS DE ENTREGA ESPECIALIZADA              │
    │  ┌─────────────────────────┐     ┌─────────────────────────┐  │
    │  │     BACKEND & DATA      │     │  FULL STACK & AI FLOW   │  │
    │  │   Juan David Villegas   │     │  Harol Medina & Heiner  │  │
    │  │  (Ingestión & Chunking) │     │  Godoy (RAG / Prompts)  │  │
    │  └─────────────────────────┘     └─────────────────────────┘  │
    │  ┌─────────────────────────┐     ┌─────────────────────────┐  │
    │  │      FRONTEND & UI      │     │    DEVOPS & CLOUD QA    │  │
    │  │   Cristian Contreras &  │     │  Ivan Hernandez (OCI /  │  │
    │  │  Diana Castaño (Web App)│     │  Testing / Despliegue)  │  │
    │  └─────────────────────────┘     └─────────────────────────┘  │
    └───────────────────────────────────────────────────────────────┘
```

| Rol PRINCE2 | Integrante Asignado | Responsabilidad Primaria |
| :--- | :--- | :--- |
| **Executive / Project Manager** | **Martin Morfe** | Responsable final de la viabilidad del proyecto, toma de decisiones estratégicas, gestión de tolerancias, entrega de las 4 tareas en No Country y coordinación general. |
| **Senior Supplier (Autoridad Técnica)** | **Esteban Guillermo Morales Velazquez** | Garantiza la integridad arquitectónica, la robustez de la solución RAG, la viabilidad técnica y el cumplimiento de estándares de código. |
| **Senior User (Aseguramiento de Usuario)** | **Cristian Contreras & Diana Castaño** | Representan las necesidades pedagógicas del usuario final (estudiantes, docentes, líderes técnicos), validando la usabilidad, claridad didáctica y fidelidad de los formatos. |
| **Team Manager: Backend & Ingestión** | **Juan David Villegas Anaya** | Ejecución de paquetes de trabajo de extracción documental (PDF, MD, TXT), sanitización de datos y pipelines de segmentación. |
| **Team Managers: Full Stack & AI** | **Harol Benjamin Medina & Heiner Jair Godoy** | Implementación de la capa de orquestación LLM, diseño de prompts, integración de APIs y conexión de capas de servicio. |
| **Team Managers: Frontend & Visualización** | **Cristian Contreras & Diana Castaño** | Construcción de interfaces reactivas en Streamlit, visualizadores de flashcards/quizzes y componentes interactivos. |
| **Team Manager: DevOps & Cloud Assurance** | **Ivan Hernandez** | Provisión de recursos OCI Always Free, seguridad de credenciales (`.pem`), automatización de pruebas unitarias (`pytest`), integración continua y despliegue. |

---

## 2. Justificación Comercial y Propósito (Business Case)

### 2.1 El Problema
Las instituciones educativas y empresas de tecnología enfrentan una brecha crítica: transformar manuales técnicos complejos en contenidos pedagógicos estructurados consume semanas de trabajo manual especializado.

### 2.2 La Solución "NuevaMente"
Plataforma asistida por IA Generativa y arquitectura RAG que automatiza la ingesta, indexación semántica y adaptación de contenido en múltiples formatos didácticos (Flashcards, Quizzes, Tutoriales) con **anclaje garantizado a la fuente técnica** y persistencia en **OCI Object Storage Always Free**.

### 2.3 Tolerancias del Proyecto (Project Tolerances)
- **Tolerancia de Costo:** **CERO ($0.00 USD)**. Restricción estricta: bajo ninguna circunstancia se incurrirá en servicios de pago. Todo recurso debe pertenecer a la capa Always Free de OCI o capas gratuitas de APIs.
- **Tolerancia de Tiempo:** Cumplimiento estricto del hito final de 5 semanas (18 de Octubre de 2026). Desviación permitida: 0 días para la entrega final en plataforma.
- **Tolerancia de Alcance:** El MVP debe cumplir como mínimo los 8 criterios del Checklist de Evaluación. Los diferenciales (LangGraph, Anki export) se consideran características opcionales (*nice-to-have*).
- **Tolerancia de Calidad:** Índice de anclaje a fuentes (*Grounding Score*) >= 85% en las evaluaciones pedagógicas.

---

## 3. Análisis de Alternativas Técnicas (Enfoque Flexible y No Definitivo)

Para garantizar la adaptabilidad frente a contingencias, se establecen alternativas técnicas para cada componente crítico:

| Componente | Opción Primaria | Alternativa A | Alternativa de Contingencia (Fallback) | Criterio de Decisión para Cambio |
| :--- | :--- | :--- | :--- | :--- |
| **Persistencia Cloud** | OCI Object Storage (`oci-sdk`) | OCI Object Storage vía interfaz compatible con S3 (`boto3`) | Persistencia local temporal (`data/oci_local_storage/`) | Si las claves PEM de OCI fallan en entornos locales restringidos, se opera en modo local sin bloquear el desarrollo. |
| **Modelo Generativo** | Google Gemini 1.5 Flash (Google AI Studio Free) | OpenAI `gpt-4o-mini` | Motor heurístico offline estructurado (sin costo ni latencia de red) | Agotamiento de cuota diaria (Rate Limit 429) o indisponibilidad de API. |
| **Vector Store** | ChromaDB (Persistente en disco) | FAISS (`faiss-cpu`) | Búsqueda por similitud de coseno con embeddings normalizados | Incompatibilidad de binarios en sistemas operativos específicos. |
| **Embeddings** | `all-MiniLM-L6-v2` (Sentence-Transformers local) | Google Text-Embedding-004 | TF-IDF / BM25 tokenizado | Consumo elevado de memoria RAM en entornos virtuales ligeros. |
| **Interfaz de Usuario** | Streamlit | Gradio | API REST con FastAPI + Swagger UI | Si se requiere integración directa con aplicaciones móviles o frontends externos. |

---

## 4. Plan de Gestión de Riesgos y Registro de Riesgos (Risk Register)

Se identifican las amenazas potenciales que podrían afectar el costo, plazo o calidad del proyecto, junto con sus estrategias de mitigación preventiva y reactiva:

| ID | Riesgo Identificado | Prob. | Impacto | Severidad | Estrategia Preventiva (Mitigación) | Plan de Contingencia (Reacción) |
| :---: | :--- | :---: | :---: | :---: | :--- | :--- |
| **R-01** | **Costos involuntarios en OCI**<br>Activación accidental de recursos pagos fuera de la capa Always Free. | Baja | Crítico | **ALTO** | Configurar presupuestos (*Budgets*) con alerta al llegar a $0.01 USD. Usar únicamente Compartimento restringido a recursos gratuitos. | Eliminación inmediata del recurso mediante OCI CLI / Consola y reversión a persistencia emulada. |
| **R-02** | **Agotamiento de cuota en APIs LLM**<br>Rate limits (HTTP 429) durante pruebas o la grabación de la demo. | Media | Alto | **ALTO** | Usar Gemini 1.5 Flash optimizado, implementar backoff exponencial con reintentos y caché de respuestas para consultas idénticas. | Conmutación automática a API Key secundaria o al motor heurístico pregrabado de alta fidelidad. |
| **R-03** | **Alucinaciones o imprecisiones didácticas**<br>El LLM genera conceptos no presentes en el documento técnico. | Media | Alto | **ALTO** | Inyección de contexto RAG con límite estricto de temperatura (<= 0.3), prompts de rol con penalización por invención y cálculo de *grounding score*. | El sistema incluye una advertencia explícita en la UI si el anclaje a la fuente resulta menor a 0.80. |
| **R-04** | **Incompatibilidad en extracción de PDFs**<br>PDFs escaneados o con texto no extraíble limpiamente. | Media | Medio | **MEDIO** | Arquitectura con extractor dual: `pypdf` como primario y `pymupdf` (fitz) como secundario. | Ofrecer en la UI un cuadro de texto plano para que el usuario pegue el texto directamente si el PDF es ilegible. |
| **R-05** | **Cuellos de botella en integración del equipo**<br>Desalineación entre ramas de Git o retrasos en dependencias cruzadas. | Media | Medio | **MEDIO** | Contratos de datos tipados con Pydantic fijados desde el Sprint 1. Rama `develop` para integración y `main` protegida para releases. | Sesiones de sincronización técnica (Pair Programming) lideradas por el Solution Architect. |
| **R-06** | **Fallas de conectividad durante el Video Demo**<br>Cortes de internet durante la grabación del video de YouTube. | Baja | Alto | **MEDIO** | Grabar las tomas de pantalla utilizando los 3 escenarios oficiales precargados en almacenamiento local garantizado. | Reintento de grabación local antes de subir el material a YouTube. |

---

## 5. Estrategia de Entrega por Fases de Gestión (Stages / Sprints)

El proyecto se estructura en 5 fases de gestión de 1 semana cada una (PRINCE2 Agile):

- **Fase de Gestión 1 (14 Sep – 20 Sep):** Inicialización, gobierno, repositorio, setup de OCI Always Free y contratos de datos.
- **Fase de Gestión 2 (21 Sep – 27 Sep):** Entrega del módulo de ingestión, conexión funcional con OCI Object Storage e indexación en ChromaDB.
- **Fase de Gestión 3 (28 Sep – 04 Oct):** Implementación de cadenas de prompts pedagógicos, validación Pydantic y guardado de resultados JSON en OCI.
- **Fase de Gestión 4 (05 Oct – 11 Oct):** Conexión de UI en Streamlit, verificación de los 3 escenarios oficiales y pruebas unitarias exhaustivas.
- **Fase de Gestión 5 (12 Oct – 18 Oct):** Congelamiento de código, producción del video demo (2-3 min) y envío formal de los 4 entregables en No Country.

---

## 6. Procedimiento para la Gestión de Cambios (Change Control)

Cualquier miembro del equipo que identifique una oportunidad de mejora o una limitación técnica debe seguir este flujo:
1. **Registro:** Notificar al Project Manager (Martin Morfe) y al Solution Architect (Esteban Morales).
2. **Evaluación de Impacto:** Analizar si el cambio afecta las tolerancias de costo ($0), tiempo (5 semanas) o calidad.
3. **Aprobación en Project Board:** Decisión consensuada en la reunión diaria o semanal.
4. **Actualización:** Modificación de este plan como "letra viva" y notificación en el canal del equipo.
