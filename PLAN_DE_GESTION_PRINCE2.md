# Documento de Iniciación y Gestión del Proyecto (PID) — "NuevaMente"
## Marco Metodológico: PRINCE2 / PRINCE2 Agile Adaptado
**Proyecto:** Sistema Inteligente de Adaptación y Generación de Contenido Educativo  
**Programa:** Hackathon No Country — Oracle Next Education (ONE G10)  
**Versión:** 2.0 (Estado: *Documento Vivo / En Perfeccionamiento Continuo*)  
**Fecha de Emisión:** 14 de Septiembre de 2026  

---

> [!NOTE]
> ### 📜 Declaración de "Documento Vivo" (Living Document Clause)
> El presente Plan de Gestión no es un contrato rígido ni definitivo. En conformidad con PRINCE2 Agile, este artefacto es **"letra viva"**: un marco dinámico que se enriquece, evalúa y perfecciona semana a semana durante el cierre de cada Sprint (Fase de Gestión). El equipo tiene la potestad de proponer ajustes a los canales, dinámicas operativas y arquitecturas técnicas en las ceremonias de retrospectiva.

---

## 1. Gobernanza Democrática por Dimensiones y Organización del Equipo

Para garantizar una gestión ágil, transparente y horizontal, la gobernanza del proyecto no se basa en jerarquías impuestas, sino en un **Project Board Colegiado y Democrático estructurado por 5 Dimensiones Técnicas**, coordinado desde la cúspide por el Project Manager.

```text
                               ┌─────────────────────────────────────────┐
                               │       COORDINACIÓN Y GOBIERNO PM        │
                               │          MARTIN MORFE (PM)              │
                               │  Decisiones, Facilitación y Entregables │
                               └────────────────────┬────────────────────┘
                                                    │
             ┌──────────────────────────────────────┴──────────────────────────────────────┐
             ▼                                                                             ▼
┌─────────────────────────────────────────────────────────────────────────────────────────────────────────────────┐
│                           PROJECT BOARD COLEGIADO Y DEMOCRÁTICO (POR DIMENSIONES)                               │
│                                                                                                                 │
│ ┌──────────────────────┐ ┌──────────────────────┐ ┌──────────────────────┐ ┌─────────────────┐ ┌──────────────┐ │
│ │  DIMENSIÓN 1: ARQ.   │ │ DIMENSIÓN 2: BACKEND │ │  DIMENSIÓN 3: FULL   │ │ DIMENSIÓN 4: UI │ │ DIMENSIÓN 5: │ │
│ │  DE SOLUCIÓN & IA    │ │    & INGESTIÓN       │ │    STACK & AI FLOW   │ │    & UX/FRONT   │ │ DEVOPS & QA  │ │
│ │  Esteban Guillermo   │ │  Juan David Villegas │ │ Harol Medina Zárate  │ │ Cristian        │ │ Ivan         │ │
│ │  Morales Velazquez   │ │  Anaya               │ │ Heiner Godoy Zamora  │ │ Contreras &     │ │ Hernandez    │ │
│ │                      │ │                      │ │                      │ │ Diana Castaño   │ │              │ │
│ └──────────────────────┘ └──────────────────────┘ └──────────────────────┘ └─────────────────┘ └──────────────┘ │
└───────────────────────────────────────────────────┬─────────────────────────────────────────────────────────────┘
                                                    │
                                                    ▼
┌─────────────────────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                   NIVEL OPERATIVO / SPRINT DELIVERY                                             │
│       Ejecución colaborativa de paquetes de trabajo (Work Packages) por los 8 integrantes del equipo            │
└─────────────────────────────────────────────────────────────────────────────────────────────────────────────────┘
```

### Tabla de Participantes y Mapeo de Roles

