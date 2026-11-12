# Informe descriptivo del proyecto
## Plataforma web para diseñar y cotizar muebles a medida

**Código:** DOC-01  
**Versión:** 0.2  
**Fecha:** 4 de noviembre de 2026  
**Estado:** Borrador inicial para revisión  
**Nombre comercial:** Pendiente de definición

## 1. Resumen de la propuesta

El proyecto propone una aplicación web que ayude a transformar una idea de mueble en una propuesta visual y una ficha de referencia para solicitar presupuesto a una carpintería.

El usuario podrá cargar una fotografía del ambiente, ingresar medidas reales del espacio y crear un mueble combinando elementos de una paleta modular, desde un espacio de trabajo vacío o una plantilla opcional. La aplicación presentará el mueble en 3D, permitirá visualizar su ubicación sobre la imagen del ambiente y generará vistas de referencia y un listado estimado de piezas y materiales. Finalmente, podrá descargarse una ficha PDF y registrarse una solicitud de presupuesto destinada a una carpintería piloto.

El proyecto abarca muebles en general. El MVP tendrá como función principal un editor modular para crear muebles sencillos de tableros rectangulares, con una paleta inicial acotada y reglas de ensamblaje. Escritorios, estantes y muebles bajos serán casos de ejemplo y prueba, sin constituir un catálogo cerrado. La visión futura incluye módulos más complejos y una red de profesionales con presupuestos, seguimiento y reseñas.

## 2. Problema que se busca resolver

La hipótesis inicial es que algunas personas tienen dificultades para comunicar cómo quieren un mueble, visualizarlo en su ambiente y reunir la información necesaria para solicitar una cotización. Por su parte, un carpintero puede necesitar varios intercambios para comprender el pedido y determinar sus dimensiones, material y características.

Se propone reducir esa incertidumbre mediante una descripción visual y dimensional compartida. Estas necesidades deberán contrastarse con entrevistas; este informe no constituye un estudio de mercado ni acredita demanda comprobada.

## 3. Usuarios previstos

| Usuario | Necesidad | Beneficio esperado |
| --- | --- | --- |
| Cliente particular | Definir y comunicar un mueble para su espacio. | Visualizar una propuesta y enviar un pedido más claro. |
| Carpintero o carpintería piloto | Recibir información suficiente para evaluar un encargo. | Revisar una ficha organizada y elaborar su presupuesto. |
| Equipo del proyecto | Validar el recorrido y atender solicitudes iniciales. | Observar dificultades y reunir evidencia para mejorar el producto. |

El segmento inicial, la localidad de prueba y la carpintería participante quedan pendientes de definición. El MVP no requiere un portal completo para profesionales.

## 4. Propuesta de valor

**Convertir una idea de mueble en un proyecto de referencia para cotizar con carpinteros de la zona.**

La propuesta reúne configuración, visualización en el ambiente y documentación preliminar dentro de un mismo recorrido. Su utilidad y diferenciación frente a las alternativas se evaluarán en el estudio de mercado y las pruebas con usuarios.

## 5. Objetivo del MVP

Permitir que un usuario cree un mueble sencillo mediante un editor modular, comprenda su apariencia y dimensiones, descargue una ficha coherente con el diseño y registre una solicitud de presupuesto revisable por una carpintería piloto.

El objetivo de validación es comprobar si el cliente entiende y completa el proceso, y si el carpintero considera útil la información recibida para iniciar una cotización.

## 6. Recorrido principal

1. **Crear el proyecto:** indicar un nombre y comenzar en un espacio de trabajo vacío o con una plantilla opcional de mueble.
2. **Cargar el ambiente:** subir una fotografía e ingresar el ancho disponible, la profundidad máxima y otras medidas relevantes. Registrar obstáculos conocidos cuando corresponda.
3. **Crear el mueble:** agregar tableros, laterales y estantes desde la paleta; seleccionar, dimensionar, mover, duplicar o eliminar elementos mediante controles sencillos. Ajustar posiciones con encastres y referencias para mantener relaciones coherentes. Elegir material y acabado desde una paleta controlada.
4. **Revisar el diseño:** observar el modelo 3D y sus dimensiones generales, y resolver avisos de interferencias o elementos sin unión definida. Deshacer y rehacer cambios.
5. **Visualizar en el espacio:** colocar el modelo sobre la foto y ajustar su posición, escala y orientación mediante controles sencillos. La fidelidad de esta representación se evaluará en la POC.
6. **Consultar la ficha:** revisar frente, planta y lateral, dimensiones y piezas y materiales estimados.
7. **Descargar:** obtener un PDF correspondiente a la configuración actual.
8. **Solicitar presupuesto:** ingresar datos de contacto y observaciones, autorizar su envío al destinatario identificado y registrar el pedido junto con la versión del proyecto enviada.
9. **Recibir confirmación:** visualizar que la solicitud quedó registrada. En el piloto, la revisión y respuesta comercial podrán realizarse manualmente.

