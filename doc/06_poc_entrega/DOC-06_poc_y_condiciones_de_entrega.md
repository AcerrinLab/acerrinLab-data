# POC y condiciones de entrega
## Viruta – plataforma web para diseñar, visualizar y encargar muebles a medida

**Código:** DOC-06
**Versión:** 0.3
**Fecha:** 13 de noviembre de 2026
**Estado:** Protocolo propuesto. Pruebas no ejecutadas.
**Bases:** DOC-02A y DOC-02B V0.3, DOC-04A V0.3, DOC-05 V0.3.

---

## 1. Objetivo

Definir cómo se comprueba que lo construido cumple DOC-02A antes de presentarlo:

- **Núcleo:** el cliente arma un mueble desde una plantilla, ve si entra, lo ve en AR y obtiene la lista de materiales con resultados correctos (F1, F2 y tracción).
- **Recorrido completo:** el cliente pide presupuesto y la carpintería lo responde, cobra la seña y sigue el trabajo desde su panel (F3).

Las pruebas salen de los **criterios de aceptación de DOC-02A** y se escriben antes del código (TDD). Aprobar la parte técnica no demuestra demanda ni que el mueble sea fabricable tal cual: eso lo verifica la carpintería.

Es un estándar interno del proyecto, no una norma del sector.

## 2. Fechas y responsables

| Dato | Estado |
| --- | --- |
| Entrega del proyecto | 13/11/2026 |
| Hackatón | 22/11/2026 |
| Responsable de desarrollo | Maximo Acosta Gloss |
| Responsable de aceptación | José Manuel Fernández (a confirmar) |
| Carpinterías para la prueba de uso | Jujuy. Candidatas: las que respondieron la encuesta. A confirmar. |

## 3. Alcance de aceptación

### Núcleo (mínimo para la entrega, según la propuesta de DOC-05 §12)

- Plantillas paramétricas, medidas del espacio con aviso, material y color, AR, guardado y guía de cómo medir (RF-01 a RF-06).
- Despiece, placas, herrajes y barniz, y costo estimado si hay precios con fuente (RF-07 a RF-10).
- Lista de espera y panel de métricas (RF-20, RF-21).

### Recorrido completo

- Cuentas, perfil y mapa de carpinterías (RF-12 a RF-14).
- Pedido, aviso, presupuesto, seña con comisión y estados (RF-15 a RF-19).
- Panel de la carpintería (RF-27 a RF-30).

### Fuera de la prueba

Lo que DOC-02A marca como post-MVP (§4) y fuera de alcance (§5): PDF, chatbot, tutorial, catálogo de fotos, reseñas, más plantillas, agenda de visitas, diseño libre, chat en vivo, uso sin conexión, app nativa y cotización automática con proveedores. También la optimización real de cortes.

## 4. Entorno y límites

Los valores salen de DOC-02B. Se registran antes de ejecutar las pruebas y no se cambian después para ocultar un resultado.

| Parámetro | Valor |
| --- | --- |
| Dispositivo principal | Celular Android de gama media real, con Chrome. Registrar modelo y versión. |
| Otros dispositivos | iPhone con Safari (si hay uno disponible) y PC con Chrome. |
| Actualización del 3D al cambiar una medida | Menos de 1 s (RF-01). |
| Fluidez del visor 3D | 30 fps o más en el Android registrado (RNF-04). |
| Modelo para AR | Menos de 5 MB; abre en menos de 3 s con 4G (RNF-04). |
| Respuesta de la API | p95 menor a 500 ms, sin contar IA (RNF-04). |
| Primer mueble en AR | Menos de 5 minutos para una persona sin experiencia (RNF-02). |
| Aviso por WhatsApp | Llega en menos de 1 minuto (RF-16). |
| Medidas | Milímetros enteros; tablero de referencia de 18 mm. |
| Tamaño de placa de referencia | 2400 × 1800 mm. |

Para los tiempos: una ejecución de calentamiento y después cinco mediciones; las cinco tienen que cumplir.

## 5. Casos de referencia

Los resultados se calcularon a mano. Comprueban medidas nominales y cantidades; no son instrucciones de fabricación. No se descuenta el espesor del corte de la sierra.

### Caso A — Estante

Plantilla estante de **800 mm de ancho × 900 mm de alto × 300 mm de profundidad**, tablero de 18 mm, un estante interior. Dos laterales de altura completa; tapa, base y estante entre los laterales. Sin fondo ni puertas.

