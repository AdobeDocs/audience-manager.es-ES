---
description: Puede enviar segmentos cualificados a Google Ad Manager a través de una integración del lado del cliente o de un servidor. A continuación se enumeran los requisitos e información relacionada sobre ambos métodos.
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: Requisitos y métodos para enviar segmentos a Google Ad Manager mediante Google Publisher Tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
TQID: https://experienceleague.adobe.com/RJwzr9sCowegtUDtmi99IBoZHvMBlEZVMBYSGgEVVYE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 466
ht-degree: 0%

---

# Requisitos y métodos para enviar segmentos a Google Ad Manager mediante etiquetas de publicador de Google ( GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Puede enviar segmentos calificados a [!DNL Google Ad Manager] (anteriormente DFP) a través de una integración del lado del cliente o del lado del servidor. A continuación se enumeran los requisitos e información relacionada sobre ambos métodos.

## Integración del lado del cliente {#client-side-integration}

Para una integración del lado del cliente, debe configurar un destino [!DNL GPT] en Audience Manager. Tenga en cuenta los siguientes puntos cuando quiera configurar [!DNL GPT] como un destino de Audience Manager:

* **Agregar [!UICONTROL DIL]:** Implementar código [!UICONTROL Data Integration Library (DIL)] en todas las páginas que desee segmentar. [!UICONTROL DIL] escribe los datos del segmento de Audience Manager y los identificadores de usuario en cookies que [!DNL GPT] usa para la segmentación.

* **Crear un [!UICONTROL Cookie Destination]:** [!DNL GPT] debe configurarse como un destino basado en cookies en Audience Manager.

* **Implementar código de comprobación de cookies:** Ajuste el método de API [!DNL GPT] `.setTargeting` en nuestro [código de comprobación de cookies](../../integration/gpt-aam-destination/gpt-aam-modify-api.md) recomendado. Este código ayuda a evitar errores al buscar cookies de AAM válidas antes de que se invoque el método `.setTargeting`.

* **Agregar la función `AamGpt`:** El código `AamGpt` captura datos de las cookies de Audience Manager y los envía a [!DNL GPT]. Coloque el [código Audience Manager para etiquetas de publicador de Google](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) (`AamGpt`) en la parte superior de la página o dentro del bloque de código `<head>`.

  >[!NOTE]
  >
  >La función `AamGpt` no es necesaria si usa su propio código para leer datos de cookies de Audience Manager.

* **Enviar registros de envío a Audience Manager:** Si desea un informe de envío de segmento (opcional), proporcione a Audience Manager un registro diario que contenga los datos de envío en el nivel de impresión. Los datos pueden estar en formato sin procesar, pero cada registro debe contener el Audience Manager `UUID`. Audience Manager puede recogerlos o recibirlos a través de [!DNL FTP].

### Solo se envían a GPT segmentos calificados

La cantidad de datos pasados a [!DNL GPT] depende de la cantidad de segmentos a los que califique un usuario en particular. Por ejemplo, supongamos que configura 100 segmentos de Audience Manager. Si el visitante de un sitio califica para cinco de ellos, entonces solo esos cinco segmentos se envían a [!DNL GPT] (no todos los 100).

>[!NOTE]
>
>No hay límites en el número de valores clave que puede enviar, pero la solicitud [!DNL Google] [!DNL URL] tiene límites en el número de caracteres que puede aceptar. Ver [Configuración de destinos y tamaños con GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Integración del lado del servidor {#server-side-integration}

Hable con su asesor de Audience Manager o con el Servicio de atención al cliente si desea configurar una integración del lado del servidor con [!DNL Google Ad Manager], mediante [!DNL GPT]. Debe proporcionar su ID de vínculo de audiencia y el ID de red de la cuenta [!DNL Google Ad Manager].

>[!IMPORTANT]
>
>Si sus páginas web ejecutan la biblioteca [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]), debe utilizar la integración del lado del servidor con Audience Manager. Si está en [!DNL AMP] y tiene una integración del lado del cliente con [!DNL AMP], debe migrar a la integración del lado del servidor. Póngase en contacto con su asesor de Audience Manager o con el Servicio de atención al cliente para hablar sobre la migración.

>[!MORELIKETHIS]
>
>* [Guía de referencia de API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)
