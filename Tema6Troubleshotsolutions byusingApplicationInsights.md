## Tema 6:Troubleshoot solutions by using Application Insights

- Preguntas: 

  

 **¿Qué es Azure Application Insights y cómo se utiliza para el monitoreo de aplicaciones?**

Azure Application Insights es un servicio de monitoreo y diagnóstico en la nube ofrecido por Microsoft Azure. Permite realizar un seguimiento y recopilación de datos sobre el rendimiento, la disponibilidad y el uso de aplicaciones en tiempo real. Se utiliza para monitorear y analizar el comportamiento de las aplicaciones, identificar problemas de rendimiento, realizar un seguimiento de las métricas clave y generar informes detallados sobre la salud y el rendimiento de las aplicaciones.

   **¿Cuáles son las principales características y beneficios de Application Insights?**
Las principales características y beneficios de Application Insights son:

* Monitoreo de aplicaciones en tiempo real: Proporciona una visión en tiempo real del rendimiento y la disponibilidad de la aplicación, lo que permite detectar problemas y tomar medidas correctivas de inmediato.

* Recopilación de datos exhaustiva: Application Insights recopila una amplia gama de datos, como tiempos de respuesta, conteo de solicitudes, excepciones, eventos personalizados y métricas personalizadas. Esto permite un análisis detallado del rendimiento de la aplicación.

* Análisis y visualización de datos: Ofrece herramientas y paneles interactivos para analizar y visualizar los datos recopilados. Esto ayuda a identificar patrones, tendencias y problemas en el rendimiento de la aplicación.

* Diagnóstico avanzado: Application Insights proporciona capacidades de diagnóstico avanzadas, como seguimiento de solicitudes, seguimiento de dependencias, registro de eventos y seguimiento de excepciones. Esto facilita la identificación y solución de problemas en la aplicación.

* Integración con Azure y otras herramientas: Se integra estrechamente con otros servicios de Azure y herramientas de desarrollo, lo que facilita la supervisión y el diagnóstico de aplicaciones en entornos de Azure. También se puede integrar con herramientas populares de terceros como Visual Studio y Jira.



**¿Cómo se configura y se utiliza Application Insights para el diagnóstico y solución de problemas en una aplicación?**

Para configurar y utilizar Application Insights para el diagnóstico y solución de problemas en una aplicación, se deben seguir estos pasos:

* Crear una instancia de Application Insights en Azure Portal.

* Agregar el SDK de Application Insights a la aplicación, lo cual implica agregar la biblioteca del SDK a la solución y configurar las opciones de instrumentación.

* Recopilar y analizar datos: Una vez que la aplicación esté instrumentada con el SDK de Application Insights, comenzará a recopilar datos automáticamente. Se pueden analizar y visualizar estos datos en Azure Portal o utilizar API y herramientas para obtener información más detallada.

* Configurar alertas y notificaciones: Se pueden establecer reglas y umbrales personalizados para recibir alertas y notificaciones cuando se detecten problemas en la aplicación.

* Utilizar características de diagnóstico avanzadas: Application Insights ofrece capacidades de seguimiento de solicitudes, seguimiento de dependencias, registro de eventos y seguimiento de excepciones. Estas características permiten investigar y solucionar problemas específicos en la aplicación.

* Utilizar integraciones y extensiones: Application Insights se integra con otras herramientas y servicios de Azure, lo que permite aprovechar aún más el monitoreo y el diagnóstico de la aplicación.

Estos pasos te permitirán configurar y utilizar Application Insights de manera efectiva para el diagnóstico y solución de problemas en tu aplicación.

Referencia: https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blob-properties-metadata





**PREGUNTA 1,página 175**

Necesitas investigar el mensaje de error de la aplicación Azure Function en el entorno de desarrollo.

**¿Qué deberías hacer?**

A. Conectar Live Metrics Stream desde Application Insights a la aplicación Azure Function y filtrar las métricas.

B. Crear un nuevo espacio de trabajo de Azure Log Analytics e instrumentar la aplicación Azure Function con Application Insights.

C. Actualizar la aplicación Azure Function con métodos de extensión de Microsoft.Extensions.Logging para registrar eventos utilizando la instancia de registro (log).

D. Agregar una nueva configuración de diagnóstico a la aplicación Azure Function para enviar registros a Log Analytics.

**Respuesta correcta: A**

Explicación:

Azure Functions ofrece integración incorporada con Azure Application Insights para monitorear funciones.

Las siguientes áreas de Application Insights pueden ser útiles al evaluar el comportamiento, el rendimiento y los errores en tus funciones:

Live Metrics: Ver datos de métricas a medida que se crean en tiempo casi real. Failures (Fallos), Performance (Rendimiento), Metrics (Métricas)

Referencia:

https://docs.microsoft.com/en-us/azure/azure-functions/functions-monitoring



**PREGUNTA 6, página 197**

Estás desarrollando un servicio web API de ASP.NET Core. El servicio web utiliza Azure Application Insights para todo el seguimiento de telemetría y dependencias. El servicio web lee y escribe datos en una base de datos que no es Microsoft SQL Server.

Necesitas asegurarte de que el seguimiento de dependencias funcione para las llamadas a la base de datos de terceros.

**¿Cuáles son las dos propiedades de telemetría de dependencia que deberías usar? **

NOTA: Cada selección correcta vale un punto.

A. Telemetry.Context.Cloud.RoleInstance

B. Telemetry.Id

C. Telemetry.Name

D. Telemetry.Context.Operation.Id

E. Telemetry.Context.Session.Id

**Respuesta correcta: B y D**

Explicación:

Debes utilizar las propiedades "Telemetry.Id" y "Telemetry.Context.Operation.Id" para el seguimiento de dependencias en las llamadas a la base de datos de terceros.

Estas propiedades permiten la correlación de operaciones entre diferentes componentes de la aplicación y aseguran que las dependencias sean rastreadas correctamente en Azure Application Insights.

Referencia:

https://docs.microsoft.com/en-us/azure/azure-monitor/app/custom-operations-tracking



**PREGUNTA 3, página 190:**

Necesitas resolver el problema de capacidad de registro.

**¿Qué deberías hacer?**

A. Crear un filtro de telemetría de Application Insights.

B. Cambiar el nivel mínimo de registro en el archivo host.json de la función.

C. Implementar el muestreo de Application Insights.

D. Establecer un filtro de categoría de registro durante el inicio.

**Respuesta correcta: C**

Explicación:

En el escenario se menciona un problema de capacidad de registro: Los desarrolladores informan que la cantidad de mensajes de registro en la salida de traza para el procesador es demasiado alta, lo que resulta en la pérdida de mensajes de registro.

El muestreo es una función de Azure Application Insights. Es la forma recomendada de reducir el tráfico y el almacenamiento de telemetría, al tiempo que se preserva un análisis estadísticamente correcto de los datos de la aplicación. El filtro selecciona elementos relacionados para que puedas navegar entre ellos durante las investigaciones de diagnóstico. Cuando se te presentan recuentos de métricas en el portal, se renormalizan teniendo en cuenta el muestreo para minimizar cualquier efecto en las estadísticas.

El muestreo reduce el tráfico y los costos de datos, y te ayuda a evitar la limitación.

Referencia:

https://docs.microsoft.com/en-us/azure/azure-monitor/app/sampling









