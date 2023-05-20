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
source-wordcount: '481'
ht-degree: 0%

---

# Requisitos y métodos para enviar segmentos a Google Ad Manager mediante etiquetas de publicador de Google ( GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Puede enviar segmentos cualificados a [!DNL Google Ad Manager] (anteriormente DFP) a través de una integración del lado del cliente o del lado del servidor. A continuación se enumeran los requisitos e información relacionada sobre ambos métodos.

## Integración del lado del cliente {#client-side-integration}

Para una integración del lado del cliente, debe configurar un [!DNL GPT] destino en Audience Manager. Tenga en cuenta los siguientes puntos cuando desee configurar [!DNL GPT] como destino de Audience Manager:

* **Añadir [!UICONTROL DIL]:** Implementar [!UICONTROL Data Integration Library (DIL)] en todas las páginas a las que desee dirigirse. [!UICONTROL DIL] escribe datos de segmentos de Audience Manager e ID de usuarios en cookies que utiliza [!DNL GPT] para la segmentación.

* **Crear un [!UICONTROL Cookie Destination]:** [!DNL GPT] debe configurarse como un destino basado en cookies en Audience Manager.

* **Implementar código de comprobación de cookies:** Ajuste el [!DNL GPT] `.setTargeting` Método de API en nuestros [código de comprobación de cookies](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). AAM Este código ayuda a evitar errores al buscar cookies de válidas antes de la `.setTargeting` método se invoca.

* **Añada el `AamGpt` Función:** El `AamGpt` El código de captura datos de las cookies del Audience Manager y los envía a [!DNL GPT]. Coloque el [Código de Audience Manager para etiquetas de publicador de Google](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`), en la parte superior de la página o dentro del `<head>` bloque de código.

   >[!NOTE]
   >
   >El `AamGpt` no es necesaria si utiliza su propio código para leer datos de cookies de Audience Manager.

* **Enviar registros de envío al Audience Manager:** Si desea un informe de entrega de segmentos (opcional), proporcione al Audience Manager un registro diario que contenga datos de entrega en el nivel de impresión. Los datos pueden estar en formato sin procesar, pero cada registro debe contener el Audience Manager `UUID`. El Audience Manager puede recogerlos o recibirlos a través de [!DNL FTP].

### Solo se envían a GPT segmentos calificados

Cantidad de datos pasados a [!DNL GPT] depende de los segmentos a los que pertenezca un usuario en particular. Por ejemplo, supongamos que configura 100 segmentos de Audience Manager. Si el visitante de un sitio cumple los requisitos para cinco de ellos, solo se envían esos cinco segmentos a [!DNL GPT] (no todos los 100).

>[!NOTE]
>
>No hay límites en la cantidad de valores clave que puede enviar, pero la variable [!DNL Google] solicitud [!DNL URL] tiene límites en el número de caracteres que puede aceptar. Consulte [Configuración de objetivos y tamaños con GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integración del lado del servidor {#server-side-integration}

Póngase en contacto con su asesor de Audience Manager o con el Servicio de atención al cliente si desea configurar una integración del lado del servidor con [!DNL Google Ad Manager], usando [!DNL GPT]. Tendrá que proporcionar su [!DNL Google Ad Manager] ID de red de la cuenta e ID de vínculo de audiencia.

>[!IMPORTANT]
>
>Si las páginas web ejecutan el [Páginas de medios acelerados](https://www.ampproject.org/) ([!DNL AMP]), debe utilizar la integración del lado del servidor con Audience Manager. Si está en [!DNL AMP] y tengan una integración de cliente con [!DNL AMP], debe migrar a la integración del lado del servidor. Póngase en contacto con su asesor Audience Manager o con el Servicio de atención al cliente para discutir la migración.

>[!MORELIKETHIS]
>
>* [Guía de referencia de API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