## 7. Alcance funcional inicial

| Función | Alcance del MVP |
| --- | --- |
| Editor modular | Crear muebles sencillos a partir de piezas rectangulares. Plantillas opcionales como ayuda, sin restringir el producto a un escritorio. |
| Paleta de elementos | Tablero, lateral y estante como conjunto mínimo propuesto. Puerta, cajón y patas aparecen en el concepto visual; su inclusión funcional se resolverá en la POC según reglas y complejidad. |
| Operaciones | Agregar, seleccionar, dimensionar, mover, duplicar y eliminar; deshacer y rehacer. Encastres o referencias de colocación dentro del sistema modular. |
| Dimensiones y materiales | Dimensiones de piezas, relaciones entre ellas, espesor y acabados controlados. Paletas iniciales y límites por definir con el carpintero. |
| Foto del ambiente | Carga de imagen y medidas ingresadas por el usuario. |
| Vista 3D | Inspección del mueble creado mediante giro y zoom. |
| Implantación visual | Superposición del modelo sobre la fotografía con ajuste manual. No se promete medición automática ni ajuste físico exacto. |
| Plano de referencia | Frente, planta y lateral con dimensiones generales. |
| Cómputo preliminar | Listado de piezas con cantidad y dimensiones; materiales y herrajes según reglas validadas para el modelo. |
| Descarga | Ficha PDF del proyecto. |
| Contacto comercial | Registro persistente de solicitud y configuración enviada para atención por una carpintería piloto. |

Las cuentas de usuario y la recuperación de proyectos entre dispositivos se decidirán en arquitectura según las necesidades de la prueba. No son un requisito inicial del recorrido.

## 8. Contenido de la ficha de referencia

- Identificación del proyecto, fecha y versión de configuración.
- Tipo de mueble, dimensiones generales, material y espesor seleccionado.
- Vistas de frente, planta y lateral con cotas generales.
- Imagen del modelo y visualización del ambiente, cuando estén disponibles.
- Listado preliminar de piezas: identificación, cantidad, largo, ancho y espesor.
- Materiales complementarios y herrajes estimados cuando existan reglas confirmadas.
- Observaciones, supuestos y aspectos que debe revisar el carpintero.
- Indicación de que se trata de documentación preliminar sujeta a verificación antes de fabricar.

La cantidad de piezas no equivale directamente a la cantidad de placas comerciales que deben comprarse. La optimización de cortes y el desperdicio no forman parte del cálculo inicial salvo incorporación expresa y validada.

## 9. Coherencia de datos y límites técnicos

Las medidas y opciones confirmadas del proyecto deberán alimentar el modelo 3D, las vistas del plano y el listado de piezas. Una modificación deberá actualizar todos esos resultados. El PDF y la solicitud conservarán la configuración correspondiente al momento de su generación o envío.

La fotografía servirá como referencia visual. Las dimensiones provendrán de mediciones ingresadas por el usuario, no de estimaciones automáticas a partir de la foto. La implantación no garantiza por sí sola que el mueble entre en el espacio ni que pueda trasladarse o instalarse.

El cómputo deberá derivarse de los elementos colocados, sus dimensiones, sus relaciones y reglas constructivas explícitas revisadas con un carpintero. La geometría, por sí sola, no confirma estabilidad, uniones o herrajes. Los diseños con relaciones sin resolver deberán identificarse como incompletos en la ficha; no podrán presentarse como listos para fabricar. Si una cantidad no puede justificarse, se marcará como pendiente de definición en lugar de presentarse como exacta.

La inteligencia artificial es una posibilidad para interpretar descripciones o mejorar la presentación visual en una evolución posterior. No es una dependencia obligatoria del MVP ni la fuente de las medidas, el despiece o la validación constructiva.

## 10. Funciones previstas para futuras versiones

- Más familias de muebles y plantillas iniciales de mayor complejidad.
- Nuevos módulos y configuraciones, con reglas propias.
- Interpretación de bocetos y descripciones asistida por IA.
- Integración visual más realista en fotografías.
- Optimización de cortes y estimación de compra de placas.
- Precios orientativos con fuentes, fecha y alcance identificados.
- Perfiles de profesionales y comparación de presupuestos.
- Seguimiento de pedidos y reseñas asociadas a trabajos realizados.
- Pagos dentro de la plataforma, sujetos a evaluación específica.
- Ampliación a otros oficios, después de validar el caso de carpintería.

El editor modular sencillo forma parte del MVP. El modelado CAD de geometría arbitraria, formas curvas, análisis estructural automático, el mercado completo de oficios y el presupuesto final automático quedan fuera de esta primera versión.