| Integrante | Rol Oficial | Dimensión en el Board | Responsabilidades Clave |
| :--- | :--- | :--- | :--- |
| **MARTIN MORFE** | **Project Manager** | **Project Management & Gobierno** | Liderazgo del proyecto, facilitador de ceremonias, control de tolerancias, relación con la organización No Country / ONE y entrega de las 4 tareas de la plataforma. |
| **Esteban Guillermo Morales Velazquez** | **Architect (Software / Solution Architect)** | **Dimensión 1: Arquitectura de Solución** | Definición y custodia de la arquitectura integral, estándares de integración RAG, selección de patrones de diseño y gobernanza de código. |
| **Juan David Villegas Anaya** | **Backend Developer** | **Dimensión 2: Ingestión & Datos** | Desarrollo de extractores documentales (PDF, Markdown, Texto), sanitización de datos y pipeline de segmentación (*chunking*). |
| **Harol Benjamin Medina Zárate** | **Full Stack Developer** | **Dimensión 3: Full Stack & Orquestación IA** | Implementación de flujos de orquestación con LLMs, diseño de prompts pedagógicos y lógica de negocio extremo a extremo. |
| **Heiner Jair Godoy Zamora** | **Full Stack Developer** | **Dimensión 3: Full Stack & Orquestación IA** | Integración de servicios RAG, serialización y validación estricta de esquemas Pydantic y comunicación inter-módulos. |
| **Cristian Contreras** | **Frontend Developer** | **Dimensión 4: Frontend & Experiencia de Usuario** | Construcción de la interfaz web interactiva en Streamlit, diseño de componentes didácticos y experiencia de usuario para estudiantes. |
| **Diana Castaño** | **Frontend Developer** | **Dimensión 4: Frontend & Experiencia de Usuario** | Desarrollo de visualizadores interactivos (Flashcards, Quizzes con retroalimentación inmediata, Tutoriales) y diseño CSS responsivo. |
| **Ivan Hernandez** | **DevOps Engineer** | **Dimensión 5: Cloud OCI, DevOps & QA** | Configuración y custodia de la infraestructura en OCI Always Free (Object Storage/Compute), seguridad de claves, suite de pruebas automatizadas y CI/CD. |

---

## 2. Plan Integral de Comunicaciones por Discord

Discord es la sede virtual oficial de **NuevaMente**. El servidor se organiza en categorías estructuradas para eliminar el ruido y garantizar máxima fluidez operativa:

### 2.1 Arquitectura de Canales en Discord

```text
📁 ── INFORMACIÓN GENERAL
   ├── 📢-anuncios-oficiales     (Solo PM / Avisos de entregas, fechas límites, hitos)
   ├── 📌-recursos-y-links       (Repositorio GitHub, Drive, Tableros, Documentación)
   └── 📜-reglas-del-equipo      (DoD, acuerdos de convivencia y políticas)

📁 ── ENCUENTRO DIARIO & GESTIÓN
   ├── ☕-general-daily          (Hilo oficial de la ceremonia Daily y registro asíncrono)
   └── 💡-ideas-y-sugerencias    (Propuestas de mejora y debate de equipo)

📁 ── DIMENSIONES DE TRABAJO
   ├── 🧠-arquitectura-e-ia      (Canal de debate para Esteban, Harol, Heiner y Juan David)
   ├── ⚙️-backend-y-datos        (Canal de trabajo para Juan David, Ivan y Full Stacks)
   ├── 🎨-frontend-y-ux          (Canal de trabajo para Cristian, Diana y Full Stacks)
   └── 🚀-devops-cloud-oci       (Canal de trabajo para Ivan, Esteban y PM)

📁 ── CANALES DE VOZ
   ├── 🔊 Sala de Reuniones (Daily)  (Canal oficial para las Dailies de 15 minutos)
   ├── 🔊 Pair Programming 1         (Espacio de colaboración técnica y codiseño)
   └── 🔊 Pair Programming 2         (Espacio de soporte y depuración)
```

### 2.2 Protocolo de Comunicación y Acuerdos de Nivel de Servicio (SLA)
- **Menciones Responsables:** Usar `@PM`, `@Arquitectura`, `@Backend`, `@Frontend`, `@DevOps` o `@everyone` únicamente para emergencias o bloqueos críticos.
- **Ventana de Respuesta Asíncrona:** Máximo **4 horas diurnas** para responder consultas en canales de dimensión de trabajo.
- **Transparencia:** Ninguna decisión técnica o funcional de impacto se tomará por mensajes privados individuales; todo acuerdo se documenta en el canal correspondiente de Discord.

---

## 3. La Ceremonia "Daily": Punto de Encuentro Diario del Equipo

La **Daily** es el corazón operativo del proyecto. No es una instancia de control ni de fiscalización jerárquica; es una **ceremonia ágil de encuentro, sincronización y desbloqueo mutuo**.

