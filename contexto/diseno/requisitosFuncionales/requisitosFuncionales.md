# Viruta (AcerrinLab) – Requisitos funcionales (v3)

**Etapa:** Análisis, paso 3 – requisitos funcionales (los no funcionales están en `../requisitosNoFuncionales/requisitosNoFuncionales.md`)
**Estado:** Borrador para aprobación (José Manuel Fernández / Maximo Acosta Gloss)
**Fecha:** 12/11/2026
**Cambios v3:** se agrega el **panel de la carpintería** como parte del MVP (WhatsApp queda solo como aviso que lleva al panel).
**Cambios respecto de la v1:** reestructurado según el compendio de los workshops (enfoque vertical, MVP de 3 funcionalidades, máquina de estados, fuera de alcance explícito, honestidad de datos). Stack confirmado: **frontend React** + backend **Spring Boot**.

**Fuentes:** encuesta a clientes (31 respuestas), encuesta a carpinterías (4 respuestas), 2 testimonios de carpinteros, `contexto/*.md` del repo y `viruta-hackaton-2026-contexto-completo.md` (workshops).

---

## 0. Cómo leer este documento

Siguiendo el workshop, el MVP se limita a **3 funcionalidades clave** de un producto **vertical**. Todo requisito pertenece a una de ellas o queda explícitamente **fuera de alcance**. Cada requisito funcional tiene **criterios de aceptación**, que se convierten directamente en las pruebas de la etapa de Programación.

| Etiqueta | Significado |
|---|---|
| **MVP** | Se construye para la entrega del 13/11 (regla de la PoC: flujo básico funcional en pocos días). |
| **Post-MVP** | Validado por los datos, pero se hace después de la entrega. |
| **Fuera** | No se construye en esta versión. |

---

## 1. Problema y nicho (enfoque vertical)

**Problema:** las personas no pueden pasar de "tengo una idea de mueble" a "tengo un mueble que entra y un carpintero que lo cotiza" sin errores de medida ni idas y vueltas.

**Evidencia (números para el pitch):**
- **58%** de los clientes dice que su mayor frustración es calcular mal las dimensiones y que el mueble no entre.
- Los carpinteros lo confirman: *"siempre me dirijo a tomar las medidas del cliente, porque a veces no saben interpretar las medidas"* (testimonio 1).
- **100%** de las carpinterías necesita **medidas** y **tipo de madera** para cotizar, y quiere el aviso por **WhatsApp** (0% email).
- **87%** califica la realidad aumentada con 4 o 5 sobre 5; **81%** usaría el diseño 3D.
- **90%** dice que hoy le cuesta encontrar planos o guías (3 o menos sobre 5, promedio 2,55).

**Nicho:** vecinos de Jujuy que quieren un **mueble a medida simple** (estantes, mesas, bajo mesadas, placares) en **madera, melamina o aglomerado**, y **carpinterías independientes** de la zona que hoy reciben pedidos sin medidas confiables.

**Quién paga y por qué:** la **carpintería** paga una **comisión de 8% a 12%** sobre el trabajo concretado, descontada de la **seña** que el cliente paga por Mercado Pago. Lo confirman los datos: solo el 19% de los clientes pagaría una suscripción, y la seña del 50% ya es como trabajan hoy los carpinteros (testimonio 1).

---

## 2. Resultados consolidados de las encuestas

### 2.1 Clientes (n = 31)

| Pregunta | Resultado |
|---|---|
| Cómo amueblan hoy | 71% compra estándar · 35% fabrica por su cuenta · 35% busca ideas sin planificar · 13% contrata carpintero |
| Mayor frustración | **58% medidas/no entra** · 48% no visualiza color y estilo · 32% no sabe cuánto material comprar · 23% no tiene herramientas sencillas |
| Utilidad de AR (1 a 5) | Promedio **4,58** · 87% da 4 o 5 |
| Funciones que más usaría | **81% diseño 3D** · 58% cálculo de materiales · 45% conexión con carpinteros · 32% exportar planos |
| Dispositivo | **81% Android** · 35% iPhone · 26% tablet Android · 10% iPad |
| Expectativas | **65% precisión** en medidas y despiece · 55% interfaz intuitiva · 55% AR fluida · 35% uso sin conexión |
| Disposición a pagar | 48% pago único · 39% solo gratis · 26% gratis con anuncios · 19% suscripción |
| Cotizar materiales con proveedores locales (1 a 10) | Promedio **8,74** · 84% da 8 o más |
| Facilidad para encontrar planos (1 = muy difícil, 5 = muy fácil) | Promedio **2,55** · 90% da 3 o menos |