| Pieza | Cantidad | Medidas por pieza |
| --- | --- | --- |
| Lateral | 2 | 900 × 300 × 18 mm |
| Tapa | 1 | 764 × 300 × 18 mm |
| Base | 1 | 764 × 300 × 18 mm |
| Estante | 1 | 764 × 300 × 18 mm |
| **Total** | **5** | Superficie de tablero: 1,2276 m² |

Ancho interior: 800 − 2 × 18 = 764 mm. Placas de 2400 × 1800 mm: **1** (redondeado hacia arriba).

**Modificación:** con 1000 mm de ancho, tapa, base y estante pasan a 964 × 300 × 18 mm; los laterales no cambian. Siguen siendo 5 piezas; superficie 1,4076 m².

### Caso B — Mesa

Plantilla mesa de **1200 mm de ancho × 750 mm de alto × 600 mm de profundidad**, tablero de 18 mm. Cubierta apoyada sobre dos laterales en los extremos.

| Pieza | Cantidad | Medidas por pieza |
| --- | --- | --- |
| Cubierta | 1 | 1200 × 600 × 18 mm |
| Lateral | 2 | 732 × 600 × 18 mm |
| **Total** | **3** | Superficie de tablero: 1,5984 m² |

**Modificación:** con 800 mm de alto, los laterales pasan a 782 × 600 × 18 mm; la cubierta no cambia. Superficie 1,6584 m².

### Caso C — Placas (testimonio 2)

| Caso | Entrada | Resultado esperado |
| --- | --- | --- |
| C1 | 5 piezas de 1800 × 400 mm en placa de 2400 × 1800 mm | **1 placa** (entran 6 piezas por placa) |
| C2 | 8 piezas de 1800 × 400 mm en placa de 2400 × 1800 mm | **2 placas** (redondeo hacia arriba) |

El testimonio 2 expresa el resultado con fracciones ("dos placas y media"). DOC-02A pide redondear hacia arriba; mostrar también la fracción queda a decidir.

### Caso D — Medidas inválidas

| Entrada | Resultado esperado |
| --- | --- |
| Ancho 0 | Se rechaza; se conserva el último diseño válido. |
| Ancho negativo | Se rechaza; se conserva el último diseño válido. |
| Ancho mayor al máximo de la plantilla | Se rechaza y se muestra el rango permitido. |

### Caso E — No entra en el espacio

Estante del caso A (800 × 900 × 300 mm) en un espacio de 780 mm de ancho, 1000 mm de alto, 320 mm de profundidad adelante y 290 mm atrás.

| Comprobación | Resultado esperado |
| --- | --- |
| Ancho | Aviso: el mueble supera el espacio por 2 cm. |
| Profundidad | Aviso de profundidades distintas; se usa 290 mm. Aviso: el mueble supera el espacio por 1 cm. |
| Alto | Sin aviso. |

## 6. Matriz de aceptación del núcleo

Todos los criterios empiezan en **No ejecutado**.

| ID | Requisito | Acción | Resultado esperado | Evidencia |
| --- | --- | --- | --- | --- |
| N01 | RF-01 | Cambiar una medida de la plantilla. | El 3D se actualiza en menos de 1 s. | Medición de tiempo. |
| N02 | RF-01 | Ejecutar el caso D. | Se rechazan las medidas inválidas sin perder el diseño. | Captura de cada caso. |
| N03 | RF-02 | Ejecutar el caso E. | Avisos con la diferencia en cm y uso de la profundidad menor. | Captura. |
| N04 | RF-03 | Elegir material y color. | El 3D muestra el color; el material queda guardado. | Captura y dato guardado. |
| N05 | RF-04 | Abrir la AR en Android con Chrome, en iPhone con Safari y en PC. | AR a escala real en celulares; visor 3D en PC. | Video o captura por dispositivo. |
| N06 | RF-04 | Girar, hacer zoom y mover el mueble en AR. | Las medidas y cantidades no cambian. | Comparación antes y después. |
| N07 | RF-05 | Guardar, cerrar y reabrir un proyecto. | Mismas medidas, material y color. | Comparación. |
| N08 | RF-06 | Abrir la guía de cómo medir desde el paso de medidas. | Se ve la ilustración. | Captura. |
| N09 | RF-07 | Ejecutar los casos A y B y sus modificaciones. | Piezas y medidas iguales a las esperadas. | Pruebas automáticas. |
| N10 | RF-08 | Ejecutar los casos C1, C2 y la placa del caso A. | Cantidades de placas iguales a las esperadas. | Pruebas automáticas. |
| N11 | RF-09 | Ver la lista de materiales de los casos A y B. | Tornillos, bisagras o correderas y barniz con su unidad. | Captura. |
| N12 | RF-10 | Ver el costo estimado. | Etiqueta "estimado" y fecha de los precios. Si RF-10 pasa a post-MVP, se registra como alcance modificado. | Captura. |
| N13 | RF-20 | Inscribirse en la lista de espera. | El contador sube en 1. | Captura antes y después. |
| N14 | RF-21 | Ver el panel interno. | Los números coinciden con la base de datos. | Consulta comparada. |
| N15 | RNF-01, RNF-12 | Correr las pruebas del módulo `materiales`. | Todas pasan; cobertura de 80% o más. | Reporte de pruebas. |
| N16 | RNF-02 | Prueba con una persona sin experiencia. | Primer mueble en AR en menos de 5 minutos, sin ayuda. | Registro de tiempo. |
| N17 | RNF-04 | Medir el visor y el modelo AR en el Android registrado. | 30 fps o más; modelo de menos de 5 MB que abre en menos de 3 s. | Medición. |

