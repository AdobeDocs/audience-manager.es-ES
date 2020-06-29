---
description: Puede enviar segmentos cualificados a DFP a través de una integración de cliente o de servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.
seo-description: Puede enviar segmentos cualificados a DFP a través de una integración de cliente o de servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.
seo-title: Requisitos y métodos para enviar segmentos a DFP usando Google Publisher Tags (GPT)
solution: Audience Manager
title: Requisitos y métodos para enviar segmentos a DFP usando Google Publisher Tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 7%

---


# Requisitos y métodos para enviar segmentos a DFP usando Google Publisher Tags (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Puede enviar segmentos cualificados a [!DNL DFP] través de una integración de cliente o de servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.

## Integración del cliente {#client-side-integration}

Para una integración de cliente, debe configurar un [!DNL GPT] destino en Audience Manager. Tenga en cuenta los siguientes puntos cuando desee configurar [!DNL GPT] como destino de Audience Manager:

* **Añadir[!UICONTROL DIL]:** Implemente [!UICONTROL Data Integration Library (DIL)] código en todas las páginas que desee destinatario. [!UICONTROL DIL] escribe datos de segmentos de Audience Manager e ID de usuario en cookies que se utilizan [!DNL GPT] para la segmentación.

* **Crear un[!UICONTROL Cookie Destination]:** [!DNL GPT] debe configurarse como un destino basado en cookies en Audience Manager.

* **Implementar código de comprobación de cookies:** Ajuste el [!DNL GPT] método de API en nuestro código `.setTargeting` de comprobación de [](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)cookies recomendado. Este código ayuda a evitar errores al buscar cookies AAM válidas antes de que se invoque el `.setTargeting` método.

* **Añada la`AamGpt`Función:** El `AamGpt` código captura datos de cookies de Audience Manager y los envía a [!DNL GPT]. Coloque el código de [Audience Manager para las etiquetas](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) de publicador de Google ( `AamGpt`) en la parte superior de la página o dentro del bloque de `<head>` código.

   >[!NOTE]
   >
   >La `AamGpt` función no es necesaria si utiliza su propio código para leer datos de cookies Audience Manager.

* **Enviar Registros de envío al Audience Manager:** Si desea un informe de envío de segmentos (opcional), proporcione al Audience Manager un registro diario que contenga datos de envío de nivel de impresión. Los datos pueden tener un formato sin procesar, pero cada registro debe contener al Audience Manager `UUID`. El Audience Manager puede recogerlos o recibirlos a través de [!DNL FTP].

### Solo se envían segmentos cualificados a GPT

La cantidad de datos pasados [!DNL GPT] depende de la cantidad de segmentos para los que un usuario en particular cumpla los requisitos. Por ejemplo, supongamos que configura 100 segmentos de Audience Manager. Si un visitante del sitio cumple los requisitos para cinco de ellos, solo se envían a esos cinco segmentos [!DNL GPT] (no a todos los 100).

>[!NOTE]
>
>No hay límites para el número de valores clave que puede enviar, pero la [!DNL Google] solicitud [!DNL URL] tiene límites para el número de caracteres que puede aceptar. Consulte [Configuración de objetivos y tamaños con GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integración del lado del servidor {#server-side-integration}

Póngase en contacto con el consultor de Audience Manager o con el Servicio de atención al cliente si desea configurar una integración del lado del servidor con [!DNL DFP], mediante [!DNL GPT]. Deberá proporcionar el ID de red y el ID de vínculo de Audiencia de su [!DNL DFP] cuenta.

>[!IMPORTANT]
>
>Si las páginas web están ejecutando la biblioteca [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]), debe utilizar la integración del lado del servidor con Audience Manager. Si se encuentra en [!DNL AMP] y dispone de una integración de cliente con [!DNL AMP], debe migrar a la integración de servidor. Comuníquese con el consultor de Audience Manager o con el Servicio de atención al cliente para analizar la migración.

>[!MORELIKETHIS]
>
>* [Guía de referencia de API de GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

