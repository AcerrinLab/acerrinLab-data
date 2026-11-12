# Coherencia de la documentación y decisiones pendientes

**Fecha:** 12 de noviembre de 2026
**Estado:** Para revisar entre José Manuel Fernández y Maximo Acosta Gloss.
**Contexto:** los documentos DOC-01, 02, 04A, 05 y 06 se escribieron el 4/11, antes de las encuestas y de varias decisiones del equipo. Este archivo compara esos documentos con lo que ya teníamos (`01_idea/contexto_general.md`, `01_idea/idea_original.md`, `04_diseno_y_arquitectura/tecnologias.md`, `00_hackaton/paso_a_paso.md`, DOC-02A y DOC-02B).

---

## A. Corregido directamente (eran datos ya definidos)

| Documento | Antes | Ahora |
|---|---|---|
| DOC-01 | Nombre comercial pendiente; sin fecha ni tecnologías | Viruta (AcerrinLab), equipo, entrega 13/11/2026, stack React + Spring Boot |
| DOC-02 | Trabajo de campo pendiente; zona a definir; modelo de negocio sin elegir | Encuestas (31 clientes, 4 carpinterías) y 2 testimonios registrados; zona Jujuy; comisión por trabajo concretado |
| DOC-04A | Tecnologías a elegir en DOC-04B | Referencia al stack ya definido en `tecnologias.md` |
| DOC-05 | Sin fecha límite | Fecha límite 13/11 registrada; marcado "pendiente de revisión con Maxi". **Hitos sin tocar.** |
| DOC-06 | Fecha, responsables y localidad pendientes | Entrega 13/11, hackatón 22/11, Maxi en desarrollo, José en aceptación (a confirmar), Jujuy |

Cada documento subió de versión y lo registra en su historial.

---

## B. Contradicciones de alcance (decidir juntos)

