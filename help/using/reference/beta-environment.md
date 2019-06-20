---
description: El entorno beta sirve para probar la implementación de Audience Manager. Los cambios realizados en beta no afectan a los datos de producción. Póngase en contacto con su representante de soluciones de socio de Audience Manager si le interesa utilizar el entorno beta.
keywords: sandbox
seo-description: El entorno beta sirve para probar la implementación de Audience Manager. Los cambios realizados en beta no afectan a los datos de producción. Póngase en contacto con su representante de soluciones de socio de Audience Manager si le interesa utilizar el entorno beta.
seo-title: Entorno beta
solution: Audience Manager
title: Entorno beta
uuid: de 4 a 1 a 46-cfa 4-4 f 64-8569-48 a 7650 fd 8 cf
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Entorno beta {#beta-environment}

El entorno beta sirve para probar la implementación de Audience Manager. Los cambios realizados en beta no afectan a los datos de producción. Póngase en contacto con su representante de soluciones de socio de Audience Manager si le interesa utilizar el entorno beta.

## Información general

El entorno beta es una réplica exacta del entorno de producción, sin ninguna característica experimental ni liberada. Las credenciales de inicio de sesión desde el entorno de producción son válidas en el entorno beta.

**Actualizar programación**

El entorno beta se actualiza al final de cada mes durante las horas de desactivación.

**Tráfico saliente**

El tráfico saliente no está habilitado para el entorno beta.

<!-- 

Added re: AAM-30826.

 -->

## Puntos finales



| Servicio | URL/Nombre de host | Cómo obtener acceso |
|--- |--- | --- |
| S3 | Comuníquese con el representante de soluciones de socio de Audience Manager o con el Servicio de atención al cliente | Póngase en contacto con su representante de Soluciones de socio de Audience Manager o con el Servicio de atención al cliente para configurar un bloque Amazon S 3 para su instancia beta. Read about the [advantages of using Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | See [Accessing the DCS in the Beta Environment](../reference/beta-environment.md#access-dcs-beta-environment). |
| IU | `https://bank-beta.demdex.com` | Las credenciales del entorno de producción son válidas para el entorno beta. |
| API | `https://api-beta.demdex.com/...` | Las credenciales del entorno de producción son válidas para el entorno beta. We recommend that you create a generic API user, [see details](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Accessing the DCS in the Beta Environment {#access-dcs-beta-environment}

1. Make a DCS call, using the curl [command](https://curl.haxx.se/docs/manpage.html). Curl es una herramienta para transferir datos desde o hacia un servidor utilizando uno de los muchos protocolos admitidos.

   Por ejemplo:

   `curl -v https://dcs-beta.demdex.net/event`

1. Verifique que el DCS beta ofrezca su solicitud buscando &quot;simulador para pruebas&quot; en el encabezado de respuesta de DCS.

   Por ejemplo:

   ```
   curl -v http://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

<!--

1. Determine the load balancer's endpoint IP addresses.

   Run the `dig`  [command](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The `dig` command queries the Domain Name System and returns the name and IP addresses of the [!DNL Audience Manager] [!UICONTROL Data Collection Servers (DCS)].

   ```
   dig dcs-beta.demdex.net
   ...
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

2. Using one of the addresses in the above table, add a static DNS entry in the [!DNL /etc/hosts] file.

   On Windows, modify [!DNL c:\WINDOWS\system32\drivers\etc\hosts].

   For example:

   [!DNL 52.87.15.51 *`samplepartner`*.demdex.net]

   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL /etc/hosts] file up to date.

   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL dpm.demdex.net.]

   [!DNL 52.87.15.51 dpm.demdex.net]. 

3. Make a DCS call, using the `curl` [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols.

   For example:

   [!DNL https://<domain>/event?product=camera] 

4. Verify that your request was served by the beta DCS by looking for "sandbox" in the DCS response header.

   For example:

   ```
   curl -v https://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

   -->