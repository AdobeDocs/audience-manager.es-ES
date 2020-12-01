---
description: Puede enviar segmentos cualificados al Administrador de publicidad de Google a través de una integración de cliente o de servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.
seo-description: Puede enviar segmentos cualificados al Administrador de publicidad de Google a través de una integración de cliente o de servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.
seo-title: Requisitos y métodos para enviar segmentos al Administrador de publicidad de Google mediante etiquetas de publicador de Google (GPT)
solution: Audience Manager
title: Requisitos y métodos para enviar segmentos al Administrador de publicidad de Google mediante etiquetas de publicador de Google (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---


# Requisitos y métodos para enviar segmentos al Administrador de publicidad de Google mediante etiquetas de publicador de Google ( GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Puede enviar segmentos calificados a [!DNL Google Ad Manager] (anteriormente DFP) a través de una integración de cliente o de servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.

## Integración del lado del cliente {#client-side-integration}

Para una integración de cliente, debe configurar un destino [!DNL GPT] en Audience Manager. Tenga en cuenta los siguientes puntos cuando desee configurar [!DNL GPT] como destino de Audience Manager:

* **Añadir  [!UICONTROL DIL]:** Implementar  [!UICONTROL Data Integration Library (DIL)] código en todas las páginas que desee destinatario. [!UICONTROL DIL] escribe datos de segmentos de Audience Manager e ID de usuario en cookies que se utilizan  [!DNL GPT] para la segmentación.

* **Crear un  [!UICONTROL Cookie Destination]:** [!DNL GPT] debe configurarse como destino basado en cookies en Audience Manager.

* **Implementar código de comprobación de cookies:** ajuste el método  [!DNL GPT] `.setTargeting` API en el código [ de comprobación de ](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)cookies recomendado. Este código ayuda a evitar errores al buscar cookies AAM válidas antes de que se invoque el método `.setTargeting`.

* **Añadir la  `AamGpt` función:** el  `AamGpt` código captura datos de cookies de Audience Manager y los envía a  [!DNL GPT]. Coloque el [Código de Audience Manager para etiquetas](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) de Publicador de Google ( `AamGpt`) en la parte superior de la página o dentro del bloque de código `<head>`.

   >[!NOTE]
   >
   >La función `AamGpt` no es necesaria si utiliza su propio código para leer datos de cookies del Audience Manager.

* **Enviar Registros de envío al Audience Manager:** si desea un informe de envío de segmentos (opcional), proporcione al Audience Manager un registro diario que contenga datos de envío de nivel de impresión. Los datos pueden tener un formato sin procesar, pero cada registro debe contener el Audience Manager `UUID`. El Audience Manager puede recoger o recibir estos datos a través de [!DNL FTP].

### Solo se envían segmentos cualificados a GPT

La cantidad de datos pasados a [!DNL GPT] depende de la cantidad de segmentos para los que un usuario en particular califique. Por ejemplo, supongamos que configura 100 segmentos de Audience Manager. Si un visitante del sitio cumple los requisitos para cinco de ellos, sólo esos cinco segmentos se envían a [!DNL GPT] (no todos los 100).

>[!NOTE]
>
>No hay límites para el número de valores clave que puede enviar, pero la solicitud [!DNL Google] [!DNL URL] tiene límites para el número de caracteres que puede aceptar. Consulte [Configuración de objetivos y tamaños con GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integración del lado del servidor {#server-side-integration}

Si desea configurar una integración del lado del servidor con [!DNL Google Ad Manager] mediante [!DNL GPT], póngase en contacto con su asesor Audience Manager o con el Servicio de atención al cliente. Deberá proporcionar su [!DNL Google Ad Manager] ID de red de cuenta y su ID de vínculo de Audiencia.

>[!IMPORTANT]
>
>Si las páginas Web están ejecutando la biblioteca [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]), debe utilizar la integración del lado del servidor con Audience Manager. Si está en [!DNL AMP] y tiene una integración de cliente con [!DNL AMP], debe migrar a la integración de servidor. Comuníquese con el consultor de Audience Manager o con el Servicio de atención al cliente para analizar la migración.

>[!MORELIKETHIS]
>
>* [Guía de referencia de API de GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

