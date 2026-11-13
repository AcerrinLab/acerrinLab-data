# Requisitos no funcionales
## Viruta – plataforma web para diseñar, visualizar y encargar muebles a medida

**Código:** DOC-02B
**Versión:** 0.3
**Fecha:** 12 de noviembre de 2026
**Estado:** Propuesto. Pendiente de aprobación del equipo (José Manuel Fernández / Maximo Acosta Gloss).
**Bases:** DOC-02A, encuestas de `02_analisis/`, plan del hackatón y `04_diseno_y_arquitectura/tecnologias.md`.
**Stack:** frontend React + React Three Fiber + `<model-viewer>` (Vercel) · backend Java + Spring Boot 4.x, monolito modular · MySQL · Docker · Google Maps, n8n (WhatsApp), Mercado Pago y Gemini (post-MVP).

---

## Requisitos no funcionales

| ID | Categoría | Requisito | Origen |
|---|---|---|---|
| RNF-01 | Precisión | Medidas en **milímetros enteros**. Despiece y cálculo de placas deterministas, cubiertos por pruebas unitarias con casos reales. Redondeo de placas siempre hacia arriba. | 65% precisión |
| RNF-02 | Usabilidad | Una persona sin conocimientos de diseño crea su primer mueble y lo ve en AR en **menos de 5 minutos**, sin ayuda. Lenguaje simple. | 55% interfaz intuitiva |
| RNF-03 | Accesibilidad | Texto base de 16 px o más, contraste **WCAG 2.1 AA**, botones de 44 × 44 px o más (adultos mayores). | Comentario |
| RNF-04 | Rendimiento | Visor 3D a **30 fps o más** en Android de gama media. Modelo para AR (GLB/USDZ) de menos de 5 MB, abre en menos de 3 s con 4G. API con p95 menor a 500 ms (sin contar IA). | 55% AR fluida |
| RNF-05 | Compatibilidad | Web app **mobile first**: Android Chrome primero (81%), iPhone Safari con AR Quick Look (35%), tablets y PC. | Encuesta |
| RNF-06 | Arquitectura | **Frontend:** React + React Three Fiber + `<model-viewer>`, desplegado en **Vercel**. **Backend:** **monolito modular** Java + Spring Boot 4.x con módulos que se comunican solo por interfaces públicas o eventos: `diseño`, `materiales`, `carpinterías`, `pedidos`, `pagos`, `notificaciones`, `usuarios`. Proyectos con nombre `Viruta-<módulo>`. | Plan del hackatón |
| RNF-07 | Escalabilidad | Cada módulo debe poder extraerse a un servicio aparte. Patrones: Strategy (cálculo por material), Adapter (Maps, Mercado Pago, n8n, Gemini), eventos de dominio (notificaciones), State (máquina de estados del pedido). | Plan del hackatón |
| RNF-08 | Seguridad | Spring Security con **JWT** y autorización por rol; contraseñas con **BCrypt**; solo **HTTPS**; validación de toda entrada; **OWASP Top 10**; webhooks de Mercado Pago con **firma verificada**; límite de peticiones en login. **El repositorio es público** (regla del hackatón): ninguna clave en el código, todo en `.env` ignorado por git, con escaneo de secretos activado. | Plan + workshop |
| RNF-09 | Privacidad | **Ley 25.326**: consentimiento explícito, el WhatsApp de la carpintería solo se usa para pedidos, el cliente ve la dirección exacta del taller recién al aceptar el presupuesto, posibilidad de borrar la cuenta. | Normativa + workshop |
| RNF-10 | Honestidad de datos | Todo valor calculado o de referencia (precios, cantidades de barniz) se muestra como **estimado**. Las métricas de tracción salen de datos reales. | Workshop |
| RNF-11 | Resiliencia | Si Google Maps, n8n o Mercado Pago fallan, el cliente sigue pudiendo diseñar y ver la lista de materiales. Timeouts y reintentos en todas las integraciones. | Integraciones |
| RNF-12 | Mantenibilidad | API documentada con **OpenAPI/Swagger**; README por módulo; pruebas escritas a partir de los criterios de aceptación (TDD); cobertura de 80% o más en el módulo `materiales`. | Plan del hackatón |
| RNF-13 | Despliegue | Backend y **MySQL** en **Docker**; frontend en Vercel; mismo entorno en desarrollo y producción. | tecnologias.md |
| RNF-14 | Costos | Solo niveles gratuitos (Google Maps, n8n, Gemini cuando se sume) con límites de uso configurados. | Workshop |
| RNF-15 | Localización | Español rioplatense, pesos argentinos (ARS), sistema métrico. | Público de Jujuy |
