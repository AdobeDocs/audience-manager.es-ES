---
description: Puede enviar segmentos cualificados a Google Ad Manager a través de una integración del lado del cliente o del servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.
seo-description: Puede enviar segmentos cualificados a Google Ad Manager a través de una integración del lado del cliente o del servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.
seo-title: Requisitos y métodos para enviar segmentos a Google Ad Manager usando Google Publisher Tags (GPT)
solution: Audience Manager
title: Requisitos y métodos para enviar segmentos a Google Ad Manager usando Google Publisher Tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Requisitos y métodos para enviar segmentos a Google Ad Manager usando Google Publisher Tags (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Puede enviar segmentos calificados a [!DNL Google Ad Manager] (anteriormente DFP) a través de una integración del lado del cliente o del lado del servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.

## Integración del lado del cliente {#client-side-integration}

Para una integración del lado del cliente, debe configurar un destino [!DNL GPT] en Audience Manager. Tenga en cuenta los siguientes puntos cuando desee configurar [!DNL GPT] como destino de Audience Manager:

* **Agregar  [!UICONTROL DIL]:** implemente  [!UICONTROL Data Integration Library (DIL)] código en todas las páginas a las que desee dirigirse. [!UICONTROL DIL] escribe datos de segmentos de Audience Manager e ID de usuario en cookies que se utilizan  [!DNL GPT] para la segmentación.

* **Crear un  [!UICONTROL Cookie Destination]:** [!DNL GPT]  debe configurarse como un destino basado en cookies en Audience Manager.

* **Implementar código de comprobación de cookies:** ajuste el método de  [!DNL GPT] `.setTargeting` API en el código de comprobación de  [cookies](../../integration/gpt-aam-destination/gpt-aam-modify-api.md) recomendado. Este código ayuda a evitar errores al buscar cookies de AAM válidas antes de que se invoque el método `.setTargeting` .

* **Añadir la  `AamGpt` función:** el  `AamGpt` código captura datos de las cookies del Audience Manager y los envía a  [!DNL GPT]. Coloque el [Código de Audience Manager para etiquetas de publicador de Google](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) en la parte superior de la página o dentro del bloque de código `<head>`.

   >[!NOTE]
   >
   >La función `AamGpt` no es necesaria si utiliza su propio código para leer los datos de cookies del Audience Manager.

* **Envío de registros de envío al Audience Manager:** si desea un informe de envío de segmento (opcional), proporcione al Audience Manager un registro diario que contenga datos de envío de nivel de impresión. Los datos pueden tener un formato sin procesar, pero cada registro debe contener el Audience Manager `UUID`. El Audience Manager puede recogerlas o recibirlas a través de [!DNL FTP].

### Solo se envían segmentos aptos a GPT

La cantidad de datos pasados a [!DNL GPT] depende de cuántos segmentos califica un usuario en particular. Por ejemplo, supongamos que configura 100 segmentos de Audience Manager. Si el visitante de un sitio cumple los requisitos para cinco de ellos, solo esos cinco segmentos se envían a [!DNL GPT] (no todos los 100).

>[!NOTE]
>
>No hay límites en el número de valores clave que puede enviar, pero la solicitud [!DNL Google] [!DNL URL] tiene límites en el número de caracteres que puede aceptar. Consulte [Configuración de objetivos y tamaños con GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integración del lado del servidor {#server-side-integration}

Hable con su asesor de Audience Manager o con el Servicio de atención al cliente si desea configurar una integración del lado del servidor con [!DNL Google Ad Manager] mediante [!DNL GPT]. Deberá proporcionar su [!DNL Google Ad Manager] cuenta de ID de red e ID de vínculo de audiencia.

>[!IMPORTANT]
>
>Si las páginas web ejecutan la biblioteca [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]), debe utilizar la integración del lado del servidor con el Audience Manager. Si se encuentra en [!DNL AMP] y tiene una integración del lado del cliente con [!DNL AMP], debe migrar a la integración del lado del servidor. Póngase en contacto con su asesor de Audience Manager o con el Servicio de atención al cliente para analizar la migración.

>[!MORELIKETHIS]
>
>* [Guía de referencia de API de GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

