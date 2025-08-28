### **ACTIVIDAD: Evaluación de Rendimiento sobre API de Libros** 💻

**Objetivo:**
Aplicar de manera integrada los conocimientos adquiridos en el módulo de Pruebas de Rendimiento para diseñar, configurar, ejecutar y analizar un plan de pruebas completo en JMeter, sobre un sistema real accesible de manera pública. El sistema a evaluar es el endpoint de lectura `/api/books` de la API en Spring Boot.

**Contexto:**
La empresa ficticia "DataTest SPA" ha contratado tus servicios como Ingeniero de Pruebas de Performance. Uno de sus nuevos proyectos consiste en validar el rendimiento de su API interna desarrollada en Java con Spring Boot.

Como parte de la validación del rendimiento del consumo de esta API, te solicitan elaborar un plan de pruebas que permita medir su comportamiento ante diferentes escenarios de carga, parametrización de datos y configuración avanzada de elementos de prueba.

**Requerimientos:**

1.  **Crear un Plan de Pruebas en JMeter que contemple:**
    * Grupos de Thread configurados con distintos modelos de carga: **prueba de carga** (Load Test) y **prueba de estrés** (Stress Test).
    * Uso de Samplers **HTTP Request** para consultar los siguientes endpoints:
        * `GET http://localhost:8080/api/books`.
        * `GET http://localhost:8080/api/books/{id}`.
    * Uso de Controllers lógicos para modularizar la prueba y definir el flujo de ejecución.

2.  **Configurar elementos adicionales:**
    * **Pre-processors** para generar datos dinámicos o variables de usuario.
    * **Post-processors** para capturar respuestas y validar contenido.
    * **Assertions** que permitan verificar el correcto funcionamiento de las respuestas obtenidas (por ejemplo, el código de respuesta `200 OK` o `204 No Content`).
    * **Listeners** adecuados para la recolección de métricas.

3.  **Parametrización:**
    * Consumir datos desde un archivo **CSV** para enviar solicitudes simulando distintos IDs de libros. Los datos a utilizar deben ser los IDs existentes en la base de datos de inicio (`data.sql`), por ejemplo, los IDs `1`, `2` y `3`.

4.  **Ejecución y Optimización:**
    * Definir hilos de ejecución considerando un **ramp-up** y **loop count** adecuados.
    * Emular comportamiento humano incorporando temporizadores.
    * Ejecutar la prueba en modo no-GUI y generar reportes automáticos.

5.  **Análisis de Resultados:**
    * Interpretar las métricas obtenidas (tiempos de respuesta, throughput, desviación estándar, percentiles).
    * Identificar cuellos de botella.
    * Crear un reporte final de resultados en formato Excel o PDF que contenga:
        * Gráficos de tiempos de respuesta.
        * Tabla resumen con resultados clave.
        * Conclusiones y recomendaciones.
