# Tema 2: Implement Azure Functions



### Preguntas:

- ¿Qué son las Azure Functions y para qué se utilizan?

  Las Azure Functions son una excelente solución para procesar datos, integrar sistemas, trabajar con el Internet de las cosas (IoT) y construir APIs y microservicios simples.

  Se utilizan Functions para tareas como el procesamiento de imágenes o pedidos, el mantenimiento de archivos o cualquier tarea que desees ejecutar según un horario.

  Azure Functions admite desencadenadores (triggers), que son formas de iniciar la ejecución de tu código, y enlaces (bindings), que son formas de simplificar la codificación para los datos de entrada y salida.

  

- ¿Cuáles son los desencadenadores (triggers) más comunes en Azure Functions?

  Los triggers mas comunes son:

  Timer

  - Azure Storage queues and blobs
  - Azure Service Bus queues and topics
  - Azure Cosmos DB
  - Azure Event Hubs
  - HTTP/ WebHook (GitHub)
  - Azure Event Grid

- ¿Cómo se configura y se despliega una Azure Function?

​	La configuración y el despliegue de una Azure Function implican los siguientes pasos generales:

1. Crear una Function App: Una Function App es el contenedor lógico que alojará tus Azure Functions. Puedes crear una Function App en el portal de Azure o mediante herramientas de línea de comandos como Azure CLI o Azure PowerShell.
2. Crear una Azure Function: Dentro de tu Function App, puedes crear una nueva Azure Function. Debes seleccionar el tipo de desencadenador (trigger) que desees utilizar, como HTTP, Timer, Blob Storage, Queue Storage, etc. También puedes elegir el lenguaje de programación que prefieras, como C#, JavaScript, Python, etc.
3. Escribir el código de la Function: Una vez creada la Azure Function, puedes escribir el código que se ejecutará cuando se active el desencadenador. Puedes utilizar el editor en línea del portal de Azure o trabajar localmente con tu IDE preferido y luego subir el código a la Function App.
4. Configurar las conexiones y los enlaces (bindings): Si tu Azure Function necesita interactuar con otros servicios o recursos, puedes configurar conexiones y enlaces para simplificar el acceso a ellos. Por ejemplo, puedes establecer una conexión a una base de datos, a un servicio de almacenamiento o a una API externa.
5. Probar y depurar la Function: Antes de implementarla, es recomendable probar y depurar tu Azure Function para asegurarte de que funcione correctamente. Puedes utilizar herramientas como el registro de trazas y las pruebas locales para identificar y solucionar cualquier problema.
6. Implementar la Function: Una vez que estés satisfecho con tu Azure Function, puedes implementarla en tu Function App. Puedes hacerlo directamente desde el portal de Azure, a través de herramientas de línea de comandos o mediante la automatización de CI/CD (integración continua/distribución continua).
7. Monitorear y escalar: Después de desplegar tu Azure Function, es importante monitorear su rendimiento y comportamiento. Puedes utilizar las herramientas de supervisión de Azure para obtener métricas y registros, y ajustar la escala según sea necesario para satisfacer las demandas de carga.





-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------







### Identificar y explicar (comprobar si es posible) de la bateria de Preguntas 3 preguntas por cada integrante relacionadas con Azure Functions



**DEVELOP AZURE COMPUTE SOLUTIONS -  QUESTION SET 5 - PAGINA 36/37**

**QUESTION 14**

DRAG DROP
You are developing a serverless Java application on Azure. You create a new Azure Key Vault to work with
secrets from a new Azure Functions application.
The application must meet the following requirements:

- Reference the Azure Key Vault without requiring any changes to the Java code.-

- Dynamically add and remove instances of the Azure Functions host based on the number of incoming
  application events.

- Ensure that instances are perpetually warm to avoid any cold starts.

- Connect to a VNet.

- Authentication to the Azure Key Vault instance must be removed if the Azure Function application is
  deleted.

  You need to grant the Azure Functions application access to the Azure Key Vault.

  Which three actions should you perform in sequence? To answer, move the appropriate actions from the list of actions to the answer area and arrange them in the correct order.