Comentarios libres: recomendación de madera según uso, con pros, contras y precio (3); diseñar a partir de una foto o imagen de Pinterest (2); asistente por preguntas que advierta diseños inseguros (1); tutorial inicial (1); pensar en adultos mayores (1); ver en PC y elegir colores (1); poder probar la app antes (1).

### 2.2 Carpinterías (n = 4 + 2 testimonios)

| Tema | Resultado |
|---|---|
| Canal de alerta | **100% WhatsApp** · 0% email |
| Datos para cotizar | **100% medidas** · **100% tipo de madera** |

- **Testimonio 1:** los clientes miden mal (bajo mesada con distinta profundidad adelante y atrás) y ella siempre re-mide; cobra 50% de seña y 50% contra entrega; muchos clientes compran el material ellos con el listado que ella arma y pagan solo la mano de obra; propone catálogo de fotos por carpintero y una guía de cómo medir.
- **Testimonio 2:** quiere cargar las piezas y el tipo de placa (por ejemplo, aglomerado de 2,40 × 1,80 m) y que la app diga cuántas placas usar ("dos placas y media").

---

## 3. Las 3 funcionalidades clave del MVP

```
[F1] Diseñá y probalo en tu espacio  ──>  [F2] Sabé qué comprar  ──>  [F3] Encargalo a una carpintería
     plantilla + medidas validadas             despiece + placas            pedido + panel del carpintero
     + realidad aumentada                      + herrajes + barniz          + aviso WhatsApp + seña
```

Cada una responde a un dolor medido: F1 al 58% que mide mal y al 87% que valora la AR, F2 al 32% que no sabe qué comprar y al testimonio 2, F3 al 100% de carpinterías que pide medidas y madera por WhatsApp.

### F1 – Diseñá y probalo en tu espacio

| ID | Requisito | Alcance | Criterios de aceptación |
|---|---|---|---|
| RF-01 | El cliente crea un mueble desde una **plantilla paramétrica** (estante, mesa, bajo mesada) y ajusta ancho, alto, profundidad y cantidad de estantes, viéndolo en 3D. | MVP | Al cambiar una medida, el modelo 3D se actualiza en menos de 1 s. Solo acepta valores dentro del rango de la plantilla. |
| RF-02 | El cliente ingresa las **medidas del espacio** (ancho, alto, profundidad adelante y atrás) y el sistema **avisa si el mueble no entra** o si las medidas son inconsistentes. | MVP | Si el mueble supera el espacio en cualquier eje, se muestra un aviso con la diferencia en cm. Si profundidad adelante y atrás difieren, se usa la menor y se avisa. |
| RF-03 | El cliente elige **material** (pino, melamina, aglomerado) y **color o terminación**. | MVP | El modelo 3D refleja el color elegido. El material queda guardado en el proyecto. |
| RF-04 | El cliente ve el mueble **en su espacio real con AR**, a escala 1:1. | MVP | En Android (Chrome) y en iPhone (Safari) se abre la vista AR con las medidas del diseño. En PC se muestra el visor 3D. |
| RF-05 | El cliente **guarda** su proyecto y lo ve en "Mis proyectos". | MVP | Un proyecto guardado se puede reabrir con las mismas medidas, material y color. |
| RF-06 | Guía visual de **cómo medir** el espacio (frente, fondo, arriba y abajo). | MVP | Accesible desde el paso de medidas del espacio, con ilustración. |

### F2 – Sabé qué comprar

