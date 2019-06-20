---
description: Información sobre requisitos generales, autenticación, parámetros de consulta opcionales, direcciones URL de solicitud y otras referencias.
seo-description: Información sobre requisitos generales, autenticación, parámetros de consulta opcionales, direcciones URL de solicitud y otras referencias.
seo-title: Introducción a las API de REST
solution: Audience Manager
title: Introducción a las API de REST
uuid: af 0 e 527 e -6 eec -449 c -9709-f 90 e 57 cd 188 d
translation-type: tm+mt
source-git-commit: 27800ce003a62733eece0d5de3b94737ed61133a

---


# Getting Started with REST APIs {#getting-started-with-rest-apis}

Información sobre requisitos generales, autenticación, parámetros de consulta opcionales, direcciones URL de solicitud y otras referencias.

<!-- c_rest_api_overview.xml -->

## API Requirements and Recommendations {#api-requirements-recommendations}

Things you must and should do when working with the Audience Manager [!DNL API]s.

<!-- aam-api-requirements.xml -->

Note the following when working with [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) code:

* **Parámetros de solicitud:** Se requieren todos los parámetros de solicitud a menos que se especifique lo contrario.
* **[!DNL JSON]tipo de contenido:** Especifique `content-type: application/json`*y* `accept: application/json` en su código.

* **Solicitudes y respuestas:** Envíe solicitudes como objeto formateado [!DNL JSON] correctamente. [!DNL Audience Manager] responde con [!DNL JSON] datos formateados. Las respuestas del servidor pueden contener los datos solicitados, un código de estado o ambos.

* **Acceso:** [!DNL Audience Manager] Su consultor le proporcionará un ID de cliente y una clave que le permitirán [!DNL API] realizar solicitudes.

* **Documentación y muestras de código:** El texto en *cursiva* representa una variable que usted proporciona o pasa al realizar o recibir [!DNL API] datos. Replace *italicised* text with your own code, parameters, or other required information.

## Recommendations: Create a Generic API User {#requirements}

We recommend you create a separate, technical user account for working with the Audience Manager [!DNL API]s. This is a generic account that is not tied to or associated with a specific user in your organization. This type of [!DNL API] user account helps you accomplish 2 things:

* Identify what service is calling the [!DNL API] (e.g., calls from your apps that use our [!DNL API]s or from other tools that make [!DNL API] requests).
* Provide uninterrupted access to the [!DNL API]s. An account tied to a specific person may be deleted when they leave your company. This will prevent you from working with the available [!DNL API] code. Una cuenta genérica que no está vinculada a un empleado en particular ayuda a evitar este problema.

As an example or use case for this type of account, let&#39;s say you want to change a lot of segments at once with the [Bulk Management Tools](../../reference/bulk-management-tools/bulk-management-intro.md). Well, to do this, your user account needs [!DNL API] access. Rather than add permissions to a specific user, create a non-specific, [!DNL API] user account that has the appropriate credentials, key, and secret to make [!DNL API] calls. This is also useful if you develop your own applications that use the Audience Manager [!DNL API]s.

Work with your Audience Manager consultant to set up a generic, [!DNL API]-only user account.

## OAuth Authentication {#oauth}

The Audience Manager [!UICONTROL REST API] follows [!DNL OAuth 2.0] standards for token authentication and renewal. The sections below describe how to authenticate and start working with the [!DNL API]s.

## Password Authentication Workflow {#password-authentication-workflow}

<!-- oath-authentication.xml -->

Password authentication secure access our [!DNL REST API]. The steps below outline the workflow for password authentication from a [!DNL JSON] client in your browser.

>[!TIP]
>
>Codifique el acceso y actualice tokens si los almacena en una base de datos.

### Paso 1: Solicitar acceso a API

Póngase en contacto con el administrador de soluciones de socio. They will provide you with an [!DNL API] client ID and secret. The ID and secret authenticate you to the [!DNL API].

Note: If you&#39;d like to receive a refresh token, specify that when you request [!DNL API] access.

### Paso 2: Solicitar el token

