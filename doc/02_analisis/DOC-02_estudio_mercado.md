# Estudio de mercado y validación de la propuesta
## Viruta – plataforma web para diseñar, visualizar y encargar muebles a medida

**Código:** DOC-02
**Versión:** 0.4
**Fecha:** 13 de noviembre de 2026 (fuentes consultadas el 4/11/2026)
**Estado:** Investigación exploratoria. Trabajo de campo inicial realizado: encuesta a 31 clientes, encuesta a 4 carpinterías y 2 testimonios. Pruebas de uso pendientes.
**Bases:** DOC-01 V0.4, `02_analisis/encuestas/`, `02_analisis/testimonios/`.

---

## 1. Objetivo

Identificar las alternativas que ya existen, definir en qué se diferencia Viruta y establecer cómo comprobar que clientes y carpinterías necesitan el recorrido propuesto: armar un mueble desde una plantilla, verlo en su espacio con AR, saber qué comprar y encargarlo a una carpintería de la zona.

Este estudio orienta el MVP. Las encuestas muestran que el problema existe; todavía no demuestran demanda suficiente ni disposición a pagar.

## 2. Método y límites

**Investigación documental:** se revisaron páginas públicas de los proveedores, consultadas el 4/11/2026. Las funciones se describen según lo que publica cada empresa; no se probaron ni se verificaron de forma independiente.

**Trabajo de campo:**
- Encuesta a 31 potenciales clientes.
- Encuesta a 4 carpinterías.
- 2 testimonios de carpinteros.

Se distinguen tres tipos de contenido:

- **Observación:** algo que dice una fuente o que respondieron las personas encuestadas.
- **Inferencia:** interpretación del equipo para tomar decisiones.
- **Hipótesis:** afirmación que todavía hay que comprobar.

Las muestras son chicas y no representativas: sirven para orientar, no para estimar el mercado. La comparación de alternativas es selectiva, no exhaustiva.

## 3. Mercado inicial

**Segmento principal:** vecinos de Jujuy que quieren un mueble a medida simple (estantes, mesas, bajo mesadas) en madera, melamina o aglomerado.

**Oferta:** carpinterías independientes de la zona que trabajan muebles de placas. Las que respondieron la encuesta son las primeras candidatas para sumarse.

**Geografía:** San Salvador de Jujuy y alrededores. Es requisito del hackatón y es donde el equipo tiene las respuestas.

| Segmento | Necesidad | Prioridad |
| --- | --- | --- |
| Personas que necesitan un mueble simple a medida | Que entre en el espacio, saber qué comprar y encontrar quién lo haga. | Principal. |
| Carpinterías independientes de muebles de placas | Recibir pedidos con medidas y material definidos. | Socio indispensable: es quien paga. |
| Personas que fabrican por su cuenta | Saber qué piezas cortar y qué comprar. | Secundario: lo cubre la lista de materiales. |
| Otros oficios y muebles complejos | Otros profesionales y otras reglas. | Fuera de esta etapa. |

## 4. Alternativas identificadas

| Alternativa | Funciones publicadas y fuente | Relación con Viruta |
| --- | --- | --- |
| Armandolo | Configuración de muebles de melamina, representación 3D, piezas, herrajes y corte por plancha; incluye escritorios. [F1–F2] | Competencia directa en configuración y despiece. Viruta se diferencia por la AR y la conexión con carpinterías locales. |
| Tylko | Configurador para modificar dimensiones, colores y otras opciones en tiempo real. [F3] | Referente de experiencia de personalización. |
| Pickawood | Configuradores de muebles a medida, incluidas mesas y escritorios. [F4] | Referente de configuración ligada a un fabricante. |
| IKEA Kreativ | Visualización de productos IKEA en el espacio del usuario. [F5] | Referente de visualización, atado a su catálogo. |
| Servidos | Publicación de trabajos, ofertas, chat, perfiles y reseñas; incluye carpintería en Argentina. [F6–F7] | Competencia en la conexión entre clientes y profesionales. No se comprobó actividad en Jujuy. |
| Habitissimo | Solicitudes de presupuesto, contacto con profesionales y opiniones. [F8] | Referente de intermediación. La fuente es de España (2019). |
| WhatsApp, recomendaciones y redes | Es como se contrata hoy: el 100% de las carpinterías quiere recibir los pedidos por WhatsApp. | La alternativa real. Viruta tiene que mejorar ese proceso, no reemplazarlo: por eso el aviso llega por WhatsApp. |

