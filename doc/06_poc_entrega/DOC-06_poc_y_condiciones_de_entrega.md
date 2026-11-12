# POC, fecha y condiciones de entrega
## Plataforma web para crear y cotizar muebles a medida

**Código:** DOC-06  
**Versión:** 0.2  
**Fecha del documento:** 4 de noviembre de 2026  
**Estado:** Protocolo propuesto. Pruebas no ejecutadas.  
**Bases:** DOC-01 y DOC-02 V0.2; DOC-04A, DOC-04B y DOC-05 V0.1.

## 1. Objetivo de la prueba de concepto

Comprobar que una persona puede crear muebles sencillos con una paleta común y que las piezas, medidas y relaciones producen un modelo 3D, un plano y un cómputo consistentes. Comprobar después que ese proyecto puede visualizarse en una foto, documentarse y registrarse como consulta revisable por una carpintería.

La POC se divide en núcleo y recorrido completo, siguiendo DOC-05. La aprobación técnica no acredita demanda, rentabilidad ni validez constructiva del mueble.

Este documento es un estándar interno propuesto para este proyecto, no una norma técnica del sector ni una certificación externa.

## 2. Fecha y responsables

| Dato | Estado |
| --- | --- |
| Fecha límite del hackathon | Entrega del proyecto: 13/11/2026. Hackatón: 22/11/2026. |
| Inicio de implementación | Pendiente de acordar. |
| Revisión del núcleo H0–H2 | Se calendariza al confirmar inicio y dedicación. |
| Revisión del recorrido H3–H5 | Se calendariza después de estimar el núcleo. |
| Presentación del MVP H6 | Pendiente del plazo y disponibilidad del piloto. |
| Responsable de desarrollo | Maximo Acosta Gloss (programación). |
| Responsable de aceptación técnica | José Manuel Fernández (análisis y diseño). Pendiente de confirmar. |
| Carpintero revisor y localidad | Jujuy. Carpintero pendiente; candidatos: talleres que respondieron la encuesta. |
| Operador de solicitudes | Pendiente de asignación. |

Las fechas y horas se expresarán en horario de Argentina. Ningún plazo está comprometido en esta versión. Las personas podrán asumir varios roles en un equipo pequeño, dejando registrada la revisión que realizaron.

## 3. Alcance de aceptación

### POC del núcleo

- Paleta mínima de tablero, lateral y estante.
- Creación desde vacío de dos tipologías con las mismas operaciones.
- Agregar, seleccionar, dimensionar, ubicar por referencias, duplicar y eliminar.
- Deshacer y rehacer cambios confirmados.
- Reglas simples, geometría resuelta, dimensiones generales y piezas.
- Modelo 3D y comparación de resultados con casos manuales.
- Avisos de datos inválidos y diseño incompleto.

### POC del recorrido

- Recuperación local y archivo JSON editable auxiliar.
- Frente, planta, lateral y PDF de referencia.
- Fotografía y colocación visual del mismo mueble.
- Solicitud persistente con revisión fija, contacto y autorización.
- Reintento sin duplicado y recuperación por operador autorizado.

### Fuera de la prueba inicial

CAD de formas arbitrarias, cálculos de estabilidad, optimización de placas, precios finales automáticos, pagos, reseñas, red abierta de profesionales y dependencias obligatorias de IA. Puertas, cajones y patas no son necesarios para aprobar la paleta mínima.

## 4. Entorno y límites propuestos

Los siguientes valores son objetivos internos iniciales para que la prueba sea reproducible. Deben confirmarse en H0 y registrarse antes de ejecutar la aceptación. Un cambio debe quedar documentado, sin ajustar los umbrales después para ocultar un resultado fallido.

