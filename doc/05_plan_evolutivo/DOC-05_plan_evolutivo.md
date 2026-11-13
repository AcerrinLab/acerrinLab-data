# Plan evolutivo
## Viruta – plataforma web para diseñar, visualizar y encargar muebles a medida

**Código:** DOC-05
**Versión:** 0.3
**Fecha:** 13 de noviembre de 2026
**Estado:** Propuesto. Pendiente de aprobación del equipo (José Manuel Fernández / Maximo Acosta Gloss).
**Bases:** DOC-01 V0.4, DOC-02A y DOC-02B V0.3, DOC-04A V0.3, `00_hackaton/paso_a_paso.md`, `04_diseno_y_arquitectura/tecnologias.md`, `coherencia_y_decisiones.md`.
**Fechas:** entrega del proyecto el 13/11/2026 · hackatón el 22/11/2026.

---

## 1. Objetivo

Ordenar la construcción del MVP definido en DOC-02A en entregas que se puedan demostrar y probar, una por una, siguiendo las dependencias entre requisitos. La tracción (lista de espera y métricas) se trabaja en paralelo desde el primer día porque es lo que más pesa en la evaluación del hackatón.

Esta versión reemplaza a la 0.2. Se quitó el alcance del borrador del 4/11 que no coincidía con lo que definió el equipo: el editor modular desde cero, la foto del ambiente como forma principal de visualizar, el producto sin cuentas ni panel de carpintería, el producto sin pagos y la atención manual del piloto.

## 2. Alcance de referencia

El alcance es el de DOC-02A:

| Funcionalidad | Qué resuelve | Requisitos |
|---|---|---|
| **F1 – Diseñá y probalo en tu espacio** | Plantillas paramétricas, medidas del espacio con aviso, material y color, realidad aumentada, guardado y guía de cómo medir. | RF-01 a RF-06 |
| **F2 – Sabé qué comprar** | Despiece, cantidad de placas, herrajes y barniz, costo estimado. | RF-07 a RF-10 |
| **F3 – Encargalo a una carpintería** | Cuentas por rol, perfil y mapa de carpinterías, pedido, aviso por WhatsApp, presupuesto, seña por Mercado Pago con comisión, estados y panel de la carpintería. | RF-12 a RF-19, RF-27 a RF-30 |
| **Tracción** | Lista de espera con contador y panel de métricas. | RF-20, RF-21 |

Lo que queda **post-MVP** y **fuera de alcance** está en DOC-02A §4 y §5. Este plan no agrega funcionalidades.

## 3. Vista general de hitos

| Hito | Entrega | Requisitos | Depende de | Responsable |
|---|---|---|---|---|
| **T** | Tracción (en paralelo, desde el día 1) | RF-20, RF-21 | — | A definir |
| **H0** | Diseño, base del proyecto y contratos | Diagrama de clases, casos de uso, RNF-06, RNF-08, RNF-12, RNF-13 | DOC-02A y DOC-02B aprobados | José (diseño) · Maxi (base) |
| **H1** | Motor de materiales (F2) | RF-07 a RF-10 | H0 | Maxi |
| **H2** | Diseño 3D y realidad aumentada (F1) | RF-01 a RF-06 | H0 | Maxi |
| **H3** | Carpinterías, pedidos y panel (F3) | RF-12 a RF-15, RF-17, RF-19, RF-27 a RF-29 | H0; H1 y H2 para el detalle del pedido | Maxi |
| **H4** | Aviso y cobro (F3) | RF-16, RF-18, RF-30 | H3 | Maxi |
| **H5** | Seguridad, deploy y prueba con personas | RNF-08, RNF-09, RNF-11, RNF-13 | H1 a H4 | Maxi · José |
| **H6** | Entrega y video | Casos de uso probados y video | H5 | A definir |

Responsables según `paso_a_paso.md`: análisis y diseño a cargo de José, programación a cargo de Maxi.

**Trabajo en paralelo** (igual que DOC-02A §6): una vez definidos los contratos en H0, H1 (backend), H2 (frontend) y H3 (backend y panel) avanzan al mismo tiempo, cada uno con su agente y su rama. La tracción (T) corre aparte durante todo el proyecto.

