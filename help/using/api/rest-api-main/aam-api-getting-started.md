---
description: Información sobre requisitos generales, autenticación, parámetros de consulta opcionales, direcciones URL de solicitud y otras referencias.
seo-description: Información sobre requisitos generales, autenticación, parámetros de consulta opcionales, direcciones URL de solicitud y otras referencias.
seo-title: Introducción a las API de REST
solution: Audience Manager
title: Introducción a las API de REST
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
translation-type: tm+mt
source-git-commit: af43becaf841909174fad097f4d4d5040c279b47

---


# Introducción a las API de REST {#getting-started-with-rest-apis}

Información sobre requisitos generales, autenticación, parámetros de consulta opcionales, direcciones URL de solicitud y otras referencias.

<!-- c_rest_api_overview.xml -->

## Requisitos de API y recomendaciones {#api-requirements-recommendations}

Cosas que debe y debe hacer cuando trabaje con el Administrador [!DNL API]de Audiencias.

<!-- aam-api-requirements.xml -->

Tenga en cuenta lo siguiente al trabajar con el código de API [del Administrador de](https://bank.demdex.com/portal/swagger/index.html#/) Audiencias:

* **Parámetros de solicitud:** Todos los parámetros de solicitud son obligatorios a menos que se especifique lo contrario.
* **[!DNL JSON]tipo de contenido:**Especifique`content-type: application/json`y **`accept: application/json`en el código.

* **Solicitudes y respuestas:** Enviar solicitudes como un [!DNL JSON] objeto con el formato correcto. [!DNL Audience Manager] responde con datos con [!DNL JSON] formato. Las respuestas del servidor pueden contener datos solicitados, un código de estado o ambos.

* **Acceso:** El [!DNL Audience Manager] consultor le proporcionará un ID de cliente y una clave que le permitirá realizar [!DNL API] solicitudes.

* **Muestras de documentación y código:** El texto en *cursiva* representa una variable que se proporciona o pasa al crear o recibir [!DNL API] datos. Reemplace el texto *en cursiva* con su propio código, parámetros u otra información requerida.

## Recomendaciones: Creación de un usuario de API genérico {#requirements}

Le recomendamos que cree una cuenta de usuario técnica independiente para trabajar con el Administrador [!DNL API]de Audiencias. Es una cuenta genérica que no está vinculada a un usuario específico de su organización ni asociada a él. Este tipo de cuenta de [!DNL API] usuario le ayuda a realizar dos tareas:

* Identifique qué servicio llama a la [!DNL API] (p. ej., llamadas desde sus aplicaciones que usan nuestros [!DNL API]o desde otras herramientas que realizan [!DNL API] solicitudes).
* Proporcionar acceso ininterrumpido a los [!DNL API]informes. Una cuenta vinculada a una persona específica puede ser eliminada cuando abandone su compañía. Esto impedirá que trabaje con el [!DNL API] código disponible. Una cuenta genérica que no está vinculada a un empleado en particular le ayuda a evitar este problema.

Como ejemplo o caso de uso para este tipo de cuenta, supongamos que desea cambiar muchos segmentos a la vez con las Herramientas [de administración](../../reference/bulk-management-tools/bulk-management-intro.md)masiva. Bueno, para hacerlo, su cuenta de usuario necesita [!DNL API] acceso. En lugar de agregar permisos a un usuario específico, cree una cuenta de usuario no específica que tenga las credenciales, la clave y el secreto adecuados para realizar [!DNL API] [!DNL API] llamadas. Esto también es útil si desarrolla sus propias aplicaciones que utilizan el Administrador [!DNL API]de Audiencias.

Póngase en contacto con el consultor del administrador de Audiencias para configurar una cuenta de usuario genérica [!DNL API]exclusiva.

## OAuth Authentication {#oauth}

El Administrador de Audiencias [!UICONTROL REST API] sigue [!DNL OAuth 2.0] los estándares de autenticación y renovación de testigos. Las secciones siguientes describen cómo autenticar y inicio el trabajo con [!DNL API]s.

## Flujo de trabajo de autenticación de contraseña {#password-authentication-workflow}

<!-- oath-authentication.xml -->

Autenticación de contraseña acceso seguro a nuestro [!DNL REST API]. Los pasos a continuación describen el flujo de trabajo para la autenticación de contraseña de un [!DNL JSON] cliente en su explorador.

>[!TIP]
>
>Cifre los tokens de acceso y actualícelos si los almacena en una base de datos.

### Paso 1: Solicitar acceso a API

Póngase en contacto con el administrador de soluciones de socio. Le proporcionarán un ID de [!DNL API] cliente y un secreto. El ID y el secreto le autentican en el [!DNL API].

Nota: Si desea recibir un autentificador de actualización, especifíquelo cuando solicite [!DNL API] acceso.

### Paso 2: Solicitar el token

Pasa una solicitud de token con tu [!DNL JSON] cliente preferido. Al generar la solicitud:

* Utilice un `POST` método para llamar `https://api.demdex.com/oauth/token`.
* Convierta el ID de cliente y el secreto en una cadena con codificación base-64. Separe el ID y el secreto con dos puntos durante el proceso de conversión. Por ejemplo, las credenciales `testId : testSecret` se convierten en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pasa los [!DNL HTTP] encabezados `Authorization:Basic <base-64 clientID:clientSecret>` y `Content-Type: application/x-www-form-urlencoded` . Por ejemplo, el encabezado podría tener este aspecto: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configure el cuerpo de la solicitud de la siguiente manera:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

### Paso 3: Recibir el token

La [!DNL JSON] respuesta contiene su token de acceso. La respuesta debería tener este aspecto:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

La `expires_in` clave representa el número de segundos hasta que caduca el token de acceso. Se recomienda utilizar tiempos de caducidad cortos para limitar la exposición si el token se expone alguna vez.

## Actualizar token {#refresh-token}

Actualice los tokens para renovar [!DNL API] el acceso después de que caduque el token original. Si se solicita, la respuesta [!DNL JSON] en el flujo de trabajo de contraseña incluye un token de actualización. Si no recibe un token de actualización, cree uno nuevo mediante el proceso de autenticación de contraseña.

También puede utilizar un token de actualización para generar un nuevo token antes de que caduque el token de acceso existente.

Si el token de acceso ha caducado, recibirá un encabezado `401 Status Code` y el siguiente en la respuesta:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Los pasos siguientes describen el flujo de trabajo para utilizar un token de actualización para crear un nuevo token de acceso desde un [!DNL JSON] cliente en el explorador.

### Paso 1: Solicitar el nuevo token

Pasa una solicitud de token de actualización con el [!DNL JSON] cliente preferido. Al generar la solicitud:

* Utilice un `POST` método para llamar `https://api.demdex.com/oauth/token`.
* Convierta el ID de cliente y el secreto en una cadena con codificación base-64. Separe el ID y el secreto con dos puntos durante el proceso de conversión. Por ejemplo, las credenciales `testId : testSecret` se convierten en `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pasa los encabezados HTTP `Authorization:Basic <base-64 clientID:clientSecret>` y `Content-Type: application/x-www-form-urlencoded`. Por ejemplo, el encabezado podría tener este aspecto: <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* En el cuerpo de la solicitud, especifique `grant_type:refresh_token` y pase el token de actualización que recibió en la solicitud de acceso anterior. La solicitud debería tener este aspecto: <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

### Paso 2: Recibir el nuevo token

La [!DNL JSON] respuesta contiene el nuevo token de acceso. La respuesta debería tener este aspecto:

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

## Código de autorización y autenticación implícita {#authentication-code-implicit}

El Administrador de Audiencias [!UICONTROL REST API] admite código de autorización y autenticación implícita. Para utilizar estos métodos de acceso, los usuarios deben iniciar sesión para `https://api.demdex.com/oauth/authorize` obtener acceso y actualizar los tokens.

## Realizar solicitudes de API autenticadas {#authenticated-api-requests}

Requisitos para llamar a [!DNL API] métodos después de recibir un autentificador.

<!-- c_oauth_call_methods.xml -->

Para realizar llamadas con los [!DNL API] métodos disponibles:

* En el `HTTP` encabezado, establezca `Authorization: Bearer <token>`.
* Llame al [!DNL API] método requerido.

## Parámetros de Consulta de API opcionales {#optional-api-query-parameters}

Establezca los parámetros opcionales disponibles para los métodos que devuelven todas las propiedades de un objeto.

<!-- c_rest_api_optional.xml -->

Puede utilizar estos parámetros opcionales con [!DNL API] métodos que devuelven *todas* las propiedades de un objeto. Configure estas opciones en la cadena de solicitud al pasar esa consulta al [!DNL API].

| Parámetro | Descripción |
|--- |--- |
| página | Devuelve los resultados por número de página. inicios de numeración en 0. |
| pageSize | Define el número de resultados de respuesta que devuelve la solicitud (10 es el valor predeterminado). |
| sortBy | Ordena y devuelve resultados según la [!DNL JSON] propiedad especificada. |
| descendente | Ordena y devuelve los resultados en orden descendente. De subida es el valor predeterminado. |
| OR | Devuelve los resultados en función de la cadena especificada que desee utilizar como parámetro de búsqueda. Por ejemplo, supongamos que desea buscar resultados para todos los modelos que tienen la palabra &quot;Prueba&quot; en cualquiera de los campos de valor para ese elemento. Su solicitud de muestra podría tener este aspecto:   `GET https://api.demdex.com/v1/models/?search=Test`.  Puede buscar cualquier valor devuelto por un método &quot;get all&quot;. |
| folderId | Devuelve todos los ID de características dentro de la carpeta especificada. No está disponible para todos los métodos. |
| permisos | Devuelve una lista de segmentos basada en el permiso especificado.  READ es el valor predeterminado. Los permisos incluyen:<ul><li>`READ` :: Información de retorno y vista sobre un segmento.</li><li>`WRITE` :: Se utiliza `PUT` para actualizar un segmento.</li><li>`CREATE` :: Se utiliza `POST` para crear un segmento.</li><li>`DELETE` : Eliminar un segmento. Requiere acceso a las características subyacentes, si las hay. Por ejemplo, necesitará derechos para eliminar las características que pertenecen a un segmento si desea eliminarlo.</li></ul><br>Especifique varios permisos con pares de clave-valor independientes. Por ejemplo, para devolver una lista de segmentos solo con `READ` y `WRITE` permisos, pase `"permissions":"READ"`, `"permissions":"WRITE"` . |
| includePermissions | (Booleano) Establezca en true para devolver los permisos para el segmento. El valor predeterminado es false. |

### Una nota sobre las opciones de página

Cuando no *se especifica la información de la página* , la solicitud devuelve [!DNL JSON] resultados sencillos en una matriz. Si *se especifica* la información de la página, la lista devuelta se envuelve en un [!DNL JSON] objeto que contiene información sobre el resultado total y la página actual. La solicitud de muestra con opciones de página podría tener un aspecto similar a este:

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## API URL {#api-urls}

[!DNL URLs] para solicitudes, entornos de ensayo y producción y versiones.

<!-- r_rest_urls.xml -->

## URL de solicitud {#request-urls}

La siguiente tabla lista las direcciones URL de solicitud utilizadas para pasar [!DNL API] solicitudes, por método.

| [!DNL API] Métodos | Solicitud [!DNL URL] |
|--- |--- |
| Modelado algorítmico | `https://api.demdex.com/v1/models/` |
| Fuente de datos | `https://api.demdex.com/v1/datasources/` |
| Señales derivadas | `https://api.demdex.com/v1/signals/derived/` |
| Destinos  | `https://api.demdex.com/v1/destinations/` |
| Dominios | `https://api.demdex.com/v1/partner-sites/` |
| Carpetas | Características:  `https://api.demdex.com/v1/folders/traits /`<br>Segmentos:  `https://api.demdex.com/v1/folders/segments /` |
| Esquema | `https://api.demdex.com/v1/schemas/` |
| Segmentos | `https://api.demdex.com/v1/segments/` |
| Características | `https://api.demdex.com/v1/traits/` |
| Tipos de características | `https://api.demdex.com/v1/customer-trait-types` |
| Taxonomía | `https://api.demdex.com/v1/taxonomies/0/` |

## Entornos {#environments}

Los [!DNL Audience Manager] dos [!DNL API]ofrecen acceso a diferentes entornos de trabajo. Estos entornos le ayudan a probar el código con bases de datos independientes sin afectar a los datos de producción activos. La siguiente tabla lista los [!DNL API] entornos disponibles y los nombres de host de recursos correspondientes.

| Entorno | Nombre del host |
|---|---|
| **Producción** | `https://api.demdex.com/...` |
| **Beta** | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>El entorno beta del Administrador de Audiencias es una versión independiente de menor escala del entorno de producción. Todos los datos que desee probar deben introducirse y recopilarse en este entorno.

## Versiones {#versions}

Las nuevas versiones de estos [!DNL API]informes se publican con regularidad. Una nueva versión incrementa el número de la [!DNL API] versión. Se hace referencia al número de versión en la dirección URL de la solicitud, como `v<version number>` se muestra en el siguiente ejemplo:

`https://<host>/v1/...`

## Códigos de respuesta definidos {#response-codes-defined}

`HTTP` códigos de estado y texto de respuesta devueltos por el Administrador de Audiencias [!UICONTROL REST API].

<!-- r_api_http_response_codes.xml -->

| ID del código de respuesta | Texto de respuesta | Definición |
|---|---|---|
| 200 | OK | La solicitud se procesó correctamente. Devolverá el contenido o los datos esperados si es necesario. |
| 201 | Creado | Se creó el recurso. Devuelve `PUT` y `POST` solicitudes. |
| 204 | Sin contenido | Se eliminó el recurso. El cuerpo de la respuesta estará en blanco. |
| 400 | Solicitud incorrecta | El servidor no entendía la solicitud. Generalmente debido a una sintaxis mal formada. Compruebe su solicitud e inténtelo de nuevo. |
| 403 | Prohibido | No tiene acceso al recurso. |
| 404 | No encontrado | No se encontró el recurso para la ruta especificada. |
| 409 | Conflicto | No se pudo completar la solicitud debido a un conflicto con el estado del recurso. |
| 500 | Error del servidor | El servidor encontró un error inesperado que le impedía cumplir la solicitud. |

>[!MORELIKETHIS]
>
>* [Autenticación OAuth](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 simplificado](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

