# Compendio Técnico y Base de Contexto: Workshops Viruta - Hackaton 2026

Este documento constituye la síntesis técnica integral y estructurada de las tres sesiones de workshop preparatorias para la **Viruta - Hackaton 2026**. Ha sido diseñado con el propósito de servir como base de conocimiento para sistemas de inteligencia artificial y agentes agénticos, proporcionando un contexto preciso sobre metodologías de desarrollo, arquitectura de software, validación de productos y orquestación de inteligencia artificial.

---

## 1. Contexto General del Evento y Ecosistema de Innovación

### 1.1. La Hackaton del Tren Solar 2026
La Hackaton del Tren Solar representa un evento tecnológico de características únicas llevado a cabo en Jujuy y Salta, Argentina. La competencia reúne a desarrolladores, emprendedores y creadores (*builders*) seleccionados que abordan y resuelven problemas reales a bordo del Tren Solar de la Quebrada de Humahuaca.

- **Visibilidad e Alianzas Internacionales**: El evento cuenta con alianzas y presencia de actores clave de la industria global, incluyendo la participación de mentores e iniciativas vinculadas a **SpaceX AI**, así como embajadores de redes blockchain de escala internacional (**Solana, Stellar**).
- **Red de Networking y Capital Semilla**: El objetivo principal trasciende la mera competencia técnica; busca poner par a par a los desarrolladores locales con más de 30 *founders* e inversores de empresas de tecnología consolidadas. Se plantean oportunidades de inserción laboral, alianzas estratégicas y rondas de inversión semilla que oscilan entre los **\$5,000 USD y \$50,000 USD**.

### 1.2. Reglas de Participación y Filosofía del Evento
- **Modalidad Preferente**: Si bien se permiten equipos de hasta 2 personas, se valora con prioridad la **participación individual**. La construcción individual demuestra la capacidad del *builder* para gestionar el ciclo completo de desarrollo, comunicación y resolución autónoma de problemas.
- **Transparencia en Código**: Es obligatorio el uso de repositorios públicos en **GitHub** desde el primer día de trabajo, manteniendo protegidas y aisladas las claves sensibles y variables de entorno (`.env`).
- **Agnosticismo Tecnológico**: No se impone un *track* o *stack* tecnológico obligatorio. Se aceptan soluciones en Web2, Web3, agentes de IA, aplicaciones móviles, desarrollo Web plano o lenguajes tradicionales (TypeScript, Python, Java, Rust), priorizando la validez funcional y la innovación.

---

## 2. Metodología de Investigación, Validación de Mercado y Definición de Producto

### 2.1. Filosofía de Producto: "Enamorarse del Problema"
El error recurrente en etapas iniciales de desarrollo es construir soluciones impulsadas por caprichos técnicos o tendencias del mercado sin validar la existencia real de una necesidad.

1. **Identificación de Fricciones Reales**: La búsqueda debe enfocarse en dolores cotidianos no resueltos o ineficiencias operativas de la comunidad o la industria.
2. **Validación con Usuarios**: Un producto en etapa de prueba (*testing*) vale por el *feedback* y la tracción real que genera. La métrica decisiva para inversores no es la complejidad estética, sino la adopción (p. ej., contar con 100 usuarios activos probando el prototipo).
3. **Pensamiento Determinista y Reducción de Tokens**: Antes de escribir una sola línea de código o realizar peticiones a modelos de lenguaje (*prompts*), se debe realizar una investigación de mercado profunda. Dedicar 20 minutos a estructurar las especificaciones y el contexto ahorra horas de computación y consumo excesivo de *tokens*.

### 2.2. Soluciones Verticales vs. Horizontales
Para garantizar la retención y la viabilidad técnica en etapas tempranas, los productos deben enfocarse **verticalmente**:

| Dimensión | Solución Horizontal | Solución Vertical (Enfoque Recomendado) |
| :--- | :--- | :--- |
| **Alcance** | Aborda múltiples problemas para diversos sectores de forma genérica. | Resuelve un problema específico para un nicho bien definido. |
| **Retención** | Alta tasa de abandono (*churn*) por falta de adaptación profunda. | Alta retención e integración en el flujo diario de trabajo del usuario. |
| **Desarrollo MVP** | Requiere arquitecturas extensas e inmanejables en poco tiempo. | Se limita a 3 funcionalidades clave (*features*) construibles rápidamente. |

