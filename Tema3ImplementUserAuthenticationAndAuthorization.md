## Tema 3: Implement user authentication and authorization

- Preguntas: 
  - ¿Qué es la Plataforma de Identidad de Microsoft y cómo se utiliza para la autenticación de usuarios? 
  
    La Plataforma de Identidad de Microsoft Azure es un conjunto de servicios y herramientas que facilitan la autenticación y gestión de identidades en aplicaciones y servicios en la nube. Con servicios como Azure Active Directory, Azure AD B2C y Azure AD Connect, los desarrolladores pueden agregar funciones de inicio de sesión seguro y administración de identidades en sus aplicaciones. Estos servicios se integran mediante APIs y SDKs, permitiendo solicitar tokens de acceso, autenticar usuarios y proteger recursos de manera segura. En resumen, la plataforma de identidad de Azure proporciona una solución completa para implementar la autenticación de usuarios de manera segura en aplicaciones y servicios en la nube.
  
  - ¿Cuál es el flujo de autenticación más común al utilizar la Plataforma de Identidad de Microsoft? 
  
    El flujo de autenticación más común al utilizar la Plataforma de Identidad de Microsoft Azure comienza con el usuario ingresando sus credenciales en una aplicación que utiliza Azure AD o Azure AD B2C como proveedor de identidad. El proveedor de identidad verifica las credenciales, emite un token de acceso y redirige al usuario de vuelta a la aplicación. La aplicación valida el token de acceso y, una vez confirmado, permite al usuario acceder a los recursos protegidos. Este flujo garantiza la autenticación segura del usuario y la protección de los recursos en aplicaciones y servicios basados en Azure.
  
  - ¿Cómo se obtienen y se utilizan los tokens de acceso para autorizar solicitudes a recursos protegidos?
  
    Para obtener y utilizar los tokens de acceso en la Plataforma de Identidad de Microsoft Azure para autorizar solicitudes a recursos protegidos, el usuario se autentica a través del proveedor de identidad, como Azure AD. El proveedor de identidad emite un token de acceso que contiene información sobre la identidad del usuario y sus permisos. El token de acceso se envía a la aplicación, que lo valida verificando su firma y fecha de expiración. Una vez validado, la aplicación utiliza la información del token para autorizar las solicitudes del usuario a los recursos protegidos, asegurando que el usuario tenga los permisos adecuados. De esta manera, los tokens de acceso desempeñan un papel crucial en la autorización segura de las solicitudes a los recursos protegidos en la Plataforma de Identidad de Azure.
  
