---
description: Información general sobre cómo integrar Google Ad Manager mediante Google Publisher Tags (GPT).
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: Integración de Google Ad Manager con Google Publisher Tags (GPT)
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
TQID: https://experienceleague.adobe.com/29V5C3MbEondd3-qWLBfi3jaGid1I1UM9nYIl9nZWVo
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baaid: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2: id: a49258d4-867f-4130-b875-d72c001bdf6c
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 212
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