Que una función no aparezca en las páginas consultadas no prueba que el proveedor no la tenga.

## 5. Resultados del trabajo de campo

El detalle está en DOC-02A §2. Lo principal:

**Clientes (n = 31):**
- 71% compra muebles estándar; solo 13% contrata a un carpintero.
- **58%** se frustra porque calcula mal las medidas y el mueble no entra.
- 48% no logra imaginar color y estilo; 32% no sabe cuánto material comprar.
- La realidad aumentada tiene una utilidad promedio de **4,58 sobre 5**.
- Funciones que más usarían: diseño 3D (81%), cálculo de materiales (58%), conexión con carpinteros (45%).
- **81%** usa Android.
- Disposición a pagar: 48% pago único, 39% solo gratis, 19% suscripción.
- Cotizar materiales con proveedores locales: importancia **8,74 sobre 10**.
- Encontrar planos o guías: **2,55 sobre 5** (90% dice que le cuesta).

**Carpinterías (n = 4 + 2 testimonios):**
- **100%** quiere el aviso por WhatsApp; 0% por correo.
- **100%** necesita medidas y tipo de madera para cotizar.
- Testimonio 1: los clientes miden mal y ella siempre vuelve a medir; cobra 50% de seña; muchos clientes compran el material y pagan solo la mano de obra; propone un catálogo de fotos por carpintero y una guía de cómo medir.
- Testimonio 2: quiere cargar las piezas y el tamaño de placa y que la aplicación diga cuántas placas usar.

## 6. Hallazgos y consecuencias para el MVP

**Observación:** ya existen herramientas de configuración y despiece, y otras que conectan clientes con profesionales.

**Inferencia:** presentar Viruta solo como un configurador o solo como una plataforma de oficios no alcanza para diferenciarse. La oportunidad es unir las dos cosas para una zona concreta: que el cliente diseñe algo que entre, lo vea en su casa y la carpintería reciba exactamente eso.

**Consecuencias en el MVP (DOC-02A):**

| Dato | Decisión |
|---|---|
| 58% mide mal; los carpinteros vuelven a medir | Medidas del espacio con aviso (RF-02), guía de cómo medir (RF-06) y estado *Medidas verificadas* (RF-19). |
| AR 4,58/5; 81% usaría diseño 3D | Plantillas en 3D (RF-01) y realidad aumentada (RF-04). |
| 32% no sabe qué comprar; testimonio 2 | Despiece, placas, herrajes y barniz (RF-07 a RF-09). |
| 100% de carpinterías pide medidas y madera por WhatsApp | Pedido con todos los datos (RF-15) y aviso por WhatsApp (RF-16). |
| 81% Android | Mobile first, Android primero (RNF-05). |
| 19% pagaría suscripción; seña del 50% ya es práctica | Comisión a la carpintería descontada de la seña (RF-18). |

## 7. Posicionamiento

**"Diseñá tu mueble, probalo en tu espacio, sabé qué comprar y encargalo a una carpintería de tu zona."**

El cliente decide el diseño; la carpintería verifica las medidas y define el presupuesto. Las cantidades de materiales son estimadas y la AR no reemplaza una medición.

No se propone competir en amplitud de catálogo ni en optimización industrial de cortes, ni abrir una red nacional de profesionales en esta etapa.

## 8. Hipótesis críticas

