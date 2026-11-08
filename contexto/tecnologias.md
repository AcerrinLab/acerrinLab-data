# Stack Tecnológico y Arquitectura - AcerrinLab

## 1. El Diferencial: Más allá del Modelado
Mientras que herramientas tradicionales (como SketchUp) se limitan al diseño técnico aislado, nuestra arquitectura está orientada a la **coordinación integral**. La tecnología seleccionada permite que un cliente diseñe de forma intuitiva en la web y, con un solo clic, ese modelo se traduzca en una lista de materiales exacta y una solicitud de cotización directa para la red de carpinteros locales.

## 2. Frontend y Experiencia Visual (El "Anti-SketchUp")
El objetivo aquí es eliminar la barrera de entrada. No hay descargas ni instalaciones complejas; todo ocurre en el navegador del celular o la PC.

*   **React.js / Next.js:** Framework principal para construir una Web App rápida y responsiva. Permite interfaces separadas pero unificadas: un panel (dashboard) simplificado para el cliente y un panel de gestión de órdenes y planos para el carpintero.
*   **React Three Fiber (Three.js):** Motor de renderizado 3D en el navegador. 
    *   *Propósito:* Permite al cliente manipular dimensiones (ancho, alto, profundidad) de piezas de madera predefinidas de forma visual, sin necesidad de conocimientos técnicos de CAD.
*   **`<model-viewer>` (Google):** Componente web para Realidad Aumentada (AR).
    *   *Propósito:* Permite al cliente proyectar el mueble diseñado directamente en su habitación usando la cámara de su celular, ayudando a la decisión de compra antes de contactar al carpintero.

## 3. Backend y Lógica de Coordinación
El núcleo de la plataforma, encargado de calcular materiales y conectar a las dos entidades (clientes y carpinteros).

*   **Spring Boot 4.x.x (Monolito Modular):** Framework principal en Java. 
    *   *Propósito:* Estructurar la lógica de negocio en módulos independientes (Módulo Cliente, Módulo Diseño, Módulo Carpintero/Cotizaciones) garantizando rapidez en el desarrollo actual y escalabilidad a futuro.
*   **Spring WebSockets (o Server-Sent Events):** Protocolo de comunicación bidireccional.
    *   *Propósito:* Habilitar notificaciones en tiempo real para el carpintero cuando ingresa un nuevo pedido de mueble en su zona, y un chat en vivo para que cliente y carpintero ajusten detalles del plano.
*   **Algoritmo de Cálculo de Materiales (Lógica interna):** 
    *   *Propósito:* Traducir las dimensiones del modelo 3D en requerimientos físicos (metros cuadrados de madera, cantidad de tornillos, litros de barniz) para que el carpintero reciba una orden de trabajo lista para presupuestar, ahorrándole horas de cálculo manual.

## 4. Persistencia y Despliegue
*   **MySQL + JPA/Hibernate:** Base de datos relacional.
    *   *Propósito:* Mantener la integridad de los datos entre los perfiles de usuario, el directorio de carpinteros validados, el historial de proyectos 3D guardados y el estado de las cotizaciones (Pendiente, Aceptada, En Progreso).
*   **Docker:** Contenedorización del entorno.
    *   *Propósito:* Asegurar que el entorno de desarrollo y producción sean idénticos, permitiendo empaquetar el monolito y la base de datos de forma segura.