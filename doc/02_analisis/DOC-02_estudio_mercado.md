# Estudio de mercado y validación de la propuesta
## Plataforma web para diseñar y cotizar muebles a medida

**Código:** DOC-02  
**Versión:** 0.3  
**Fecha de consulta:** 4 de noviembre de 2026  
**Estado:** Investigación exploratoria. Trabajo de campo inicial realizado: encuesta a 31 clientes, encuesta a 4 carpinterías y 2 testimonios (`encuestas/`, `testimonios/`; resultados consolidados en DOC-02A §2). Entrevistas y pruebas de uso pendientes.  
**Alineación (12/11/2026):** hay puntos de alcance que difieren de lo ya definido por el equipo. Ver `doc/coherencia_y_decisiones.md`.  
**Documento base:** DOC-01 — Informe descriptivo V0.2.

## 1. Objetivo

Identificar alternativas existentes, formular una diferenciación defendible y definir cómo comprobar si clientes y carpinteros necesitan el recorrido propuesto: crear un mueble con una paleta modular, visualizarlo en su ambiente, descargar una ficha preliminar y solicitar presupuesto.

Este estudio sirve para orientar el MVP. No demuestra todavía viabilidad comercial, demanda suficiente ni disposición de pago.

## 2. Método y límites

Se revisaron páginas públicas de los propios proveedores, consultadas en la fecha indicada. Las funciones se describen según lo publicado por cada empresa: no se ejecutaron pruebas completas, compras ni verificaciones independientes de calidad o exactitud.

Se distinguen tres tipos de contenido:

- **Observación documental:** función o proceso descrito por una fuente identificada.
- **Inferencia del proyecto:** interpretación de esas observaciones para orientar decisiones.
- **Hipótesis:** afirmación pendiente de entrevistas, experimentos o resultados reales.

La comparación es selectiva, no un relevamiento exhaustivo. Los referentes internacionales aportan patrones de producto; no se asume que operen en Argentina. Tampoco se presume cobertura efectiva de plataformas locales en la futura localidad piloto. No se investigaron participaciones de mercado ni volúmenes de usuarios o ventas.

## 3. Mercado inicial propuesto

**Hipótesis de segmento:** personas que necesitan crear o adaptar un mueble sencillo a medida para su hogar o espacio de trabajo, con restricciones de espacio o distribución. El segmento es una propuesta de prueba, no una conclusión estadística.

**Oferta inicial:** una o dos carpinterías que fabriquen muebles de placas y estén dispuestas a revisar solicitudes. Antes del lanzamiento debe confirmarse capacidad, zona de atención y condiciones de respuesta.

**Geografía:** Jujuy (San Salvador de Jujuy y alrededores), donde el equipo ya obtuvo respuestas de clientes y de carpinterías. Es requisito de participación del hackatón.

| Segmento | Necesidad a comprobar | Prioridad propuesta |
| --- | --- | --- |
| Personas con necesidad actual o reciente de un mueble sencillo a medida | Comunicar dimensiones y apariencia, y encontrar quién lo fabrique. | Principal para el piloto. |
| Carpinterías pequeñas de muebles de placas | Recibir pedidos mejor definidos sin aumentar el trabajo de revisión. | Socio indispensable. |
| Personas que fabrican por cuenta propia | Obtener piezas y cortes para construir. | Secundario; necesidad distinta del servicio de contratación. |
| Otros oficios y muebles complejos | Resolver proyectos con otras reglas y profesionales. | Fuera de la validación inicial. |

## 4. Alternativas identificadas