| Parámetro | Propuesta inicial |
| --- | --- |
| Entorno principal | Computadora con navegador Chromium estable; registrar sistema, CPU, RAM, navegador y resolución reales. |
| Pantalla principal | 1366 × 768 o superior. |
| Prueba móvil | Un dispositivo real, ancho lógico próximo a 390 px; registrar modelo y navegador. |
| Edición móvil | Probar al menos selección y cambio numérico de dimensiones; no se exige arrastre preciso. Si no es usable, declarar soporte móvil parcial y mantener el pendiente. |
| Piezas por proyecto de prueba | Hasta 30 piezas rectangulares. |
| Historial | Al menos 20 operaciones confirmadas. |
| Dimensiones de casos | Valores enteros en mm; espesor geométrico de referencia de 18 mm. |
| Imagen de entrada | JPEG o PNG válido, hasta 5 MB; otros formatos se rechazan con explicación. |
| Foto procesada | Lado mayor hasta 2048 px, conservando proporción. |
| Archivo editable | JSON hasta 1 MB, sin foto ni datos personales. |
| PDF de prueba | Hasta 10 MB; una y varias páginas. |
| Recálculo confirmado | Objetivo de hasta 500 ms para 30 piezas en la computadora registrada. |
| Exportación PDF | Objetivo de hasta 10 s para el caso de prueba en el entorno registrado. |

Medir recálculo y PDF en cinco repeticiones después de una ejecución de calentamiento; registrar los valores y exigir que cada repetición cumpla el objetivo. Los límites anteriores no implican capacidades garantizadas de proveedores ni tolerancias de carpintería. Se revisarán antes de congelar la implementación de cargas y almacenamiento.

No se fija tiempo máximo de envío remoto porque depende de conexión y tamaño. Debe mostrarse progreso o estado, evitar confirmaciones falsas y permitir recuperación ante error. Registrar conexión y duración observada.

## 5. Casos geométricos de referencia

Estos casos comprueban geometría nominal y conteo. No son instrucciones de fabricación ni afirman que las uniones o la estabilidad estén resueltas. Material: tablero nominal de 18 mm, con herrajes y descuentos pendientes de revisión profesional.

### Caso A — Mueble abierto con estante

Envolvente de **800 mm de ancho × 900 mm de alto × 300 mm de profundidad**. Dos laterales exteriores de altura completa; tapa, base y estante ubicados entre caras interiores. Sin fondo, patas, puertas ni cajones.

| Pieza | Cantidad | Medidas nominales por pieza |
| --- | --- | --- |
| Lateral | 2 | 900 × 300 × 18 mm |
| Tapa entre laterales | 1 | 764 × 300 × 18 mm |
| Base entre laterales | 1 | 764 × 300 × 18 mm |
| Estante interior | 1 | 764 × 300 × 18 mm |
| Total | 5 | Área nominal de tablero: 1,2276 m². |

El ancho interior resulta de 800 − 2 × 18 = 764 mm. El estante se ubica con su cara inferior a Z = 441 mm; su cara superior queda a 459 mm. Las caras interiores de base y tapa quedan a Z = 18 y Z = 882 mm. Los dos huecos libres verticales resultan de 423 mm cada uno.

**Modificación esperada:** al aumentar el ancho exterior a 1000 mm conservando espesores y relaciones, las tres piezas interiores pasan a 964 × 300 × 18 mm. Los dos laterales no cambian; continúan cinco piezas. Área nominal: 1,4076 m².

### Caso B — Escritorio sencillo de tableros

Envolvente de **1200 mm de ancho × 750 mm de alto × 600 mm de profundidad**. Una cubierta apoyada sobre dos laterales de altura 732 mm, ubicados en los extremos. Sin cajones, fondo ni refuerzo modelado. La estabilidad y las uniones permanecen pendientes.

| Pieza | Cantidad | Medidas nominales por pieza |
| --- | --- | --- |
| Cubierta | 1 | 1200 × 600 × 18 mm |
| Lateral | 2 | 732 × 600 × 18 mm |
| Total | 3 | Área nominal de tablero: 1,5984 m². |

El ancho libre entre laterales es 1164 mm. La cubierta ocupa Z = 732 a 750 mm.

