---
description: Información sobre requisitos generales, autenticación, parámetros de consulta opcionales, direcciones URL de solicitud y otras referencias.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Introducción a las API de REST
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 622664170f2a76039bcf2333bde43ce9e60b6af2
workflow-type: tm+mt
source-wordcount: '2563'
ht-degree: 1%

---

# Introducción a [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Información sobre requisitos generales, autenticación, parámetros de consulta opcionales, solicitud [!DNL URLs] y otras referencias.

## Requisitos y recomendaciones de API {#api-requirements-recommendations}

Tenga en cuenta lo siguiente al trabajar con el código [API de Audience Manager](https://bank.demdex.com/portal/swagger/index.html#/):

* **Parámetros de solicitud:** todos los parámetros de solicitud son obligatorios a menos que se especifique lo contrario.
* **Encabezados de solicitud**: al usar tokens de [Adobe Developer](https://www.adobe.io/), debe proporcionar el encabezado `x-api-key`. Puede obtener su clave [!DNL API] siguiendo las instrucciones de la página [Integración de cuenta de servicio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* **[!DNL JSON]tipo de contenido:** Especifique `content-type: application/json` *y* `accept: application/json` en su código.
* **Solicitudes y respuestas:** Envíe solicitudes como un objeto [!DNL JSON] correctamente formateado. [!DNL Audience Manager] responde con [!DNL JSON] datos formateados. Las respuestas del servidor pueden contener datos solicitados, un código de estado o ambos.
* **Acceso:** Su asesor de [!DNL Audience Manager] le proporcionará un identificador de cliente y una clave que le permitirán realizar [!DNL API] solicitudes.
* **Ejemplos de documentación y código:** El texto en *cursiva* representa una variable que proporciona o pasa al realizar o recibir datos de [!DNL API]. Reemplace el texto *cursiva* con su propio código, parámetros u otra información necesaria.

## Autenticación {#authentication}

[!DNL Audience Manager] [!DNL REST APIs] admite tres métodos de autenticación.

* [!BADGE Se ha recomendado]{type=positive} [autenticación de servidor a servidor OAuth](#oauth-adobe-developer) mediante [Adobe developer console](https://www.adobe.io/). [!DNL Adobe Developer] es el ecosistema y la comunidad de desarrolladores de Adobe. Incluye [API para todos los productos de Adobe](https://developer.adobe.com/apis/). Esta es la forma recomendada de configurar y usar [!DNL Adobe] [!DNL APIs]. Obtenga más información sobre la [autenticación de servidor a servidor OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) en la documentación para desarrolladores de Adobe.
* [!BADGE Autenticación &#x200B;]{type=negative}JWT (cuenta de servicio) [&#128279;](#jwt)obsoleta mediante [Adobe developer console](https://www.adobe.io/). [!DNL Adobe Developer] es el ecosistema y la comunidad de desarrolladores de Adobe. Incluye [API para todos los productos de Adobe](https://developer.adobe.com/apis/).
* [!BADGE Obsoleto]{type=negative} [Autenticación OAuth heredada](#oauth-deprecated). Mientras este método esté obsoleto, los clientes con integraciones existentes de [!DNL OAuth] pueden seguir usando este método.

>[!IMPORTANT]
>
>Según el método de autenticación, debe ajustar la solicitud [!DNL URLs] en consecuencia. Consulte la sección [Entornos](#environments) para obtener más información sobre los nombres de host que debe usar.

## Autenticación de servidor a servidor OAuth mediante Adobe Developer {#oauth-adobe-developer}

Esta sección cubre cómo recopilar las credenciales necesarias para autenticar las llamadas a la API de Audience Manager, como se describe en el diagrama de flujo siguiente. Puede recopilar la mayoría de las credenciales necesarias en la configuración inicial única. Sin embargo, el token de acceso debe actualizarse cada 24 horas.

![Diagrama del flujo de autenticación de Audience Manager.](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Información general de Adobe Developer {#developer-overview}

[!DNL Adobe Developer] es el ecosistema y la comunidad de desarrolladores de Adobe. Incluye [API para todos los productos de Adobe](https://developer.adobe.com/apis).

Esta es la forma recomendada de configurar y usar [!DNL Adobe] [!DNL APIs].

### Requisitos previos {#prerequisites-server-to-server}

Antes de configurar la autenticación de [!DNL OAuth Server-to-Server], asegúrate de tener acceso a [Adobe Developer Console](https://developer.adobe.com/console/home) en [Adobe Developer](https://developer.adobe.com/). Póngase en contacto con el administrador de su organización para solicitudes de acceso.

### Autenticación {#oauth}

Siga los pasos a continuación para configurar la autenticación de [!DNL OAuth Server-to-Server] mediante [!DNL Adobe Developer]:

1. Inicie sesión en [Adobe Developer Console](https://developer.adobe.com/console/home).
1. Siga los pasos de la [guía de implementación de credenciales de servidor a servidor OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/).
   * Durante [Paso 2: Agregue una API al proyecto mediante la autenticación de cuenta de servicio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), elija la opción [!DNL Audience Manager] [!DNL API].
1. Pruebe la conexión realizando la primera llamada de [!DNL API] según las instrucciones del [Paso 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Para configurar y trabajar con [!DNL Audience Manager] [!DNL REST APIs] de forma automatizada, puede rotar los secretos de cliente mediante programación. Consulte [la documentación para desarrolladores](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically) para obtener instrucciones detalladas.

### Añadir la API de Audience Manager a un proyecto {#add-aam-api-to-project}

Ve a [Adobe Developer Console](https://www.adobe.com/go/devs_console_ui) e inicia sesión con tu Adobe ID. A continuación, siga los pasos descritos en el tutorial sobre [creación de un proyecto vacío](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/) en la documentación de Adobe Developer Console.

Una vez creado un nuevo proyecto, seleccione **[!UICONTROL Add API]** en la pantalla **[!UICONTROL Project Overview]**.

>[!TIP]
>
>Si está aprovisionado para varias organizaciones, utilice el selector de organizaciones en la esquina superior derecha de la interfaz para asegurarse de que se encuentra en la organización que necesita.

![Pantalla de Developer Console con la opción Agregar API resaltada.](/help/using/api/rest-api-main/assets/add-api.png)

Aparecerá la pantalla **[!UICONTROL Add an API]**. Seleccione el icono de producto de Adobe Experience Cloud y, a continuación, elija **[!UICONTROL Audience Manager API]** antes de seleccionar **[!UICONTROL Next]**.

![Seleccionar API de Audience Manager.](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>Seleccione la opción **[!UICONTROL View docs]** para navegar en una ventana separada del explorador a la [documentación de referencia de la API de Audience Manager](https://bank.demdex.com/portal/swagger/index.html#) completa.

### Seleccione el tipo de autenticación de servidor a servidor OAuth {#select-oauth-server-to-server}

A continuación, seleccione el tipo de autenticación para generar tokens de acceso y acceder a la API de Audience Manager.

>[!IMPORTANT]
>
>Seleccione el método **[!UICONTROL OAuth Server-to-Server]**, ya que este será el único método admitido a partir de ahora. El método **[!UICONTROL Service Account (JWT)]** está obsoleto. Aunque las integraciones que utilizan el método de autenticación JWT seguirán funcionando hasta el 1 de enero de 2025, Adobe recomienda migrar las integraciones existentes al nuevo método de servidor a servidor OAuth antes de esa fecha.

![Seleccionar método de autenticación OAuth.](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### Selección de los perfiles de producto para la integración {#select-product-profiles}

En la pantalla **[!UICONTROL Configure API]**, seleccione los perfiles de producto que desee. La cuenta de servicio de su integración obtendrá acceso a las funciones granulares a través de los perfiles de producto seleccionados aquí.

![Seleccione perfiles de producto para su integración.](/help/using/api/rest-api-main/assets/select-product-profiles.png)

Seleccione **[!UICONTROL Save configured API]** cuando esté listo.

### Recopilar credenciales {#gather-credentials}

Una vez que la API se ha agregado al proyecto, la página **[!UICONTROL Audience Manager API]** del proyecto muestra las siguientes credenciales que son necesarias en todas las llamadas a las API de Audience Manager:

![Información de integración después de agregar una API en Developer Console.](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}` ([!UICONTROL Client ID])
* `{ORG_ID}` ([!UICONTROL Organization ID])

## Generación de un token de acceso {#generate-access-token}

El siguiente paso es generar una credencial `{ACCESS_TOKEN}` para usarla en llamadas a la API de Audience Manager. A diferencia de los valores de `{API_KEY}` y `{ORG_ID}`, se debe generar un nuevo token cada 24 horas para seguir usando las API de Audience Manager. Seleccione **[!UICONTROL Generate access token]**, como se muestra a continuación.

![Mostrar cómo generar token de acceso](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## Prueba de una llamada API {#test-api-call}

Después de obtener el token de portador de autenticación, realice una llamada a la API para probar que ahora puede acceder a las API de Audience Manager.

1. Vaya a la [documentación de referencia de API](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_).
2. Seleccione **[!UICONTROL Authorize]** y pegue el token de acceso que obtuvo en el paso [generar token de acceso](#generate-access-token).

   ![Autorizar llamadas API](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. Realice una llamada de GET al extremo de API `/datasources` para recuperar una lista de todos los orígenes de datos disponibles globalmente, tal como se indica en la [documentación de referencia de API](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_). Seleccione **[!UICONTROL Try it out]**, seguido de **[!UICONTROL Execute]**, como se muestra a continuación.

   ![Realizar llamadas API](/help/using/api/rest-api-main/assets/perform-api-calls.gif)


>[!BEGINSHADEBOX]

>[!BEGINTABS]

>[!TAB Solicitud de API]

```shell
curl -X 'GET' \
  'https://api.demdex.com/v1/datasources/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer your-access-token'
```


>[!TAB Respuesta API en caso de usar el token portador correcto]


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

## Autenticación [!BADGE obsoleta]{type=negative} [!DNL JWT] ([!DNL Service Account]) mediante Adobe Developer {#jwt}

+++ Vea información sobre el método obsoleto [!DNL JWT] ([!DNL Service Account]) de obtención de tokens de autenticación.

### Información general de Adobe Developer {#adobeio}

[!DNL Adobe Developer] es el ecosistema y la comunidad de desarrolladores de Adobe. Incluye [API para todos los productos de Adobe](https://www.adobe.io/apis.html).

Esta es la forma recomendada de configurar y usar [!DNL Adobe] [!DNL APIs].

### Requisitos previos {#prerequisites}

Antes de configurar la autenticación de [!DNL JWT], asegúrate de tener acceso a [Adobe Developer Console](https://console.adobe.io/) en [Adobe Developer](https://www.adobe.io/). Póngase en contacto con el administrador de su organización para solicitudes de acceso.

### Autenticación {#auth}

Siga los pasos a continuación para configurar la autenticación de [!DNL JWT (Service Account)] mediante [!DNL Adobe Developer]:

1. Inicie sesión en [Adobe Developer Console](https://console.adobe.io/).
1. Siga los pasos de [Conexión de cuenta de servicio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Durante [Paso 2: Agregue una API al proyecto mediante la autenticación de cuenta de servicio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), elija la opción [!DNL Audience Manager] [!DNL API].
1. Pruebe la conexión realizando la primera llamada de [!DNL API] según las instrucciones del [Paso 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Para configurar y trabajar con [!DNL Audience Manager] [!DNL REST APIs] de manera automatizada, puede generar [!DNL JWT] mediante programación. Consulte [Autenticación JWT (cuenta de servicio)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) para obtener instrucciones detalladas.

### Permisos de RBAC de cuenta técnica

Si su cuenta de Audience Manager usa [Control de acceso basado en roles](../../features/administration/administration-overview.md), debe crear una cuenta de usuario técnico de Audience Manager y agregarla al grupo RBAC de Audience Manager que realizará las llamadas de API.

Siga los pasos a continuación para crear una cuenta de usuario técnica y agregarla a un grupo RBAC:

1. Realizar una llamada de `GET` a `https://aam.adobe.io/v1/users/self`. La llamada creará una cuenta de usuario técnica que podrá ver en [!UICONTROL Admin Console], en la página [!UICONTROL Users].

   ![cuenta técnica](assets/technical-account.png)

1. Inicie sesión en su cuenta de Audience Manager y [agregue la cuenta de usuario técnica](../../features/administration/administration-overview.md#create-group) al grupo de usuarios que realizará las llamadas de API.

+++

## Autenticación [!BADGE Obsoleta]{type=negative} [!DNL OAuth] (Obsoleta) {#oauth-deprecated}

+++ Vea información sobre el método de autenticación [!DNL OAuth] heredado obsoleto para obtener tokens de autenticación.

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] La autenticación y renovación de tokens mediante [!DNL OAuth 2.0] ya no se utiliza.
>
> En su lugar, use la autenticación [JWT (cuenta de servicio)](#jwt-service-account-authentication-jwt).

[!DNL Audience Manager] [!UICONTROL REST API] sigue [!DNL OAuth 2.0] estándares para la autenticación y renovación de tokens. Las secciones siguientes describen cómo autenticarse y comenzar a trabajar con [!DNL API].

### Crear un usuario [!DNL API] genérico {#requirements}

Le recomendamos que cree una cuenta de usuario técnica independiente para trabajar con [!DNL Audience Manager] [!DNL API]s. Se trata de una cuenta genérica que no está vinculada a un usuario específico de su organización ni asociada a él. Este tipo de cuenta de usuario [!DNL API] le ayuda a lograr dos cosas:

* Identifique qué servicio está llamando a [!DNL API] (por ejemplo, llamadas de sus aplicaciones que usan nuestros [!DNL API]s o de otras herramientas que realizan [!DNL API] solicitudes).
* Proporcione acceso ininterrumpido a [!DNL API]. Una cuenta vinculada a una persona específica puede eliminarse cuando abandone la compañía. Esto evitará que trabaje con el código [!DNL API] disponible. Una cuenta genérica que no esté vinculada a un empleado en particular le ayuda a evitar este problema.

Como ejemplo o caso de uso para este tipo de cuenta, supongamos que desea cambiar muchos segmentos a la vez con las [herramientas de administración masiva](../../reference/bulk-management-tools/bulk-management-intro.md). Para ello, su cuenta de usuario necesita el acceso de [!DNL API]. En lugar de agregar permisos a un usuario específico, cree una cuenta de usuario [!DNL API] no específica que tenga las credenciales, la clave y el secreto adecuados para realizar llamadas a [!DNL API]. Esto también resulta útil si desarrolla sus propias aplicaciones que utilizan [!DNL Audience Manager] [!DNL API]s.

Póngase en contacto con el consultor de [!DNL Audience Manager] para configurar una cuenta de usuario genérica de solo [!DNL API].

### Flujo de trabajo de autenticación de contraseña {#password-authentication-workflow}

Autenticación de contraseña: acceso seguro a [!DNL REST API]. Los pasos siguientes describen el flujo de trabajo para la autenticación mediante contraseña desde un cliente de [!DNL JSON] en su explorador.

>[!TIP]
>
>Cifre los tokens de acceso y actualización si los almacena en una base de datos.

#### Paso 1: Solicitar acceso de [!DNL API]

Póngase en contacto con su administrador de Soluciones para socios. Proporcionarán un ID de cliente [!DNL API] y un secreto. El identificador y secreto le autentican en [!DNL API].

Nota: Si desea recibir un token de actualización, especifíquelo cuando solicite acceso a [!DNL API].

#### Paso 2: Solicitar el token

Pase una solicitud de token con su cliente [!DNL JSON] preferido. Cuando genere la solicitud:

* Use un método `POST` para llamar a `https://api.demdex.com/oauth/token`.
* Convierta su ID de cliente y secreto en una cadena codificada en base 64. Separe el ID y el secreto con dos puntos durante el proceso de conversión. Por ejemplo, las credenciales `testId : testSecret` se convierten en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pasar [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` y `Content-Type: application/x-www-form-urlencoded` Por ejemplo, el encabezado podría tener el aspecto siguiente: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configure el cuerpo de la solicitud de la siguiente manera:
  <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Paso 3: Recibir el token

La respuesta [!DNL JSON] contiene su token de acceso. La respuesta debería ser similar a la siguiente:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

La clave `expires_in` representa el número de segundos hasta que caduca el token de acceso. Se recomienda utilizar tiempos de caducidad cortos para limitar la exposición si el token se expone en algún momento.

### Actualizar token {#refresh-token}

Actualizar tokens renovar el acceso de [!DNL API] después de que caduque el token original. Si se solicita, la respuesta [!DNL JSON] en el flujo de trabajo de contraseñas incluye un token de actualización. Si no recibe un token de actualización, cree uno nuevo mediante el proceso de autenticación de contraseña.

También puede utilizar un token de actualización para generar un nuevo token antes de que caduque el token de acceso existente.

Si su token de acceso ha caducado, recibirá un `401 Status Code` y el siguiente encabezado en la respuesta:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Los siguientes pasos describen el flujo de trabajo para usar un token de actualización con el fin de crear un nuevo token de acceso a partir de un cliente [!DNL JSON] en el explorador.

#### Paso 1: Solicitar el nuevo token

Pase una solicitud de token de actualización con su cliente [!DNL JSON] preferido. Cuando genere la solicitud:

* Use un método `POST` para llamar a `https://api.demdex.com/oauth/token`.
* Convierta su ID de cliente y secreto en una cadena codificada en base 64. Separe el ID y el secreto con dos puntos durante el proceso de conversión. Por ejemplo, las credenciales `testId : testSecret` se convierten en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pase los encabezados HTTP `Authorization:Basic <base-64 clientID:clientSecret>` y `Content-Type: application/x-www-form-urlencoded`. Por ejemplo, el encabezado podría tener el aspecto siguiente: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* En el cuerpo de la solicitud, especifique `grant_type:refresh_token` y pase el token de actualización que recibió en su solicitud de acceso anterior. La solicitud debe tener este aspecto: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Paso 2: Recibir el nuevo token

La respuesta [!DNL JSON] contiene su nuevo token de acceso. La respuesta debería ser similar a la siguiente:

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

[!DNL Audience Manager] [!UICONTROL REST API] admite código de autorización y autenticación implícita. Para usar estos métodos de acceso, los usuarios deben iniciar sesión en `https://api.demdex.com/oauth/authorize` para obtener acceso y actualizar los tokens.

+++

## Hacer solicitudes autenticadas de [!DNL API] {#authenticated-api-requests}

Requisitos para llamar a los métodos [!DNL API] después de recibir un token de autenticación.

Para realizar llamadas contra los métodos [!DNL API] disponibles:

* En el encabezado `HTTP`, establezca `Authorization: Bearer <token>`.
* Al usar la autenticación [JWT (cuenta de servicio)](#jwt), debe proporcionar el encabezado `x-api-key`, que será el mismo que `client_id`. Puede obtener su `client_id` desde la página [Integración de Adobe Developer](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* Llame al método [!DNL API] requerido.

## Parámetros de consulta [!DNL API] opcionales {#optional-api-query-parameters}

Establezca los parámetros opcionales disponibles para los métodos que devuelven todas las propiedades de un objeto.

Puede utilizar estos parámetros opcionales con [!DNL API] métodos que devuelven *todas* las propiedades de un objeto. Establezca estas opciones en la cadena de solicitud al pasar esa consulta al [!DNL API].

| Parámetro | Descripción |
|--- |--- |
| `page` | Devuelve los resultados por número de página. La numeración comienza en 0. |
| `pageSize` | Establece el número de resultados de respuesta que devuelve la solicitud (10 es el valor predeterminado). |
| `sortBy` | Ordena y devuelve los resultados según la propiedad [!DNL JSON] especificada. |
| `descending` | Ordena y devuelve los resultados en orden descendente. `ascending` es el valor predeterminado. |
| `search` | Devuelve los resultados en función de la cadena especificada que desee utilizar como parámetro de búsqueda. Por ejemplo, supongamos que desea buscar resultados para todos los modelos que tienen la palabra &quot;Test&quot; en cualquiera de los campos de valor de ese elemento. La solicitud de ejemplo podría tener este aspecto:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Puede buscar cualquier valor devuelto por un método &quot;[!DNL get all]&quot;. |
| `folderId` | Devuelve todos los identificadores de [!UICONTROL traits] dentro de la carpeta especificada. No disponible para todos los métodos. |
| `permissions` | Devuelve una lista de segmentos en función del permiso especificado. `READ` es el valor predeterminado. Los permisos incluyen:<ul><li>`READ` : devolver y ver información sobre un segmento.</li><li>`WRITE` : usar `PUT` para actualizar un segmento.</li><li>`CREATE` : usar `POST` para crear un segmento.</li><li>`DELETE` : Eliminar un segmento. Requiere acceso a los rasgos subyacentes, si los hay. Por ejemplo, necesitará derechos para eliminar los rasgos que pertenecen a un segmento si desea eliminarlo.</li></ul><br>Especifique varios permisos con pares clave-valor independientes. Por ejemplo, para devolver una lista de segmentos con `READ` y `WRITE` permisos solamente, pase `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Configúrelo en `true` para devolver sus permisos para el segmento. El valor predeterminado es `false`. |

{style="table-layout:auto"}

### Una Nota Sobre Las Opciones De Página

Si no se especifica la información de página **, la solicitud devolverá [!DNL JSON] resultados sin formato en una matriz. Si se especifica la información de página *is*, la lista devuelta se incluirá en un objeto [!DNL JSON] que contiene información sobre el resultado total y la página actual. La solicitud de muestra que utiliza opciones de página puede tener un aspecto similar al siguiente:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] para solicitudes, entornos de ensayo y producción y versiones.

## Solicitud [!DNL URLs] {#request-urls}

En la tabla siguiente se enumera la solicitud [!DNL URLs] utilizada para pasar [!DNL API] solicitudes, por método.

Según el método de autenticación que utilice, debe ajustar la solicitud [!DNL URLs] según las tablas siguientes.

### Solicite [!DNL URLs] la autenticación [!BADGE recomendada]{type=positive} de servidor a servidor OAuth y la autenticación [!BADGE obsoleta]{type=negative} [!DNL JWT] a través de Adobe Developer {#request-urls-jwt}

| [!DNL API] métodos | Solicitud [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | Características: `https://aam.adobe.io/v1/folders/traits /`<br>Segmentos: `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

{style="table-layout:auto"}

### Solicitud [!DNL URLs] para la autenticación [!BADGE obsoleta]{type=negative} heredada [!DNL OAuth] {#request-urls-oauth}

| [!DNL API] métodos | Solicitud [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | Características: `https://api.demdex.com/v1/folders/traits /`<br>Segmentos: `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

{style="table-layout:auto"}

## Entornos {#environments}

Los [!DNL Audience Manager] [!DNL API] proporcionan acceso a diferentes entornos de trabajo. Estos entornos le ayudan a probar el código en bases de datos independientes sin afectar a los datos activos y de producción. En la tabla siguiente se enumeran los entornos [!DNL API] disponibles y los nombres de host de recursos correspondientes.

Según el método de autenticación que utilice, debe ajustar su entorno [!DNL URLs] según la tabla siguiente.

| Entorno | Nombre de host para la autenticación [!DNL JWT] | Nombre de host para la autenticación [!DNL OAuth] |
|---|---|---|
| **Producción** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>El entorno beta [!DNL Audience Manager] es una versión independiente a menor escala del entorno de producción. Todos los datos que desee probar deben introducirse y recopilarse en este entorno.

## Versiones {#versions}

Las nuevas versiones de estos(as) [!DNL API] se publican de manera regular. Una nueva versión incrementa el número de versión [!DNL API]. Se hace referencia al número de versión en la solicitud [!DNL URL] como `v<version number>`, como se muestra en el siguiente ejemplo:

`https://<host>/v1/...`

## Códigos de respuesta definidos {#response-codes-defined}

`HTTP` códigos de estado y texto de respuesta devuelto por [!DNL Audience Manager] [!UICONTROL REST API].

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
>* [Autenticación OAuth](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 simplificado](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)