| Alternativa | Funciones publicadas y fuente | Relación con la propuesta |
| --- | --- | --- |
| Armandolo | Configuración de muebles de melamina, representación 3D, piezas, herrajes y corte por plancha; incluye escritorios. [F1–F2] | Solapamiento directo con la configuración y el despiece. Obliga a diferenciar más allá de generar piezas. |
| Tylko | Configurador para modificar dimensiones, colores y otras opciones del mobiliario en tiempo real. [F3] | Referente de experiencia de personalización y venta de muebles. |
| Pickawood | Configuradores de mobiliario a medida, con categorías que incluyen mesas y escritorios. [F4] | Referente de configuración ligada a la oferta de un fabricante/proveedor. |
| IKEA Kreativ | Visualización de productos IKEA en el espacio del usuario mediante foto y herramientas de planificación. [F5] | Referente de visualización contextual, ligado a su catálogo. |
| Servidos | Publicación de trabajos, ofertas, chat, perfiles y reseñas; el sitio presenta servicios de carpintería en Argentina. [F6–F7] | Solapamiento con conexión entre clientes y profesionales. No se comprobó actividad en la zona piloto. |
| Habitissimo | Su ayuda en español describe solicitudes de presupuesto, contacto con profesionales y opiniones posteriores. [F8] | Referente de intermediación. La fuente consultada corresponde a España y tiene actualización de 2019; no acredita operación argentina actual. |
| Contacto directo por WhatsApp, recomendación o redes | Alternativa de referencia para las entrevistas; su frecuencia y eficacia no fueron medidas. | Debemos comprobar si nuestra ficha mejora un proceso que el cliente ya puede realizar directamente. |

La ausencia de una función en las páginas consultadas no prueba que el proveedor no la tenga. Para cada competidor quedan pendientes la prueba de uso, las condiciones comerciales y la cobertura pertinente.

## 5. Hallazgos y consecuencias para el MVP

**Observación:** ya existen herramientas que resuelven configuración y despiece, y otras que conectan clientes con profesionales. Las fuentes F1–F8 respaldan estos antecedentes.

**Inferencia:** presentar la idea únicamente como un generador de planos o una plataforma de oficios no establece una diferencia suficiente. La oportunidad a investigar es unir esas capacidades con un editor modular fácil de usar para una persona sin conocimientos técnicos. Que el usuario pueda crear su composición es una decisión de producto, no una demanda comprobada.

**Hipótesis de diferenciación:** el cliente puede crear su propio mueble con elementos de una paleta, entender cómo quedará en su ambiente y enviar una ficha coherente que un carpintero local pueda revisar y adaptar para cotizar.

No se afirma que esta combinación sea única ni que garantice demanda. La facilidad de uso, la utilidad profesional y la respuesta efectiva del carpintero serán más relevantes que la cantidad de funciones.

## 6. Posicionamiento propuesto

**“Creá tu mueble, visualizalo en tu espacio y compartí una ficha de referencia para pedir presupuesto.”**

El cliente conserva la decisión y el carpintero conserva la revisión constructiva y comercial. El plano y los materiales son preliminares; la imagen del ambiente no constituye una medición.

El MVP se actualiza a un editor modular acotado para muebles sencillos de tableros rectangulares. Los escritorios son un ejemplo, junto con estantes y muebles bajos. La POC deberá comprobar al menos dos tipologías utilizando el mismo sistema de elementos y relaciones. No se propone competir inicialmente en amplitud de catálogo, optimización industrial de cortes, pagos o red nacional de profesionales.

## 7. Hipótesis críticas

| Código | Hipótesis | Evidencia buscada |
| --- | --- | --- |
| H1 | El cliente tiene dificultades concretas para definir o comunicar el pedido. | Relatos de encargos reales, aclaraciones y cambios recientes. |
| H2 | Puede ingresar las medidas mínimas con una guía breve. | Ejercicio observado y registro de errores o dudas. |
| H3 | La vista en el ambiente aporta una decisión útil. | Comparación con la ficha sin implantación y explicación del cambio realizado. |
| H4 | La ficha ayuda al carpintero a iniciar la cotización. | Revisión de un caso y comparación con un pedido de texto y foto. |
| H5 | Hay intención de solicitar un presupuesto real. | Solicitud voluntaria y consentimiento para compartirla con un profesional identificado. |
| H6 | El profesional acepta revisar pedidos y responder. | Compromiso operativo y atención de una solicitud real. |
| H7 | Alguna parte pagaría por el servicio. | Prueba posterior de una oferta concreta; una respuesta favorable en entrevista no basta. |
| H8 | Un usuario sin formación puede crear su composición con una paleta acotada. | Tarea desde un espacio vacío: agregar, dimensionar, ubicar y modificar elementos sin que opere el facilitador. |
| H9 | La libertad de creación aporta valor frente a adaptar una plantilla. | Comparar ambas tareas, registrar preferencia razonada, errores y resultado, sin asumir que más libertad es mejor. |
| H10 | La paleta permite diseños suficientemente claros para revisión profesional. | Evaluar dos tipologías, relaciones, interferencias y datos faltantes con los carpinteros. |