**Modificación esperada:** al aumentar la altura total a 800 mm manteniendo la cubierta de 18 mm y la relación de apoyo, los laterales pasan a 782 × 600 × 18 mm. La cubierta no cambia. Área nominal: 1,6584 m².

Las áreas son la suma del largo por ancho de las piezas, no el área de todas sus caras. No equivalen a cantidad de placas comerciales, desperdicio ni superficie de terminación.

### Caso C — Datos inválidos y diseño incompleto

Probar una dimensión cero, una referencia inexistente, un ciclo de dependencias y una pieza aislada sin relación definida. Los errores de datos deben rechazarse sin corromper el último proyecto válido. La pieza aislada puede conservarse como diseño incompleto, con aviso visible en la ficha y solicitud.

## 6. Matriz de aceptación del núcleo

Todos los criterios comienzan con resultado **No ejecutado**. El resultado deberá registrarse al realizar la prueba.

| ID | Acción | Resultado esperado | Evidencia |
| --- | --- | --- | --- |
| N01 | Crear A y B desde vacío. | Misma paleta y operaciones; no editar código ni usar controles exclusivos de escritorio. | Grabación breve o ejecución observada y archivos. |
| N02 | Comparar piezas y envolventes. | Cantidades enteras exactas y dimensiones esperadas; diferencia geométrica numérica máxima de 0,01 mm por redondeo computacional. | Tabla esperado/obtenido. |
| N03 | Aplicar modificaciones de A y B. | Cambian las piezas dependientes y las áreas indicadas; las restantes se conservan. | Comparación antes/después. |
| N04 | Duplicar una pieza y eliminarla. | ID nuevo y una pieza adicional; al eliminar vuelve el conteo anterior. | Registro de IDs y cantidades. |
| N05 | Eliminar un lateral con dependientes. | Explicar relaciones afectadas y permitir cancelar o continuar con pendientes explícitos. | Captura del aviso y resultado. |
| N06 | Deshacer y rehacer. | Restaurar geometría, relaciones y conteos; no se exige restaurar la misma marca temporal. | Comparación de datos relevantes. |
| N07 | Ejecutar C. | Rechazo de errores y aviso persistente de incompleto, según su tipo. | Resultado de cada entrada. |
| N08 | Girar cámara y hacer zoom. | Ninguna dimensión ni cantidad cambia. | Comparación del dominio antes/después. |
| N09 | Resolver el mismo archivo en navegador y servidor. | Coinciden geometría, piezas y avisos con las mismas reglas. | Resultados comparados. |
| N10 | Medir recálculo en 30 piezas. | Cumplir objetivo y procedimiento del apartado 4. | Registro de tiempos y entorno. |

La tolerancia numérica de N02 es solo para comparar representaciones computacionales; no autoriza precisión constructiva de centésimas de milímetro. Las dimensiones presentadas seguirán la resolución de 1 mm.

## 7. Matriz de aceptación del recorrido