```
                 ┌──> H1 Motor de materiales (backend)       ──┐
H0 Diseño y      ├──> H2 Diseño 3D y AR (frontend)           ──┤
contratos        ┼──> H3 Carpinterías y pedidos (back + panel)──┼──> H4 Aviso y cobro ──> H5 Seguridad, deploy y prueba ──> H6 Entrega y video
                 └──────────────────────────────────────────────┘
T Tracción: lista de espera y métricas (en paralelo, desde el día 1)
```

---

## 4. T — Tracción (en paralelo)

**Resultado:** números reales, con link o captura, para mostrar en la entrega.

- Lista de espera para clientes y para carpinterías, con **contador visible** del número real de inscriptos (RF-20).
- Panel interno con usuarios, diseños creados, pedidos y señas cobradas, sacado de la base de datos (RF-21).
- Sumar 2 o 3 respuestas más de carpinterías antes del pitch (DOC-02A §7, punto abierto 1).

**Cierre:** el contador y el panel muestran datos reales, no cargados a mano (RNF-10).
**Evidencia:** número y link o captura de cada métrica.

## 5. H0 — Diseño, base del proyecto y contratos

**Resultado:** el diseño aprobado y una base sobre la que se pueda construir en paralelo.

Diseño (José):
- Aprobar DOC-02A y DOC-02B.
- Diagrama de clases base y casos de uso.
- Tareas de backend y frontend.

Base (Maxi):
- Backend Java + Spring Boot 4.x, **monolito modular** con los módulos `diseño`, `materiales`, `carpinterías`, `pedidos`, `pagos`, `notificaciones` y `usuarios`, que se comunican solo por interfaces públicas o eventos (RNF-06). Proyectos con nombre `Viruta-<módulo>`.
- Frontend React desplegado en Vercel.
- MySQL y backend en Docker, mismo entorno en desarrollo y producción (RNF-13).
- Contratos de la API en OpenAPI/Swagger, para que frontend y backend avancen en paralelo (RNF-12).
- Repositorio público: claves en `.env` ignorado por git y escaneo de secretos activado (RNF-08).
- Convención de medidas: milímetros enteros, con origen en la esquina frontal izquierda inferior del mueble; X hacia la derecha, Y hacia el fondo y Z hacia arriba (RNF-01).

Casos de prueba fijos (se escriben primero, siguiendo TDD):

| Caso | Entrada | Resultado esperado | Requisito |
|---|---|---|---|
| Testimonio 2 | 5 piezas de 1800 × 400 mm en placa de 2400 × 1800 mm | Cantidad de placas correcta, redondeada hacia arriba | RF-08 |
| Estante | Plantilla estante de 800 × 900 × 300 mm, tablero de 18 mm, un estante | 2 laterales de 900 × 300 mm; tapa, base y estante de 764 × 300 mm (5 piezas) | RF-07 |
| Estante más ancho | El mismo estante, con 1000 mm de ancho | Las 3 piezas interiores pasan a 964 × 300 mm; los laterales no cambian | RF-07 |
| Mesa | Plantilla mesa de 1200 × 750 × 600 mm, tablero de 18 mm | Cubierta de 1200 × 600 mm y 2 laterales de 732 × 600 mm (3 piezas) | RF-07 |
| Fuera de rango | Medida en cero o fuera del rango de la plantilla | Se rechaza sin perder el último diseño válido | RF-01 |

El detalle de estos casos, y los de medidas inválidas y espacio insuficiente, está en DOC-06 §5.

**Cierre:** el proyecto compila y levanta con Docker, los contratos se ven en Swagger y los casos de prueba están escritos.

## 6. H1 — Motor de materiales (F2)

**Resultado:** a partir de una plantilla y sus medidas, el sistema dice qué piezas cortar y qué comprar.

- Despiece con medidas en mm y cantidad (RF-07).
- Cantidad de placas o tablas según el tamaño estándar del material, con **cálculo simple** (piezas por placa, redondeo hacia arriba) y marcado como **estimado** (RF-08). La optimización real de cortes queda para después.
- Tornillos, bisagras o correderas y litros de barniz o pintura (RF-09).
- Costo estimado de materiales (RF-10), **solo si conseguimos precios de referencia con fuente y fecha**. Si no, pasa a post-MVP.
- Un cálculo por material con patrón Strategy (RNF-07).