## 7. Matriz de aceptación del recorrido completo

| ID | Requisito | Acción | Resultado esperado | Evidencia |
| --- | --- | --- | --- | --- |
| R01 | RF-12 | Entrar como cliente a la bandeja de una carpintería. | Acceso denegado. | Prueba automática. |
| R02 | RF-13 | Crear un perfil sin zona o sin WhatsApp. | No aparece en el mapa. | Captura. |
| R03 | RF-14 | Elegir melamina y abrir el mapa. | Solo aparecen carpinterías que trabajan melamina. | Captura. |
| R04 | RF-15 | Pedir presupuesto. | Pedido *Pendiente*; la carpintería ve diseño, medidas, material y despiece. | Captura del panel. |
| R05 | RF-15 | Editar el proyecto después de enviar el pedido. | El pedido enviado no cambia. | Comparación. |
| R06 | RF-15 | Reintentar el envío con la misma clave. | Se devuelve el mismo pedido; no se duplica. | Consulta de la base de datos. |
| R07 | RF-16 | Crear un pedido. | Aviso por WhatsApp en menos de 1 minuto con el enlace al pedido. | Captura del mensaje. |
| R08 | RF-16 | Simular una falla de n8n. | Se reintenta y el pedido igual está en la bandeja. | Registro. |
| R09 | RF-17 | Responder un presupuesto con materiales y mano de obra. | Pedido *Presupuestado*; el cliente ve el detalle. | Captura. |
| R10 | RF-18 | Pagar la seña en el entorno de prueba de Mercado Pago. | Pedido *Aceptado* solo después del webhook; comisión calculada. | Registro del webhook. |
| R11 | RF-18 | Enviar un webhook con firma inválida. | Se rechaza; el pedido no cambia. | Prueba automática. |
| R12 | RF-19 | Cambiar estados fuera de orden o desde otra carpintería. | Se rechaza. | Prueba automática. |
| R13 | RF-27 | Abrir la bandeja con pedidos nuevos y viejos. | Los nuevos primero y marcados como no leídos. | Captura. |
| R14 | RF-28 | Abrir el detalle de un pedido. | Visor 3D, medidas del mueble y del espacio, material, color, despiece y placas. | Captura. |
| R15 | RF-29 | Crear un pedido con el panel abierto. | Aparece sin recargar. | Video. |
| R16 | RF-30 | Ver el resumen de trabajos. | Los montos coinciden con los pagos confirmados. | Comparación. |
| R17 | RNF-08 | Pedir un pedido ajeno conociendo su ID. | Acceso denegado. | Prueba automática. |
| R18 | RNF-08 | Escanear el repositorio. | Ninguna clave en el código. | Resultado del escaneo. |
| R19 | RNF-11 | Simular fallas de Maps, n8n y Mercado Pago. | El cliente sigue diseñando y viendo materiales. | Registro. |

## 8. Prueba de uso

Se sigue el protocolo de DOC-02 §9: cinco clientes y dos carpinteros.

