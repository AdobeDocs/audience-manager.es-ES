---
description: Información general sobre cómo integrar Google Ad Manager mediante Google Publisher Tags (GPT).
seo-description: Información general sobre cómo integrar Google Ad Manager mediante Google Publisher Tags (GPT) en Adobe Audience Manager (AAM).
seo-title: Integrar Google Ad Manager con Google Publisher Tags (GPT) en Adobe Audience Manager (AAM)
title: Integrar Google Ad Manager con Google Publisher Tags (GPT)
feature: Integración de terceros
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# Integrar [!DNL Google Ad Manager] (anteriormente DFP) con Google Publisher Tags (GPT)

Los artículos que se enumeran a continuación proporcionan información general sobre cómo integrar [!DNL Google Ad Manager] mediante Google Publisher Tags (GPT). Puede utilizar una integración del lado del servidor o configurar GPT como destino para enviar datos de segmento del Audience Manager a [!DNL Google Ad Manager]. También aprenderá los pasos necesarios para ingerir [!DNL Google Ad Manager] archivos de registro para generar informes en Audience Manager.

* [Requisitos y métodos para enviar segmentos a Google Ad Manager usando Google Publisher Tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Puede enviar segmentos calificados a [!DNL Google Ad Manager] a través de una integración del lado del cliente o del lado del servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.

* [Crear un destino GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Puede enviar segmentos calificados a [!DNL Google Ad Manager] a través de una integración del lado del cliente (del lado del explorador) o del lado del servidor. Si elige la integración del lado del cliente, debe crear un destino basado en cookies para Google Publisher Tags en Audience Manager.

* [Modificación de la llamada de API de setTargeting de GPT](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Agregue una instrucción if para comprobar si hay cookies de Audience Manager antes de llamar al método Google Publisher Tag .setTargeting .

* [Código de Audience Manager para etiquetas de Publicador de Google](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt es una función de JavaScript que lee datos de cookies de Audience Manager y envía esa información a Google Publisher Tags.
