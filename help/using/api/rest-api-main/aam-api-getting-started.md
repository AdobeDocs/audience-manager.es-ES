---
description: Información sobre requisitos generales, autenticación, parámetros de consulta opcionales, direcciones URL de solicitud y otras referencias.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Introducción a las API de REST
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '1910'
ht-degree: 3%

---

# Introducción con [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Información sobre requisitos generales, autenticación, parámetros de consulta opcionales, solicitud [!DNL URLs], y otras referencias.

<!-- c_rest_api_overview.xml -->

## Requisitos y recomendaciones de API {#api-requirements-recommendations}

Cosas que debe y debe hacer al trabajar con [!DNL Audience Manager] [!DNL API]s.

<!-- aam-api-requirements.xml -->

Tenga en cuenta lo siguiente al trabajar con [API de Audience Manager](https://bank.demdex.com/portal/swagger/index.html#/) código:

* **Parámetros de solicitud:** todos los parámetros de solicitud son obligatorios a menos que se especifique lo contrario.
* **Encabezados de solicitud**: cuando se usa [Desarrollador de Adobe](https://www.adobe.io/) tokens, debe proporcionar la variable `x-api-key` encabezado. Puede obtener su [!DNL API] siguiendo las instrucciones de la sección [Integración de cuentas de servicio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) página.
* **[!DNL JSON]tipo de contenido:** Especifique `content-type: application/json`  *y*  `accept: application/json` en su código.
* **Solicitudes y respuestas:** Enviar solicitudes con el formato correcto [!DNL JSON] objeto. [!DNL Audience Manager] responde con [!DNL JSON] datos con formato. Las respuestas del servidor pueden contener datos solicitados, un código de estado o ambos.
* **Acceso:** Su [!DNL Audience Manager] el consultor le proporcionará un ID de cliente y una clave que le permitirán hacer [!DNL API] solicitudes.
* **Documentación y ejemplos de código:** Texto en *cursiva* representa una variable que se proporciona o pasa al realizar o recibir [!DNL API] datos. Reemplazar *cursiva* texto con su propio código, parámetros u otra información requerida.

## Autenticación {#authentication}

La variable [!DNL Audience Manager] [!DNL REST APIs] admiten dos métodos de autenticación.

* [Autenticación JWT (cuenta de servicio)](#jwt) using [Desarrollador de Adobe](https://www.adobe.io/). [!DNL Adobe Developer] es el ecosistema y la comunidad de desarrolladores de Adobe. Incluye [API para todos los productos de Adobe](https://www.adobe.io/apis.html). Esta es la forma recomendada de configurar y utilizar [!DNL Adobe] [!DNL APIs].
* [Autenticación OAuth (obsoleto)](#oauth). Aunque este método está en desuso, los clientes con [!DNL OAuth] las integraciones pueden seguir utilizando este método.

>[!IMPORTANT]
>
>Según el método de autenticación, debe ajustar la solicitud [!DNL URLs] en consecuencia. Consulte la [Entornos](#environments) para obtener más información sobre los nombres de host que debe utilizar.

## [!DNL JWT] ([!DNL Service Account]) Autenticación mediante el desarrollador de Adobe {#jwt}

### Información general para desarrolladores de Adobe {#adobeio}

[!DNL Adobe Developer] es el ecosistema y la comunidad de desarrolladores de Adobe. Incluye [API para todos los productos de Adobe](https://www.adobe.io/apis.html).

Esta es la forma recomendada de configurar y utilizar [!DNL Adobe] [!DNL APIs].

### Requisitos previos {#prerequisites}

Antes de configurar [!DNL JWT] autenticación, asegúrese de tener acceso a la [Adobe Developer Console](https://console.adobe.io/) en [Desarrollador de Adobe](https://www.adobe.io/). Póngase en contacto con el administrador de su organización para solicitar acceso.

### Autenticación {#auth}

Siga los pasos a continuación para configurar [!DNL JWT (Service Account)] autenticación [!DNL Adobe Developer]:

1. Inicie sesión en la [Adobe Developer Console](https://console.adobe.io/).
1. Siga los pasos indicados en [Conexión de cuenta de servicio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Durante [Paso 2: Añadir una API al proyecto mediante autenticación de cuenta de servicio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), elija el [!DNL Audience Manager] [!DNL API] .
1. Pruebe la conexión realizando la primera [!DNL API] realice una llamada según las instrucciones de [Paso 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Para configurar y trabajar con la variable [!DNL Audience Manager] [!DNL REST APIs] de forma automatizada, puede generar la variable [!DNL JWT] mediante programación. Consulte [Autenticación JWT (cuenta de servicio)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) para obtener instrucciones detalladas.

### Permisos RBAC de cuenta técnica

Si su cuenta de Audience Manager utiliza [Control de acceso basado en roles](../../features/administration/administration-overview.md), debe crear una cuenta de usuario técnica de Audience Manager y agregarla al grupo RBAC de Audience Manager que hará las llamadas de API.

Siga los pasos a continuación para crear una cuenta de usuario técnica y agregarla a un grupo RBAC:

1. Haga un `GET` llamar a `https://aam.adobe.io/v1/users/self`. La llamada creará una cuenta de usuario técnica que puede ver en la [!UICONTROL Admin Console], en el [!UICONTROL Users] página.

   ![cuenta técnica](assets/technical-account.png)

1. Inicie sesión en su cuenta de Audience Manager y [agregar la cuenta de usuario técnica](../../features/administration/administration-overview.md#create-group) al grupo de usuarios que realizará las llamadas de API.

## [!DNL OAuth] Autenticación (obsoleto) {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] autenticación y renovación de tokens mediante [!DNL OAuth 2.0] está en desuso.
>
> Utilice [Autenticación JWT (cuenta de servicio)](#jwt-service-account-authentication-jwt) en su lugar.

La variable [!DNL Audience Manager] [!UICONTROL REST API] following [!DNL OAuth 2.0] estándares para la autenticación y renovación de tokens. Las secciones siguientes describen cómo autenticarse y comenzar a trabajar con el [!DNL API]s.

### Crear un genérico [!DNL API] Usuario {#requirements}

Le recomendamos que cree una cuenta de usuario técnica independiente para trabajar con el [!DNL Audience Manager] [!DNL API]s. Se trata de una cuenta genérica que no está vinculada a un usuario específico de su organización ni asociada a él. Este tipo de [!DNL API] la cuenta de usuario de ayuda a realizar dos tareas:

* Identifique qué servicio llama a la función [!DNL API] (p. ej., llamadas de sus aplicaciones que usan nuestra [!DNL API]s o de otras herramientas que realizan [!DNL API] solicitudes).
* Proporcionar acceso ininterrumpido a la variable [!DNL API]s. Una cuenta vinculada a una persona específica puede ser eliminada cuando abandone la empresa. Esto le impedirá trabajar con los [!DNL API] código. Una cuenta genérica que no está vinculada a un empleado en particular le ayuda a evitar este problema.

Como ejemplo o caso de uso para este tipo de cuenta, supongamos que desea cambiar muchos segmentos a la vez con la variable [Herramientas de administración masiva](../../reference/bulk-management-tools/bulk-management-intro.md). Bueno, para ello, su cuenta de usuario necesita [!DNL API] acceso. En lugar de agregar permisos a un usuario específico, cree un [!DNL API] cuenta de usuario que tiene las credenciales, la clave y el secreto adecuados para realizar [!DNL API] llamadas a . Esto también resulta útil si desarrolla sus propias aplicaciones que utilizan la variable [!DNL Audience Manager] [!DNL API]s.

Trabaje con su [!DNL Audience Manager] consultor para configurar un genérico, [!DNL API]-solo cuenta de usuario.

### Flujo de trabajo de autenticación de contraseña {#password-authentication-workflow}

Autenticación de contraseña acceso seguro a [!DNL REST API]. Los pasos siguientes describen el flujo de trabajo para la autenticación de contraseña desde una [!DNL JSON] en su explorador.

>[!TIP]
>
>Codifique el acceso y actualice los tokens si los almacena en una base de datos.

#### Paso 1: Solicitud [!DNL API] Acceso

Póngase en contacto con el administrador de soluciones de socios. Le proporcionarán un [!DNL API] ID de cliente y secreto. El ID y el secreto le autentican en el [!DNL API].

Nota: Si desea recibir un token de actualización, especifique que cuando lo solicite [!DNL API] acceso.

#### Paso 2: Solicitar el token

Pase una solicitud de token con su [!DNL JSON] cliente. Al crear la solicitud:

* Utilice un `POST` método para llamar `https://api.demdex.com/oauth/token`.
* Convierta el ID de cliente y el secreto en una cadena codificada base-64. Separe el ID y el secreto con dos puntos durante el proceso de conversión. Por ejemplo, las credenciales `testId : testSecret` convertir a `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pasa el [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` y `Content-Type: application/x-www-form-urlencoded` . Por ejemplo, el encabezado podría tener este aspecto: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configure el cuerpo de la solicitud de la siguiente manera:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Paso 3: Recibir el token

La variable [!DNL JSON] La respuesta contiene su token de acceso. La respuesta debería tener este aspecto:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

La variable `expires_in` representa el número de segundos hasta que caduca el token de acceso. Se recomienda utilizar tiempos de caducidad cortos para limitar la exposición si el token se expone alguna vez.

### Actualizar token {#refresh-token}

Actualizar la renovación de tokens [!DNL API] después de que caduque el token original. Si se solicita, la respuesta [!DNL JSON] en el flujo de trabajo de contraseña incluye un token de actualización. Si no recibe un token de actualización, cree uno nuevo mediante el proceso de autenticación de contraseña.

También puede utilizar un token de actualización para generar un nuevo token antes de que caduque el token de acceso existente.

Si el token de acceso ha caducado, recibirá una `401 Status Code` y el siguiente encabezado en la respuesta:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Los siguientes pasos describen el flujo de trabajo para utilizar un token de actualización para crear un nuevo token de acceso a partir de un [!DNL JSON] en su explorador.

#### Paso 1: Solicitar el nuevo token

Pase una solicitud de token de actualización con su [!DNL JSON] cliente. Al crear la solicitud:

* Utilice un `POST` método para llamar `https://api.demdex.com/oauth/token`.
* Convierta el ID de cliente y el secreto en una cadena codificada base-64. Separe el ID y el secreto con dos puntos durante el proceso de conversión. Por ejemplo, las credenciales `testId : testSecret` convertir a `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pasar los encabezados HTTP `Authorization:Basic <base-64 clientID:clientSecret>` y `Content-Type: application/x-www-form-urlencoded`. Por ejemplo, el encabezado podría tener este aspecto: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* En el cuerpo de la solicitud, especifique la variable `grant_type:refresh_token` y pase el token de actualización que recibió en su solicitud de acceso anterior. La solicitud debe tener este aspecto: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Paso 2: Recibir el nuevo token

La variable [!DNL JSON] contiene su nuevo token de acceso. La respuesta debería tener este aspecto:

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

La variable [!DNL Audience Manager] [!UICONTROL REST API] admite código de autorización y autenticación implícita. Para utilizar estos métodos de acceso, los usuarios deben iniciar sesión en `https://api.demdex.com/oauth/authorize` para obtener acceso y actualizar tokens.

## Autenticar [!DNL API] Solicitudes {#authenticated-api-requests}

Requisitos para llamar [!DNL API] métodos después de recibir un token de autenticación.

Para realizar llamadas con los disponibles [!DNL API] métodos:

* En el `HTTP` encabezado, conjunto `Authorization: Bearer <token>`.
* Al usar [Autenticación JWT (cuenta de servicio)](#jwt), debe proporcionar la variable `x-api-key` encabezado, que será el mismo que su `client_id`. Puede obtener su `client_id` de la variable [Integración de desarrolladores de Adobe](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) página.
* Llame al [!DNL API] método.

## Opcional [!DNL API] Parámetros de consulta {#optional-api-query-parameters}

Establezca los parámetros opcionales disponibles para los métodos que devuelven todas las propiedades de un objeto.

Puede utilizar estos parámetros opcionales con [!DNL API] métodos que devuelven *all* propiedades de un objeto. Establezca estas opciones en la cadena de solicitud al pasar esa consulta a la variable [!DNL API].

| Parámetro | Descripción |
|--- |--- |
| `page` | Devuelve los resultados por número de página. La numeración comienza en 0. |
| `pageSize` | Define el número de resultados de respuesta que devuelve la solicitud (10 es el valor predeterminado). |
| `sortBy` | Ordena y devuelve los resultados según el valor especificado [!DNL JSON] propiedad. |
| `descending` | Ordena y devuelve los resultados en orden descendente. `ascending` es el valor predeterminado. |
| `search` | Devuelve los resultados en función de la cadena especificada que desee utilizar como parámetro de búsqueda. Por ejemplo, supongamos que desea encontrar resultados para todos los modelos que tienen la palabra &quot;Prueba&quot; en cualquiera de los campos de valor para ese elemento. Su solicitud de ejemplo podría tener este aspecto:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Puede buscar cualquier valor devuelto por un &quot;[!DNL get all]&quot;. |
| `folderId` | Devuelve todos los ID de [!UICONTROL traits] dentro de la carpeta especificada. No está disponible para todos los métodos. |
| `permissions` | Devuelve una lista de segmentos en función del permiso especificado. `READ` es el valor predeterminado. Los permisos incluyen:<ul><li>`READ` : Devolver y ver información sobre un segmento.</li><li>`WRITE` : Uso  `PUT`  para actualizar un segmento.</li><li>`CREATE` : Uso  `POST`  para crear un segmento.</li><li>`DELETE` : Eliminar un segmento. Requiere acceso a los rasgos subyacentes, si los hay. Por ejemplo, necesitará derechos para eliminar las características que pertenecen a un segmento si desea eliminarlas.</li></ul><br>Especifique varios permisos con pares de clave-valor independientes. Por ejemplo, para devolver una lista de segmentos con  `READ`  y  `WRITE`  solo permisos, pasar  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Establecer en `true` para devolver los permisos del segmento. El valor predeterminado es `false`. |

### Una Nota Sobre Las Opciones De Página

Cuando la información de la página *no es* especificado, la solicitud devuelve sin formato [!DNL JSON] genera una matriz. Si la información de la página *es* especificado, la lista devuelta se ajusta en un [!DNL JSON] objeto que contiene información sobre el resultado total y la página actual. Su solicitud de ejemplo con opciones de página podría tener un aspecto similar al siguiente:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] para solicitudes, entornos de ensayo y producción y versiones.

## Solicitud [!DNL URLs] {#request-urls}

La tabla siguiente muestra la solicitud [!DNL URLs] usado para pasar [!DNL API] por método.

Según el método de autenticación que utilice, debe ajustar la solicitud [!DNL URLs] según las tablas siguientes.

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

### Solicitud [!DNL URLs] para [!DNL OAuth] Autenticación (obsoleto) {#request-urls-oauth}

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

La variable [!DNL Audience Manager] [!DNL API]proporcionan acceso a diferentes entornos de trabajo. Estos entornos ayudan a probar el código con bases de datos independientes sin afectar a los datos de producción activos. La tabla siguiente muestra las [!DNL API] entornos y nombres de host de recursos correspondientes.

Según el método de autenticación que utilice, debe ajustar el entorno [!DNL URLs] según la tabla siguiente.

| Entorno | Nombre de host para [!DNL JWT] autenticación | Nombre de host para [!DNL OAuth] autenticación |
|---|---|---|
| **Producción** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>La variable [!DNL Audience Manager] el entorno beta es una versión independiente a menor escala del entorno de producción. Todos los datos que desee probar deben introducirse y recopilarse en este entorno.

## Versiones {#versions}

Nuevas versiones de estas [!DNL API]Los informes se publican con regularidad. Una nueva versión incrementa la variable [!DNL API] número de versión. Se hace referencia al número de versión en la solicitud [!DNL URL] como `v<version number>` como se muestra en el siguiente ejemplo:

`https://<host>/v1/...`

## Códigos de respuesta definidos {#response-codes-defined}

`HTTP` códigos de estado y texto de respuesta devueltos por la variable [!DNL Audience Manager] [!UICONTROL REST API].

| ID del código de respuesta | Texto de respuesta | Definición |
|---|---|---|
| `200` | `OK` | La solicitud se procesó correctamente. Devuelve el contenido o los datos esperados si es necesario. |
| `201` | `Created` | Se creó el recurso. Devuelve para `PUT` y `POST` solicitudes. |
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
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 simplificado](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

