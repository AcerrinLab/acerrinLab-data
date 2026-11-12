# AcerrinLab – Contexto general del proyecto (Hackatón)

**Equipo:** Maximo Acosta Gloss y José Manuel Fernández
**Organización:** AcerrinLab
**Repositorio:** https://github.com/AcerrinLab/acerrinLab-data

---

## 1. La hackatón

- **Evento:** Solar Train Hackathon – Pre-Hackatón jujuy.dev
- **Fecha de la hackatón:** 22 de noviembre
- **Entrega del proyecto (fecha límite):** 13 de noviembre
- **Cupo:** 30 builders de Jujuy + 30 invitados especiales
- **Landing y entrega:** https://tren-solar-hackathon.vercel.app
- **Requisito excluyente:** vivir o residir en Jujuy (lo cumplimos).
- Organización y jurado evalúan cada proyecto con la misma planilla. Pasan los 30 con mayor puntaje.

### Criterios de evaluación

1. **Utilidad:** ¿Resuelve un problema real? ¿Para quién?
2. **Experiencia de usuario:** ¿Se entiende solo? ¿Da ganas de volver a usarlo?
3. **Modelo de negocio:** ¿Cómo se sostiene? ¿Quién paga y por qué?
4. **Tecnología interesante:** ¿Qué tiene de nuevo por adentro? Contanos la decisión técnica que te enorgullece.

### Tracción (es lo que más pesa)

Es la evidencia que más influye en la evaluación: un proyecto con gente usándolo le gana a uno perfecto en el papel.

- USERS (usuarios)
- REVENUE (ingresos)
- WAITLIST (lista de espera)
- STARS (estrellas / interacciones)

> **Regla de oro:** siempre presentar cada métrica con **número y link o captura** que la respalde.

---

## 2. La idea del producto: app de modelado de muebles

Una aplicación online donde las personas pueden:

### Funcionalidades principales

- **Modelado y medidas:** modelar un mueble (al principio, solo de madera) y evaluar sus medidas.
- **Visualización en el espacio:** ver cómo quedaría el mueble en el lugar donde lo quieren poner.
- **Cálculo de materiales:** obtener la lista de materiales que hay que comprar:
  - Cantidad de maderas y sus medidas.
  - Clavos.
  - Tornillos.
  - Litros de pintura o barniz.

### Opciones para hacer el mueble

Con el archivo del proyecto listo, la app ofrece dos caminos:

1. **Hacelo vos mismo:** imprimir el archivo y hacer el mueble por tu cuenta.
2. **Servicio de terceros:** buscar carpinterías de tu zona que puedan hacer el mueble.

### Para quién es

- **Clientes:** personas que quieren un mueble a medida, ya sea para hacerlo ellas mismas o para encargarlo.
- **Carpinterías:** reciben clientes que ya tienen el diseño, las medidas y los materiales definidos.

---

## 3. Modelo de negocio elegido: comisión por trabajo concretado (marketplace)

- Cuando un cliente acepta el presupuesto de una carpintería dentro de la app, la plataforma cobra un **porcentaje del trabajo (por ejemplo, entre 8% y 12%)**.
- Lo ideal es cobrarlo con una **seña pagada por Mercado Pago dentro de la app** y descontar la comisión de esa seña.
- **Quién paga:** la carpintería.
- **Por qué paga:** recibe un cliente que ya trae medidas, diseño y materiales definidos. Así puede presupuestar sin ir a medir y pierde menos tiempo en consultas que no terminan en venta.

---

## 4. Arquitectura y tecnología

- **Arquitectura:** monolito modular. Se eligió para entregar rápido, desplegar de forma simple y validar tracción antes del 13 de noviembre.
- **Tecnologías:** Java y Spring Boot (4.x.x).
- **Integraciones:** agentes de IA y APIs (Gemini, n8n, Google Maps).
- **Detalle agregado:** chatbot.

---

## 5. Paso a paso del proyecto

### Análisis
1. Encuesta a clientes → resultados obtenidos.
2. Encuesta a carpinterías → resultados obtenidos.
3. Generar los requisitos funcionales y no funcionales a partir de los datos recabados. **[Aprobarlos]**

### Diseño
1. Diseñar el diagrama de clases base para entender con qué estamos trabajando.
2. Diseñar los casos de uso.
3. Diseñar las tareas de backend y frontend (agentes de IA y APIs: Gemini, n8n, Google Maps).
   - Arquitectura: monolito modular
   - Tecnologías: Java y Spring Boot
   - Detalle agregado: chatbot

### Programación [Agentes – aprobar o rechazar cambios]
- Usar como base el procedimiento de Joel para construir páginas **[Enviar contexto]**.

1. A partir de los diseños y de los requisitos funcionales y no funcionales:
   - Escribir las pruebas a partir de los casos de uso del diseño (las vamos a mostrar en el video de la hackatón).
   - Si arrancamos por las pruebas, podemos escribir solo el código necesario para la funcionalidad base de la presentación.
   - Documentar el backend y el frontend de forma clara y precisa.
   - Seguir patrones de diseño que permitan escalar (para las próximas actualizaciones).
   - Aplicar en ambos proyectos los estándares de seguridad más rigurosos.
2. Deployar y probar el diseño con compañeros y posibles clientes.

### Testeo y generación del video
1. Probar todos los casos de uso importantes y que cumplan con la idea.
2. Generar el video.

### Importante: para clasificar hay que responder
- **Utilidad:** ¿Resuelve un problema real? ¿Para quién?
- **Experiencia de usuario:** ¿Se entiende solo? ¿Da ganas de volver a usarlo?
- **Modelo de negocio:** ¿Cómo se sostiene? ¿Quién paga y por qué?
- **Tecnología interesante:** ¿Qué tiene de nuevo por adentro? Contanos la decisión técnica que te enorgullece.

---

## 6. Tracción a conseguir antes de la entrega

Todo con captura o link:

- **REVENUE:** cobrar señas por Mercado Pago dentro de la app a los clientes que acepten un presupuesto (modelo de comisión).
- **WAITLIST:** un formulario de lista de espera para clientes y otro para carpinterías, con un contador visible.
- **Evidencia del problema:** usar los resultados de las encuestas a clientes y carpinterías para mostrar que el problema existe (por ejemplo, el porcentaje de carpinterías que pierde tiempo midiendo para presupuestos que no se concretan, o el dato que hayamos obtenido).