### 2.3. Herramientas Gratuitas de Investigación Profunda (*Deep Research*)
Para llevar a cabo el *research* inicial sin incurrir en costos de suscripción, se recomiendan:
- **Kimi (Bit Research)**: Búsqueda e investigación profunda de mercado, competidores y viabilidad.
- **DeepSeek & ChatGPT**: Análisis comparativo, estructuración de matriz FODA (Fortalezas, Oportunidades, Debilidades, Amenazas) y desglose de requerimientos.

---

## 3. Arquitectura de Prototipado Rápido y Prueba de Concepto (PoC)

### 3.1. Regla de los 3 Días para la PoC
Una Prueba de Concepto (*Proof of Concept*) no debe extenderse más de 3 días de desarrollo. Si dentro de ese período no se logra un flujo básico funcional que resuelva el problema planteado, el proyecto debe iterarse, redefinirse o descartarse.

### 3.2. Caso de Estudio Práctico: "Rescate Local"
Durante la segunda sesión del workshop se construyó en vivo un prototipo enfocado en el impacto social denominado **Rescate Local**, dedicado a conectar comercios con excedentes de alimentos con comedores comunitarios y vecinos.

#### Funcionalidades Clave (MVP):
1. **Publicación de Lote Excedente**: El comercio registra tipo de alimento, cantidad y ventana horaria de retiro.
2. **Reserva del Lote**: Una institución o vecino reserva el lote disponible (revelando la dirección exacta únicamente tras la reserva).
3. **Confirmación y Registro de Impacto**: Confirmación de entrega con registro de kilogramos o unidades rescatadas (distinguiendo entre valores reales y estimados para mantener la honestidad de datos).

#### Máquina de Estados del Lote:
```
[Publicado] ──> (Reserva de Receptor) ──> [Reservado] ──> (Confirmación de Entrega) ──> [Recogido / Rescatado]
     │                                        │
     ├──> (Expiración de Ventana) ────────────┼──> [Vencido]
     │                                        │
     └──> (Cancelación por Comercio/Admin) ───┴──> [Liberado / Vencido]
```

#### Lo que NO Incluye el MVP (Fuera de Alcance):
- Logística de transporte integrada o mapas en tiempo real.
- Aplicaciones nativas móviles (iOS/Android).
- Pasarelas de pago o chat interno.
- Algoritmos complejos de emparejamiento (*matching*).

### 3.3. Stack Tecnológico de Prototipado Rápido

```
  [ Frontend ]               [ Backend Worker ]              [ Base de Datos ]
HTML5 / CSS / JS  ───────>  Cloudflare Workers  ───────>  Neon Postgres (Serverless)
(Sin Build Steps)            (Wrangler CLI)                  (Drizzle ORM)
```

1. **Base de Datos**: **Neon** (PostgreSQL Serverless), utilizando **Drizzle ORM** para la gestión de migraciones e interacción con datos.
2. **Backend**: **Cloudflare Workers**, configurados mediante la herramienta de línea de comandos **Wrangler** (`wrangler.toml`).
3. **Frontend**: HTML5, CSS3 y JavaScript plano embebido. Se evitan intencionalmente los frameworks pesados (React, Next.js) y las etapas de compilación (*build steps*) durante la PoC para asegurar el despliegue inmediato.
4. **Model Context Protocol (MCP)**: Uso de servidores MCP para conectar el agente de codificación directamente con las APIs de Neon, Cloudflare y GitHub, ejecutando tareas administrativas automáticamente.

---

## 4. Orquestación de Agentes de IA e Ingeniería de Software Moderna

### 4.1. Las 5 Etapas del Duelo del Programador ante la IA
El avance de la inteligencia artificial transforma el rol del desarrollador de software. La adaptación profesional atraviesa cinco etapas emocionales y técnicas:

```
1. Negación  ──> "La IA escribe código malo; la programación manual siempre será superior."
2. Ira       ──> Frustración cuando los modelos alucinan o reemplazan tareas junior.
3. Negociación ─> Integración paulatina de la IA para tareas menores (scripts, regex, correos).
4. Depresión ──> Sensación de obsolescencia ante la velocidad de generación de los modelos.
5. Aceptación ──> Comprensión de la IA como un aliado estratégico para multiplicar la productividad.
```

### 4.2. Diferencia entre Modelo de Lenguaje (LLM) y Agente de IA

- **Modelo (LLM)**: Es un motor cognitivo aislado que procesa entradas y salidas de texto. Realiza tareas de lectura, síntesis o generación.
- **Agente de IA**: Es la combinación de un **LLM + Herramientas + Percepción + Ciclos de Decisión + Arnés (*Harness*) de Control**.

$$\text{Agente} = \text{Modelo (LLM)} + \text{Herramientas (APIs/CLI)} + \text{Arnés de Control (Harness)}$$

