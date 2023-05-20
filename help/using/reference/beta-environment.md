---
description: El entorno beta sirve para probar la implementación de Audience Manager. Los cambios realizados en la versión beta no afectan a los datos de producción. Póngase en contacto con su Audience Manager de Soluciones para socios si está interesado en utilizar el entorno beta.
keywords: espacio aislado
seo-description: The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.
seo-title: Beta Environment
solution: Audience Manager
title: Entorno beta
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: Reference
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
source-git-commit: fce39268f1c8c4dd1b7ff21b61a9830a20fa0b4e
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 3%

---

# Entorno beta {#beta-environment}

El entorno beta sirve para probar la implementación de Audience Manager. Los cambios realizados en la versión beta no afectan a los datos de producción. Póngase en contacto con su Audience Manager de Soluciones para socios si está interesado en utilizar el entorno beta.

## Información general

La funcionalidad en el entorno beta es una réplica exacta del entorno de producción, sin ninguna función experimental o sin publicar. Las credenciales de inicio de sesión del entorno de producción son válidas en el entorno beta.

**Calendario de actualizaciones**

El entorno beta se actualiza al final de cada mes durante las horas de menor actividad.

>[!IMPORTANT]
>
>Tenga en cuenta que los datos de clientes ([señales, rasgos y segmentos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=en)) no se sincroniza entre los entornos de producción y beta.

## Tráfico entrante

El entorno beta solo admite tráfico entrante para fines de validación de nombres de archivo y sintaxis de contenido. Dado que no hay ninguna asignación de ID en curso en el entorno beta, los clientes no verán ninguna población de segmentos.

En consecuencia, la [!UICONTROL Onboarding Status] La página siempre informará [!UICONTROL No matching AAM ID] tras la ingesta de archivos en el entorno beta.

Recomendamos a todos los clientes que realicen cualquier prueba entrante en su entorno de producción.

## Tráfico saliente

El tráfico saliente no está habilitado para el entorno beta.

## Extremos

| Servicio | URL/Nombre de host | Cómo obtener acceso |
|--- |--- | --- |
| S3 | Póngase en contacto con su Audience Manager de Soluciones para socios o con el Servicio de atención al cliente | Póngase en contacto con su Audience Manager de Soluciones para socios o con el Servicio de atención al cliente para configurar un contenedor de Amazon S3 para su instancia beta. Lea más información sobre [ventajas de utilizar Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | Consulte [Acceso al DCS en el entorno beta](../reference/beta-environment.md#access-dcs-beta-environment). |
| IU | `https://bank-beta.demdex.com` | Las credenciales del entorno de producción son válidas para el entorno beta. |
| API | `https://api-beta.demdex.com/...` | Las credenciales del entorno de producción son válidas para el entorno beta. Le recomendamos que cree un usuario de API genérico, [ver detalles](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Acceso al DCS en el entorno beta {#access-dcs-beta-environment}

1. Realizar una llamada del DCS utilizando el curl [mando](https://curl.haxx.se/docs/manpage.html). Curl es una herramienta para transferir datos desde o hacia un servidor, utilizando uno de los muchos protocolos admitidos.

   Por ejemplo:

   `curl -v https://dcs-beta.demdex.net/event`

1. Compruebe que el DCS beta proporcionó su solicitud buscando &quot;sandbox&quot; en el encabezado de respuesta del DCS.

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
