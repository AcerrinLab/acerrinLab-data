# Paso a paso del hackatón

## Análisis (José)
1. Encuesta a clientes → resultados en `02_analisis/encuestas/`
2. Encuesta a carpinterías → resultados en `02_analisis/encuestas/`
3. Generar los requisitos funcionales y no funcionales a partir de los datos recabados **[Aprobarlos]** → `02_analisis/requisitos/`

## Diseño (José)
1. Diseñar el diagrama de clases base para entender con qué estamos trabajando.
2. Diseñar los casos de uso.
3. Diseñar las tareas de backend y frontend (agentes de IA y APIs: Gemini, n8n, Google Maps).
   - Arquitectura: monolito modular
   - Tecnologías: Java y Spring Boot (backend), React (frontend)
   - Detalle agregado: chatbot
   - GitHub en común
   - Nombre del proyecto: Viruta → por cada monolito, `Viruta-<nombre del monolito>`

## Programación (Maxi) [Agentes – aprobar o desaprobar cambios]
- Tomar de base el procedimiento de Joel para la construcción de páginas **[Enviar contexto]**.
1. A partir de los diseños y requisitos:
   - Crear las pruebas en base a los casos de uso (se muestran en el video).
   - Arrancar por las pruebas y construir solo el código para la funcionalidad base de la presentación.
   - Documentar backend y frontend de forma clara y precisa.
   - Cumplir patrones de diseño que permitan escalar.
   - Aplicar los estándares de seguridad más rigurosos en ambos proyectos.
2. Deployar y probar con compañeros y posibles clientes (dominio en Vercel).
- Agregado si se llega: aplicación Android.

## Testeo y video
1. Probar todos los casos de uso importantes.
2. Generar el video. El guion debe responder:
   - **Utilidad:** ¿Resuelve un problema real? ¿Para quién?
   - **Experiencia de usuario:** ¿Se entiende solo? ¿Da ganas de volver a usarlo?
   - **Modelo de negocio:** ¿Cómo se sostiene? ¿Quién paga y por qué? → comisión por trabajo concretado.
   - **Tecnología interesante:** ¿Qué tiene de nuevo por adentro? ¿Qué decisión técnica nos enorgullece?
