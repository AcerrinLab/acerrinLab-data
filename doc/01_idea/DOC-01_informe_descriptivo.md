# Informe descriptivo del proyecto
## Viruta – plataforma web para diseñar, visualizar y encargar muebles a medida

**Código:** DOC-01
**Versión:** 0.4
**Fecha:** 13 de noviembre de 2026
**Estado:** Borrador para revisión del equipo.
**Nombre comercial:** Viruta (AcerrinLab)
**Equipo:** José Manuel Fernández y Maximo Acosta Gloss
**Bases:** `idea_original.md`, `contexto_general.md`, DOC-02A y DOC-02B V0.3, encuestas y testimonios de `02_analisis/`.

---

## 1. Resumen de la propuesta

Viruta es una aplicación web para que una persona pase de "tengo una idea de mueble" a "tengo un mueble que entra en mi espacio y una carpintería que lo cotiza".

El cliente elige una plantilla (estante, mesa o bajo mesada), carga las medidas de su espacio y ajusta el mueble viéndolo en 3D. La aplicación le avisa si no entra, se lo muestra en su casa con realidad aumentada y le calcula qué tiene que comprar: piezas, placas, herrajes y barniz. Con eso puede hacerlo por su cuenta o encargarlo a una carpintería de su zona.

La carpintería recibe el pedido con las medidas, el material y el despiece, por WhatsApp y en un panel propio. Desde ahí responde el presupuesto y sigue el trabajo. Cuando el cliente acepta, paga la seña por Mercado Pago y la plataforma cobra una comisión a la carpintería.

El MVP es **vertical**: muebles simples en madera, melamina o aglomerado, para vecinos y carpinterías independientes de Jujuy.

## 2. Problema que se busca resolver

Las personas no pueden pasar de una idea de mueble a un pedido que una carpintería pueda cotizar sin errores de medida ni idas y vueltas.

Lo que dicen los datos (encuesta a 31 clientes y 4 carpinterías, más 2 testimonios):

- **58%** de los clientes dice que su mayor frustración es calcular mal las medidas y que el mueble no entre.
- **48%** no logra imaginar cómo combina el color y el estilo con su ambiente.
- **32%** no sabe cuánto material comprar.
- **90%** dice que hoy le cuesta encontrar planos o guías (promedio 2,55 sobre 5).
- Los carpinteros lo confirman: el cliente mide mal (por ejemplo, un bajo mesada con distinta profundidad adelante y atrás) y ellos tienen que volver a medir siempre (testimonio 1).
- **100%** de las carpinterías necesita **medidas** y **tipo de madera** para cotizar.

El detalle de las encuestas está en DOC-02A §2.

## 3. Usuarios

| Usuario | Necesidad | Beneficio |
|---|---|---|
| Cliente | Definir un mueble que entre en su espacio, saber qué comprar y encontrar quién lo haga. | Ve el mueble en su casa antes de encargarlo, recibe la lista de materiales y pide presupuesto con todos los datos. |
| Carpintería | Recibir pedidos con medidas confiables y el material definido. | Presupuesta sin perder tiempo en pedidos incompletos y gestiona sus trabajos desde un panel. |
| Equipo (AcerrinLab) | Validar el producto y conseguir tracción. | Métricas reales de uso, lista de espera y señas cobradas. |

**Zona inicial:** San Salvador de Jujuy y alrededores.

## 4. Propuesta de valor

**Diseñá tu mueble, probalo en tu espacio, sabé qué comprar y encargalo a una carpintería de tu zona.**

Hay herramientas que configuran muebles y calculan piezas, y otras que conectan clientes con profesionales (DOC-02 §4). Viruta une las dos cosas en un mismo recorrido: la carpintería recibe exactamente lo que diseñó el cliente.

## 5. Objetivo del MVP

Que un cliente arme un mueble desde una plantilla, compruebe que entra, lo vea en su espacio con AR, obtenga la lista de materiales y pida presupuesto a una carpintería. Y que esa carpintería pueda presupuestar desde su panel y cobrar la seña dentro de la aplicación.

El MVP se limita a **3 funcionalidades clave** (DOC-02A §3):

```
[F1] Diseñá y probalo en tu espacio  ──>  [F2] Sabé qué comprar  ──>  [F3] Encargalo a una carpintería
```

## 6. Recorrido principal

**Cliente:**