| ID | Acción | Resultado esperado | Evidencia |
| --- | --- | --- | --- |
| R01 | Guardar, cerrar y reabrir. | Recuperar último borrador confirmado y foto en el mismo navegador. | Comparación del proyecto. |
| R02 | Exportar e importar JSON. | Recuperar piezas y relaciones sin foto ni contacto; informar esa limitación. | Archivos y resultado. |
| R03 | Importar archivo incompatible. | Explicar rechazo y conservar el proyecto válido. | Caso de entrada y mensaje. |
| R04 | Generar las tres vistas de A y B. | Frente, planta y lateral coinciden con geometría y cotas generales. | Plano y comparación manual. |
| R05 | Exportar PDF y luego modificar el proyecto. | PDF conserva su revisión; nueva exportación refleja el cambio. | Ambos archivos identificados. |
| R06 | Exportar tabla de varias páginas. | Sin filas perdidas, texto cortado o cotas superpuestas; unidades y avisos legibles. | Inspección visual del PDF. |
| R07 | Subir foto admitida y ajustar composición. | Mueble visible y comparación antes/después; medidas y cómputo invariantes. | Imágenes y comparación de datos. |
| R08 | Subir imagen inválida o excedida. | Rechazo claro sin pérdida del mueble. | Entradas de prueba. |
| R09 | Enviar pedido de prueba. | Captura y archivos obligatorios conservados; ID solo tras finalizar. | Registro recuperado por operador. |
| R10 | Reintentar por respuesta perdida. | Misma clave y contenido recuperan un único ID; contenido diferente con igual clave se rechaza. | Consulta de registros y respuestas. |
| R11 | Interrumpir una carga obligatoria. | No presentar pedido completo; permitir recuperar o cancelar el intento. | Estado del intento y pantalla. |
| R12 | Editar después del envío. | Captura enviada permanece fija e independiente del borrador. | Comparación de revisiones. |
| R13 | Intentar lectura sin autorización. | Tablas, documentos y fotos privados no resultan accesibles por conocer sus IDs. | Prueba negativa registrada. |
| R14 | Revisar y responder por el procedimiento piloto. | Operador accede a la ficha correcta y registra estado; registrada no se confunde con presupuestada. | Registro del procedimiento. |
| R15 | Probar computadora y móvil declarados. | Recorrido y edición móvil mínima del apartado 4; errores y soporte parcial documentados. | Registro de dispositivos y obstáculos. |
| R16 | Medir PDF y revisar límites. | Cumplir apartado 4; no ofrecer archivos incompletos como válidos. | Tiempos, tamaños y PDF. |

Para R06 usar un proyecto válido con suficientes piezas identificadas individualmente dentro del límite de 30. La prueba no debe depender de cantidades ficticias o filas duplicadas sin relación con el diseño.

## 8. Validación de uso y piloto

La ronda propuesta conserva el protocolo de DOC-02: cinco clientes y dos carpinteros. Se documentará cualquier cambio de muestra antes de ejecutar y se evitará extrapolar porcentajes a todo el mercado.

| Indicador | Criterio exploratorio propuesto |
| --- | --- |
| Creación y descarga | Al menos cuatro de cinco clientes completan sin que el facilitador opere por ellos. |
| Edición modular | Al menos cuatro agregan, dimensionan y reubican un elemento y duplican o eliminan otro. |
| Comprensión | Al menos cuatro explican correctamente dimensiones y carácter preliminar de la ficha. |
| Aporte del ambiente | Al menos tres describen una decisión concreta apoyada por la visualización. |
| Utilidad para cotizar | Ambos carpinteros pueden iniciar una estimación y explican aclaraciones abordables. |
| Atención efectiva | Al menos un profesional acepta y atiende una solicitud real bajo plazo acordado. |

Registrar ayuda verbal, tiempo y bloqueos; no ocultarlos al contar finalizaciones. Comparar creación desde vacío y desde plantilla opcional cuando esté disponible, sin exigir que una modalidad gane.

Sin necesidad genuina de compra, la atención comercial se marca como pendiente; no se simulan encargos reales para aprobar. Una prueba técnica puede aprobarse aunque la validación de uso o comercial falle, pero ese resultado deberá declararse por separado.

## 9. Clasificación de incidencias

| Severidad | Ejemplo | Efecto en aceptación |
| --- | --- | --- |
| Bloqueante | Pérdida de proyecto, cantidades contradictorias, acceso indebido, envío falso o imposible. | Impide aprobar el nivel afectado. |
| Relevante | Operación esencial falla, plano ilegible o implantación no utilizable. | Corregir y repetir el criterio; no aprobar como cumplido. |
| Menor | Alineación visual o texto mejorable sin afectar resultado ni comprensión. | Puede quedar pendiente con identificación y motivo. |

No se exigen cero detalles visuales pendientes. Sí se exige ausencia de fallos que invaliden los criterios esenciales. Tras una corrección, repetir el caso afectado y las dependencias pertinentes; no rehacer comprobaciones sin relación con el cambio.

## 10. Regla de aprobación