### 3.1 Dinámica y Reglas de la Daily
- **Duración Estricta:** **15 minutos cronometrados** (*Timeboxed*).
- **Frecuencia:** Diaria de lunes a viernes (horario consensuado en Discord, sugerido 20:00 UTC).
- **Lugar:** Canal de voz `🔊 Sala de Reuniones (Daily)` con registro paralelo en `#☕-general-daily`.
- **Modo Asíncrono (Respaldo):** Si algún integrante no puede asistir por motivos de fuerza mayor o compromisos laborales, debe publicar sus respuestas en `#☕-general-daily` antes de la hora de la sesión.

### 3.2 Las 3 Preguntas Clave Contextualizadas para NuevaMente
Cada participante responde de forma concreta:
1. **¿Qué logré ayer que contribuyó a los objetivos del Sprint de NuevaMente?**
   *(Ejemplo: "Juan David: Completé el extractor de PDFs con pypdf y procesa tablas sin errores").*
2. **¿Qué paquete de trabajo abordaré hoy?**
   *(Ejemplo: "Diana: Maquetaré el componente de flashcards con CSS para el volteo de tarjetas").*
3. **¿Tengo algún impedimento, bloqueo o riesgo técnico que requiera apoyo del equipo?**
   *(Ejemplo: "Ivan: Necesito el OCID del bucket de OCI para terminar la prueba de integración").*

> [!TIP]
> Si surge un debate técnico profundo que exceda los 2 minutos, el Project Manager o el Arquitecto abrirán un espacio posterior (*parking lot* o sesión de pair programming en canal de voz 2) para no extender la Daily del resto del equipo.

---

## 4. Justificación Comercial (Business Case) y Tolerancias

- **Propósito:** Desarrollar el MVP de un Sistema Inteligente de Adaptación y Generación de Contenido Educativo basado en RAG y OCI Always Free para el Hackathon ONE G10.
- **Tolerancia de Costo:** **$0.00 USD estrictos**. Uso exclusivo de recursos Always Free en Oracle Cloud y modelos gratuitos (Gemini 1.5 Flash Free Tier).
- **Tolerancia de Tiempo:** 5 semanas (14 Sep – 18 Oct 2026). Entrega sin demoras para el Demo Day.
- **Tolerancia de Calidad:** Métrica de anclaje (*grounding score*) >= 85% en las salidas adaptadas.

---

## 5. Plan de Gestión de Riesgos y Mitigaciones

| ID | Riesgo Identificado | Impacto | Estrategia Preventiva | Plan de Contingencia / Reacción |
| :---: | :--- | :---: | :--- | :--- |
| **R-01** | **Costos involuntarios en OCI** | Crítico | Presupuestos de OCI configurados con alerta a $0.01 USD. Restricción estricta a recursos Always Free. | Destrucción inmediata vía CLI y reversión automática a almacenamiento emulado local. |
| **R-02** | **Agotamiento de cuota en LLM APIs** | Alto | Uso de Gemini 1.5 Flash, compresión de prompts y control de reintentos con backoff. | Conmutación en caliente a OpenAI o fallback a motor heurístico offline sin latencia. |
| **R-03** | **Alucinaciones en contenido didáctico** | Alto | Inyección de fragmentos RAG con temperatura <= 0.3, role prompting pedagógico y score de fidelidad. | Advertencia explícita en la interfaz si el índice de anclaje es < 0.80. |
| **R-04** | **PDFs con formato no estructurado** | Medio | Extractor dual (`pypdf` + `pymupdf`). | Cuadro de pegado directo de texto plano en la interfaz Streamlit. |
| **R-05** | **Fallas en la grabación del Video Demo** | Medio | Uso de los 3 escenarios oficiales pre-cargados en entorno local seguro. | Grabación por módulos independientes y ensamblado final en editor de video. |

---

## 6. Procedimiento para la Gestión de Cambios (Change Control)

1. **Propuesta:** Cualquier integrante presenta la iniciativa en `#💡-ideas-y-sugerencias` o durante la Daily.
2. **Evaluación de Tolerancias:** El PM (Martin) y el Arquitecto (Esteban) evalúan si no se vulnera la regla de costo $0 ni el plazo del Sprint.
3. **Acuerdo en el Board Colegiado:** Se vota de forma democrática con los líderes de dimensión.
4. **Actualización:** El PM actualiza este documento en GitHub y Drive como testimonio de "letra viva".