1. **Elegir una plantilla:** estante, mesa o bajo mesada.
2. **Medir el espacio:** con la guía visual de cómo medir (frente, fondo, arriba y abajo), cargar ancho, alto y profundidad adelante y atrás.
3. **Ajustar el mueble:** ancho, alto, profundidad y cantidad de estantes, viendo el modelo 3D. Si el mueble no entra, la aplicación avisa cuánto sobra.
4. **Elegir material y color:** pino, melamina o aglomerado.
5. **Verlo en su espacio:** abrir la vista de realidad aumentada en el celular, a escala real.
6. **Ver qué comprar:** despiece, cantidad de placas, tornillos, bisagras o correderas, litros de barniz o pintura y costo estimado.
7. **Guardar** el proyecto en "Mis proyectos".
8. **Elegir cómo hacerlo:**
   - **Hacelo vos mismo:** usar la lista de materiales para comprar y fabricar.
   - **Encargalo:** ver en un mapa las carpinterías cercanas que trabajan ese material y pedir presupuesto.
9. **Aceptar el presupuesto** y pagar la seña por Mercado Pago.
10. **Seguir el estado** del pedido hasta la entrega.

**Carpintería:**

1. Crear su perfil: nombre, zona, WhatsApp y materiales con los que trabaja.
2. Recibir el aviso del pedido por WhatsApp, con el enlace al panel.
3. Ver el pedido en su panel: modelo 3D, medidas del mueble y del espacio, material, color, despiece y placas.
4. Responder con un presupuesto que separa materiales y mano de obra, e indicar si el cliente compra el material.
5. Cuando el cliente paga la seña, verificar las medidas en el lugar, fabricar y marcar la entrega.

## 7. Alcance funcional del MVP

| Funcionalidad | Alcance | Requisitos |
|---|---|---|
| Plantillas paramétricas | Estante, mesa y bajo mesada, con medidas dentro de un rango por plantilla. | RF-01 |
| Medidas del espacio | Aviso si el mueble no entra o si las medidas son inconsistentes. | RF-02 |
| Material y color | Pino, melamina y aglomerado. | RF-03 |
| Realidad aumentada | Vista a escala real en Android e iPhone; visor 3D en PC. | RF-04 |
| Mis proyectos | Guardar y reabrir. | RF-05 |
| Guía de cómo medir | Ilustración en el paso de medidas. | RF-06 |
| Despiece | Piezas con medidas en mm y cantidad. | RF-07 |
| Placas | Cantidad de placas o tablas según el tamaño estándar del material, redondeada hacia arriba. | RF-08 |
| Herrajes y terminación | Tornillos, bisagras o correderas y litros de barniz o pintura. | RF-09 |
| Costo estimado | Marcado como estimado, con fecha de los precios de referencia. | RF-10 |
| Cuentas | Roles Cliente y Carpintería. | RF-12 |
| Carpinterías | Perfil y mapa filtrado por material. | RF-13, RF-14 |
| Pedido y presupuesto | Pedido con todos los datos del diseño; presupuesto con materiales y mano de obra. | RF-15, RF-17 |
| Aviso | WhatsApp vía n8n. | RF-16 |
| Seña y comisión | Mercado Pago, con registro de la comisión. | RF-18 |
| Estados | Medidas verificadas, en fabricación y entregado. | RF-19 |
| Panel de la carpintería | Bandeja, detalle con visor 3D, avisos en tiempo real y resumen de trabajos. | RF-27 a RF-30 |
| Tracción | Lista de espera con contador y panel de métricas. | RF-20, RF-21 |

Lo que queda para después y lo que está fuera de alcance está en DOC-02A §4 y §5.

## 8. Contenido del pedido que recibe la carpintería

- Identificación del pedido, fecha y cliente.
- Modelo 3D del mueble, que se puede girar.
- Tipo de mueble (plantilla) y medidas generales.
- Medidas del espacio, incluida la profundidad adelante y atrás.
- Material, espesor y color.
- Despiece: cada pieza con largo, ancho, espesor y cantidad.
- Cantidad estimada de placas o tablas.
- Herrajes y litros de barniz o pintura estimados.
- Aclaración de que las medidas las cargó el cliente y se verifican en el lugar antes de fabricar.

Al enviar el pedido se guarda una **copia fija** del diseño: si el cliente lo edita después, el pedido enviado no cambia.

## 9. Coherencia de datos y límites

- Las medidas del mueble alimentan el modelo 3D, la vista en AR, el despiece y la lista de materiales. Cambiar una medida actualiza todo.
- Las medidas se guardan en **milímetros enteros**.
- Las medidas del espacio las carga el cliente. La aplicación ayuda con la guía y los avisos, pero la carpintería las verifica en el lugar (estado *Medidas verificadas*), como ya lo hace hoy.
- La realidad aumentada sirve para ver el mueble en el espacio; no es una herramienta de medición.
- Las placas, los herrajes, el barniz y el costo son **estimados** y se muestran así. El cálculo de placas es simple (piezas por placa, redondeo hacia arriba); no optimiza cortes.
- La inteligencia artificial no es la fuente de las medidas ni del despiece. El chatbot con Gemini queda para después, solo como asistente (RF-22).

## 10. Funciones previstas para después del MVP