**Cierre:** pasan los casos de H0 y los criterios de aceptación de RF-07 a RF-10. Cobertura del módulo `materiales` de 80% o más (RNF-12).
**Evidencia:** resultado de las pruebas. Es la "tecnología interesante" del pitch.

## 7. H2 — Diseño 3D y realidad aumentada (F1)

**Resultado:** el cliente arma su mueble desde una plantilla, ve si entra y lo ve en su casa.

- Plantillas paramétricas de estante, mesa y bajo mesada: ancho, alto, profundidad y cantidad de estantes, con el modelo 3D actualizado en menos de 1 s (RF-01).
- Medidas del espacio, con profundidad adelante y atrás, y aviso si el mueble no entra (RF-02).
- Material (pino, melamina, aglomerado) y color (RF-03).
- Realidad aumentada con `<model-viewer>` en Android (Chrome) e iPhone (Safari); en PC, visor 3D (RF-04).
- Guardar y reabrir en "Mis proyectos" (RF-05).
- Guía visual de cómo medir el espacio (RF-06).
- Mobile first, Android primero (RNF-05). Visor 3D a 30 fps o más en gama media y modelo AR de menos de 5 MB (RNF-04).

**Cierre:** pasan los criterios de aceptación de RF-01 a RF-06. Una persona sin experiencia crea su primer mueble y lo ve en AR en menos de 5 minutos (RNF-02).
**Evidencia:** demo en un celular Android real.

## 8. H3 — Carpinterías, pedidos y panel (F3)

**Resultado:** el cliente pide presupuesto y la carpintería lo trabaja desde su panel.

- Registro e inicio de sesión con roles Cliente y Carpintería, con JWT (RF-12).
- Perfil de la carpintería: nombre, zona, WhatsApp y materiales (RF-13).
- Mapa de carpinterías cercanas que trabajan el material elegido (Google Maps) (RF-14).
- Pedido de presupuesto con diseño, medidas, material y despiece (RF-15):
  - Al enviar se guarda una **copia fija** del diseño; editar después no cambia lo enviado.
  - Un reintento **no duplica** el pedido.
  - Los datos personales se piden recién al pedir presupuesto.
- Presupuesto que separa materiales y mano de obra (RF-17).
- Estados del pedido según la máquina de estados de DOC-02A, con patrón State (RF-19, RNF-07).
- Panel de la carpintería: bandeja con filtros (RF-27), detalle con visor 3D, despiece y placas (RF-28) y avisos en tiempo real (RF-29).

**Cierre:** pasan los criterios de aceptación de esos requisitos. Un cliente no puede entrar a la bandeja de una carpintería.

## 9. H4 — Aviso y cobro (F3)

**Resultado:** la carpintería se entera del pedido y la plataforma cobra la comisión.

- Aviso por WhatsApp vía n8n con el enlace al pedido. Si falla, se reintenta y el pedido igual queda en la bandeja (RF-16).
- El cliente acepta y paga la seña por Mercado Pago; el pedido pasa a *Aceptado* solo cuando el webhook (con firma verificada) confirma el pago, y se registra la comisión (RF-18, RNF-08).
- Resumen de trabajos, señas cobradas y comisión (RF-30).
- Si Maps, n8n o Mercado Pago fallan, el cliente sigue pudiendo diseñar y ver los materiales (RNF-11).

**Si no llegamos con la integración:** cobrar el primer pedido real con un link de pago de Mercado Pago generado a mano. También cuenta como REVENUE con captura (`coherencia_y_decisiones.md`, punto 4).

**Cierre:** pasan los criterios de aceptación de RF-16, RF-18 y RF-30.

## 10. H5 — Seguridad, deploy y prueba con personas

- Revisión de seguridad: BCrypt, solo HTTPS, validación de entradas, OWASP Top 10 y límite de peticiones en el login (RNF-08).
- Privacidad según Ley 25.326 (RNF-09).
- Deploy: frontend en Vercel y backend con MySQL en Docker (RNF-13).
- Prueba con compañeros y posibles clientes (`paso_a_paso.md`). Registrar qué les costó.

