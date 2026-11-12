# Documentación de Viruta

Seguimos el estándar de trabajo que nos compartió un colega: **antes de programar se documenta el
proyecto en piezas numeradas**, y el desarrollo avanza por partes (plan evolutivo) hasta una prueba de
concepto y luego la V1. Hacer todo de una vez da un producto mediocre.

## Índice

| Código | Documento | Carpeta | Estado |
|---|---|---|---|
| — | Reglas, criterios, plan paso a paso y workshops | `00_hackaton/` | Referencia |
| DOC-01 | Informe descriptivo (idea principal) | `01_idea/` | V0.2 borrador |
| DOC-02 | Estudio de mercado y validación | `02_analisis/` | V0.2 + encuestas y testimonios reales |
| DOC-02A | Requisitos funcionales | `02_analisis/requisitos/` | V0.3 pendiente de aprobación |
| DOC-02B | Requisitos no funcionales | `02_analisis/requisitos/` | V0.3 pendiente de aprobación |
| DOC-03 | Modelos visuales (mockups) | `03_visual/` | 2 mockups |
| DOC-04A | Flujo de arquitectura (del usuario al producto final) | `04_diseno_y_arquitectura/` | V0.1 |
| DOC-04B | Arquitectura técnica (cómo se conectan los programas: backend, n8n, Gemini, Maps, Mercado Pago) | `04_diseno_y_arquitectura/` | **Pendiente.** Base: `tecnologias.md` |
| — | Diagrama de clases y casos de uso | `04_diseno_y_arquitectura/` | **Pendiente** (etapa Diseño) |
| DOC-05 | Plan evolutivo (hitos H0 a H6) | `05_plan_evolutivo/` | V0.1 |
| DOC-06 | POC y condiciones de entrega | `06_poc_entrega/` | V0.1 |
| — | Resultados de programación y testeo | `07_programacion/`, `08_testeo/` | Vacío |

## Estándar de trabajo
1. **Informe descriptivo** con la idea principal (DOC-01).
2. **Estudio de mercado** cuando hay que validar la idea (DOC-02), más los requisitos que salen de él.
3. **Modelos visuales**: mockup de la interfaz principal y de cada pantalla (DOC-03).
4. **Flujo de arquitectura** en dos versiones:
   - DOC-04A: el ciclo de trabajo, desde el usuario hasta el producto final y sus variables.
   - DOC-04B: cómo están conectados los programas y servicios (por ejemplo, n8n con los demás).
5. **Plan evolutivo**: integración parte por parte (DOC-05).
6. **POC** estándar y funcional, con condiciones de entrega (DOC-06), y después la **V1**.
7. Con la carpeta completa, se le da acceso a un agente (Claude o Codex) para que la analice y trabaje sobre ella.

## Convenciones
- Cada documento empieza con **Código, Versión, Fecha, Estado y Bases**, y termina con un **Historial** de versiones.
- La versión va dentro del documento y en el historial, no en el nombre del archivo.
- Lo que no está validado se marca como **propuesto**, **pendiente** o **estimado**.

## Ideas pendientes de ubicar
- **Visualización del mueble en una foto del ambiente con IA generativa** (sugerencia del colega): generar la imagen con
  el mueble diseñado dentro de la foto del cliente. Según su experiencia, la opción de mejor precio y calidad es la API de
  imágenes de **Gemini**. Complementa la AR con `<model-viewer>` (útil en PC o cuando el celular no soporta AR).
  Evaluar en DOC-04B y, si entra, sumar como requisito en DOC-02A.