Validadas por los datos (DOC-02A §4):

- Exportar el plano en PDF para hacerlo por tu cuenta (RF-11).
- Chatbot con Gemini que recomienda madera según el uso y advierte diseños inseguros (RF-22).
- Tutorial inicial (RF-23).
- Catálogo de fotos por carpintería (RF-24).
- Calificaciones y reseñas (RF-25).
- Más plantillas: placard, mesa de luz, muebles infantiles (RF-26).
- Agenda de visitas para verificar medidas (RF-31).

Otras ideas para evaluar:

- Optimización real de cortes.
- Imagen del mueble dentro de una foto del ambiente, generada con Gemini, como mejora ilustrativa.

## 11. Modelo de negocio

**Comisión por trabajo concretado.**

- Cuando el cliente acepta el presupuesto, paga la seña por Mercado Pago dentro de la aplicación.
- La plataforma cobra a la carpintería una comisión de **8% a 12%** sobre el trabajo, descontada de esa seña.
- **Quién paga:** la carpintería.
- **Por qué paga:** recibe un cliente que ya trae diseño, medidas y material definidos. Presupuesta más rápido y pierde menos tiempo en consultas que no se concretan.

Lo respaldan los datos: solo el 19% de los clientes pagaría una suscripción, y cobrar 50% de seña ya es como trabajan hoy los carpinteros (testimonio 1).

## 12. Supuestos y cuestiones pendientes

| Supuesto o decisión | Cómo resolverlo |
|---|---|
| Las carpinterías aceptan pagar la comisión. | No se preguntó en la encuesta. Consultarlo al sumar 2 o 3 respuestas más (DOC-02A §7). |
| Base de la comisión cuando el cliente compra el material y paga solo la mano de obra (testimonio 1). | Definir con las carpinterías. |
| El cliente puede medir bien con la guía. | Prueba de uso (DOC-02 §9). |
| Un cliente sin experiencia arma su mueble y lo ve en AR en menos de 5 minutos. | Prueba de uso (RNF-02). |
| El pedido le alcanza a la carpintería para presupuestar sin pedir datos por fuera. | Revisión de un pedido con carpinterías (DOC-02 §9). |
| Hay precios de referencia con fuente para el costo estimado. | Si no se consiguen, RF-10 pasa a post-MVP. |
| Decisiones abiertas: qué se entrega el 13/11, seña integrada o link manual, chatbot, app Android, cuenta del cliente. | DOC-05 §15. |

## 13. Condiciones generales de calidad

Las condiciones medibles están en DOC-02B. En resumen:

- Precisión: milímetros enteros y cálculos cubiertos por pruebas (RNF-01).
- Simple: primer mueble en AR en menos de 5 minutos, lenguaje simple (RNF-02).
- Accesible: texto de 16 px o más, contraste AA, botones grandes (RNF-03).
- Rápido: 3D a 30 fps en Android de gama media (RNF-04).
- **Mobile first**, Android primero (RNF-05).
- Seguro: JWT, BCrypt, HTTPS, OWASP Top 10, sin claves en el repositorio público (RNF-08).
- Privado: Ley 25.326; los datos personales se piden recién al pedir presupuesto (RNF-09).
- Honesto: todo valor calculado se muestra como estimado y las métricas salen de datos reales (RNF-10).

## 14. Resultado esperado

Una aplicación online en la que una persona arma un mueble desde una plantilla, ve que entra, lo prueba en su espacio con AR, obtiene la lista de materiales y pide presupuesto a una carpintería de Jujuy, que lo responde desde su panel. Más métricas reales de uso para la entrega del hackatón.

## 15. Documentación relacionada

| Código | Documento |
|---|---|
| DOC-02 | Estudio de mercado y validación |
| DOC-02A | Requisitos funcionales |
| DOC-02B | Requisitos no funcionales |
| DOC-03 | Modelos visuales (mockups) |
| DOC-04A | Flujo de arquitectura |
| DOC-04B | Arquitectura técnica (pendiente; base: `tecnologias.md`) |
| DOC-05 | Plan evolutivo |
| DOC-06 | POC y condiciones de entrega |

## 16. Historial

| Versión | Fecha | Cambio |
| --- | --- | --- |
| 0.1 | 04/11/2026 | Primera descripción del proyecto y delimitación propuesta del MVP. |
| 0.2 | 04/11/2026 | Editor modular como función principal. |
| 0.3 | 12/11/2026 | Nombre comercial, equipo, fecha de entrega y tecnologías actualizados. |
| 0.4 | 13/11/2026 | Reescrito sobre la idea original, las encuestas y DOC-02A: plantillas paramétricas, realidad aumentada, cálculo de placas, cuentas, panel de la carpintería y comisión. Se quita el editor modular, la foto del ambiente como vista principal y la atención manual. |
