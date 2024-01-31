---
description: Información sobre requisitos generales, autenticación, parámetros de consulta opcionales, direcciones URL de solicitud y otras referencias.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Introducción a las API de REST
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 16421f8f15a8aa8c1a561b0b6682091bf78683ce
workflow-type: tm+mt
source-wordcount: '2551'
ht-degree: 1%

---

# Introducción a [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Información sobre requisitos generales, autenticación, parámetros de consulta opcionales, solicitud [!DNL URLs]y otras referencias.

## Requisitos de API y Recommendations {#api-requirements-recommendations}

Tenga en cuenta lo siguiente al trabajar con [API de Audience Manager](https://bank.demdex.com/portal/swagger/index.html#/) código:

* **Parámetros de solicitud:** todos los parámetros de solicitud son obligatorios a menos que se especifique lo contrario.
* **Encabezados de solicitud**: al utilizar [Adobe Developer](https://www.adobe.io/) tokens, debe proporcionar el `x-api-key` encabezado. Puede obtener su [!DNL API] clave siguiendo las instrucciones de la [Integración de cuenta de servicio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) página.
* **[!DNL JSON]tipo de contenido:** Especificar `content-type: application/json`  *y*  `accept: application/json` en el código.
* **Solicitudes y respuestas:** Envío de solicitudes como una solicitud con el formato correcto [!DNL JSON] objeto. [!DNL Audience Manager] responde con [!DNL JSON] datos con formato. Las respuestas del servidor pueden contener datos solicitados, un código de estado o ambos.
* **Acceso:** Su [!DNL Audience Manager] El consultor de le proporcionará un ID de cliente y una clave que le permitirán realizar [!DNL API] solicitudes.
* **Documentación y ejemplos de código:** Texto en *cursiva* representa una variable que se proporciona o se pasa al realizar o recibir [!DNL API] datos. Reemplazar *en cursiva* texto con su propio código, parámetros u otra información necesaria.

## Autenticación {#authentication}

El [!DNL Audience Manager] [!DNL REST APIs] admite tres métodos de autenticación.

* [!BADGE Recomendado]{type=positive}[Autenticación de servidor a servidor OAuth](#oauth-adobe-developer) usando [consola de desarrollador de Adobe](https://www.adobe.io/). [!DNL Adobe Developer] es el ecosistema y la comunidad de desarrolladores de Adobe. Incluye [API para todos los productos de Adobe](https://developer.adobe.com/apis/). Esta es la forma recomendada de configurar y utilizar [!DNL Adobe] [!DNL APIs]. Más información sobre [Autenticación de servidor a servidor OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) en la documentación para desarrolladores de Adobe.
* [!BADGE Obsoleto]{type=negative}[Autenticación JWT (cuenta de servicio)](#jwt) usando [consola de desarrollador de Adobe](https://www.adobe.io/). [!DNL Adobe Developer] es el ecosistema y la comunidad de desarrolladores de Adobe. Incluye [API para todos los productos de Adobe](https://developer.adobe.com/apis/).
* [!BADGE Obsoleto]{type=negative}[Autenticación OAuth heredada](#oauth-deprecated). Aunque este método esté obsoleto, los clientes con [!DNL OAuth] Las integraciones de pueden seguir utilizando este método.

>[!IMPORTANT]
>
>Según el método de autenticación, debe ajustar la solicitud [!DNL URLs] en consecuencia. Consulte la [Entornos](#environments) para obtener más información sobre los nombres de host que debe utilizar.

## Autenticación de servidor a servidor OAuth mediante Adobe Developer {#oauth-adobe-developer}

Esta sección cubre cómo recopilar las credenciales necesarias para autenticar las llamadas a la API de Audience Manager, como se describe en el diagrama de flujo siguiente. Puede recopilar la mayoría de las credenciales necesarias en la configuración inicial única. Sin embargo, el token de acceso debe actualizarse cada 24 horas.

![Diagrama de flujo de autenticación del Audience Manager.](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Información general de Adobe Developer {#developer-overview}

[!DNL Adobe Developer] es el ecosistema y la comunidad de desarrolladores de Adobe. Incluye [API para todos los productos de Adobe](https://developer.adobe.com/apis).

Esta es la forma recomendada de configurar y utilizar [!DNL Adobe] [!DNL APIs].

### Requisitos previos {#prerequisites-server-to-server}

Antes de poder configurar [!DNL OAuth Server-to-Server] autenticación, asegúrese de que tiene acceso a la [Consola de Adobe Developer](https://developer.adobe.com/console/home) in [Adobe Developer](https://developer.adobe.com/). Póngase en contacto con el administrador de su organización para solicitudes de acceso.

### Autenticación {#oauth}

Siga los pasos a continuación para configurar [!DNL OAuth Server-to-Server] autenticación mediante [!DNL Adobe Developer]:

1. Inicie sesión en [Consola de Adobe Developer](https://developer.adobe.com/console/home).
1. Siga los pasos de la [Guía de implementación de credenciales de servidor a servidor de OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/).
   * Durante [Paso 2: Añadir una API al proyecto mediante la autenticación de cuenta de servicio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), elija la [!DNL Audience Manager] [!DNL API] opción.
1. Pruebe la conexión estableciendo la primera [!DNL API] llamada de basada en las instrucciones de [Paso 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Para configurar y trabajar con [!DNL Audience Manager] [!DNL REST APIs] de forma automatizada, puede rotar secretos de cliente mediante programación. Consulte [la documentación para desarrolladores](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically) para obtener instrucciones detalladas.

### Añadir la API de Audience Manager a un proyecto {#add-aam-api-to-project}

Ir a [Consola de Adobe Developer](https://www.adobe.com/go/devs_console_ui) e inicie sesión con su Adobe ID. A continuación, siga los pasos descritos en el tutorial sobre [creación de un proyecto vacío](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/) en la documentación de la consola de Adobe Developer.

Una vez creado un nuevo proyecto, seleccione **[!UICONTROL Add API]** en el **[!UICONTROL Project Overview]** pantalla.

>[!TIP]
>
>Si está aprovisionado para varias organizaciones, utilice el selector de organizaciones en la esquina superior derecha de la interfaz para asegurarse de que se encuentra en la organización que necesita.

![Pantalla de la consola del desarrollador con la opción Añadir API resaltada.](/help/using/api/rest-api-main/assets/add-api.png)

El **[!UICONTROL Add an API]** aparece la pantalla. Seleccione el icono de producto de Adobe Experience Cloud y, a continuación, elija **[!UICONTROL Audience Manager API]** antes de seleccionar **[!UICONTROL Next]**.

![Seleccione API de Audience Manager.](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>Seleccione el **[!UICONTROL View docs]** opción para navegar en una ventana separada del explorador para completar el [Documentación de referencia de la API de Audience Manager](https://bank.demdex.com/portal/swagger/index.html#).

### Seleccione el tipo de autenticación de servidor a servidor OAuth {#select-oauth-server-to-server}

A continuación, seleccione el tipo de autenticación para generar tokens de acceso y acceder a la API de Audience Manager.

>[!IMPORTANT]
>
>Seleccione el **[!UICONTROL OAuth Server-to-Server]** ya que este será el único método admitido a partir de ahora. El **[!UICONTROL Service Account (JWT)]** El método está obsoleto. Aunque las integraciones que utilizan el método de autenticación JWT seguirán funcionando hasta el 1 de enero de 2025, Adobe recomienda migrar las integraciones existentes al nuevo método de servidor a servidor OAuth antes de esa fecha.

![Seleccione el método de autenticación OAuth.](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### Selección de los perfiles de producto para la integración {#select-product-profiles}

En el **[!UICONTROL Configure API]** , seleccione los perfiles de producto que desee. La cuenta de servicio de su integración obtendrá acceso a las funciones granulares a través de los perfiles de producto seleccionados aquí.

![Seleccione perfiles de producto para la integración.](/help/using/api/rest-api-main/assets/select-product-profiles.png)

Seleccionar **[!UICONTROL Save configured API]** cuando esté listo.

### Recopilar credenciales {#gather-credentials}

Una vez añadida la API al proyecto, la variable **[!UICONTROL Audience Manager API]** Esta página del proyecto muestra las siguientes credenciales, necesarias en todas las llamadas a las API de Audience Manager:

![Información de integración después de agregar una API en Developer Console.](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}` ([!UICONTROL Client ID])
* `{ORG_ID}` ([!UICONTROL Organization ID])

## Generación de un token de acceso {#generate-access-token}

El siguiente paso es generar una `{ACCESS_TOKEN}` credenciales para utilizarlas en llamadas a la API de Audience Manager. A diferencia de los valores para `{API_KEY}` y `{ORG_ID}`, se debe generar un nuevo token cada 24 horas para seguir utilizando las API de Audience Manager. Seleccionar **[!UICONTROL Generate access token]**, como se muestra a continuación.

![Mostrar cómo generar el token de acceso](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## Prueba de una llamada API {#test-api-call}

Después de obtener el token de portador de autenticación, realice una llamada a la API para probar que ahora puede acceder a las API de Audience Manager.

1. Vaya a [Documentación de referencia del API](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_).
2. Seleccionar **[!UICONTROL Authorize]** y pegue el token de acceso que obtuvo en la [generar token de acceso](#generate-access-token) paso.

   ![Autorizar llamadas API](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. Realice una llamada de GET a `/datasources` Punto final de API para recuperar una lista de todas las fuentes de datos disponibles globalmente, como se indica en la [Documentación de referencia del API](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_). Seleccionar **[!UICONTROL Try it out]**, seguido de **[!UICONTROL Execute]**, como se muestra a continuación.

   ![Realizar llamadas de API](/help/using/api/rest-api-main/assets/perform-api-calls.gif)


>[!BEGINSHADEBOX]

>[!BEGINTABS]

>[!TAB Solicitud de API]

```shell
curl -X 'GET' \
  'https://api.demdex.com/v1/datasources/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer your-access-token'
```


>[!TAB Respuesta de API en caso de utilizar el token de portador correcto]


Al utilizar un token de acceso de trabajo, el extremo de la API devuelve una respuesta 200, junto con un cuerpo de respuesta que incluye todas las fuentes de datos globales a las que su organización tiene acceso.

```json
[
  {
    "pid": 1794,
    "name": "testdatasource1",
    "description": "Test data source",
    "status": "ACTIVE",
    "integrationCode": "test_ds1",
    "dataExportRestrictions": [],
    "updateTime": 1595340792000,
    "crUID": 0,
    "upUID": 15910,
    "linkNamespace": false,
    "type": "GENERAL",
    "subIdType": "CROSS_DEVICE_PERSON",
    "inboundS2S": true,
    "outboundS2S": true,
    "useAudienceManagerVisitorID": false,
    "allowDataSharing": true,
    "masterDataSourceIdProvider": true,
    "uniqueTraitIntegrationCodes": false,
    "uniqueSegmentIntegrationCodes": false,
    "marketingCloudVisitorIdVersion": 0,
    "idType": "CROSS_DEVICE",
    "samplingEndTime": 1596550392825,
    "allowDeviceGraphSharing": false,
    "supportsAuthenticatedProfile": true,
    "deviceGraph": false,
    "authenticatedProfileName": "testdatasource1",
    "deviceGraphName": "",
    "customNamespaceId": 29769,
    "customNamespaceCode": "silviu_ds1",
    "customerProfileDataRetention": 62208000,
    "samplingStartTime": 1595340792825,
    "dataSourceId": 29769,
    "containerIds": [],
    "samplingEnabled": false
  },
  {
    "pid": 1794,
    "name": "AAM Test Company Audiences",
    "description": "Automatically generated trait data source",
    "status": "ACTIVE",
    "integrationCode": "adobe-provided",
    "dataExportRestrictions": [
      "PII"
    ],

    [...]
```

>[!ENDTABS]

>[!ENDSHADEBOX]

## [!BADGE Obsoleto]{type=negative}[!DNL JWT] ([!DNL Service Account]) Autenticación mediante Adobe Developer {#jwt}

+++ Ver información sobre el obsoleto [!DNL JWT] ([!DNL Service Account]) método de obtención de tokens de autenticación.

### Información general de Adobe Developer {#adobeio}

[!DNL Adobe Developer] es el ecosistema y la comunidad de desarrolladores de Adobe. Incluye [API para todos los productos de Adobe](https://www.adobe.io/apis.html).

Esta es la forma recomendada de configurar y utilizar [!DNL Adobe] [!DNL APIs].

### Requisitos previos {#prerequisites}

Antes de poder configurar [!DNL JWT] autenticación, asegúrese de que tiene acceso a la [Consola de Adobe Developer](https://console.adobe.io/) in [Adobe Developer](https://www.adobe.io/). Póngase en contacto con el administrador de su organización para solicitudes de acceso.

### Autenticación {#auth}

Siga los pasos a continuación para configurar [!DNL JWT (Service Account)] autenticación mediante [!DNL Adobe Developer]:

1. Inicie sesión en [Consola de Adobe Developer](https://console.adobe.io/).
1. Siga los pasos de [Conexión de cuenta de servicio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Durante [Paso 2: Añadir una API al proyecto mediante la autenticación de cuenta de servicio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), elija la [!DNL Audience Manager] [!DNL API] opción.
1. Pruebe la conexión estableciendo la primera [!DNL API] llamada de basada en las instrucciones de [Paso 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Para configurar y trabajar con [!DNL Audience Manager] [!DNL REST APIs] de forma automatizada, puede generar las [!DNL JWT] mediante programación. Consulte [Autenticación JWT (cuenta de servicio)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) para obtener instrucciones detalladas.

### Permisos de RBAC de cuenta técnica

Si su cuenta de Audience Manager utiliza [Control de acceso basado en roles](../../features/administration/administration-overview.md), debe crear una cuenta de usuario técnica de Audience Manager y agregarla al grupo RBAC de Audience Manager que realizará las llamadas de API.

Siga los pasos a continuación para crear una cuenta de usuario técnica y agregarla a un grupo RBAC:

1. Crear un `GET` llamada a `https://aam.adobe.io/v1/users/self`. La llamada creará una cuenta de usuario técnica que puede ver en el [!UICONTROL Admin Console], en el [!UICONTROL Users] página.

   ![cuenta técnica](assets/technical-account.png)

1. Inicie sesión en su cuenta de Audience Manager y [agregar la cuenta de usuario técnica](../../features/administration/administration-overview.md#create-group) al grupo de usuarios que realizará las llamadas de API.

+++

## [!BADGE Obsoleto]{type=negative}[!DNL OAuth] Autenticación (obsoleta) {#oauth-deprecated}

+++ Ver información sobre el heredado obsoleto [!DNL OAuth] Método de autenticación para obtener tokens de autenticación.

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] autenticación y renovación de tokens mediante [!DNL OAuth 2.0] está en desuso.
>
> Utilice [Autenticación JWT (cuenta de servicio)](#jwt-service-account-authentication-jwt) en su lugar.

El [!DNL Audience Manager] [!UICONTROL REST API] sigue [!DNL OAuth 2.0] estándares para la autenticación y renovación de tokens. Las secciones siguientes describen cómo autenticarse y comenzar a trabajar con [!DNL API]s.

### Crear un genérico [!DNL API] Usuario {#requirements}

Le recomendamos que cree una cuenta de usuario técnica independiente para trabajar con [!DNL Audience Manager] [!DNL API]s. Es una cuenta genérica que no está vinculada a un usuario específico de su organización ni asociada a él. Este tipo de [!DNL API] La cuenta de usuario de le ayuda a lograr dos cosas:

* Identificar qué servicio llama al [!DNL API] (p. ej., llamadas desde sus aplicaciones que usan nuestro [!DNL API]u otras herramientas que hacen que [!DNL API] solicitudes).
* Proporcionar acceso ininterrumpido al [!DNL API]s. Una cuenta vinculada a una persona específica puede eliminarse cuando abandone la compañía. Esto evitará que trabaje con el disponible [!DNL API] código. Una cuenta genérica que no esté vinculada a un empleado en particular le ayuda a evitar este problema.

Como ejemplo o caso de uso para este tipo de cuenta, supongamos que desea cambiar muchos segmentos a la vez con [Herramientas de administración masiva](../../reference/bulk-management-tools/bulk-management-intro.md). Bueno, para ello, su cuenta de usuario necesita [!DNL API] acceso. En lugar de agregar permisos a un usuario específico, cree un de tipo no específico, [!DNL API] cuenta de usuario que tiene las credenciales, la clave y el secreto adecuados para realizar [!DNL API] llamadas. Esto también resulta útil si desarrolla sus propias aplicaciones que utilizan [!DNL Audience Manager] [!DNL API]s.

Trabaje con su [!DNL Audience Manager] consultor para configurar un genérico, [!DNL API]Cuenta de usuario solo de.

### Flujo de trabajo de autenticación de contraseña {#password-authentication-workflow}

Autenticación de contraseña acceso seguro nuestro [!DNL REST API]. Los pasos siguientes describen el flujo de trabajo para la autenticación de contraseña desde un [!DNL JSON] cliente en el explorador.

>[!TIP]
>
>Cifre los tokens de acceso y actualización si los almacena en una base de datos.

#### Paso 1: Solicitud [!DNL API] Acceso

Póngase en contacto con su administrador de Soluciones para socios. Ellos le proporcionarán una [!DNL API] ID de cliente y secreto. El ID y el secreto le autentican en el [!DNL API].

Nota: Si desea recibir un token de actualización, especifique eso cuando solicite [!DNL API] acceso.

#### Paso 2: Solicitar el token

Pase una solicitud de token con su preferido [!DNL JSON] cliente. Cuando genere la solicitud:

* Utilice un `POST` método al que llamar `https://api.demdex.com/oauth/token`.
* Convierta su ID de cliente y secreto en una cadena codificada en base 64. Separe el ID y el secreto con dos puntos durante el proceso de conversión. Por ejemplo, las credenciales de `testId : testSecret` convertir a `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pase el [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` y `Content-Type: application/x-www-form-urlencoded` . Por ejemplo, el encabezado podría tener este aspecto: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configure el cuerpo de la solicitud de la siguiente manera:
  <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Paso 3: Recibir el token

El [!DNL JSON] La respuesta de contiene su token de acceso. La respuesta debería ser similar a la siguiente:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

El `expires_in` representa el número de segundos hasta que caduca el token de acceso. Se recomienda utilizar tiempos de caducidad cortos para limitar la exposición si el token se expone en algún momento.

### Actualizar token {#refresh-token}

Actualizar tokens renovar [!DNL API] una vez caducado el token original. Si se solicita, la respuesta [!DNL JSON] en el flujo de trabajo de contraseñas incluye un token de actualización. Si no recibe un token de actualización, cree uno nuevo mediante el proceso de autenticación de contraseña.

También puede utilizar un token de actualización para generar un nuevo token antes de que caduque el token de acceso existente.

Si el token de acceso ha caducado, recibirá un `401 Status Code` y el siguiente encabezado en la respuesta:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Los siguientes pasos describen el flujo de trabajo para el uso de un token de actualización con el fin de crear un nuevo token de acceso a partir de un [!DNL JSON] cliente en el explorador.

#### Paso 1: Solicitar el nuevo token

Pase una solicitud de token de actualización con su preferido [!DNL JSON] cliente. Cuando genere la solicitud:

* Utilice un `POST` método al que llamar `https://api.demdex.com/oauth/token`.
* Convierta su ID de cliente y secreto en una cadena codificada en base 64. Separe el ID y el secreto con dos puntos durante el proceso de conversión. Por ejemplo, las credenciales de `testId : testSecret` convertir a `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pasar los encabezados HTTP `Authorization:Basic <base-64 clientID:clientSecret>` y `Content-Type: application/x-www-form-urlencoded`. Por ejemplo, el encabezado podría tener este aspecto: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* En el cuerpo de la solicitud, especifique `grant_type:refresh_token` y pase el token de actualización que recibió en su solicitud de acceso anterior. La solicitud debe tener este aspecto: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Paso 2: Recibir el nuevo token

El [!DNL JSON] La respuesta de contiene su nuevo token de acceso. La respuesta debería ser similar a la siguiente:

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### Código de autorización y autenticación implícita {#authentication-code-implicit}

El [!DNL Audience Manager] [!UICONTROL REST API] admite código de autorización y autenticación implícita. Para utilizar estos métodos de acceso, los usuarios deben iniciar sesión en `https://api.demdex.com/oauth/authorize` para obtener acceso y actualizar tokens.

+++

## Convertir en autenticado [!DNL API] Solicitudes {#authenticated-api-requests}

Requisitos para llamar a [!DNL API] métodos después de recibir un token de autenticación.

Para realizar llamadas contra el disponible [!DNL API] métodos:

* En el `HTTP` encabezado, establecer `Authorization: Bearer <token>`.
* Al utilizar [Autenticación JWT (cuenta de servicio)](#jwt), debe proporcionar el `x-api-key` encabezado, que será el mismo que su `client_id`. Puede obtener su `client_id` desde el [Integración de Adobe Developer](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) página.
* Llame a la función requerida [!DNL API] método.

## Opcional [!DNL API] Parámetros de consulta {#optional-api-query-parameters}

Establezca los parámetros opcionales disponibles para los métodos que devuelven todas las propiedades de un objeto.

Puede utilizar estos parámetros opcionales con [!DNL API] métodos que devuelven *todo* propiedades de un objeto. Establezca estas opciones en la cadena de solicitud al pasar esa consulta al [!DNL API].

| Parámetro | Descripción |
|--- |--- |
| `page` | Devuelve los resultados por número de página. La numeración comienza en 0. |
| `pageSize` | Establece el número de resultados de respuesta que devuelve la solicitud (10 es el valor predeterminado). |
| `sortBy` | Ordena y devuelve los resultados según el especificado [!DNL JSON] propiedad. |
| `descending` | Ordena y devuelve los resultados en orden descendente. `ascending` es el valor predeterminado. |
| `search` | Devuelve los resultados en función de la cadena especificada que desee utilizar como parámetro de búsqueda. Por ejemplo, supongamos que desea buscar resultados para todos los modelos que tienen la palabra &quot;Test&quot; en cualquiera de los campos de valor de ese elemento. La solicitud de ejemplo podría tener este aspecto:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Puede buscar cualquier valor devuelto por un &quot;[!DNL get all]método &quot;. |
| `folderId` | Devuelve todos los ID de [!UICONTROL traits] dentro de la carpeta especificada. No disponible para todos los métodos. |
| `permissions` | Devuelve una lista de segmentos en función del permiso especificado. `READ` es el valor predeterminado. Los permisos incluyen:<ul><li>`READ` : Devuelve y ve información sobre un segmento.</li><li>`WRITE` : uso  `PUT`  para actualizar un segmento.</li><li>`CREATE` : uso  `POST`  para crear un segmento.</li><li>`DELETE` : elimine un segmento. Requiere acceso a los rasgos subyacentes, si los hay. Por ejemplo, necesitará derechos para eliminar los rasgos que pertenecen a un segmento si desea eliminarlo.</li></ul><br>Especifique varios permisos con pares clave-valor independientes. Por ejemplo, para devolver una lista de segmentos con  `READ`  y  `WRITE`  solo permisos, pasar  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Establecido en `true` para devolver sus permisos para el segmento. El valor predeterminado es `false`. |

### Una Nota Sobre Las Opciones De Página

Cuando la información de página *no es* especificado, la solicitud se devuelve sin formato [!DNL JSON] da como resultado una matriz. Si la información de página *es* especificado, la lista devuelta se incluirá dentro de un [!DNL JSON] que contiene información sobre el resultado total y la página actual. La solicitud de muestra que utiliza opciones de página puede tener un aspecto similar al siguiente:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] para solicitudes, entornos de ensayo y producción y versiones.

## Solicitud [!DNL URLs] {#request-urls}

La siguiente tabla enumera la solicitud [!DNL URLs] se usa para pasar [!DNL API] solicitudes, por método.

Según el método de autenticación que utilice, debe ajustar la solicitud [!DNL URLs] según las tablas que figuran a continuación.

### Solicitud [!DNL URLs] para [!DNL JWT] Autenticación {#request-urls-jwt}

| [!DNL API] Métodos | Solicitud [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | Características:  `https://aam.adobe.io/v1/folders/traits /`<br>Segmentos:  `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### Solicitud [!DNL URLs] para [!DNL OAuth] Autenticación (obsoleta) {#request-urls-oauth}

| [!DNL API] Métodos | Solicitud [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | Características:  `https://api.demdex.com/v1/folders/traits /`<br>Segmentos:  `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## Entornos {#environments}

El [!DNL Audience Manager] [!DNL API]proporciona acceso a diferentes entornos de trabajo. Estos entornos le ayudan a probar el código en bases de datos independientes sin afectar a los datos activos y de producción. En la tabla siguiente se enumeran los disponibles [!DNL API] entornos y nombres de host de recursos correspondientes.

Según el método de autenticación que utilice, debe ajustar el entorno [!DNL URLs] de acuerdo con la tabla siguiente.

| Entorno | Nombre de host para [!DNL JWT] authentication | Nombre de host para [!DNL OAuth] authentication |
|---|---|---|
| **Producción** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>El [!DNL Audience Manager] el entorno beta es una versión independiente a menor escala del entorno de producción. Todos los datos que desee probar deben introducirse y recopilarse en este entorno.

## Versiones {#versions}

Nuevas versiones de estos [!DNL API]Las se publican de forma regular. Una nueva versión incrementa el [!DNL API] número de versión. Se hace referencia al número de versión en la solicitud [!DNL URL] as `v<version number>` como se muestra en el siguiente ejemplo:

`https://<host>/v1/...`

## Códigos de respuesta definidos {#response-codes-defined}

`HTTP` códigos de estado y texto de respuesta devueltos por el [!DNL Audience Manager] [!UICONTROL REST API].

| ID de código de respuesta | Texto de respuesta | Definición |
|---|---|---|
| `200` | `OK` | Solicitud procesada correctamente. Devuelve el contenido o los datos esperados si es necesario. |
| `201` | `Created` | Se ha creado el recurso. Devuelve para `PUT` y `POST` solicitudes. |
| `204` | `No Content` | Se ha eliminado el recurso. El cuerpo de la respuesta estará en blanco. |
| `400` | `Bad Request` | El servidor no entendió la solicitud. Por lo general, debido a sintaxis mal formada. Compruebe su solicitud e inténtelo de nuevo. |
| `403` | `Forbidden` | No tiene acceso al recurso. |
| `404` | `Not Found` | No se encontró el recurso para la ruta de acceso especificada. |
| `409` | `Conflict` | No se pudo completar la solicitud debido a un conflicto con el estado del recurso. |
| `500` | `Server Error` | El servidor encontró un error inesperado que le impidió cumplir la solicitud. |

>[!MORELIKETHIS]
>
>* [Autenticación JWT (cuenta de servicio)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [Autenticación de OAuth](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 simplificado](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)
