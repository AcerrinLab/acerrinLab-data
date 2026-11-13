# Documentación de Viruta

Seguimos el estándar de trabajo que nos compartió un colega: **antes de programar se documenta el
proyecto en piezas numeradas**, y el desarrollo avanza por partes (plan evolutivo) hasta una prueba de
concepto y luego la V1. Hacer todo de una vez da un producto mediocre.

## Índice

> **Alcance vigente:** el de DOC-02A (plantillas paramétricas, realidad aumentada, cálculo de materiales y pedido a carpinterías con seña y comisión). DOC-01, DOC-02, DOC-04A, DOC-05 y DOC-06 se alinearon con él el 13/11. Las decisiones que siguen abiertas están en DOC-05 §15.

| Código | Documento | Carpeta | Estado |
|---|---|---|---|
| — | Reglas, criterios, plan paso a paso y workshops | `00_hackaton/` | Referencia |
| DOC-01 | Informe descriptivo (idea principal) | `01_idea/` | V0.4 borrador |
| DOC-02 | Estudio de mercado y validación | `02_analisis/` | V0.4 + encuestas y testimonios |
| DOC-02A | Requisitos funcionales | `02_analisis/requisitos/` | V0.3 pendiente de aprobación |
| DOC-02B | Requisitos no funcionales | `02_analisis/requisitos/` | V0.3 pendiente de aprobación |
| DOC-03 | Modelos visuales (mockups) | `03_visual/` | 2 mockups del alcance anterior (editor modular y foto del ambiente). **A rehacer** con plantillas, AR, materiales, mapa y panel de la carpintería. |
| DOC-04A | Flujo de arquitectura (del usuario al producto final) | `04_diseno_y_arquitectura/` | V0.3 propuesto |
| DOC-04B | Arquitectura técnica (cómo se conectan los programas: backend, n8n, Maps, Mercado Pago) | `04_diseno_y_arquitectura/` | **Pendiente.** Base: `tecnologias.md` y DOC-04A §17 |
| — | Diagrama de clases y casos de uso | `04_diseno_y_arquitectura/` | **Pendiente** (etapa Diseño) |
| DOC-05 | Plan evolutivo (hitos T y H0 a H6) | `05_plan_evolutivo/` | V0.3 propuesto |
| DOC-06 | POC y condiciones de entrega | `06_poc_entrega/` | V0.3 propuesto |
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

**Nombres de archivo**
- Todo en minúsculas, palabras separadas con guion bajo (`_`), sin tildes ni espacios.
- Documentos formales del estándar: `DOC-XX_nombre.md` (por ejemplo `DOC-02A_requisitos_funcionales.md`). Archivos que forman parte de un documento llevan su código: `DOC-03_mockup_01_mueble_en_el_ambiente.png`.
- Material de apoyo sin código: nombre descriptivo (`encuesta_clientes.csv`, `testimonio_01_carpintera_melamina.md`). Si hay varios del mismo tipo, numerarlos (`_01`, `_02`).
- Carpetas: `NN_nombre`, en el orden de trabajo.

**Contenido**
- Cada documento formal empieza con **Código, Versión, Fecha, Estado y Bases**, y termina con un **Historial** de versiones.
- La versión va dentro del documento y en el historial, no en el nombre del archivo.
- Lo que no está validado se marca como **propuesto**, **pendiente** o **estimado**.

## Ideas para después del MVP
- **Visualización del mueble en una foto del ambiente con IA generativa** (sugerencia del colega): generar la imagen con
  el mueble diseñado dentro de la foto del cliente. Según su experiencia, la opción de mejor precio y calidad es la API de
  imágenes de **Gemini**. Complementa la AR con `<model-viewer>` (útil en PC o cuando el celular no soporta AR).
  Queda como mejora ilustrativa posterior (DOC-05 §14).
