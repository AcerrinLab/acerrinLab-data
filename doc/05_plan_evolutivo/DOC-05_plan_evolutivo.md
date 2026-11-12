# Plan evolutivo
## Plataforma web para crear y cotizar muebles a medida

**Código:** DOC-05  
**Versión:** 0.2  
**Fecha:** 4 de noviembre de 2026  
**Estado:** Plan propuesto; **pendiente de revisión con Maxi** (hitos, fechas y responsables).  
**Fecha límite conocida:** entrega del hackatón el 13/11/2026.  
**Alineación (12/11/2026):** hay puntos de alcance que difieren de lo ya definido por el equipo. Ver `doc/coherencia_y_decisiones.md`.  
**Bases:** DOC-01 y DOC-02 V0.2, modelos visuales, DOC-04A y DOC-04B V0.1.

## 1. Objetivo

Organizar el desarrollo en entregas que puedan ejecutarse, demostrarse y revisarse. El producto permitirá crear muebles sencillos con una paleta modular, visualizarlos en su ambiente, obtener documentación preliminar y solicitar presupuesto.

La prioridad inicial será demostrar que una misma definición de piezas y relaciones produce geometría, plano y cómputo coherentes. Después se completará el recorrido comercial. Un escritorio será un caso de prueba, no una restricción del producto.

No se fijan fechas o estimaciones de horas sin conocer dedicación del equipo y plazo del hackathon. DOC-06 establecerá el calendario y las condiciones de la prueba. Todos los hitos de este plan comienzan en estado pendiente.

## 2. Niveles de entrega

| Nivel | Qué demuestra | Qué no permite afirmar todavía |
| --- | --- | --- |
| POC del núcleo | Crear dos muebles sencillos con el mismo editor y obtener resultados dimensionales coherentes. | Que existe un servicio completo de cotización. |
| POC del recorrido | Agregar ambiente, guardado, documentos y registro real de una solicitud de prueba. | Que hay demanda comercial o capacidad sostenida de atención. |
| MVP piloto | Recorrido usable y atención por una carpintería participante, con prueba observada y pendientes conocidos. | Que el modelo de negocio es rentable o escalable. |
| Evoluciones posteriores | Ampliaciones elegidas por evidencia del piloto. | Que todas deban construirse o tengan fecha comprometida. |

Las dos comprobaciones técnicas forman partes de la POC general prevista en DOC-04A. Aprobar solo el núcleo no equivale a entregar el MVP.

## 3. Vista general de hitos

| Hito | Entrega | Depende de | Condición principal de cierre |
| --- | --- | --- | --- |
| H0 | Base y casos de referencia | Documentación inicial | Paleta mínima, casos y reglas iniciales definidos. |
| H1 | Motor de piezas y relaciones | H0 | Dos tipologías calculadas con resultados contrastados. |
| H2 | Editor modular y 3D | H1 | Crear y modificar ambas tipologías con la misma paleta. |
| H3 | Guardado y documentación | H2 | Recuperar proyecto y generar plano, cómputo y PDF coherentes. |
| H4 | Mueble en el ambiente | H2; integración con H3 | Colocación visual usable sin alterar medidas. |
| H5 | Solicitudes y atención de prueba | Captura de H3; ambiente de H4 para prueba completa | Envío persistente, único ante reintentos y recuperable por el operador. |
| H6 | MVP piloto y demostración | H0–H5 | Recorrido completo probado, profesional disponible y entrega documentada. |

Las entrevistas de DOC-02 pueden comenzar durante H0 y continuar mientras se construye. La preparación del profesional y del entorno de solicitudes puede avanzar antes de terminar H4. Estas posibilidades de trabajo concurrente no implican asignación de tareas a agentes ni responsabilidades ya acordadas.

## 4. H0 — Base del proyecto y casos de referencia

**Resultado:** una base mínima sobre la que pueda construirse y verificarse el editor.

Trabajo:

- Crear repositorio y estructura acordada en DOC-04B, registrar versiones y comprobar compilación.
- Definir tablero, lateral y estante, materiales iniciales y convenciones de unidades y ejes.
- Preparar dos casos manuales: un estante o mueble abierto y un escritorio sencillo de tableros, sin cajonera obligatoria.
- Documentar medidas, piezas esperadas, relaciones, supuestos y aspectos pendientes de revisión profesional.
- Definir un caso intencionalmente incompleto o conflictivo para comprobar avisos.
- Iniciar entrevistas y conseguir una persona de carpintería que pueda revisar las reglas.