## 11. Presupuesto y relación con el profesional

El MVP no garantizará un precio final automático. El carpintero revisará medidas, material, uniones, terminaciones, herrajes, transporte e instalación antes de emitir su propuesta comercial.

La plataforma facilitará el pedido inicial; el alcance definitivo del trabajo y las condiciones comerciales deberán confirmarse con el profesional. En esta etapa no se define una comisión, suscripción ni cobro por solicitud: son alternativas para estudiar.

## 12. Supuestos y cuestiones pendientes

| Supuesto o decisión | Forma prevista de resolverlo |
| --- | --- |
| El cliente puede obtener las medidas mínimas del espacio. | Probar instrucciones de medición con usuarios. |
| La visualización ayuda a decidir o comunicar el pedido. | Observar su uso y preguntar qué decisiones facilita. |
| La ficha aporta información útil para cotizar. | Revisarla con un carpintero sobre un caso concreto. |
| Un usuario puede crear un mueble con una paleta limitada. | Probar tareas de creación y modificación sin asistencia operativa. |
| Los muebles creados pueden documentarse con coherencia. | Definir reglas por elemento, relaciones, límites y avisos con el profesional; comprobar al menos dos tipologías sencillas. |
| La implantación manual resulta comprensible. | Evaluarla en la POC y ajustar controles o alcance. |
| Existe interés de profesionales en recibir solicitudes. | Entrevistas y acuerdo con una carpintería piloto. |
| Plazo y recursos disponibles. | Confirmar reglas del hackathon, integrantes, dedicación y presupuesto. |

No se han fijado aún tecnologías, proveedores de IA, costos operativos, fecha de entrega ni metas numéricas de validación.

## 13. Condiciones generales de calidad

- Mostrar unidades de forma consistente y advertir configuraciones fuera de los límites permitidos.
- Mantener coherencia entre elementos, relaciones, modelo, vistas, cómputo y PDF, incluso al duplicar, eliminar o redimensionar piezas.
- Diferenciar entre una pieza de tablero, un conjunto como un cajón y un herraje comercial para evitar doble conteo.
- Evitar posiciones ambiguas mediante referencias y mostrar conflictos detectados sin prometer una validación constructiva completa.
- Presentar controles comprensibles y mensajes claros ante errores de carga o envío.
- Permitir completar el recorrido en computadora y disponer de una interfaz usable en celular; el alcance de la edición 3D móvil se verificará en las pruebas.
- Confirmar el registro efectivo de solicitudes y evitar pedidos duplicados por reintentos.
- Solicitar solamente los datos necesarios e informar qué fotos, datos y documentos recibirá la carpintería. La conservación y eliminación se definirán antes del piloto.

Los criterios medibles y casos de prueba se desarrollarán en la ficha de POC y estándar de entrega.

## 14. Resultado esperado

Una demostración funcional en la que una persona cree un mueble sencillo con la paleta modular, lo visualice sobre una foto de su ambiente, descargue una ficha de referencia y registre un pedido que pueda revisar una carpintería piloto.

La demostración deberá aportar evidencia sobre la coherencia técnica del proyecto y su utilidad para cliente y profesional. Las conclusiones definirán si corresponde ampliar funciones, corregir el recorrido o revisar la propuesta.

## 15. Documentación relacionada y siguiente paso

Este informe establece la base conceptual. Se completará con el estudio de mercado, los modelos visuales, la arquitectura, el modo de desarrollo y herramientas, el plan evolutivo y la ficha de POC con fecha y condiciones de entrega.

El siguiente documento será el **Estudio de mercado y validación de la propuesta**. Sus resultados podrán modificar este alcance antes de iniciar la implementación.

## 16. Referencias visuales y alcance de las paletas

Las imágenes conceptuales muestran dos momentos: visualización del mueble en el ambiente y creación modular con ficha de referencia. La primera imagen utiliza un escritorio como ejemplo; su texto específico no limita el producto. La segunda muestra un mueble bajo y una paleta de componentes. Son referencias de interfaz, no evidencias de funciones implementadas ni planos constructivos validados.

La paleta de componentes define qué elementos puede agregar el usuario. La paleta de materiales y colores define opciones de tablero y acabado. Los colores iniciales ilustrativos son roble, blanco y nogal; marcas, disponibilidades, espesores y compatibilidades quedan por definir. No se presupone que cualquier combinación sea fabricable.

## 17. Historial

| Versión | Fecha | Cambio |
| --- | --- | --- |
| 0.1 | 04/11/2026 | Primera descripción del proyecto y delimitación propuesta del MVP. Pendiente de revisión del equipo y validación externa. |

| 0.2 | 04/11/2026 | Editor modular como función principal; muebles generales, paletas, operaciones y validación de creación. Escritorio conservado como ejemplo. |