| ID | Requisito | Alcance | Criterios de aceptación |
|---|---|---|---|
| RF-07 | El sistema genera el **despiece**: lista de piezas con medidas en mm y cantidad. | MVP | Para cada plantilla y medida, la suma de piezas coincide con el modelo. Probado con casos fijos. |
| RF-08 | El sistema calcula **cuántas placas o tablas** hacen falta según el tamaño estándar del material (por ejemplo, 2,40 × 1,80 m). | MVP | Caso del testimonio 2: 5 piezas de 1,80 × 0,40 m en placa de 2,40 × 1,80 m da el resultado correcto. Siempre redondea hacia arriba. |
| RF-09 | El sistema calcula **tornillos, bisagras/correderas y litros de barniz o pintura**. | MVP | Las cantidades se muestran en la lista de materiales con su unidad. |
| RF-10 | El sistema muestra el **costo estimado de materiales**, marcado como **estimado** (no como precio real). | MVP | El total aparece con la etiqueta "estimado" y la fecha de los precios de referencia. |
| RF-11 | El cliente **descarga un PDF** con medidas, despiece y lista de materiales para hacerlo por su cuenta. | Post-MVP | — |

### F3 – Encargalo a una carpintería

| ID | Requisito | Alcance | Criterios de aceptación |
|---|---|---|---|
| RF-12 | Registro e inicio de sesión con roles **Cliente** y **Carpintería**. | MVP | Cada rol ve solo sus pantallas. Un cliente no puede acceder a la bandeja de una carpintería. |
| RF-13 | La carpintería crea su **perfil**: nombre, zona, WhatsApp y materiales con los que trabaja. | MVP | El perfil aparece en el mapa solo si tiene zona y WhatsApp cargados. |
| RF-14 | El cliente ve **carpinterías cercanas en un mapa** (Google Maps) que trabajan el material elegido. | MVP | El mapa muestra solo carpinterías que trabajan ese material. |
| RF-15 | El cliente **pide presupuesto** enviando diseño, medidas, material y despiece. | MVP | El pedido se crea en estado *Pendiente* y la carpintería lo ve con todos esos datos. |
| RF-16 | La carpintería recibe un **aviso por WhatsApp** (vía n8n) con el enlace directo al pedido en su panel. WhatsApp es solo el aviso: toda la gestión se hace en el panel. | MVP | El aviso llega en menos de 1 minuto. Si falla, se reintenta y el pedido igual queda en la bandeja del panel. |
| RF-17 | Desde el panel, la carpintería responde con un **presupuesto** que separa **materiales** y **mano de obra**, e indica si el cliente compra el material. | MVP | El pedido pasa a *Presupuestado* y el cliente ve el detalle. |
| RF-18 | El cliente **acepta** y paga la **seña por Mercado Pago**; el sistema registra la **comisión** de la carpintería. | MVP | El pedido pasa a *Aceptado* solo cuando el webhook de Mercado Pago confirma el pago. La comisión se calcula con el porcentaje configurado. |
| RF-19 | La carpintería marca **Medidas verificadas**, **En fabricación** y **Entregado**, y el cliente ve el estado actualizado. | MVP | Solo la carpintería del pedido puede cambiar el estado, y solo en el orden de la máquina de estados. |

#### Panel de la carpintería (interfaz propia del carpintero)

La carpintería es quien paga la comisión, así que necesita una interfaz propia para trabajar los pedidos, no solo un mensaje. El panel es mobile first, porque el carpintero lo usa desde el taller con el celular.

| ID | Requisito | Alcance | Criterios de aceptación |
|---|---|---|---|
| RF-27 | **Bandeja de pedidos** con filtros por estado (nuevos, presupuestados, aceptados, en fabricación, entregados). | MVP | Los pedidos nuevos aparecen primero y marcados como no leídos. |
| RF-28 | **Detalle del pedido**: visor 3D del mueble que se puede girar, medidas del mueble y del espacio, material, color, despiece y cantidad de placas. | MVP | El carpintero ve exactamente lo que diseñó el cliente, sin pedirle datos por fuera de la app. |
| RF-29 | **Avisos dentro de la app**: contador de pedidos nuevos y actualización en tiempo real (WebSocket o SSE) cuando entra un pedido o el cliente paga la seña. | MVP | Con el panel abierto, un pedido nuevo aparece sin recargar la página. |
| RF-30 | **Resumen de trabajos**: pedidos aceptados, señas cobradas y comisión descontada. | MVP | Los montos coinciden con los pagos confirmados por Mercado Pago. |
| RF-31 | Agenda de visitas para verificar medidas. | Post-MVP | — |

