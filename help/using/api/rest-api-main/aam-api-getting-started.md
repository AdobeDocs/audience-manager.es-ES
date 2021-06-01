---
description: Información sobre requisitos generales, autenticación, parámetros de consulta opcionales, direcciones URL de solicitud y otras referencias.
seo-description: Información sobre requisitos generales, autenticación, parámetros de consulta opcionales, direcciones URL de solicitud y otras referencias.
seo-title: Introducción a las API de REST
solution: Audience Manager
title: Introducción a las API de REST
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1861'
ht-degree: 4%

---

# Introducción a [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Información sobre requisitos generales, autenticación, parámetros de consulta opcionales, solicitud [!DNL URLs] y otras referencias.

<!-- c_rest_api_overview.xml -->

## Requisitos y recomendaciones de API {#api-requirements-recommendations}

Cosas que debe y debe hacer al trabajar con [!DNL Audience Manager] [!DNL API]s.

<!-- aam-api-requirements.xml -->

Tenga en cuenta lo siguiente al trabajar con código [API de Audience Manager](https://bank.demdex.com/portal/swagger/index.html#/):

* **Parámetros de solicitud:** todos los parámetros de solicitud son obligatorios a menos que se especifique lo contrario.
* **Encabezados** de solicitud: al utilizar  [Adobe I/](https://www.adobe.io/) Otokens, debe proporcionar el  `x-api-key` encabezado. Puede obtener la clave [!DNL API] siguiendo las instrucciones de la página [Service Account Integration](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* **[!DNL JSON]tipo de contenido:** especifique  `content-type: application/json`  **  `accept: application/json` y en su código.
* **Solicitudes y respuestas:** envíe solicitudes como  [!DNL JSON] objeto con el formato correcto. [!DNL Audience Manager] responde con datos  [!DNL JSON] formateados. Las respuestas del servidor pueden contener datos solicitados, un código de estado o ambos.
* **Acceso:** el  [!DNL Audience Manager] consultor le proporcionará un ID de cliente y una clave que le permitirán realizar  [!DNL API] solicitudes.
* **Ejemplos de documentación y código:** el texto en  ** cursiva representa una variable que se proporciona o pasa al crear o recibir  [!DNL API] datos. Reemplace el texto *cursiva* con su propio código, parámetros u otra información requerida.

## Autenticación {#authentication}

El [!DNL Audience Manager] [!DNL REST APIs] admite dos métodos de autenticación.

* [Autenticación de JWT (cuenta de servicio) ](#jwt) mediante  [Adobe I/O](https://www.adobe.io/). [!DNL Adobe I/O] es el ecosistema y la comunidad de desarrolladores de Adobe. Incluye las [herramientas para desarrolladores de Adobe I/O y las API](https://www.adobe.io/apis/experienceplatform.html) y [API para todos los productos de Adobe](https://www.adobe.io/apis.html). Esta es la forma recomendada de configurar y utilizar [!DNL Adobe] [!DNL APIs].
* [Autenticación OAuth (obsoleta)](#oauth). Aunque este método está obsoleto, los clientes con integraciones [!DNL OAuth] existentes pueden seguir usando este método.

>[!IMPORTANT]
>
>Según el método de autenticación, debe ajustar la solicitud [!DNL URLs] en consecuencia. Consulte la sección [Environments](#environments) para obtener más información sobre los nombres de host que debe utilizar.

## [!DNL JWT] ([!DNL Service Account]) Autenticación mediante Adobe I/O {#jwt}

### Información general sobre Adobes I/O {#adobeio}

[!DNL Adobe I/O] es el ecosistema y la comunidad de desarrolladores de Adobe. Incluye las [herramientas para desarrolladores de Adobe I/O y las API](https://www.adobe.io/apis/experienceplatform.html) y [API para todos los productos de Adobe](https://www.adobe.io/apis.html).

Esta es la forma recomendada de configurar y utilizar [!DNL Adobe] [!DNL APIs].

### Requisitos previos {#prerequisites}

Antes de configurar la autenticación [!DNL JWT], asegúrese de tener acceso a la [Consola del desarrollador de Adobe](https://console.adobe.io/) en [Adobe I/O](https://www.adobe.io/). Póngase en contacto con el administrador de su organización para solicitar acceso.

### Autenticación {#auth}

Siga los pasos a continuación para configurar la autenticación [!DNL JWT (Service Account)] mediante [!DNL Adobe I/O]:

1. Inicie sesión en [Adobe Developer Console](https://console.adobe.io/).
1. Siga los pasos de [Conexión de cuenta de servicio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Durante [Paso 2: Añada una API al proyecto mediante autenticación de cuenta de servicio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), elija la opción [!DNL Audience Manager] [!DNL API] .
1. Pruebe la conexión realizando la primera llamada [!DNL API] en función de las instrucciones del [Paso 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Para configurar y trabajar con [!DNL Audience Manager] [!DNL REST APIs] de forma automatizada, puede generar el [!DNL JWT] mediante programación. Consulte [Autenticación JWT (cuenta de servicio)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) para obtener instrucciones detalladas.

## [!DNL OAuth] Autenticación (obsoleto) {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] la autenticación y la renovación de tokens mediante ahora  [!DNL OAuth 2.0] están en desuso.
>
> En su lugar, utilice [Autenticación JWT (cuenta de servicio)](#jwt-service-account-authentication-jwt).

El [!DNL Audience Manager] [!UICONTROL REST API] sigue los [!DNL OAuth 2.0] estándares para la autenticación y renovación de tokens. Las secciones siguientes describen cómo autenticarse y comenzar a trabajar con [!DNL API]s.

### Crear un usuario [!DNL API] genérico {#requirements}

Le recomendamos que cree una cuenta de usuario técnica independiente para trabajar con [!DNL Audience Manager] [!DNL API]s. Se trata de una cuenta genérica que no está vinculada a un usuario específico de su organización ni asociada a él. Este tipo de cuenta de usuario [!DNL API] le ayuda a realizar dos cosas:

* Identifique qué servicio llama a [!DNL API] (p. ej., llamadas de sus aplicaciones que usan nuestros [!DNL API]s o de otras herramientas que realizan [!DNL API] solicitudes).
* Proporcione acceso ininterrumpido a [!DNL API]s. Una cuenta vinculada a una persona específica puede ser eliminada cuando abandone la empresa. Esto impedirá que trabaje con el código [!DNL API] disponible. Una cuenta genérica que no está vinculada a un empleado en particular le ayuda a evitar este problema.

Como ejemplo o caso de uso para este tipo de cuenta, supongamos que desea cambiar muchos segmentos a la vez con las [herramientas de administración masiva](../../reference/bulk-management-tools/bulk-management-intro.md). Bueno, para ello, su cuenta de usuario necesita [!DNL API] acceso. En lugar de agregar permisos a un usuario específico, cree una cuenta de usuario [!DNL API] no específica que tenga las credenciales, la clave y el secreto adecuados para realizar llamadas [!DNL API]. Esto también resulta útil si desarrolla sus propias aplicaciones que utilizan [!DNL Audience Manager] [!DNL API]s.

Póngase en contacto con su consultor de [!DNL Audience Manager] para configurar una cuenta de usuario genérica de solo [!DNL API].

### Flujo de trabajo de autenticación de contraseña {#password-authentication-workflow}

Autenticación de contraseña acceso seguro a nuestro [!DNL REST API]. Los pasos siguientes describen el flujo de trabajo para la autenticación de contraseña de un cliente [!DNL JSON] en su explorador.

>[!TIP]
>
>Codifique el acceso y actualice los tokens si los almacena en una base de datos.

#### Paso 1: Solicitar acceso [!DNL API]

Póngase en contacto con el administrador de soluciones de socios. Le proporcionarán un [!DNL API] ID de cliente y un secreto. El ID y el secreto le autentican en [!DNL API].

Nota: Si desea recibir un token de actualización, especifíquelo cuando solicite el acceso [!DNL API].

#### Paso 2: Solicitar el token

Pase una solicitud de token con su cliente [!DNL JSON] preferido. Al crear la solicitud:

* Utilice un método `POST` para llamar a `https://api.demdex.com/oauth/token`.
* Convierta el ID de cliente y el secreto en una cadena codificada base-64. Separe el ID y el secreto con dos puntos durante el proceso de conversión. Por ejemplo, las credenciales `testId : testSecret` se convierten en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pasa [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` y `Content-Type: application/x-www-form-urlencoded` . Por ejemplo, el encabezado podría tener este aspecto: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configure el cuerpo de la solicitud de la siguiente manera:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Paso 3: Recibir el token

La respuesta [!DNL JSON] contiene su token de acceso. La respuesta debería tener este aspecto:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

La clave `expires_in` representa el número de segundos hasta que caduca el token de acceso. Se recomienda utilizar tiempos de caducidad cortos para limitar la exposición si el token se expone alguna vez.

### Actualizar token {#refresh-token}

Actualice los tokens para renovar el acceso [!DNL API] después de que caduque el token original. Si se solicita, la respuesta [!DNL JSON] en el flujo de trabajo de la contraseña incluye un token de actualización. Si no recibe un token de actualización, cree uno nuevo mediante el proceso de autenticación de contraseña.

También puede utilizar un token de actualización para generar un nuevo token antes de que caduque el token de acceso existente.

Si el token de acceso ha caducado, recibirá un `401 Status Code` y el siguiente encabezado en la respuesta:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Los siguientes pasos describen el flujo de trabajo para utilizar un token de actualización para crear un nuevo token de acceso desde un cliente [!DNL JSON] en el explorador.

#### Paso 1: Solicitar el nuevo token

Pase una solicitud de token de actualización con su cliente [!DNL JSON] preferido. Al crear la solicitud:

* Utilice un método `POST` para llamar a `https://api.demdex.com/oauth/token`.
* Convierta el ID de cliente y el secreto en una cadena codificada base-64. Separe el ID y el secreto con dos puntos durante el proceso de conversión. Por ejemplo, las credenciales `testId : testSecret` se convierten en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pasa los encabezados HTTP `Authorization:Basic <base-64 clientID:clientSecret>` y `Content-Type: application/x-www-form-urlencoded`. Por ejemplo, el encabezado podría tener este aspecto: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* En el cuerpo de la solicitud, especifique `grant_type:refresh_token` y pase el token de actualización que recibió en su solicitud de acceso anterior. La solicitud debe tener este aspecto: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Paso 2: Recibir el nuevo token

La respuesta [!DNL JSON] contiene el nuevo token de acceso. La respuesta debería tener este aspecto:

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

El [!DNL Audience Manager] [!UICONTROL REST API] admite código de autorización y autenticación implícita. Para utilizar estos métodos de acceso, los usuarios deben iniciar sesión en `https://api.demdex.com/oauth/authorize` para obtener acceso y actualizar los tokens.

## Realizar [!DNL API] solicitudes autenticadas {#authenticated-api-requests}

Requisitos para llamar a los métodos [!DNL API] después de recibir un token de autenticación.

Para realizar llamadas con los métodos [!DNL API] disponibles:

* En el encabezado `HTTP`, establezca `Authorization: Bearer <token>`.
* Al utilizar [JWT (Service Account) Authentication](#jwt), debe proporcionar el encabezado `x-api-key`, que será el mismo que su `client_id`. Puede obtener su `client_id` desde la página [Integración de Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* Llame al método [!DNL API] requerido.

## Parámetros de consulta [!DNL API] opcionales {#optional-api-query-parameters}

Establezca los parámetros opcionales disponibles para los métodos que devuelven todas las propiedades de un objeto.

Puede utilizar estos parámetros opcionales con métodos [!DNL API] que devuelven *todas* propiedades para un objeto. Establezca estas opciones en la cadena de solicitud al pasar esa consulta a [!DNL API].

| Parámetro | Descripción |
|--- |--- |
| `page` | Devuelve los resultados por número de página. La numeración comienza en 0. |
| `pageSize` | Define el número de resultados de respuesta que devuelve la solicitud (10 es el valor predeterminado). |
| `sortBy` | Ordena y devuelve los resultados según la propiedad [!DNL JSON] especificada. |
| `descending` | Ordena y devuelve los resultados en orden descendente. `ascending` es el valor predeterminado. |
| `search` | Devuelve los resultados en función de la cadena especificada que desee utilizar como parámetro de búsqueda. Por ejemplo, supongamos que desea encontrar resultados para todos los modelos que tienen la palabra &quot;Prueba&quot; en cualquiera de los campos de valor para ese elemento. Su solicitud de ejemplo podría tener este aspecto:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Puede buscar cualquier valor devuelto mediante el método &quot;[!DNL get all]&quot;. |
| `folderId` | Devuelve todos los ID de [!UICONTROL traits] dentro de la carpeta especificada. No está disponible para todos los métodos. |
| `permissions` | Devuelve una lista de segmentos en función del permiso especificado. `READ` es el valor predeterminado. Los permisos incluyen:<ul><li>`READ` : Devolver y ver información sobre un segmento.</li><li>`WRITE` : Utilice   `PUT`  para actualizar un segmento.</li><li>`CREATE` : Utilice   `POST`  para crear un segmento.</li><li>`DELETE` : Eliminar un segmento. Requiere acceso a los rasgos subyacentes, si los hay. Por ejemplo, necesitará derechos para eliminar las características que pertenecen a un segmento si desea eliminarlas.</li></ul><br>Especifique varios permisos con pares de clave-valor independientes. Por ejemplo, para devolver una lista de segmentos con permisos de `READ` y `WRITE` , pase `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Configúrelo en `true` para devolver sus permisos para el segmento. El valor predeterminado es `false`. |

### Una Nota Sobre Las Opciones De Página

Cuando la información de la página *no se especifica*, la solicitud devuelve [!DNL JSON] sin formato y resulta en una matriz. Si se especifica la información de la página *es*, la lista devuelta se ajusta en un objeto [!DNL JSON] que contiene información sobre el resultado total y la página actual. Su solicitud de ejemplo con opciones de página podría tener un aspecto similar al siguiente:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] para solicitudes, entornos de ensayo y producción y versiones.

## Solicitud [!DNL URLs] {#request-urls}

La siguiente tabla enumera la solicitud [!DNL URLs] utilizada para pasar las solicitudes [!DNL API], por método.

Según el método de autenticación que utilice, debe ajustar la solicitud [!DNL URLs] según las tablas siguientes.

### Solicitar [!DNL URLs] autenticación [!DNL JWT] {#request-urls-jwt}

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

### Solicitar [!DNL URLs] autenticación [!DNL OAuth] (obsoleto) {#request-urls-oauth}

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

Los [!DNL Audience Manager] [!DNL API]proporcionan acceso a diferentes entornos de trabajo. Estos entornos ayudan a probar el código con bases de datos independientes sin afectar a los datos de producción activos. La siguiente tabla enumera los entornos [!DNL API] disponibles y los nombres de host de recursos correspondientes.

Según el método de autenticación que utilice, debe ajustar el entorno [!DNL URLs] según la tabla siguiente.

| Entorno | Nombre de host para la autenticación [!DNL JWT] | Nombre de host para la autenticación [!DNL OAuth] |
|---|---|---|
| **Producción** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>El entorno beta [!DNL Audience Manager] es una versión independiente de menor escala del entorno de producción. Todos los datos que desee probar deben introducirse y recopilarse en este entorno.

## Versiones {#versions}

Las nuevas versiones de estos [!DNL API]s se publican con regularidad. Una nueva versión incrementa el número de versión [!DNL API]. Se hace referencia al número de versión en la solicitud [!DNL URL] como `v<version number>` como se muestra en el siguiente ejemplo:

`https://<host>/v1/...`

## Códigos de respuesta definidos {#response-codes-defined}

`HTTP` códigos de estado y texto de respuesta que devuelve  [!DNL Audience Manager] [!UICONTROL REST API].

| ID del código de respuesta | Texto de respuesta | Definición |
|---|---|---|
| `200` | `OK` | La solicitud se procesó correctamente. Devuelve el contenido o los datos esperados si es necesario. |
| `201` | `Created` | Se creó el recurso. Devuelve para solicitudes `PUT` y `POST`. |
| `204` | `No Content` | El recurso se ha eliminado. El cuerpo de la respuesta estará en blanco. |
| `400` | `Bad Request` | El servidor no entendió la solicitud. Normalmente se debe a una sintaxis mal formada. Compruebe la solicitud e inténtelo de nuevo. |
| `403` | `Forbidden` | No tiene acceso al recurso. |
| `404` | `Not Found` | No se encontró el recurso para la ruta especificada. |
| `409` | `Conflict` | No se pudo completar la solicitud debido a un conflicto con el estado del recurso. |
| `500` | `Server Error` | El servidor encontró un error inesperado que impedía que cumpliera la solicitud. |

>[!MORELIKETHIS]
>
>* [Autenticación JWT (cuenta de servicio)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [Autenticación OAuth](../../api/rest-api-main/aam-api-getting-started.md#oauth)
* [OAuth 2.0](https://oauth.net/2/)
* [OAuth 2 simplificado](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