| Código | Hipótesis | Evidencia hasta ahora | Evidencia que falta |
| --- | --- | --- | --- |
| H1 | El cliente tiene dificultades para medir y comunicar su pedido. | 58% mide mal; testimonio 1. | — |
| H2 | Con la guía y los avisos, el cliente carga medidas útiles. | — | Prueba de uso observada. |
| H3 | Ver el mueble en AR ayuda a decidir. | AR 4,58/5 en encuesta. | Uso real: qué decide el cliente al verlo. |
| H4 | El pedido de Viruta le alcanza a la carpintería para presupuestar. | 100% pide medidas y madera. | Revisión de un pedido real con carpinterías. |
| H5 | Hay clientes que piden presupuesto de verdad. | — | Pedidos reales registrados. |
| H6 | Las carpinterías responden los pedidos. | — | Presupuestos respondidos en el panel. |
| H7 | La carpintería acepta pagar la comisión. | Solo 19% de clientes pagaría suscripción; la seña ya es práctica. | Preguntarlo a las carpinterías y cobrar la primera seña. |
| H8 | Una persona sin experiencia arma su mueble y lo ve en AR en menos de 5 minutos. | — | Prueba de uso (RNF-02). |

## 9. Prueba de uso

Una primera ronda con **5 clientes** y **2 carpinteros**. Pueden participar personas que respondieron la encuesta, dejando constancia de que ya conocen la idea.

**Tarea del cliente:** con un espacio real de su casa, elegir una plantilla, medir con la guía, cargar las medidas del espacio, ajustar el mueble hasta que entre, verlo en AR y revisar la lista de materiales. Si tiene una necesidad real, ofrecerle pedir presupuesto; no pedir encargos ficticios. Registrar tiempo, ayuda que necesitó y errores.

**Tarea del carpintero:** comparar un pedido como los que recibe hoy por WhatsApp (texto y foto) con el pedido de Viruta para el mismo mueble. Alternar el orden entre participantes. Registrar qué información falta, qué tendría que preguntar y si puede presupuestar. Preguntar si aceptaría la comisión.

Los casos de demostración se identifican como tales. Pedidos, presupuestos, señas y trabajos terminados se registran como eventos distintos.

## 10. Métricas y reglas de decisión

**Prueba de uso:**

| Indicador | Cómo medirlo | Umbral propuesto |
| --- | --- | --- |
| Finalización | Clientes que llegan de la plantilla a la lista de materiales sin que el facilitador opere por ellos. | Al menos 4 de 5. |
| Tiempo | Minutos hasta ver el primer mueble en AR. | Al menos 4 de 5 en menos de 5 minutos (RNF-02). |
| Medidas | Clientes que cargan bien la profundidad adelante y atrás con la guía. | Al menos 4 de 5. |
| Aporte de la AR | Decisión concreta que cambia o se confirma al ver el mueble en el espacio. | Al menos 3 de 5. |
| Utilidad para la carpintería | Puede presupuestar con el pedido de Viruta sin pedir datos por fuera. | Los 2 carpinteros. |
| Oferta disponible | Una carpintería responde un pedido real desde el panel. | Al menos 1. |

**Tracción (lo que más pesa en el hackatón):**

| Indicador | Fuente |
| --- | --- |
| Inscriptos en la lista de espera (clientes y carpinterías) | Contador real (RF-20). |
| Usuarios y diseños creados | Panel interno (RF-21). |
| Pedidos y presupuestos | Panel interno (RF-21). |
| Señas cobradas | Mercado Pago (RF-18, RF-30). |

Cada número se presenta con link o captura. Los umbrales son propuestos por el equipo, no estándares del sector.

Si la prueba de uso sale bien pero no hay pedidos reales, la demanda queda sin comprobar. Si la carpintería tiene que pedir todo de nuevo, se revisa el contenido del pedido antes de sumar funciones.

## 11. Dimensión de mercado

No hay datos suficientes para calcular el tamaño del mercado de forma defendible. Para el arranque se usa la capacidad real:

**Capacidad mensual = carpinterías activas × pedidos que cada una acepta revisar por mes.**

El volumen posible es el menor entre los pedidos que genera la aplicación y la capacidad de las carpinterías. Cualquier proyección se presenta como escenario, no como venta confirmada.

## 12. Modelo de negocio

Alternativas evaluadas:

| Alternativa | Por qué no se eligió |
| --- | --- |
| Suscripción para carpinterías | Requiere un uso frecuente que todavía no está demostrado. |
| Cobro por pedido recibido | Obliga a definir qué es un pedido válido y cómo tratar los que no se responden. |
| Cobro al cliente por diseño o plano | Solo 19% pagaría suscripción y 39% solo usaría la versión gratis. |
| **Comisión por trabajo concretado** | **Elegida.** |