![tema 2 - pregunta 14](https://github.com/amatmar95/FirstAzureDevelopment/blob/7ab1586e223a075d5109c5e4f3e2fce98eddbc67/imagenes/tema%202-%20pregunta%2014.png)





**SOLUCION:** 

![tema 2 - pregunta 14 - respuesta](https://github.com/amatmar95/FirstAzureDevelopment/blob/7ab1586e223a075d5109c5e4f3e2fce98eddbc67/imagenes/tema%202-%20pregunta%2014%20-%20respuesta.png)





**EXPLICACION:**

Paso 1: Crea la aplicación de Azure Functions con un tipo de plan de consumo. Utiliza el plan de consumo para el modelo sin servidor.

Paso 2: Crea una identidad administrada asignada por el sistema para la aplicación. Crea una identidad administrada asignada por el sistema para tu aplicación. Actualmente, las referencias a Key Vault solo admiten identidades administradas asignadas por el sistema. No se pueden utilizar identidades asignadas por el usuario.

Paso 3: Crea una política de acceso en Key Vault para la identidad de la aplicación. Crea una política de acceso en Key Vault para la identidad de la aplicación que creaste anteriormente. Habilita el permiso "Obtener" para secretos en esta política. No configures la opción "aplicación autorizada" o "applicationId", ya que esto no es compatible con una identidad administrada.



-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------





**DEVELOP AZURE COMPUTE SOLUTIONS -  QUESTION SET 5 - PAGINA 44**

**QUESTION 19**

Note: This question is part of a series of questions that present the same scenario. Each question
in the series contains a unique solution that might meet the stated goals. Some question sets might
have more than one correct solution, while others might not have a correct solution.

You develop an HTTP triggered Azure Function app to process Azure Storage blob data. The app is
triggered using an output binding on the blob.
The app continues to time out after four minutes. The app must process the blob data.
You need to ensure the app does not time out and processes the blob data.
Solution: Pass the HTTP trigger payload into an Azure Service Bus queue to be processed by a queue
trigger function and return an immediate HTTP success response.
Does the solution meet the goal?
A. Yes
B. No



**SOLUCION:** 

A - YES



**EXPLICACION:**

Las funciones grandes y de larga duración pueden causar problemas inesperados de tiempo de espera. Las buenas prácticas generalmente incluyen: cuando sea posible, refactorizar las funciones grandes en conjuntos más pequeños de funciones que trabajen juntas y devuelvan respuestas rápidas. Por ejemplo, una función de webhook o activador HTTP puede requerir una respuesta de confirmación dentro de un límite de tiempo determinado; es común que los webhooks requieran una respuesta inmediata. Una forma de abordar esto es pasar la carga útil del activador HTTP a una cola para ser procesada por una función de activación de cola. Este enfoque le permite posponer el trabajo real y devolver una respuesta inmediata.





-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------





**DEVELOP AZURE COMPUTE SOLUTIONS -  QUESTION SET 5 - PAGINA 47**

**QUESTION 24**

You are developing an Azure Function App that processes images that are uploaded to an Azure Blob container.
Images must be processed as quickly as possible after they are uploaded, and the solution must minimize
latency. You create code to process images when the Function App is triggered.
You need to configure the Function App.
What should you do?
A. Use an App Service plan. Configure the Function App to use an Azure Blob Storage input trigger.
B. Use a Consumption plan. Configure the Function App to use an Azure Blob Storage trigger.
C. Use a Consumption plan. Configure the Function App to use a Timer trigger.
D. Use an App Service plan. Configure the Function App to use an Azure Blob Storage trigger.
E. Use a Consumption plan. Configure the Function App to use an Azure Blob Storage input trigger.



**SOLUCION:** 

B. Use a Consumption plan. Configure the Function App to use an Azure Blob Storage trigger



**EXPLICACION:**

El desencadenador de almacenamiento Blob inicia una función cuando se detecta un nuevo archivo blob o cuando un blob existente se actualiza. El contenido del blob se proporciona como entrada a la función.

El plan de consumo limita una funcion en una máquina virtual (VM) a 1,5 GB de memoria.