**Cierre:** la app está online, probada por personas reales, y las métricas de T salen de ese uso.

## 11. H6 — Entrega y video

- Probar todos los casos de uso importantes.
- Mostrar en el video las pruebas escritas a partir de los casos de uso.
- El guion responde los cuatro criterios: utilidad, experiencia de usuario, modelo de negocio (comisión por trabajo concretado, a cargo de la carpintería) y tecnología interesante.
- Tracción con número y link o captura.

---

## 12. Qué se entrega el 13/11 (a decidir)

**Propuesta:** el mínimo para la entrega es **T + H0 + H1 + H2** desplegado (F1 y F2 funcionando), más lo que se llegue de F3. Lo que no esté terminado se muestra en el video como hoja de ruta, no como hecho.

**Orden de recorte propuesto** si no alcanza el tiempo (de lo que menos afecta a lo que más):

1. RF-10 costo estimado (ya depende de conseguir precios con fuente).
2. RF-29 avisos en tiempo real (el pedido aparece al recargar).
3. RF-30 resumen de trabajos.
4. RF-18 seña integrada → link de pago manual (ver H4).
5. RF-14 mapa → listado de carpinterías filtrado por material.

No se recortan: lista de espera (RF-20), despiece y placas (RF-07, RF-08), plantilla con aviso de medidas y AR (RF-01, RF-02, RF-04) y pedido de presupuesto (RF-15).

## 13. Definición de terminado

Un hito está terminado cuando:

- sus criterios de aceptación de DOC-02A pasan como pruebas automáticas;
- está desplegado en la versión identificada (commit);
- la API está documentada en Swagger y el módulo tiene su README (RNF-12);
- no hay claves en el repositorio (RNF-08);
- tiene una nota breve: qué funciona, cómo probarlo y qué queda pendiente.

Una captura, un mockup o una prueba sin evidencia no reemplazan una función que anda.

## 14. Después del MVP

Lo validado por los datos que se hace después está en DOC-02A §4: exportar PDF (RF-11), chatbot con Gemini (RF-22), tutorial inicial (RF-23), catálogo de fotos por carpintería (RF-24), reseñas (RF-25), más plantillas (RF-26) y agenda de visitas (RF-31).

También quedan para después:
- Optimización real de cortes (más allá del cálculo simple de RF-08).
- Imagen del mueble en una foto del ambiente generada con Gemini, como mejora ilustrativa (`doc/README.md`, ideas para después del MVP).

## 15. Decisiones pendientes

| # | Tema | Opciones |
|---|---|---|
| 1 | Qué se entrega el 13/11 | Propuesta del §12. |
| 2 | Seña por Mercado Pago | Integración completa (RF-18) o link de pago manual para el primer pedido. |
| 3 | Costo estimado (RF-10) | Entra solo si hay precios de referencia con fuente; si no, post-MVP. |
| 4 | Chatbot | `paso_a_paso.md` lo lista como "detalle agregado"; DOC-02A lo deja post-MVP (RF-22). |
| 5 | Aplicación Android | `paso_a_paso.md` dice "si se llega"; DOC-02A deja fuera la app nativa. |
| 6 | Cuenta del cliente | RF-05 ("Mis proyectos") implica cuenta; `coherencia_y_decisiones.md` propone que el cliente no necesite cuenta hasta pedir presupuesto. |

## Historial

| Versión | Fecha | Cambio |
| --- | --- | --- |
| 0.1 | 04/11/2026 | Hitos del núcleo, recorrido y MVP piloto sobre el editor modular. |
| 0.2 | 12/11/2026 | Se registra la fecha límite y se marca para revisión conjunta. Sin cambios en los hitos. |
| 0.3 | 13/11/2026 | Reescrito sobre DOC-02A y DOC-02B: hitos por funcionalidad (F1, F2, F3), tracción en paralelo, casos de prueba, propuesta para la entrega del 13/11 y orden de recorte. Se quita el alcance del borrador del 4/11 que no coincidía con lo definido por el equipo. |