| # | Tema | Lo que teníamos | Lo que dicen los docs nuevos | Qué dicen los datos | Recomendación |
|---|---|---|---|---|---|
| 1 | **Cómo se crea el mueble** | Plantillas paramétricas; "diseño libre desde cero" fuera de alcance (DOC-02A RF-01, §5) | **Editor modular** desde vacío con paleta de piezas (tablero, lateral, estante); plantillas opcionales (DOC-01 §6-7, DOC-04A §5, mockup 02) | 81% usaría "diseño libre en 3D"; 23% dice que le faltan herramientas sencillas | Adoptar el **modelo de piezas** del editor modular como base (es más sólido), pero para el 13/11 mostrar **plantillas editables** construidas con esas piezas. El editor libre completo queda para el siguiente hito. Actualizar RF-01. |
| 2 | **Ver el mueble en el espacio** | **Realidad aumentada** con la cámara del celular (RF-04, `tecnologias.md`) | **Foto del ambiente** con superposición manual (DOC-01 §6, DOC-04A §9, mockup 01) | 87% valora la AR con 4 o 5 | Mantener **AR como principal** (con `<model-viewer>` es poco código) y dejar la foto como alternativa para PC y para la ficha. La imagen generada con Gemini (idea del audio) queda como mejora ilustrativa posterior. |
| 3 | **Cuentas y panel de la carpintería** | Roles cliente y carpintería, panel completo del carpintero (RF-12, RF-27 a RF-30) | Sin cuentas en la primera prueba, guardado local, atención manual del piloto, "no requiere portal de profesionales" (DOC-01 §3, DOC-04A §2) | 100% de carpinterías quiere recibir los pedidos con medidas y madera | Mantener el **panel de la carpintería** (lo pediste explícitamente) y tomar del doc nuevo que el **cliente no necesite cuenta** hasta pedir presupuesto. |
| 4 | **Seña por Mercado Pago** | En el MVP, para generar ingresos (RF-18) | Pagos fuera de la primera versión (DOC-01 §10-11, DOC-05 §11, DOC-06 §3) | Solo 19% pagaría suscripción; la carpintera ya cobra 50% de seña | Decidir según el tiempo. Pesa mucho en tracción (REVENUE), pero es lo más riesgoso de construir. Alternativa: un link de pago de Mercado Pago generado a mano para el primer pedido real. |
| 5 | **Cantidad de placas** | En el MVP (RF-08, pedido del testimonio 2) | Optimización de cortes y compra de placas fuera (DOC-01 §8, DOC-04A §8, DOC-06 §3) | 32% no sabe cuánto material comprar | MVP con **cálculo simple** (piezas por placa, redondeo hacia arriba, marcado "estimado"). La optimización real de cortes queda después. |
| 6 | **Aviso al carpintero** | WhatsApp (RF-16) | Correo opcional (DOC-04A §11) | **100% WhatsApp, 0% correo** | WhatsApp. Corregir DOC-04A cuando se apruebe. |
| 7 | **Dispositivo principal** | Mobile first, Android primero (RNF-05) | Computadora como entorno principal; celular parcial (DOC-01 §13, DOC-06 §4) | 81% Android | Cliente y AR mobile first; aceptar que el **editor** se use mejor en PC si en celular no es cómodo. |
| 8 | **Precio estimado de materiales** | En el MVP (RF-10) | Evolución posterior (DOC-01 §10) | Importancia 8,74/10 | Solo si conseguimos precios de referencia con fuente (deep research R2). Si no, pasa a post-MVP. |
| 9 | **Plan evolutivo y plazos** | Entrega 13/11 | Hitos H0 a H6 sin fechas, con revisión profesional y piloto | — | **Revisar con Maxi:** qué hitos entran para el 13/11 (propuesta: H0 a H2 más un H5 mínimo) y cuáles se muestran como hoja de ruta en el video. |
| 10 | **Tracción** | Lista de espera y métricas (RF-20, RF-21); es lo que más pesa en el hackatón | No aparece en los docs nuevos (DOC-02 §13 la relativiza) | — | Mantenerla. Sumarla al plan evolutivo como tarea paralela desde el día 1. |
| 11 | **Chatbot** | En el plan del hackatón ("detalle agregado: chatbot"); post-MVP en DOC-02A (RF-22) | IA opcional y posterior; nunca fuente de medidas (DOC-01 §9) | 4 comentarios piden recomendación de madera | Coinciden: post-MVP y solo como asistente. Confirmar que no entra para el 13/11. |

---

## C. Lo bueno de los docs nuevos que conviene sumar a DOC-02A y DOC-02B

- Convención de ejes y medidas en mm con origen definido (DOC-04A §4). Refuerza RNF-01.
- Al enviar un pedido se guarda una **copia fija** del diseño; editar después no altera lo enviado (DOC-04A §11).
- Reintentos **sin pedidos duplicados** (DOC-04A §11).
- Diseño "incompleto" marcado como tal, nunca como listo para fabricar (DOC-04A §7).
- **Casos de referencia A, B y C** con resultados calculados a mano: sirven directo como pruebas (DOC-06 §5).
- **Ficha PDF** de referencia con frente, planta y lateral (DOC-01 §8). Hoy está en post-MVP (RF-11).
- Datos personales solo al pedir presupuesto; fotos en almacenamiento privado (DOC-04A §13).
- Definición común de "terminado" (DOC-05 §14).

## D. Huecos en la documentación

- **DOC-04B** (arquitectura técnica) aparece como base de DOC-05 y DOC-06, pero no existe. Es el próximo documento de Diseño.
- **DOC-03** (modelos visuales) solo tiene los dos mockups, sin texto que describa el recorrido.
- DOC-01 §15 menciona un documento de "modo de desarrollo y herramientas": puede ser la guía del entorno de IA, como DOC-04C.

## Próximo paso

Cuando decidan los puntos de la sección B, se actualizan DOC-02A, DOC-04A, DOC-05 y DOC-06 en una sola pasada y se borra este archivo o se archiva como registro de decisiones.