## 8. Investigación con personas

### 8.1 Muestra exploratoria propuesta

Entrevistar a **8 potenciales clientes** con una compra reciente o necesidad actual de mueble sencillo a medida y a **4 carpinteros** con experiencia en muebles de placas. Estas cantidades son metas operativas iniciales, no una muestra representativa.

Incluir personas ajenas al círculo cercano y participantes con distinta experiencia digital. Registrar cómo se reclutó a cada participante. No convertir las respuestas de amigos o contactos voluntarios en porcentajes del mercado.

No se enviarán mensajes ni se contactará a participantes desde este documento; el reclutamiento y las entrevistas están pendientes.

### 8.2 Guion para clientes

1. Contame la última vez que buscaste o encargaste un mueble a medida.
2. ¿Cómo encontraste al profesional y qué le enviaste inicialmente?
3. ¿Qué tuviste que medir y qué dudas aparecieron?
4. ¿Cuántas aclaraciones o modificaciones necesitaste antes de recibir una propuesta?
5. ¿Cómo imaginaste si el mueble quedaría bien en tu ambiente?
6. ¿Qué te hizo aceptar, postergar o abandonar el pedido?
7. ¿Qué información te faltó para decidir?
8. ¿Qué partes de ese mueble necesitabas cambiar o combinar y cómo lo explicaste?

Después del relato, mostrar el concepto y pedir que explique qué entiende. Evitar empezar con “¿usarías esta app?” o presentar la solución antes de conocer la experiencia.

### 8.3 Guion para carpinteros

1. ¿Cómo llegan los pedidos y qué información suele faltar?
2. ¿Qué necesitás para emitir una estimación y qué exige una visita?
3. ¿Cómo definís medidas, uniones, material y herrajes?
4. ¿Qué problemas te generaría recibir un plano hecho por una aplicación?
5. Revisando esta ficha, ¿qué podés cotizar y qué tendrías que corregir?
6. ¿Aceptarías una prueba con una solicitud real? ¿En qué zona y plazo podrías responder?
7. ¿Cómo evaluás hoy si vale la pena atender una consulta?

Hablar de cobros después de entender el flujo actual y el valor aportado. No interpretar disposición a probar como compromiso de pago.

## 9. Experimento de uso

Realizar una primera ronda con **5 clientes** y **2 carpinteros**; pueden participar entrevistados anteriores, dejando constancia de que ya conocen la idea.

**Tarea del cliente:** con una foto y medidas disponibles, crear un mueble sencillo desde un espacio vacío usando la paleta: agregar tableros, laterales y estantes, cambiar dimensiones, duplicar o eliminar un elemento y resolver su colocación. Revisar la implantación, interpretar el plano y descargar la ficha. Incluir un segundo ejercicio con plantilla opcional y alternar el orden entre participantes. Registrar tiempo, asistencia y errores de cada modo. Distribuir los casos entre al menos dos tipologías, por ejemplo estante y escritorio o mueble bajo. Las tipologías son tareas de prueba, no un catálogo exclusivo. Si existe una necesidad genuina, ofrecer registrar la solicitud; no pedir un encargo ficticio para aumentar conversiones.

**Tarea del carpintero:** comparar un pedido breve con foto frente a la ficha del mismo caso. Alternar el orden entre participantes para reducir el efecto de presentación. Registrar información faltante, aclaraciones necesarias y posibilidad de cotizar de manera preliminar.

Los casos de demostración se identificarán como tales. Solicitudes, respuestas, contrataciones y trabajos terminados se registrarán como eventos diferentes.

## 10. Métricas y reglas de decisión propuestas

