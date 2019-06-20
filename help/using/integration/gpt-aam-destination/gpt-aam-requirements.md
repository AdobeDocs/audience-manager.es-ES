---
description: Puede enviar segmentos cualificados a DFP a través de un lado del cliente o mediante una integración del lado del servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.
seo-description: Puede enviar segmentos cualificados a DFP a través de un lado del cliente o mediante una integración del lado del servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.
seo-title: Requisitos y métodos para enviar segmentos a DFP usando Google Publisher Tags (GPT)
solution: Audience Manager
title: Requisitos y métodos para enviar segmentos a DFP usando Google Publisher Tags (GPT)
uuid: 4 b 2 ea 81 c -29 bb -42 d 3-93 d 3-1 d 8 e 677790 b 6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Requisitos y métodos para enviar segmentos a DFP usando Google Publisher Tags (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

You can send qualified segments to [!DNL DFP] either through a client-side or through a server-side integration. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.

## Client-Side Integration {#client-side-integration}

For a client-side integration, you need to set up a [!DNL GPT] destination in Audience Manager. Consider the following points when you want to set up [!DNL GPT] as an Audience Manager destination:

* **Agregar[!UICONTROL DIL]:** Implemente [!UICONTROL Data Integration Library (DIL)] código en todas las páginas que desee establecer como objetivo. [!UICONTROL DIL] escribe datos de segmento de Audience Manager y ID de usuario en cookies que se utilizan [!DNL GPT] para segmentación.

* **Crear un[!UICONTROL Cookie Destination]:**[!DNL GPT] debe configurarse como destino basado en cookies en Audience Manager.

* **Implementar código de comprobación de cookies:** Ajuste el método [!DNL GPT]`.setTargeting` API en nuestro código de comprobación de [cookies recomendado](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). This code helps prevent errors by looking for valid AAM cookies before the `.setTargeting` method gets invoked.

* **Agregar la`AamGpt`función:** `AamGpt` El código captura los datos de las cookies de Audience Manager y los envía [!DNL GPT]a. Place the [Audience Manager Code for Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) at the top of the page or inside the `<head>` code block.

   >[!NOTE]
   >
   >The `AamGpt` function is not required if you use your own code to read Audience Manager cookie data.

* **Enviar registros de envío a Audience Manager:** Si desea un informe de entrega de segmentos (opcional), proporcione a Audience Manager un registro diario que contenga datos de entrega en el nivel de impresión. The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager can pick up or receive these via [!DNL FTP].

### Solo se envían a GPT los segmentos cualificados

The amount of data passed in to [!DNL GPT] depends on how many segments a particular user qualifies for. Por ejemplo, supongamos que configura 100 segmentos de Audience Manager. If a site visitor qualifies for five of them, then only those five segments get sent to [!DNL GPT] (not all 100).

>[!NOTE]
>
>There are no limits to the number of key-values you can send, but the [!DNL Google] request [!DNL URL] does have limits to the number of characters it can accept. See [Setting targeting and sizes with GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Server-Side Integration {#server-side-integration}

Talk to your Audience Manager consultant or Customer Care if you want to set up a server-side integration with [!DNL DFP], using [!DNL GPT]. You&#39;ll need to provide your [!DNL DFP] account Network ID and Audience Link ID.

>[!IMPORTANT]
>
>If your web pages are running the [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) library, you must use the server-side integration with Audience Manager. If you are on [!DNL AMP] and have a client-side integration with [!DNL AMP], you must migrate to the server-side integration. Comuníquese con el consultor de Audience Manager o con el Servicio de atención al cliente para analizar la migración.

>[!MORE_ LIKE_ THIS]
>
>* [Guía de referencia de API de GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)

