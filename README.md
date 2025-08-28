
### **ACTIVIDAD: Evaluación de Rendimiento sobre API de Libros**

**Objetivo:**
Aplicar de manera integrada los conocimientos adquiridos en el módulo de Pruebas de Rendimiento para diseñar, configurar, ejecutar y analizar un plan de pruebas completo en JMeter, sobre la API de Libros (`/api/books`) del proyecto "api-restfull-springboot".

**Contexto:**
La empresa ficticia "DataTest SPA" ha contratado tus servicios como Ingeniero de Pruebas de Performance. Uno de sus nuevos proyectos consiste en validar el rendimiento de su API interna desarrollada en Java con Spring Boot.

Como parte de esta validación, te solicitan elaborar un plan de pruebas que permita medir el comportamiento del endpoint de lectura `/api/books` ante diferentes escenarios de carga y configuraciones avanzadas.

**Requerimientos:**

1.  **Crear un Plan de Pruebas en JMeter que contemple:**
    * Grupos de Thread configurados con distintos modelos de carga: prueba de carga (Load Test) y prueba de estrés (Stress Test).
    * Uso de Samplers **HTTP Request** para consultar los siguientes endpoints, que requieren autenticación con un token JWT:
        * `GET http://localhost:8080/api/books`.
        * `GET http://localhost:8080/api/books/{id}`.
    * Uso de Controllers lógicos para modularizar la prueba y definir el flujo de ejecución.

2.  **Configurar elementos adicionales:**
    * **Pre-processors** para obtener dinámicamente el `accessToken` mediante una solicitud `POST` al endpoint `http://localhost:8080/api/auth/login` con las credenciales del usuario de prueba "sofia" y contraseña "Academy".
    * **Post-processors** para capturar el `accessToken` de la respuesta de login y pasarlo al `Header` de las peticiones protegidas (`/api/books`).
    * **Assertions** que permitan verificar el correcto funcionamiento de las respuestas obtenidas (por ejemplo, código de respuesta 200 OK y contenido de la respuesta).
    * **Listeners** adecuados para la recolección de métricas.

3.  **Parametrización:**
    * Consumir datos desde un archivo **CSV** para enviar solicitudes a `http://localhost:8080/api/books/{id}`. Los datos a utilizar deben ser los IDs existentes en la base de datos de inicio (`data.sql`), por ejemplo, los IDs `1`, `2` y `3`.

4.  **Ejecución y Optimización:**
    * Definir hilos de ejecución considerando un `ramp-up` y `loop count` adecuados.
    * Emular comportamiento humano incorporando temporizadores.
    * Ejecutar la prueba en modo no-GUI y generar reportes automáticos.

5.  **Análisis de Resultados:**
    * Interpretar las métricas obtenidas (tiempos de respuesta, throughput, desviación estándar, percentiles).
    * Identificar cuellos de botella.
    * Crear un reporte final de resultados en formato Excel o PDF que contenga:
        * Gráficos de tiempos de respuesta.
        * Tabla resumen con resultados clave.
        * Conclusiones y recomendaciones.

---

### **Rúbrica de Evaluación:**

La rúbrica se mantiene igual que en el documento original, pero se aplicará a la nueva prueba de rendimiento sobre la API de libros.

| Criterio | Descripción | Nivel de Logro |
| :--- | :--- | :--- |
| **Diseño del Plan de Pruebas** | La prueba debe estar bien estructurada y modularizada. | Sobresaliente, Satisfactorio, Básico, Insuficiente |
| **Configuración de Elementos Avanzados** | Se evalúa el uso adecuado y eficiente de Pre-processors, Post-processors, Assertions y Listeners. | Sobresaliente, Satisfactorio, Básico, Insuficiente |
| **Parametrización y Emulación de Carga** | Se evalúa la parametrización correcta de datos desde un CSV y la emulación realista de usuarios mediante la configuración de ramp-up, loop count y temporizadores. | Sobresaliente, Satisfactorio, Básico, Insuficiente |
| **Análisis de Resultados y Reporte Final** | Se evalúa la interpretación adecuada de métricas, la identificación de cuellos de botella y la calidad del reporte final. | Sobresaliente, Satisfactorio, Básico, Insuficiente |