**Cierre:** los dos casos tienen resultados esperados calculados fuera de la aplicación y alcance constructivo explícito. Si no hay revisión profesional, se puede continuar la prueba geométrica, identificando las reglas constructivas como provisionales; no habilita un piloto de fabricación.

**Evidencia:** casos de referencia, inventario mínimo del catálogo y proyecto que compila.

## 5. H1 — Motor de piezas, relaciones y cómputo

**Resultado:** transformar datos editables en geometría resuelta y cantidades sin depender del visor.

Trabajo:

- Implementar formato del proyecto, IDs y versiones.
- Resolver posiciones y parámetros dependientes mediante relaciones simples sin ciclos.
- Calcular envolvente y dimensiones generales.
- Producir piezas, proyecciones y avisos básicos de datos o interferencias.
- Contar cantos y herrajes únicamente cuando existan reglas definidas; marcar lo restante como pendiente.
- Usar el mismo módulo en un ensayo de navegador y servidor para comprobar compatibilidad temprana.

**Cierre:** ambos casos coinciden con los resultados manuales; cambiar una dimensión dependiente actualiza sus piezas. Referencias inválidas y ciclos se detectan. El caso incompleto conserva sus pendientes sin inventar cantidades.

**Evidencia:** resultados comparados y pruebas de las reglas críticas. No se exige una cantidad arbitraria de tests.

## 6. H2 — Editor modular y visor 3D

**Resultado:** el usuario puede crear su composición a partir de la paleta.

Trabajo:

- Agregar y seleccionar elementos; modificar medidas y materiales.
- Ubicar elementos con panel numérico y referencias de colocación.
- Duplicar y eliminar con tratamiento explícito de relaciones dependientes.
- Incorporar deshacer y rehacer sobre operaciones confirmadas.
- Visualizar el modelo, girar la cámara y acercar o alejar.
- Mostrar avisos y dimensiones generales derivados del motor.

**Cierre:** una persona del equipo crea desde vacío las dos tipologías sin editar el código ni recurrir a controles específicos de una sola clase de mueble. Deshacer restaura medidas y relaciones; cámara y zoom no alteran el cómputo.

**Evidencia:** demo ejecutable y registro breve de las operaciones. Aquí se evalúa la POC del núcleo junto con H1; la prueba con usuarios externos se realiza después.

**Alcance acotado:** agregar mediante botón es suficiente en esta etapa. El arrastre desde la paleta puede incorporarse después sin bloquear el núcleo.

## 7. H3 — Recuperación, planos y ficha

**Resultado:** conservar un diseño y comunicarlo mediante documentación consistente.

Trabajo:

- Guardar borrador y foto en el navegador con estados reales de guardado.
- Recuperar el último borrador confirmado al reabrir.
- Exportar e importar JSON editable sin fotografía ni datos personales, según DOC-04B.
- Presentar frente, planta y lateral desde la geometría común.
- Mostrar piezas y materiales con identificación y pendientes.
- Generar PDF desde una revisión fija, incluyendo cotas, unidades, avisos y tablas paginadas.

**Cierre:** reabrir o importar conserva geometría y relaciones. El PDF y el plano coinciden con la revisión exportada; las tablas no se cortan y los caracteres son legibles. Un archivo incompatible produce un mensaje sin reemplazar el borrador válido.

**Evidencia:** archivo editable de cada caso, PDF de ejemplo de una y varias páginas y revisión visual de las salidas.

## 8. H4 — Visualización en el ambiente

**Resultado:** visualizar el mueble creado sobre una fotografía del espacio.

Trabajo:

- Cargar una imagen y registrar medidas reales ingresadas por el usuario.
- Ajustar encuadre, ubicación y tamaño aparente sin cambiar las piezas.
- Ofrecer comparación con la imagen original.
- Incorporar una captura compuesta a la ficha de la misma revisión.
- Explicar el carácter ilustrativo y permitir retirar la imagen del envío.