- **Núcleo aprobado:** N01–N10 cumplen bajo el entorno y límites registrados.
- **Recorrido aprobado:** núcleo aprobado y R01–R16 cumplen. Una reducción de soporte debe registrarse como alcance modificado y dejar de presentarse como cumplimiento del alcance original.
- **MVP piloto aceptado:** recorrido aprobado, atención disponible, protocolo de uso ejecutado y resultados evaluados. Si no se alcanzan sus umbrales, registrar MVP en validación y los cambios necesarios.
- **Pendiente:** una prueba no ejecutada no se considera aprobada.

Los umbrales propuestos se congelarán en la versión de DOC-06 utilizada para aceptación. Un cambio posterior requiere motivo y nueva versión; no puede convertir retrospectivamente un fallo en éxito sin declarar la modificación.

## 11. Paquete estándar de entrega

| Elemento | Contenido mínimo |
| --- | --- |
| Aplicación | Versión ejecutable y acceso o instrucciones locales comprobadas. |
| Código | Repositorio, commit y dependencias fijadas. |
| Ejecución | README con instalación, configuración, arranque, compilación y comprobaciones necesarias. |
| Configuración | Archivo de ejemplo de variables sin secretos; instrucciones de servicio y almacenamiento. |
| Casos | JSON de A y B, modificaciones y entradas inválidas identificadas. |
| Documentación generada | PDF e imágenes de ejemplo, con revisión y avisos. |
| Resultados | Matrices N y R completadas, entorno, tiempos e incidencias. |
| Piloto | Procedimiento de atención y resultados de uso, anonimizados. |
| Pendientes | Lista breve con impacto, siguiente acción y responsable cuando exista. |

No incluir credenciales, datos de clientes reales ni fotografías privadas en el repositorio o paquete de demostración. Usar datos sintéticos o expresamente autorizados.

## 12. Registro de ejecución y aceptación

Cada criterio se registrará con esta estructura:

| Campo | Valor a completar |
| --- | --- |
| ID de criterio | Nxx o Rxx. |
| Versión y commit | Pendiente. |
| Entorno y fecha | Pendiente. |
| Entrada y pasos | Archivo y acciones realizadas. |
| Resultado esperado | Según este protocolo. |
| Resultado observado | Pendiente de ejecución. |
| Estado | No ejecutado / Cumple / No cumple / No aplica justificado. |
| Evidencia | Archivo, captura, registro o ejecución observada. |
| Revisor e incidencia | Pendiente. |

No aplica no cuenta como cumple. Si afecta un criterio esencial, debe revisarse el alcance y la regla de aceptación antes de declarar aprobado el nivel.

El acta de cierre identificará el nivel aprobado, la fecha, la versión probada y los pendientes. En esta emisión no se ha ejecutado ni aprobado ninguna prueba.

## 13. Condiciones previas al uso real

Antes de recibir pedidos reales deben estar confirmados destinatario, zona, responsable, canal y plazo de respuesta; acceso privado a archivos; autorización del cliente y procedimiento de conservación y eliminación. La revisión profesional sigue siendo necesaria antes de fabricar.

La POC puede avanzar con casos sintéticos mientras se coordinan estas condiciones. No se presentará una demostración con datos de prueba como servicio operativo de carpinterías asociadas.

## 14. Próximo paso

Completar fechas, responsables y entorno de aceptación; confirmar los casos y límites propuestos. Después comenzar H0 de DOC-05: base del proyecto, catálogo mínimo y casos de referencia. Este documento no inicia por sí mismo la implementación ni reserva servicios.

## 15. Historial

| Versión | Fecha | Cambio |
| --- | --- | --- |
| 0.1 | 04/11/2026 | Protocolo inicial, casos manuales, matrices de aceptación y estándar de entrega. Fechas y ejecución pendientes. |
| 0.2 | 12/11/2026 | Fechas, responsables y localidad completados con lo definido por el equipo. Alcance de pagos y placas pendiente de alinear (ver `coherencia_y_decisiones.md`). |
