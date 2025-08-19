---
description: Puede enviar segmentos calificados a Google Ad Manager mediante una integración lado del cliente o del lado del servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.
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

# Requisitos y métodos para enviar segmentos a Google Ad Manager utilizando Google Publisher Tags (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Puede enviar segmentos cualificados a [!DNL Google Ad Manager] (anteriormente DFP) mediante una integración lado del cliente o del lado del servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.

## Integración del lado del cliente {#client-side-integration}

Para una integración lado del cliente, debe configurar un [!DNL GPT] destino en Audience Manager. Tenga en cuenta los siguientes puntos cuando desee configurar [!DNL GPT] como destino Audience Manager:

* **[!UICONTROL DIL]añadir :** Implemente [!UICONTROL Data Integration Library (DIL)] el código en todas las páginas que desee destino. [!UICONTROL DIL] escribe Audience Manager datos de segmento e ID de usuario en cookies que utilizan [!DNL GPT] para direccionamiento.

* **Crear a [!UICONTROL Cookie Destination]:** [!DNL GPT] debe configurarse como destino basado en cookie en Audience Manager.

* **Implementar el Code de comprobación de cookies:** Envuelva el [!DNL GPT] `.setTargeting` método API en nuestro código[ de comprobación de cookie recomendado](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). Este código ayuda a evitar errores al buscar cookies de AAM válidas antes de invocar el `.setTargeting` método.

* **añadir la `AamGpt` función:** El `AamGpt` código captura datos de Audience Manager cookies y los envía a [!DNL GPT]. Coloque el [Code Audience Manager de las etiquetas](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) de editor de Google ( `AamGpt`) en la parte superior del Página o dentro del `<head>` bloque de código.

  >[!NOTE]
  >
  >La `AamGpt` función no es necesaria si utiliza su propio código para leer Audience Manager cookie datos.

* **Enviar registros de envío a Audience Manager:** Si desea un segmento envío informe (opcional), proporcione a Audience Manager un registro diario que contenga datos de envío de nivel impresión. Los datos pueden estar en un formato sin procesar, pero cada registro debe contener el Audience Manager `UUID`. Audience Manager pueden recogerlos o recibirlos a través de [!DNL FTP].

### Solo los segmentos calificados se envían a GPT

La cantidad de datos a los que se pasa [!DNL GPT] depende de la cantidad de segmentos para los que una usuario en particular califique. Por ejemplo, supongamos que configura 100 segmentos Audience Manager. Si un visitante del sitio califica para cinco de ellos, entonces solo se envían esos cinco segmentos ( [!DNL GPT] no todos los 100).

>[!NOTE]
>
>No hay límites para el número de valores clave que puede enviar, pero el [!DNL Google] solicitud [!DNL URL] tiene límites para el número de caracteres que puede aceptar. Consulte [Configuración de direccionamiento y tamaños con GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Integración del lado del servidor {#server-side-integration}

Póngase en contacto con su consultor Audience Manager o con el Servicio de atención al cliente si desea configurar una del lado del servidor integración con [!DNL Google Ad Manager], mediante [!DNL GPT]. Deberá proporcionar el ID de red de cuenta y el [!DNL Google Ad Manager] ID de vínculo de audiencia.

>[!IMPORTANT]
>
>Si las páginas web ejecutan el [biblioteca Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]), debe utilizar la integración del lado del servidor con Audience Manager. Si está en [!DNL AMP] y tiene una integración lado del cliente con [!DNL AMP], debe migrar a la integración de del lado del servidor. Póngase en contacto con su asesor Audience Manager o con el Servicio de atención al cliente para hablar sobre la migración.

>[!MORELIKETHIS]
>
>* [Guía de referencia de API de GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)