**Cierre:** la composición puede ajustarse y exportarse; las medidas y cantidades permanecen iguales antes y después del ajuste visual. El usuario distingue los controles del mueble de los del encuadre en una prueba observada.

**Evidencia:** comparación antes/después, ficha con imagen y registro de medidas invariables.

Si el ajuste manual no resulta comprensible, se simplificarán sus controles y se repetirá la tarea. Si sigue sin funcionar, el hito queda pendiente y se registra una reducción de alcance explícita; no se reemplazará por una imagen generada ajena al modelo presentándola como integración exacta.

## 9. H5 — Solicitudes y atención de prueba

**Resultado:** registrar un proyecto que realmente pueda revisar el operador o profesional piloto.

Trabajo:

- Configurar datos y archivos privados, destinatario habilitado y servicio de recepción.
- Validar y recalcular la captura con el motor compartido.
- Registrar contacto, autorización, revisión fija y archivos previstos.
- Finalizar únicamente envíos completos y evitar duplicados mediante clave de reintento.
- Mostrar ID y confirmación de registro; conservar posibilidad de reintentar ante fallo.
- Preparar acceso controlado del operador y procedimiento de revisión y respuesta.

**Cierre:** un envío de prueba queda almacenado con archivos y puede recuperarse por el operador autorizado. Un reintento conserva el mismo ID. Un archivo faltante impide confirmar registro completo. Cambiar el borrador después no altera la captura enviada. La lectura pública de datos privados está impedida.

**Evidencia:** registro de prueba, recuperación autorizada, prueba de reintento y limpieza del caso. Los datos de prueba estarán separados de encargos reales.

## 10. H6 — MVP piloto y demostración

**Resultado:** recorrido integrado utilizable y revisable, con atención profesional acordada.

Trabajo:

- Corregir obstáculos del recorrido y comprobar interfaz en computadora y celular según alcance declarado.
- Ejecutar la ronda propuesta de cinco clientes y dos carpinteros de DOC-02, o registrar expresamente una muestra diferente y sus límites.
- Revisar capacidad de creación desde vacío frente a plantilla opcional.
- Confirmar profesional, zona, responsable y plazo de respuesta antes de admitir solicitudes reales.
- Definir conservación y eliminación de datos y registrar limitaciones conocidas.
- Preparar una demo reproducible, archivos de ejemplo e instrucciones de ejecución.

**Cierre técnico:** se completa crear, guardar, visualizar, descargar y registrar un pedido, sin fallos que impidan el recorrido o produzcan resultados contradictorios.

**Cierre del piloto:** existe ruta efectiva de atención, se documentaron las pruebas realizadas y se evaluaron los criterios exploratorios de DOC-02. Si no hay usuarios con necesidad real o solicitudes atendidas, la validación comercial seguirá pendiente aunque la demo funcione.

**Evidencia:** versión y commit identificados, acceso de demostración, PDFs y JSON de ejemplo, resultados de pruebas, instrucciones y lista breve de pendientes.

## 11. Prioridades y tratamiento de cambios

| Prioridad | Funciones |
| --- | --- |
| Esenciales para el MVP acordado | Creación modular con paleta mínima, edición y relaciones, modelo 3D, guardado local, JSON editable auxiliar, plano, cómputo preliminar, PDF, implantación manual y solicitud persistente con atención piloto. |
| Mejoras si no retrasan el recorrido | Arrastre desde la paleta, plantillas adicionales, texturas más trabajadas, atajos y ajustes visuales. |
| Evoluciones posteriores | Puertas y cajones completos, más familias, IA, corte optimizado, cuentas, comparación de presupuestos, pagos y reseñas. |

Puertas, cajones y patas presentes en los conceptos visuales no se consideran entregados hasta contar con reglas y controles funcionales. El equipo puede incorporar alguno durante la POC si es sencillo y verificable; ello no obliga a implementar todos.

Si el plazo resulta insuficiente, primero se posponen mejoras visuales y ampliaciones del catálogo. Si es necesario retirar una función esencial, se registra el cambio en DOC-01, DOC-04A/04B y DOC-06. La entrega resultante se identificará por su alcance real, sin declararla equivalente al MVP completo.

## 12. Dependencias y condiciones externas