| Indicador | Cómo medirlo | Umbral exploratorio propuesto |
| --- | --- | --- |
| Finalización | Personas que completan creación modular y descarga / personas que inician la tarea. Registrar por separado resultados desde vacío y desde plantilla. | Al menos 4 de 5, sin que el facilitador opere por ellas. |
| Edición modular | Capacidad de agregar, dimensionar y reubicar un elemento; duplicar o eliminar otro. | Al menos 4 de 5 completan estas acciones sin operación del facilitador; registrar errores y asistencia verbal. |
| Comprensión | Explicación de dimensiones y carácter preliminar de la ficha. | Al menos 4 de 5 interpretan ambos correctamente. |
| Aporte de la implantación | Decisión concreta que cambia o se confirma al ver el ambiente. | Al menos 3 de 5 describen un aporte concreto; si no, revisar su prioridad. |
| Utilidad profesional | Revisión del caso por los carpinteros. | Ambos pueden iniciar una estimación e identifican solo aclaraciones abordables. |
| Oferta disponible | Compromiso y prueba de atención. | Al menos un carpintero acepta y atiende una solicitud real bajo un plazo acordado. |

Estos umbrales son criterios propuestos del equipo; deberán fijarse antes de la prueba y no se presentan como estándares del sector. Las muestras son demasiado pequeñas para estimar tasas comerciales.

Si no hay participantes con necesidad real, el interés comercial queda sin evaluar aunque el prototipo pase la prueba de uso. Si el carpintero debe rehacer toda la información, revisar la ficha y las reglas antes de ampliar el sistema. Si el flujo resulta útil sin la vista del ambiente, simplificar o posponer esa función.

## 11. Dimensión de mercado

No se dispone todavía de datos suficientes para calcular TAM, SAM o SOM de manera defendible. No se incluyen cifras generales de construcción como sustituto del mercado de muebles sencillos a medida.

Para el piloto, utilizar una estimación desde la capacidad real:

**Capacidad mensual de atención = carpinterías activas × solicitudes que cada una acepta revisar por mes.**

El volumen comercial posible estará limitado por el menor de dos valores: pedidos calificados generados y capacidad profesional de atenderlos. Las contrataciones dependerán además de precios, respuesta y aceptación del cliente.

Los valores se completarán con entrevistas y registros del piloto. Una proyección basada en supuestos deberá rotularse como escenario, nunca como ventas previstas confirmadas.

## 12. Modelo de negocio: alternativas a probar

| Alternativa | Posible beneficio | Pregunta pendiente |
| --- | --- | --- |
| Suscripción para carpinterías | Ingreso recurrente por herramienta y gestión. | ¿Existe uso suficientemente frecuente y valor medible? |
| Cobro por solicitud calificada | Cobro asociado a una oportunidad. | ¿Qué define un pedido válido y cómo se manejan duplicados o consultas sin respuesta? |
| Comisión por contratación | Ingreso vinculado al trabajo cerrado. | ¿Cómo confirmar el cierre y evitar que el seguimiento resulte costoso? |
| Cobro por ficha o servicio de diseño | Valor directo al cliente por documentación. | ¿Pagará antes de tener un presupuesto y qué espera recibir? |

**Decisión del equipo (12/11/2026):** se adopta la **comisión por trabajo concretado** (8% a 12%, a cargo de la carpintería). Lo respaldan los datos: solo el 19% de los clientes pagaría una suscripción. Queda pendiente decidir si la seña por Mercado Pago entra en el MVP. No se fija precio final en esta versión. Para el piloto se propone acceso sin cobro, con alcance y duración definidos. Su conversión no demostraría disposición a pagar.

## 13. Captación y operación inicial

Probar primero una sola zona con acceso a un profesional dispuesto a colaborar. Reclutar clientes con necesidad real mediante contactos autorizados, comunidades locales y la carpintería participante. No invertir en publicidad hasta disponer de una ruta de atención y una forma de medir solicitudes calificadas.

La cantidad de visitas y comentarios puede registrarse para el hackathon, pero no sustituye las métricas de tarea completada, presupuesto solicitado y respuesta profesional. Las reglas y la fecha del evento siguen pendientes de confirmación.

## 14. Riesgos y respuestas