Pass in a token request with your preferred [!DNL JSON] client. Cuando cree la solicitud:

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* Convierta su ID de cliente y su secreto en una cadena codificada de base 64. Separe el ID y el secreto con dos puntos durante el proceso de conversión. For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the [!DNL HTTP] headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded` . For example, your header could look like this: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configure el cuerpo de la solicitud como se indica a continuación:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

### Paso 3: Recibir el token

[!DNL JSON] La respuesta contiene su autentificador de acceso. La respuesta debería tener este aspecto:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

`expires_in` La clave representa el número de segundos hasta que caduca el autentificador de acceso. Como práctica recomendada, utilice tiempos de caducidad cortos para limitar la exposición si el token siempre se expone.

## Refresh Token {#refresh-token}

Refresh tokens renew [!DNL API] access after the original token expires. If requested, the response [!DNL JSON] in the password workflow includes a refresh token. Si no recibe un token de actualización, cree uno nuevo mediante el proceso de autenticación de contraseña.

También puede utilizar un token de actualización para generar un nuevo token antes de que caduque el autentificador de acceso existente.

If your access token has expired, you receive a `401 Status Code` and the following header in the response:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

The following steps outline the workflow for using a refresh token to create a new access token from a [!DNL JSON] client in your browser.

### Paso 1: Solicitar el nuevo token

Pass in a refresh token request with your preferred [!DNL JSON] client. Cuando cree la solicitud:

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* Convierta su ID de cliente y su secreto en una cadena codificada de base 64. Separe el ID y el secreto con dos puntos durante el proceso de conversión. For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the HTTP headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded`. For example, your header could look like this: <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* In the request body, specify the `grant_type:refresh_token` and pass in the refresh token you received in your previous access request. The request should look like this: <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

### Paso 2: Recibir el nuevo token

[!DNL JSON] La respuesta contiene el nuevo autentificador de acceso. La respuesta debería tener este aspecto:

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

## Authorization Code and Implicit Authentication {#authentication-code-implicit}

The Audience Manager [!UICONTROL REST API] supports authorization code and implicit authentication. To use these access methods, your users need to log in to `https://api.demdex.com/oauth/authorize` to get access and refresh tokens.

