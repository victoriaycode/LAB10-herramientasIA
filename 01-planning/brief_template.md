# 🚀 Technical Brief: [Nombre del Proyecto] (BPIR Standard)

> **Uso para IA:** "Lee este brief. Antes de codificar, confirma que entiendes la arquitectura vertical y el protocolo de commits. Detente después de cada hito para revisión y sugiere un commit."

---

## 📌 1. Identificación y Prioridad
- **Título:** `[Verbo] + [Módulo] + [Resultado]`
- **Tipo:** `[Desarrollo / Refactor / IA / Automatización]`
- **Prioridad:** `[Alta / Media / Baja]`

---

## 🗺️ 2. Contexto (El "Por Qué")
- **Sistema Actual:** `[Estado del repo y stack actual]` [Describe qué existe hoy: repo, stack, código legacy o greenfield] 
- **Problema:**  [¿Qué falla, es lento o manual? Describe el síntoma] `[Dolor técnico o funcional específico]`
- **Objetivo Final:** `[Resultado esperado al terminar]` [Frase directa del resultado esperado al finalizar]

---## 🏗️ 3. Requerimientos Técnicos, Arquitectura y Flujo (El "Plano")

### 3.1 Stack y Entorno
Lenguaje: [TypeScript / Python 3.11+ / Go] (Priorizar tipado fuerte)

Versiones: Usar siempre las versiones más actualizadas y estables de las librerías aprobadas.

Frameworks/DB: [Next.js, FastAPI, PostgreSQL, Supabase, etc.]

### 3.2 Arquitectura y Estructura
**Patrón:** [Clean Arch / Hexagonal / Strategy / Repository]
**Estructura de Directorios:**
[módulo/]
├── domain/      # Lógica de negocio pura (Entidades y Casos de Uso)
├── application/ # Orquestación y servicios
├── infra/       # Adaptadores, DB, Clientes API, Repositorios
└── tests/       # Unitarios e Integración

**Separación de Responsabilidades:** Separar claramente el Dominio (reglas de negocio), Estrategias (algoritmos intercambiables) y Servicios Principales.

**Generalización:** Si un componente de código se requiere más de una vez, se debe diseñar una generalización o abstracción reutilizable.

### 3.3 Especificaciones por Capa (Módulos Reutilizables)
**🖥️ Frontend:** [Componentes shadcn/ui, Tailwind, Zustand para estado, Next.js App Router].

**⚙️ Backend:** [API con tipado estricto, middlewares de validación, ORM (Prisma/Drizzle)].

**📊 Datos:** [Esquema: tablas, llaves foráneas, índices. Flujos de limpieza con Polars/Pandas].

**🤖 IA/LLM:** [Modelo: GPT-4o/Claude 3.5. Uso de RAG con pgvector. No usar LangChain si basta el SDK nativo].

**🏗️ Infraestructura:** [Variables en .env, Docker Compose, GitHub Actions para CI/CD].

🚧 4. Constraints (Restricciones Innegociables)
Reglas que garantizan consistencia y protegen el sistema.
**4.1 Desarrollo y Librerías**
**[ ] Librerías Externas:** Prohibido usar librerías externas no aprobadas explícitamente por el equipo.

**[ ] Paradigma:** Seguir principios SOLID y las mejores prácticas idiomáticas del lenguaje.

**[ ] Tipado:** Uso obligatorio de tipado fuerte y estricto en todo el desarrollo.

**4.2 Lógica y Frontend**
**[ ] Lógica Minimalista:** El frontend debe contener la menor lógica posible; delegar validaciones pesadas y procesos al backend/servicios.

**[ ] Inmutabilidad:** No mutar datos originales ni nombres de objetos entre procesos.
**[ ] Generalización:** Si un componente se usa +1 vez, crear una abstracción/clase genérica.

**4.3 Seguridad**
**[ ] Secretos:** Prohibido hardcodear credenciales; usar variables de entorno (.env).

**[ ] Sanitización:** Validar y sanitizar todos los inputs para prevenir inyecciones SQL y ataques XSS.

📝 5. Protocolo de Commits e Hitos (Checkpoint System)

**Instrucción:** Detente y pide aprobación tras cada hito. Sugiere el commit en formato Conventional Commits.

Hito 1 (Setup): chore(setup): Configuración de entorno y .env.example.

Hito 2 (Dominio): feat(domain): Definición de tipos, interfaces y lógica pura.

Hito 3 (Infra/Datos): feat(infra): Implementación de persistencia o clientes externos.

Hito 4 (Lógica/Servicios): feat(service): Orquestación y estrategias.

Hito 5 (Frontend/API): feat(ui): o feat(api): Entrega de interfaces.

Hito 6 (Calidad): test(core): Cobertura del 90% y refactor de generalización.

✅ 6. Definition of Done (DoD)
[ ] **Cobertura de Tests:** El código debe pasar con un 90% de cobertura en tests unitarios.

[ ] **Calidad de Código:** Pasar linters (eslint, ruff, black) sin warnings y sin código muerto.

[ ] **Funcionalidad:** Los casos de uso principales y edge cases funcionan según lo especificado.

[ ] **Documentación:** README actualizado con instrucciones de setup y .env.example.

[ ] **Commits Atómicos:** Se ha realizado un commit descriptivo y único por cada hito completado.

📎 6. Recursos y Referencias
**Docs Externos:** [Link a API externa].

**Esquema DB:** [Descripción o diagrama de tablas].

**Notas de Diseño:** [Decisiones previas a respetar].