| Riesgo | Respuesta propuesta |
| --- | --- |
| Alternativas existentes cubren la necesidad suficientemente. | Comparar el recorrido y comprobar qué mejora concreta aporta el piloto. |
| Crear con módulos resulta más difícil que explicar el pedido al carpintero. | Comparar espacio vacío y plantilla opcional, simplificar la paleta y observar tareas sin asistencia. |
| La libertad de edición permite composiciones incoherentes. | Introducir referencias de colocación, reglas por elemento y avisos; revisar con el profesional. |
| La imagen crea expectativas de precisión. | Separar visualización de dimensiones verificadas y evaluar comprensión. |
| La ficha interfiere con el método del carpintero. | Codiseñar el contenido y mantener revisión profesional. |
| Llegan solicitudes sin capacidad de respuesta. | Limitar zona y volumen según disponibilidad acordada. |
| El uso gratuito se confunde con demanda comercial. | Separar usabilidad, intención real, contratación y pago. |
| Se comparten fotos o contactos sin claridad. | Identificar al destinatario y obtener autorización para compartir el pedido. |

## 15. Conclusión provisional y próximo paso

La investigación documental confirma antecedentes en configuración, visualización e intermediación; no acredita una necesidad local desatendida. La diferenciación propuesta es facilitar el paso desde el espacio del cliente hasta un pedido que un carpintero pueda revisar.

Se adopta el alcance modular de DOC-01 V0.2 y se priorizan entrevistas, pruebas de creación y revisión de la ficha con profesionales. Este cambio responde a la definición del producto por el equipo; no se presenta como un resultado de mercado. Antes de ampliar la paleta o desarrollar una plataforma de oficios, necesitamos evidencia de facilidad de creación, utilidad y capacidad de respuesta.

El siguiente documento será **03 — Modelos visuales y recorrido del usuario**, identificando las pantallas como prototipos sujetos a los resultados de validación. Este estudio se actualizará con entrevistas y pruebas; no deberá marcarse como validado sin esos registros.

## 16. Registro para trabajo de campo

| Registro | Estado al emitir V0.2 |
| --- | --- |
| Entrevistas de clientes | Pendientes; 0 realizadas en este estudio. |
| Entrevistas de carpinteros | Pendientes; 0 realizadas en este estudio. |
| Pruebas observadas | Pendientes. |
| Solicitudes y presupuestos reales | Sin datos aportados. |
| Localidad y carpintería piloto | Pendientes de definición. |
| Responsables y fechas de ejecución | Pendientes de asignación por el equipo. |

Para cada entrevista registrar código anónimo, fecha, perfil, experiencia reciente, hallazgos, evidencia y decisión asociada. Para cada prueba registrar tarea, asistencia, resultado y obstáculos. No publicar datos de contacto en el informe.

## 17. Fuentes

Fuentes consultadas el 04/11/2026. Las descripciones comerciales pertenecen a sus respectivos proveedores y pueden cambiar.

- **F1. Armandolo — página principal:** https://www.armandolo.com/
- **F2. Armandolo — configurador de escritorio:** https://www.armandolo.com/configurador?modulo=escritorio
- **F3. Tylko — explicación del configurador:** https://tylko.com/en-at/faq/articles/customisation/what-is-the-configurator
- **F4. Pickawood — configuradores:** https://www.pickawood.com/en/configurator
- **F5. IKEA — What is IKEA Kreativ?:** https://www.ikea.com/us/en/customer-service/knowledge/articles/43460e1e-dd01-4fe8-86ac-74efecd7743f.html
- **F6. Servidos — funcionamiento:** https://servidos.ar/como-funciona
- **F7. Servidos — carpinteros en Buenos Aires:** https://servidos.ar/servicios/carpintero/buenos-aires
- **F8. Habitissimo — solicitud de presupuesto, ayuda española, actualización indicada 20/06/2019:** https://soporte.habitissimo.com/hc/es/articles/203982986--Qu%C3%A9-es-Pedir-Presupuesto

## 18. Historial

| Versión | Fecha | Cambio |
| --- | --- | --- |
| 0.1 | 04/11/2026 | Investigación documental inicial, comparación de alternativas y protocolo propuesto de validación. Sin trabajo de campo ejecutado. |

| 0.2 | 04/11/2026 | Adecuación al editor modular de muebles; nuevos segmentos, hipótesis y tareas de creación. Se conservan fuentes y pendientes; no se realizaron nuevas entrevistas ni investigación externa para esta revisión. |
| 0.3 | 12/11/2026 | Registro del trabajo de campo realizado, zona Jujuy y modelo de comisión elegido por el equipo. |
