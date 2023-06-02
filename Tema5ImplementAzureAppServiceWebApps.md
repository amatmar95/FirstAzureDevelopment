## Tema 5: Implement Azure App Service Web Apps

- Preguntas: 
  - **¿Cuáles son las características principales de Azure App Service?** 
  
    Azure App Service es un servicio de plataforma como servicio (PaaS) en Microsoft Azure que permite a los desarrolladores crear, implementar y escalar aplicaciones web y móviles de forma rápida y sencilla. Ofrece soporte para múltiples lenguajes y marcos de desarrollo, facilita la implementación continua, permite la escalabilidad automática para adaptarse a la carga de tráfico, se integra con otros servicios de Azure, ofrece herramientas de administración y monitorización, garantiza la seguridad y el cumplimiento normativo, y proporciona una experiencia de desarrollo y despliegue eficiente. En resumen, Azure App Service es una solución completa y poderosa que simplifica el desarrollo y la gestión de aplicaciones, permitiendo a los desarrolladores enfocarse en la creación de valor y la entrega de experiencias de alta calidad a los usuarios.
  
  - **¿Cómo se configura y escala una aplicación web en Azure App Service?**
  
    Para configurar y escalar una aplicación web en Azure App Service, primero se crea una instancia de App Service y se implementa la aplicación en ella. A continuación, se configuran los ajustes específicos de la aplicación, como variables de entorno, cadenas de conexión y configuraciones de enrutamiento. Para la escalabilidad, se pueden configurar reglas de escala automática basadas en métricas de rendimiento y ajustar el número de instancias según la demanda de tráfico. Además, se utiliza el monitoreo y los paneles de control de Azure App Service para supervisar el rendimiento, realizar diagnósticos y establecer alertas. Con estos pasos, se logra una configuración y escala óptima de la aplicación web, brindando una experiencia eficiente y garantizando el rendimiento y la disponibilidad de la aplicación en Azure.
  
  - **¿Qué es un plan de App Service y cómo se relaciona con las aplicaciones web?**
  
    Un plan de App Service en Azure es una configuración que define los recursos y características disponibles para ejecutar aplicaciones web en Azure App Service. Actúa como un entorno en el que se alojan y ejecutan las aplicaciones web. El plan de App Service determina la asignación de recursos, el nivel de rendimiento y la capacidad de escala vertical y horizontal de las aplicaciones web. Proporciona flexibilidad para adaptarse a los requisitos de rendimiento y escalabilidad de las aplicaciones, permitiendo a los desarrolladores elegir el nivel adecuado según sus necesidades. Al utilizar planes de App Service, se logra un despliegue eficiente y una gestión optimizada de recursos para las aplicaciones web en Azure.
  
- Identificar y explicar (comprobar si es posible) de la bateria de Preguntas 3 preguntas por cada integrante relacionadas con Azure app Service Web Apps.

  - **QUESTION 2, PÁGINA 22:**

    **You are developing a web app that is protected by Azure Web Application Firewall (WAF). All traffic to the web app is routed through an Azure Application Gateway instance that is used by multiple web apps. The web app address is contoso.azurewebsites.net.** 

    **All traffic must be secured with SSL. The Azure Application Gateway instance is used by multiple web apps.** 

    **You need to configure the Azure Application Gateway for the web app.** 

    **Which two actions should you perform? Each correct answer presents part of the solution.** 

    NOTE: Each correct selection is worth one point.

    A. In the Azure Application Gateway’s HTTP setting, enable the Use for App service setting. 

    B. Convert the web app to run in an Azure App service environment (ASE). 

    C. Add an authentication certificate for contoso.azurewebsites.net to the Azure Application Gateway. 

    D. In the Azure Application Gateway’s HTTP setting, set the value of the Override backend path option to contoso22.azurewebsites.net. 

    **Respuesta correcta: AD** 

    **Explicación:** 

    A: 

    Terminación SSL y SSL de extremo a extremo con servicios multiinquilino.

    En el caso de SSL de extremo a extremo, los servicios confiables de Azure, como las aplicaciones web de Azure App Service, no requieren incluir los backends en la lista de la application gateway. Por lo tanto, no es necesario agregar ningún certificado de autenticación.

    D: 

    La capacidad de especificar una anulación de host está definida en la configuración de HTTP y se puede aplicar a cualquier conjunto de servidores durante la creación de reglas.

    La capacidad de derivar el nombre de host de la dirección IP o el nombre de dominio completamente calificado (FQDN) de los miembros del conjunto de servidores. La configuración de HTTP también proporciona la opción de seleccionar dinámicamente el nombre de host a partir del FQDN de un miembro del conjunto de servidores si está configurado con la opción de derivar el nombre de host de un miembro individual del conjunto de servidores.

    

    ![image-20230601133352245](C:\Users\Jon Pinies\AppData\Roaming\Typora\typora-user-images\image-20230601133352245.png)

  - **QUESTION 3, PÁGINA 83:**

    **HOTSPOT** 

    **You are building a traffic monitoring system that monitors traffic along six highways. The system produces time series analysis-based reports for each highway. Data from traffic sensors are stored in Azure Event Hub.** 

    **Traffic data is consumed by four departments. Each department has an Azure Web App that displays the time series-based reports and contains a WebJob that processes the incoming data from Event Hub. All Web Apps run on App Service Plans with three instances.** 

    **Data throughput must be maximized. Latency must be minimized.** 

    **You need to implement the Azure Event Hub.** 

    **Which settings should you use? To answer, select the appropriate options in the answer area.** 

    NOTE: Each correct selection is worth one point. 

    Hot Area:

    ![image-20230601133608040](C:\Users\Jon Pinies\AppData\Roaming\Typora\typora-user-images\image-20230601133608040.png)

    Respuesta correcta:

    ![image-20230601133642959](C:\Users\Jon Pinies\AppData\Roaming\Typora\typora-user-images\image-20230601133642959.png)

    **Explicación:** 

    Desplegable 1: 6 

    El número de pariciones se especifica en la creación y debe ser de entre 2 y 32.

    Hay 6 Highways.

    Desplegable 2: Highway 

  - **QUESTION 9, PÁGINA 201:**

    **DRAG DROP** 

    **You develop a web app that uses tier D1 app service plan by using the Web Apps feature of Microsoft Azure App Service.**

    **Spikes in traffic have caused increases in page load times.** 

    **You need to ensure that the web app automatically scales when CPU load is about 85 percent and minimize costs.** 

    **Which four actions should you perform in sequence? To answer, move the appropriate actions from the list of actions to the answer area and arrange them in the correct order.** 

    NOTE: More than one order of answer choices is correct. You will receive credit for any of the correct orders you select.

    Select and Place:

    ![image-20230601133918681](C:\Users\Jon Pinies\AppData\Roaming\Typora\typora-user-images\image-20230601133918681.png)

    Respuesta correcta:

    ![image-20230601133947271](C:\Users\Jon Pinies\AppData\Roaming\Typora\typora-user-images\image-20230601133947271.png)

    **Explicación:** 

    Paso 1: Configurar el web app a Standard App Service tier .

    El Standard tier soporta el auto-escalado, y deberíamos minimizar costes.

    Paso 2: Habilitar el auto-escalado en el web app. 

    Paso 3: Añadir una scale rule. 

    Paso 4: Añadir una Scale condition.
