---
description: Puede enviar segmentos cualificados a Google Ad Manager a través de una integración del lado del cliente o de un servidor. A continuación se enumeran los requisitos e información relacionada sobre ambos métodos.
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: Requisitos y métodos para enviar segmentos a Google Ad Manager mediante Google Publisher Tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Requisitos y métodos para enviar segmentos a Google Ad Manager mediante etiquetas de publicador de Google ( GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Puede enviar segmentos calificados a [!DNL Google Ad Manager] (anteriormente DFP) a través de una integración del lado del cliente o del lado del servidor. A continuación se enumeran los requisitos e información relacionada sobre ambos métodos.

## Integración del lado del cliente {#client-side-integration}

Para una integración del lado del cliente, debe configurar un destino [!DNL GPT] en el Audience Manager. Tenga en cuenta los siguientes puntos cuando quiera configurar [!DNL GPT] como un destino de Audience Manager:

* **Agregar [!UICONTROL DIL]:** Implementar código [!UICONTROL Data Integration Library (DIL)] en todas las páginas que desee segmentar. [!UICONTROL DIL] escribe datos de segmentos de Audience Manager e ID de usuarios en cookies que [!DNL GPT] usa para la segmentación.

* **Crear un [!UICONTROL Cookie Destination]:** [!DNL GPT] debe configurarse como un destino basado en cookies en el Audience Manager.

* **Implementar código de comprobación de cookies:** Ajuste el método de API [!DNL GPT] `.setTargeting` en nuestro [código de comprobación de cookies](../../integration/gpt-aam-destination/gpt-aam-modify-api.md) recomendado. AAM Este código ayuda a evitar errores al buscar cookies de válidas antes de invocar el método `.setTargeting`.

* **Agregar la función `AamGpt`:** El código `AamGpt` captura datos de las cookies del Audience Manager y los envía a [!DNL GPT]. Coloque el código de Audience Manager [para las etiquetas de publicador de Google](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) (`AamGpt`) en la parte superior de la página o dentro del bloque de código `<head>`.

  >[!NOTE]
  >
  >La función `AamGpt` no es necesaria si usa su propio código para leer datos de cookies de Audience Manager.

* **Enviar registros de envío al Audience Manager:** Si desea un informe de envío de segmento (opcional), proporcione al Audience Manager un registro diario que contenga los datos de envío en el nivel de impresión. Los datos pueden estar en formato sin procesar, pero cada registro debe contener el Audience Manager `UUID`. El Audience Manager puede recogerlos o recibirlos a través de [!DNL FTP].

### Solo se envían a GPT segmentos calificados

La cantidad de datos pasados a [!DNL GPT] depende de la cantidad de segmentos a los que califique un usuario en particular. Por ejemplo, supongamos que configura 100 segmentos de Audience Manager. Si el visitante de un sitio califica para cinco de ellos, entonces solo esos cinco segmentos se envían a [!DNL GPT] (no todos los 100).

>[!NOTE]
>
>No hay límites en el número de valores clave que puede enviar, pero la solicitud [!DNL Google] [!DNL URL] tiene límites en el número de caracteres que puede aceptar. Ver [Configuración de destinos y tamaños con GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integración del lado del servidor {#server-side-integration}

Póngase en contacto con el consultor del Audience Manager o con el Servicio de atención al cliente si desea configurar una integración del lado del servidor con [!DNL Google Ad Manager], mediante [!DNL GPT]. Debe proporcionar su ID de vínculo de audiencia y el ID de red de la cuenta [!DNL Google Ad Manager].

>[!IMPORTANT]
>
>Si sus páginas web ejecutan la biblioteca [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]), debe usar la integración del lado del servidor con Audience Manager. Si está en [!DNL AMP] y tiene una integración del lado del cliente con [!DNL AMP], debe migrar a la integración del lado del servidor. Póngase en contacto con su asesor Audience Manager o con el Servicio de atención al cliente para discutir la migración.

>[!MORELIKETHIS]
>
>* [Guía de referencia de API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)