>[!MORE_ LIKE_ THIS]
>
>* [Oauth 2.0](https://oauth.net/2/)
>* [Oauth 2 simplificado](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)


## Make Authenticated API Requests {#authenticated-api-requests}

Requirements for calling [!DNL API] methods after you receive an authentication token.

<!-- c_oauth_call_methods.xml -->

To make calls against the available [!DNL API] methods:

* In the `HTTP` header, set `Authorization: Bearer <token>`.
* Call the required [!DNL API] method.

>[!MORE_ LIKE_ THIS]
>
>* [Autenticación oauth](../../api/rest-api-main/aam-api-getting-started.md#oauth)


## Optional API Query Parameters {#optional-api-query-parameters}

Defina los parámetros opcionales disponibles para los métodos que devuelven todas las propiedades de un objeto.

<!-- c_rest_api_optional.xml -->

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API].

| Parámetro | Descripción |
|--- |--- |
| página | Devuelve resultados por número de página. La numeración comienza en 0. |
| Pagesize | Define el número de resultados de respuesta devueltos por la solicitud (10 es predeterminado). |
| Sortby | Sorts and returns results according to the specified [!DNL JSON] property. |
| descendente | Ordena y devuelve resultados en orden descendente. Ascendente es predeterminado. |
| OR | Devuelve resultados basados en la cadena especificada que se desea utilizar como parámetro de búsqueda. Por ejemplo, supongamos que desea encontrar resultados para todos los modelos que tengan la palabra &quot;Test&quot; en cualquiera de los campos de valor de dicho elemento. Your sample request could look like this:   `GET https://api.demdex.com/v1/models/?search=Test`.  Puede buscar cualquier valor devuelto por el método &quot;get all&quot;. |
| Folderid | Devuelve todos los ID de características dentro de la carpeta especificada. No disponible para todos los métodos. |
| permisos | Devuelve una lista de segmentos en función del permiso especificado. READ es predeterminado. Los permisos incluyen:<ul><li>`READ` : Devuelve y visualice información sobre un segmento.</li><li>`WRITE` : Se utiliza `PUT` para actualizar un segmento.</li><li>`CREATE` : Se utiliza `POST` para crear un segmento.</li><li>`DELETE` : Eliminar un segmento. Requiere acceso a características subyacentes, si hay. Por ejemplo, tendrá que disponer de derechos para eliminar las características que pertenecen a un segmento si desea eliminarlo.</li></ul><br>Especifique varios permisos con pares de clave-valor separados. For example, to return a list of segments with  `READ`  and  `WRITE`  permissions only, pass in  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| Includepermissions | (Booleano) Establezca en true para devolver los permisos del segmento. El valor predeterminado es false. |

### Notas sobre las opciones de página

When page information *is not* specified, the request returns plain [!DNL JSON] results in an array. If page information *is* specified, then the returned list is wrapped in a [!DNL JSON] object that contains information about the total result and current page. Su solicitud de ejemplo con opciones de página podría tener un aspecto similar al siguiente:

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## API URL {#api-urls}

[!DNL URLs] para solicitudes, entornos de ensayo y producción y versiones.

<!-- r_rest_urls.xml -->

## Request URLs {#request-urls}

The following table lists the request URLs used to pass in [!DNL API] requests, by method.

| [!DNL API] Métodos | Solicitud [!DNL URL] |
|--- |--- |
| Modelado algorítmico | `https://api.demdex.com/v1/models/` |
| Fuente de datos | `https://api.demdex.com/v1/datasources/` |
| Señales derivadas | `https://api.demdex.com/v1/signals/derived/` |
| Destinos | `https://api.demdex.com/v1/destinations/` |
| Dominios | `https://api.demdex.com/v1/partner-sites/` |
| Carpetas | Traits:  `https://api.demdex.com/v1/folders/traits /`<br>Segments:  `https://api.demdex.com/v1/folders/segments /` |
| Esquema | `https://api.demdex.com/v1/schemas/` |
| Segmentos | `https://api.demdex.com/v1/segments/` |
| Características | `https://api.demdex.com/v1/traits/` |
| Tipos de características | `https://api.demdex.com/v1/customer-trait-types` |
| Taxonomía | `https://api.demdex.com/v1/taxonomies/0/` |

## Environments {#environments}

The [!DNL Audience Manager] [!DNL API]s provide access to different working environments. Estos entornos le ayudan a comprobar el código de bases de datos separadas sin afectar a los datos de producción activos. The following table lists the available [!DNL API] environments and corresponding resource hostnames.

| Entorno | Nombre del host |
|---|---|
| **Producción** | `https://api.demdex.com/...` |
| **Beta** | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>El entorno beta de Audience Manager es una versión independiente y en escala más pequeña del entorno de producción. Todos los datos que desee probar deben ingresarse y recopilarse en este entorno.

## Versiones {#versions}

New versions of these [!DNL API]s are released on a regular schedule. A new release increments the [!DNL API] version number. The version number is referenced in the request URL as `v<version number>` as shown in the following example:

`https://<host>/v1/...`

## Response Codes Defined {#response-codes-defined}

`HTTP` códigos de estado y texto de respuesta devueltos por Audience Manager [!UICONTROL REST API].

<!-- r_api_http_response_codes.xml -->

| ID del código de respuesta | Texto de respuesta | Definición |
|---|---|---|
| 200 | OK | La solicitud se ha procesado correctamente. Devolverá el contenido esperado o los datos, si es necesario. |
| 201 | Creado | Se creó el recurso. Returns for `PUT` and `POST` requests. |
| 204 | Sin contenido | El recurso se ha eliminado. El cuerpo de respuesta estará en blanco. |
| 400 | Solicitud incorrecta | El servidor no comprendió la solicitud. Normalmente, debido a la sintaxis incorrecta. Compruebe su solicitud e inténtelo de nuevo. |
| 403 | Prohibido | No tiene acceso al recurso. |
| 404 | No encontrado | No se encontró el recurso para la ruta especificada. |
| 409 | Conflicto | La solicitud no pudo completarse debido a un conflicto con el estado del recurso. |
| 500 | Error en el servidor | El servidor encontró un error inesperado que impedía que se cumpliera la solicitud. |