- Identificar y explicar (comprobar si es posible) de la bateria de Preguntas 3 preguntas por cada integrante relacionadas con user authentication and authorization . 

  - QUESTION 1, PÁGINA 110: 

    DRAG DROP 

    You need to add markup at line AM04 to implement the ContentReview role. How should you complete the markup? To answer, drag the appropriate json segments to the correct locations. Each json segment may be used once, more than once, or not at all. You may need to drag the split bar between panes or scroll to view content. 

    NOTE: Each correct selection is worth one point.

    Select and Place:

    ![image-20230601130221026](C:\Users\Jon Pinies\AppData\Roaming\Typora\typora-user-images\image-20230601130221026.png)

    Correct Answer:

    ![image-20230601131104614](C:\Users\Jon Pinies\AppData\Roaming\Typora\typora-user-images\image-20230601131104614.png)

    Section: (none) 

    Explanation 

    Explanation/Reference: 

    Explanation: 

    Box 1: allowedMemberTypes 

    allowedMemberTypes specifies whether this app role definition can be assigned to users and groups by setting to "User", or to other applications (that are accessing this application in daemon service scenarios) by setting to "Application", or to both. 

    Note: The following example shows the appRoles that you can assign to users. 

    "appId": "8763f1c4-f988-489c-a51e-158e9ef97d6a", 

    "appRoles": [ 

    ​	{ 

    ​		"allowedMemberTypes": [ 

    ​			"User" 

    ​		], 

    ​		"displayName": "Writer", 

    ​		"id": "d1c2ade8-98f8-45fd-aa4a-6d06b947c66f", 

    ​		"isEnabled": true, 

    ​		"description": "Writers Have the ability to create tasks.", 

    ​		"value": "Writer" A6319EC1AC83D57E5BA185C098116365 

    ​	} 

    ], 

    "availableToOtherTenants": false, 

    Box 2: User 

    Scenario: In order to review content a user must be part of a ContentReviewer role. 

    Box 3: value 

    value specifies the value which will be included in the roles claim in authentication and access tokens. 

    Reference: 

    https://docs.microsoft.com/en-us/graph/api/resources/approle

  - QUESTION 19, PÁGINA 157:

    DRAG DROP 

    You are developing an ASP.NET Core website that can be used to manage photographs which are stored in Azure Blob Storage containers. 

    Users of the website authenticate by using their Azure Active Directory (Azure AD) credentials. 

    You implement role-based access control (RBAC) role permissions on the containers that store photographs. You assign users to RBAC roles. 

    You need to configure the website’s Azure AD Application so that user’s permissions can be used with the Azure Blob containers. 

    How should you configure the application? To answer, drag the appropriate setting to the correct location. Each setting can be used once, more than once, or not at all. You may need to drag the split bar between panes or scroll to view content. 

    NOTE: 

    Each correct selection is worth one point. 

    Select and Place:

    ![image-20230601131551286](C:\Users\Jon Pinies\AppData\Roaming\Typora\typora-user-images\image-20230601131551286.png)

    Correct Answer:

    ![image-20230601131624587](C:\Users\Jon Pinies\AppData\Roaming\Typora\typora-user-images\image-20230601131624587.png)

    Section: (none) 

    Explanation 

    Explanation/Reference: 

    Explanation: 

    Box 1: user_impersonation 

    Box 2: delegated 

    Example: 

    - Select the API permissions section 
    - Click the Add a permission button and then: Ensure that the My APIs tab is selected 
    - In the list of APIs, select the API TodoListService-aspnetcore. 
    - In the Delegated permissions section, ensure that the right permissions are checked: user_impersonation. 
    - Select the Add permissions button.

    Box 3: delegated 

    Example 

    - Select the API permissions section 
    - Click the Add a permission button and then, Ensure that the Microsoft APIs tab is selected 
    - In the Commonly used Microsoft APIs section, click on Microsoft Graph 
    - In the Delegated permissions section, ensure that the right permissions are checked: User.Read. Use the search box if necessary. 
    - Select the Add permissions button 

    Reference: 

    https://docs.microsoft.com/en-us/samples/azure-samples/active-directory-dotnet-webapp-webapiopenidconnect-aspnetcore/calling-a-web-api-in-an-aspnet-core-web-application-using-azure-ad/

  - QUESTION 1, PÁGINA 78:

    DRAG DROP 

    You need to add code at line PC32 in Processing.cs to implement the GetCredentials method in the Processing class. 

    How should you complete the code? To answer, drag the appropriate code segments to the correct locations. Each code segment may be used once, more than once, or not at all. You may need to drag the split bar between panes or scroll to view content. 

    NOTE: Each correct selection is worth one point. 

    Select and Place:

    ![image-20230601132534699](C:\Users\Jon Pinies\AppData\Roaming\Typora\typora-user-images\image-20230601132534699.png)

    Correct Answer:

    ![image-20230601132605242](C:\Users\Jon Pinies\AppData\Roaming\Typora\typora-user-images\image-20230601132605242.png)

    Section: (none) 

    Explanation 

    Explanation/Reference: 

    Explanation:

    Box 1: AzureServiceTokenProvider() 

    Box 2: tp.GetAccessTokenAsync("..") 

    Acquiring an access token is then quite easy. Example code: 

    private async Task GetAccessTokenAsync() 

    { 

    ​	var tokenProvider = new AzureServiceTokenProvider(); 

    ​	return await tokenProvider.GetAccessTokenAsync("https://storage.azure.com/"); 

    } 

    Reference: 

    https://joonasw.net/view/azure-ad-authentication-with-azure-storage-and-managed-service-identity