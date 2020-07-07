---
description: Información general sobre cómo integrar Google Ad Manager con etiquetas de publicador de Google (GPT).
seo-description: Información general sobre cómo integrar Google Ad Manager con etiquetas de publicador de Google (GPT) en Adobe Audience Manager (AAM).
seo-title: Integrar Google Ad Manager con etiquetas de publicador de Google (GPT) en Adobe Audience Manager (AAM)
title: Integrar Google Ad Manager con etiquetas de publicador de Google (GPT)
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# Integrate [!DNL Google Ad Manager] (formerly DFP) using Google Publisher Tags (GPT)

Los artículos que se enumeran a continuación proporcionan información general sobre cómo integrar [!DNL Google Ad Manager] con etiquetas de publicador de Google (GPT). Puede utilizar una integración de servidor o configurar GPT como destino para enviar datos de segmentos de Audience Manager a [!DNL Google Ad Manager]. También aprenderá los pasos necesarios para ingerir archivos [!DNL Google Ad Manager] de registro para sistema de informes en Audience Manager.

* [Requisitos y métodos para enviar segmentos al Administrador de publicidad de Google mediante etiquetas de publicador de Google (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Puede enviar segmentos cualificados a [!DNL Google Ad Manager] través de una integración de cliente o de servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.

* [Crear un destino GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Puede enviar segmentos cualificados a [!DNL Google Ad Manager] través de una integración del lado del cliente (del navegador) o de un servidor. Si elige la integración del lado del cliente, debe crear un destino basado en cookies para Google Publisher Tags en Audience Manager.

* [Modificación de la llamada de API de setTargeting de GPT](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Añada una instrucción if para comprobar si hay cookies de Audience Manager antes de llamar al método Google Publisher Tag.setTargeting.

* [Código de Audience Manager para etiquetas de Publicador de Google](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt es una función de JavaScript que lee datos de cookies de Audience Manager y envía esa información a las etiquetas de Publicador de Google.