**Máquina de estados del pedido:**

```
[Pendiente] ──(carpintería presupuesta)──> [Presupuestado] ──(seña pagada)──> [Aceptado]
     │                                          │                                │
     │                                          ├──(cliente rechaza)──> [Rechazado]
     │                                          │                                │
     └──(sin respuesta en 72 h)──> [Vencido]    └──(sin respuesta en 7 días)──> [Vencido]
                                                                                 │
           MVP:      [Aceptado] ──> [Medidas verificadas] ──> [En fabricación] ──> [Entregado]
                     Cualquier estado antes de Entregado ──(cancelación)──> [Cancelado]
```

### Soporte a la tracción (no es funcionalidad del producto, pero se construye)

| ID | Requisito | Alcance | Criterios de aceptación |
|---|---|---|---|
| RF-20 | **Lista de espera** para clientes y carpinterías con **contador visible**. | MVP | El contador muestra el número real de inscriptos. |
| RF-21 | Panel interno con usuarios, diseños creados, pedidos y señas cobradas. | MVP | Los números salen de la base de datos, no se cargan a mano. |

---

## 4. Post-MVP (validado por los datos, se hace después)

| ID | Requisito | Origen |
|---|---|---|
| RF-11 | Exportar plano en PDF | 32% |
| RF-31 | Agenda de visitas para verificar medidas | Testimonio 1 |
| RF-22 | **Chatbot con Gemini** que recomienda madera según el uso, con pros, contras y precio, y advierte diseños inseguros | 4 comentarios |
| RF-23 | Tutorial inicial (onboarding) | 1 comentario |
| RF-24 | Catálogo de fotos por carpintería | Testimonio 1 |
| RF-25 | Calificaciones y reseñas de carpinterías | Tracción (STARS) |
| RF-26 | Más plantillas (placard, mesa de luz, muebles infantiles) | Testimonio 1 |

## 5. Fuera de alcance de esta versión

- Diseño libre desde cero (solo plantillas paramétricas).
- Generar un diseño a partir de una foto o imagen de Pinterest.
- Chat en vivo entre cliente y carpintería.
- Uso sin conexión (35% lo pidió, pero no es crítico para validar).
- Aplicación nativa Android o iOS (la web app funciona en el celular).
- Cotización automática con proveedores de materiales en tiempo real.
- Suscripciones o pagos premium para clientes.
- Algoritmos de asignación automática de carpinterías (el cliente elige).

---

## 6. Qué construir primero (orden sugerido)

El orden sigue las dependencias entre requisitos y permite trabajar en paralelo, como en el DAG del workshop:

```
                 ┌──> Frontend: RF-01..RF-06 (diseño 3D, medidas, AR)       ──┐
                 ├──> Backend:  RF-07..RF-10 (despiece y placas)             ──┤
Lead (contratos) ┼──> Backend:  RF-12..RF-19 (usuarios, pedidos, pagos)      ──┼──> Pruebas y revisión ──> Deploy
  API + modelo   └──> Frontend: RF-27..RF-30 (panel de la carpintería)       ──┘
                 (en cualquier momento) RF-20 lista de espera, RF-21 métricas
```

1. **RF-20 lista de espera** primero: suma tracción desde hoy.
2. **F2 (materiales)** en el backend: es lógica pura, fácil de probar y es la "tecnología interesante" del pitch.
3. **F1 (diseño + AR)** en el frontend, en paralelo.
4. **F3 (pedido + panel de la carpintería + WhatsApp + seña)**: cierra el flujo y genera REVENUE. El panel se construye junto con el backend de pedidos.

## 7. Puntos abiertos
1. **Muestra de carpinterías chica (4):** no se preguntó si aceptan la comisión ni cuánto tiempo pierden midiendo. Conviene sumar 2 o 3 respuestas antes del pitch.
2. **Plazos de vencimiento** del pedido (72 h y 7 días): son una propuesta, ajustar si hace falta.