| Indicador | Criterio propuesto |
| --- | --- |
| Finalización | Al menos 4 de 5 clientes llegan de la plantilla a la lista de materiales sin que el facilitador opere por ellos. |
| Tiempo | Al menos 4 de 5 ven su primer mueble en AR en menos de 5 minutos. |
| Medidas | Al menos 4 de 5 cargan bien la profundidad adelante y atrás con la guía. |
| Aporte de la AR | Al menos 3 de 5 cuentan una decisión concreta que tomaron al verlo. |
| Utilidad para la carpintería | Los 2 carpinteros pueden presupuestar sin pedir datos por fuera. |
| Atención real | Al menos una carpintería responde un pedido real desde el panel. |

Registrar ayuda, tiempo y bloqueos. Sin pedidos reales, la demanda queda pendiente: no se simulan encargos para aprobar.

## 9. Clasificación de incidencias

| Severidad | Ejemplo | Efecto |
| --- | --- | --- |
| Bloqueante | Despiece o placas incorrectos, pérdida del proyecto, acceso indebido, pedido duplicado, pedido aceptado sin pago confirmado. | Impide aprobar el nivel. |
| Relevante | AR que no abre en Android, aviso que no llega, panel que no carga. | Corregir y repetir el criterio. |
| Menor | Detalle visual o de texto que no cambia el resultado. | Puede quedar pendiente, identificado. |

Después de corregir, se repite el caso afectado y los que dependen de él.

## 10. Regla de aprobación

- **Núcleo aprobado:** N01 a N17 cumplen en el entorno registrado.
- **Recorrido aprobado:** núcleo aprobado y R01 a R19 cumplen.
- **Alcance modificado:** si algo se recorta (DOC-05 §12), se registra como tal y no se presenta como cumplido.
- **Pendiente:** una prueba no ejecutada no cuenta como aprobada. "No aplica" tampoco cuenta como cumple.

## 11. Paquete de entrega

| Elemento | Contenido mínimo |
| --- | --- |
| Aplicación | URL desplegada y acceso de demostración. |
| Código | Repositorio público, commit identificado y dependencias fijadas. |
| Ejecución | README con instalación, configuración y arranque (Docker). |
| Configuración | `.env` de ejemplo sin claves. |
| API | Documentación en Swagger. |
| Pruebas | Matrices N y R completadas, con entorno, tiempos e incidencias. |
| Tracción | Inscriptos, usuarios, pedidos y señas, con número y link o captura. |
| Video | Utilidad, experiencia de usuario, modelo de negocio, tecnología interesante y tracción; muestra las pruebas. |
| Pendientes | Lista breve: qué falta, impacto y siguiente paso. |

No se incluyen claves, datos de clientes reales ni fotos privadas. Se usan datos de prueba o autorizados.

## 12. Registro de cada prueba

| Campo | Valor |
| --- | --- |
| ID | Nxx o Rxx |
| Versión y commit | |
| Dispositivo y fecha | |
| Pasos | |
| Resultado esperado | Según este documento |
| Resultado observado | |
| Estado | No ejecutado / Cumple / No cumple / Alcance modificado |
| Evidencia | |
| Revisor | |

## 13. Antes de recibir pedidos reales

- Al menos una carpintería confirmada, con zona, WhatsApp y compromiso de responder.
- Comisión aceptada por la carpintería.
- Mercado Pago en modo producción.
- Consentimiento del cliente y aviso de privacidad (Ley 25.326).
- Aclaración visible de que la carpintería verifica las medidas antes de fabricar.

Mientras tanto se prueba con datos de demostración, identificados como tales.

## 14. Próximo paso

Confirmar con el equipo el alcance de la entrega (DOC-05 §12) y escribir las pruebas de los casos A a E antes de programar el módulo `materiales`.

## 15. Historial

| Versión | Fecha | Cambio |
| --- | --- | --- |
| 0.1 | 04/11/2026 | Protocolo inicial, casos manuales, matrices de aceptación y estándar de entrega para el editor modular. |
| 0.2 | 12/11/2026 | Fechas, responsables y localidad completados. |
| 0.3 | 13/11/2026 | Reescrito sobre DOC-02A y DOC-02B: matrices desde los criterios de aceptación, entorno mobile first, casos de estante, mesa, placas, medidas inválidas y espacio insuficiente, tracción y video en el paquete de entrega. Se conservan los casos A y B adaptados, la clasificación de incidencias y el registro de pruebas. |
