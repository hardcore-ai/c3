# Estación 2 — Plantilla para co-crear tu PRD con AI

Carpeta de trabajo para la Estación 2 de Hardcore AI (Cohorte 3).

El objetivo de esta estación es que pases de **PVB refinado** a **PRD v1** co-creando con Claude (o el LLM que prefieras).

> **El material completo de la clase** — slides, manual del estudiante con el paso a paso, frameworks teóricos, plantillas comentadas — **está en Circle**. Acá solo está la estructura técnica para ejecutar el ejercicio.

---

## Cómo usar esta carpeta

### 1. Clona el repo

```bash
gh repo clone hardcore-ai/c3
cd "c3/Estación 2"
```

### 2. Reemplaza los archivos de ejemplo con los tuyos

La carpeta `docs/` viene con un **ejemplo trabajado: AgentVault** (sistema de escrow autónomo en USDC para agentes de IA). Está ahí para que veas la profundidad y estructura esperada en cada input.

**Tu trabajo:** reemplazar los archivos de `docs/` con tu propio caso.

| Archivo | Reemplazar con |
|---------|----------------|
| `docs/pvb.md` | Tu Product Vision Board refinado (de la Estación 1, ajustado con los frameworks de la Estación 2) |
| `docs/overview.md` | Tu análisis del dominio: tecnologías clave, tendencias, contexto del problema |
| `docs/mercado.md` | Tu análisis de mercado: tamaño, competidores, regulación, geografías |
| `docs/icp.md` | Tu Ideal Customer Profile: buyer personas, pains, objeciones |
| `docs/critica.md` | Tu deep research de crítica: huecos, riesgos, razones por las que productos similares fracasan |

Puedes añadir tantos archivos adicionales a `docs/` como tengas: transcripciones de entrevistas con usuarios, benchmarks competitivos, notas de campo, análisis técnicos. Todos se adjuntan al prompt en el siguiente paso.

> **Tip:** prefiere **Markdown sobre PDF** para tus inputs — gastas menos tokens (sobre todo con Opus) y el modelo los lee mejor.

### 3. Ejecuta el Prompt 1 con tu LLM

Abre `prompts-especificacion.md`. Copia el **Prompt 1 (PRD)** y pégalo en una conversación nueva de Claude (Pro recomendado) o ChatGPT.

Adjunta **todos** los archivos de tu `docs/`.

Trabaja con la AI segmento por segmento. **No avances al siguiente segmento hasta aprobar el actual.** El prompt está diseñado para co-creación iterativa con human-in-the-loop.

> **Tip (evita la frustración #1):** si con Sonnet en esfuerzo medio el modelo no respeta el "segmento por segmento" y te escupe todo de una, abre una sesión nueva con **Opus** o dile explícitamente "no avancemos, vamos sección por sección". Y usa `/rename` + `/resume` para no perder la sesión entre días.

### 4. Guarda el PRD final en `specs/prd.md`

Cuando la AI consolide el documento completo (todos los segmentos aprobados), guárdalo como `specs/prd.md`.

Ese archivo es tu entregable para la **Estación 3 (Especificación y Arquitectura), viernes 19 de junio**.

---

## Estructura de la carpeta

```
Estación 2/
├── README.md                       # Este archivo
├── prompts-especificacion.md       # Los 3 prompts secuenciales (PRD, Arquitectura, Backlog)
│
├── docs/                           # Inputs — ejemplo AgentVault
│   ├── pvb.md                      # Product Vision Board
│   ├── overview.md                 # Análisis del dominio
│   ├── mercado.md                  # Análisis de mercado
│   ├── icp.md                      # Ideal Customer Profile
│   └── critica.md                  # Deep research de crítica
│
└── specs/                          # Outputs (vacío hasta que ejecutes los prompts)
    └── README.md                   # Explica qué va acá
```

---

## Para qué sirven los otros prompts

En `prompts-especificacion.md` también encuentras dos prompts adicionales que vas a usar más adelante en el programa:

| Prompt | Cuándo lo usas | Output |
|--------|----------------|--------|
| **Prompt 1 — PRD** | Esta semana (entregable para la Estación 3) | `specs/prd.md` |
| **Prompt 2 — Arquitectura** | Estación 3 — Especificación y Arquitectura (MADR) | `specs/arquitectura.md` |
| **Prompt 3 — Backlog** | Estaciones de Implementación (E4-E6) | `specs/backlog.md` |

No los ejecutes todos esta semana. Concéntrate en producir un `prd.md` sólido.

---

## El ejemplo: AgentVault (no es tu producto)

Para que veas la profundidad esperada en los inputs, esta carpeta incluye un ejemplo trabajado completo. **AgentVault** es un producto hipotético usado como referencia a lo largo del programa:

- **Categoría:** Infraestructura de escrow autónomo en USDC para agentic commerce M2M
- **Tagline:** "Stripe para agentes que no pueden firmar contratos"
- **Moat primario:** Trust (smart contract auditado + red KYA + biblioteca de evaluadores AI)
- **Arena:** Pioneer (AI-Native)
- **UX paradigm:** Autonomous

Los archivos de `docs/` están escritos para AgentVault. Cuando los reemplaces con los tuyos, mantén el mismo nivel de profundidad.

---

*Hardcore AI by 30X · Cohorte 3 · Estación 2*