El **Arnés (*Harness*)** de control actúa como una estructura de contención que limita las alucinaciones del modelo, definiendo contextos, permisos de archivos y reglas de ejecución.

### 4.3. Entornos de Desarrollo Agénticos (ADE) y Orquestación por DAG
La evolución tecnológica trasciende los Entornos de Desarrollo Integrados tradicionales (IDE como VS Code) para dar paso a los **Entornos de Desarrollo Agénticos (ADE)** como **Orca**.

#### Principios de Orquestación:
- **Grafos Acíclicos Dirigidos (DAG)**: Mapeo ordenado de tareas paralelas entre diferentes agentes especializados (p. ej., Agente UX/UI, Agente Backend, Agente de Testing, Agente de Review).
- **Paralelización sin Conflictos mediante GitHub Worktrees**: Asignación de cada agente a un *worktree* independiente dentro del repositorio de Git. Esto evita conflictos de código (*merge conflicts*) en la rama principal durante la ejecución simultánea de tareas.

```
                  ┌──> [Agente Frontend] ──┐
[Agente Lead/DAG] ┼──> [Agente Backend]  ──┼──> [Agente Testing/Review] ──> [Deploy]
                  └──> [Agente Database] ──┘
```

### 4.4. Estrategias de Optimización y Ahorro de Tokens
1. **Modelos Especializados y Comandos `/mod`**: No utilizar el modelo más costoso (p. ej., Claude 3.5 Opus) para tareas secundarias. Utilizar modelos pesados únicamente para la arquitectura y la orquestación, y modelos ligeros (Haiku, Kimi, DeepSeek) para la lectura de documentación y pruebas.
2. **Uso de Skills (`.md`)**: Archivos de instrucciones reutilizables que evitan repetir el contexto del proyecto en cada sesión. Destacan las habilidades del repositorio de **Matt Pocock**:
   - `Grillmi`: Entrevista al desarrollador con preguntas estrictas para cerrar decisiones de arquitectura antes de generar código.
   - `Engram`: Sistema de memoria persistente compartida para mantener el contexto entre diferentes ejecuciones agénticas.

---

## 5. Casos de Estudio y Proyectos Presentados por Participantes

Durante los workshops se analizaron diferentes propuestas desarrolladas por la comunidad de Jujuy:

1. **Vincular el Tren Solar con Artesanos Locales (Franco - Maimará)**:
   - **Problema**: Los artesanos de pueblos intermedios (Maimará, Tilcara, Purmamarca) no tienen visibilidad a menos que posean un puesto físico en la estación.
   - **Solución**: Plataforma *takeaway* donde el artesano publica la disponibilidad de productos de acuerdo a los horarios exactos de parada del Tren Solar. El pasajero reserva durante el trayecto y retira en la estación correspondiente.
2. **Escudo Vecinal (Fabián)**:
   - **Solución**: Plataforma interactiva de prevención de estafas virtuales para comunidades ciudadanas, utilizando módulos de microcapacitación de 5 minutos y simulaciones de riesgos cibernéticos.
3. **Plataforma Agregadora de Salud (Agustín)**:
   - **Solución**: Buscador unificado que consolida la oferta de profesionales de la salud, obras sociales aceptadas y turnos disponibles mediante raspado de datos (*web scraping*) de padrones en PDF.
4. **Estrategia de Tracción para Productos Existentes (Cristian Sandoval)**:
   - **Caso**: Proyecto con más de 100 usuarios activos. Discusión sobre la conveniencia de presentar productos consolidados frente a desarrollos nuevos en etapas de Hackaton para acceder a rondas de inversión semilla.

---

## 6. Glosario Técnico de Referencia

- **ADE (Agentic Development Environment)**: Entorno de desarrollo diseñado específicamente para coordinar y supervisar agentes de inteligencia artificial.
- **CLI (Command Line Interface)**: Interfaz de línea de comandos para la ejecución directa de programas y agentes.
- **DAG (Directed Acyclic Graph)**: Estructura de datos y trabajo para organizar tareas secuenciales y paralelas sin ciclos infinitos.
- **Drizzle ORM**: Mapper Objeto-Relacional ligero para TypeScript y JavaScript en entornos Serverless.
- **MCP (Model Context Protocol)**: Protocolo abierto para la integración de herramientas y contextos de datos externos en asistentes y agentes de IA.
- **Neon**: Proveedor de bases de datos PostgreSQL serverless orientado al escalado automático y creación de ramas de base de datos (*branching*).
- **Wrangler**: Herramienta de CLI oficial de Cloudflare para construir y desplegar Workers.