| Dependencia | Cuándo resolverla | Efecto si falta |
| --- | --- | --- |
| Reglas y materiales iniciales | H0–H1 | Se puede probar geometría provisional; no afirmar validez constructiva. |
| Versiones compatibles y motor compartido | H0–H1 | Corregir selección antes de construir toda la interfaz. |
| Profesional y zona piloto | Iniciar H0; confirmar antes de H6 | La demo técnica continúa; no abrir pedidos reales sin atención. |
| Servicio remoto y alojamiento | Preparar antes de H5 | El editor puede avanzar localmente; solicitud real pendiente. |
| Imágenes y recursos con permiso | Antes de incorporarlos | Utilizar recursos propios o de prueba autorizados. |
| Plazo del evento y dedicación del equipo | Antes de calendarizar | Mantener hitos relativos, sin fecha comprometida. |

## 13. Planificación de fechas y responsables

Antes de calendarizar se completarán cuatro datos: fecha límite externa, integrantes, dedicación efectiva y disponibilidad del profesional. Cada hito tendrá un responsable principal; las asignaciones siguen pendientes.

Se estimará primero H0–H2 para medir el esfuerzo real del editor. Con ese resultado se revisará el resto, reservando tiempo explícito para integración y correcciones. No se supone que dos personas reduzcan el plazo a la mitad ni que la asistencia de IA elimine la revisión.

DOC-06 conservará la fecha objetivo, el entorno y la lista de aceptación. Este documento conservará el orden, alcance y dependencias. Una fecha no convertirá automáticamente un hito pendiente en terminado.

## 14. Definición común de entrega terminada

Un hito se considera terminado cuando su comportamiento se ejecuta en la versión identificada, se verifica el caso acordado y se registran sus limitaciones. El código deberá compilar y sus cambios pertinentes pasarán las comprobaciones necesarias.

Cada entrega incluirá una nota breve: qué funciona, cómo probarlo, resultado de verificación y pendientes que afectan al siguiente hito. Una captura, un mockup o una declaración de pruebas sin evidencia no sustituyen una función ejecutable.

## 15. Evolución después del MVP

| Evolución | Contenido posible | Evidencia que justifica priorizarla |
| --- | --- | --- |
| E1 — Mejor creación | Nuevos módulos, puertas, cajones, patas, mejores encastres y plantillas. | Pedidos repetidos o dificultades observadas con la paleta mínima. |
| E2 — Mejor documentación | Detalles de uniones, herrajes por sistema, cantos y corte optimizado. | Necesidades concretas de profesionales y reglas constructivas verificadas. |
| E3 — Mejor visualización | Oclusión, ajuste de perspectiva y asistencia visual con IA. | La implantación mejora decisiones y sus limitaciones frenan el uso. |
| E4 — Red de carpinterías | Cuentas limitadas por destinatario, presupuestos comparables y seguimiento. | Solicitudes reales y profesionales capaces de responder. |
| E5 — Confianza y cobro | Reseñas por trabajo, validación del cierre y modalidad de monetización. | Uso recurrente, valor demostrado y proceso comercial definido. |
| E6 — Otros oficios | Nuevos tipos de proyecto y documentación especializada. | Carpintería validada y necesidad específica que justifique otro flujo. |

Estas evoluciones no son una secuencia obligatoria. Se priorizarán según utilidad, esfuerzo y evidencia. Ninguna tiene fecha o presupuesto aprobado en esta versión.

## 16. Próxima acción

Completar **DOC-06 — POC, fecha y condiciones de entrega**: fijar los casos, el entorno de prueba, los límites propuestos y los criterios de aprobación antes de comenzar la implementación. La fecha quedará pendiente hasta disponer de los datos del calendario.

Después de esa definición, la primera tarea de construcción será H0: base del proyecto y dos casos de referencia. No corresponde comenzar por el marketplace ni por un editor con todos los módulos de las imágenes.

## 17. Historial

| Versión | Fecha | Cambio |
| --- | --- | --- |
| 0.1 | 04/11/2026 | Hitos del núcleo, recorrido y MVP piloto; dependencias, evidencias y evoluciones posteriores. |
| 0.2 | 12/11/2026 | Se registra la fecha límite y se marca para revisión conjunta del equipo. Sin cambios en los hitos. |
