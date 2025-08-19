---
description: Información general sobre cómo integrar Google Ad Manager mediante Google Publisher Tags (GPT).
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: Integración de Google Ad Manager con Google Publisher Tags (GPT)
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# Integrar [!DNL Google Ad Manager] (anteriormente DFP) mediante Google Publisher Tags (GPT)

Los artículos que se enumeran a continuación proporcionan información general sobre cómo integrar [!DNL Google Ad Manager] mediante Google Publisher Tags (GPT). Puede usar una integración del lado del servidor o configurar GPT como destino para enviar datos de segmentos de Audience Manager a [!DNL Google Ad Manager]. También aprenderá los pasos necesarios para ingerir [!DNL Google Ad Manager] archivos de registro para la generación de informes en Audience Manager.

* [Requisitos y métodos para enviar segmentos a Google Ad Manager mediante Google Publisher Tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

  Puede enviar segmentos calificados a [!DNL Google Ad Manager] mediante una integración del lado del cliente o del lado del servidor. A continuación se enumeran los requisitos e información relacionada sobre ambos métodos.

* [Crear un destino GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

  Puede enviar segmentos calificados a [!DNL Google Ad Manager] mediante una integración del lado del cliente (lado del explorador) o una integración del lado del servidor. Si elige la integración del lado del cliente, debe crear un destino basado en cookies para las etiquetas de Google Publisher en Audience Manager.

* [Modificación de la llamada de API setTargeting de GPT](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

  Agregue una instrucción if para buscar cookies de Audience Manager antes de llamar al método Google Publisher Tag .setTargeting.

* [Código Audience Manager para etiquetas de publicador de Google](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

  AamGpt es una función de JavaScript que lee datos de cookies de Audience Manager y envía esa información a las etiquetas de publicador de Google.