**Decisión del equipo (12/11/2026):** comisión del **8% al 12%** sobre el trabajo concretado, a cargo de la carpintería, descontada de la seña que el cliente paga por Mercado Pago.

- **Por qué paga la carpintería:** recibe un cliente que ya trae diseño, medidas y material definidos.
- **Cómo se confirma el cierre:** el trabajo se considera concretado cuando el cliente paga la seña dentro de la aplicación.

Pendiente: confirmar con las carpinterías que aceptan la comisión y definir su base cuando el cliente compra el material por su cuenta (testimonio 1).

## 13. Captación inicial

- **Carpinterías:** empezar por las que respondieron la encuesta y los testimonios.
- **Clientes:** lista de espera con contador visible, contactos del equipo, comunidades locales y clientes de las carpinterías participantes.
- No invertir en publicidad hasta tener carpinterías que respondan pedidos.

Para el hackatón, la tracción se mide con números reales: inscriptos, usuarios, pedidos y señas, siempre con link o captura.

## 14. Riesgos y respuestas

| Riesgo | Respuesta |
| --- | --- |
| Las alternativas existentes ya resuelven el problema. | Mostrar la diferencia concreta: el pedido llega con medidas, material y despiece, y la AR evita que el mueble no entre. |
| La carpintería cierra el trabajo por fuera para no pagar la comisión. | Cobrar la seña dentro de la aplicación; es lo que ata la comisión al cierre. |
| Las carpinterías no aceptan la comisión. | Preguntarlo antes del pitch y ajustar el porcentaje dentro del rango. |
| La AR genera expectativa de precisión. | Avisar que no es una medición y que la carpintería verifica las medidas en el lugar. |
| El cliente sigue midiendo mal. | Guía de cómo medir, avisos de inconsistencia y verificación de la carpintería. |
| Llegan pedidos sin carpinterías que respondan. | Empezar en una zona chica y limitar el volumen a la capacidad acordada. |
| Se confunde interés con demanda. | Separar inscriptos, diseños, pedidos y señas. |
| Se comparten datos personales sin claridad. | Pedir datos recién al pedir presupuesto, con consentimiento (RNF-09). |

## 15. Conclusión provisional

Las encuestas confirman el problema: los clientes miden mal y no saben qué comprar, y las carpinterías necesitan medidas y material para cotizar. Las alternativas documentadas resuelven partes por separado.

La diferenciación de Viruta es unir diseño, AR, cálculo de materiales y conexión con carpinterías locales en un solo recorrido. Lo que falta comprobar es que haya pedidos reales, que las carpinterías los respondan y que acepten la comisión.

## 16. Registro del trabajo de campo

| Registro | Estado |
| --- | --- |
| Encuesta a clientes | 31 respuestas (`encuestas/encuesta_clientes.csv`). |
| Encuesta a carpinterías | 4 respuestas (`encuestas/encuesta_carpinterias.csv`). |
| Testimonios | 2 (`testimonios/`). |
| Prueba de uso | Pendiente. |
| Pedidos y presupuestos reales | Pendientes. |
| Zona | Jujuy. |
| Carpinterías participantes | Candidatas: las que respondieron la encuesta. A confirmar. |

En el repositorio no se publican datos de contacto. Cada prueba registra tarea, ayuda recibida, resultado y obstáculos.

## 17. Fuentes

Consultadas el 04/11/2026. Las descripciones pertenecen a cada proveedor y pueden cambiar.

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
| 0.1 | 04/11/2026 | Investigación documental inicial, comparación de alternativas y protocolo de validación. |
| 0.2 | 04/11/2026 | Adecuación al editor modular. |
| 0.3 | 12/11/2026 | Registro del trabajo de campo, zona Jujuy y modelo de comisión. |
| 0.4 | 13/11/2026 | Alineado con DOC-01 V0.4 y DOC-02A: se quita el editor modular (hipótesis H8 a H10 anteriores y tareas de creación desde vacío), se suman los resultados de las encuestas, la prueba de uso pasa a plantillas y AR, se agregan métricas de tracción y riesgos del modelo de comisión. Se conservan alternativas y fuentes. |
