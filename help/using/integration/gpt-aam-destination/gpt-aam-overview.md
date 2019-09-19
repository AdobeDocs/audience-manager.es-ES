---
description: Información general sobre cómo integrar DFP mediante etiquetas de publicador de Google (GPT).
seo-description: Información general sobre cómo integrar DFP con etiquetas de publicador de Google (GPT) en Adobe Audience Manager (AAM).
seo-title: Integrar DFP con etiquetas de publicador de Google (GPT) en Adobe Audience Manager (AAM)
title: Integrar DFP con etiquetas de publicador de Google (GPT)
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Integrar DFP con etiquetas de publicador de Google (GPT)

Los artículos que se enumeran a continuación proporcionan información general sobre cómo integrar DFP mediante etiquetas de publicador de Google (GPT). Puede utilizar una integración de servidor o configurar GPT como destino para enviar datos de segmentos de Audience Manager a DFP. También aprenderá los pasos necesarios para transferir archivos de registro de DFP para crear informes en Audience Manager.

* [Requisitos y métodos para enviar segmentos a DFP usando Google Publisher Tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Puede enviar segmentos cualificados a DFP a través de una integración de cliente o de servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.

* [Crear un destino GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Puede enviar segmentos cualificados a DFP mediante una integración del lado del cliente (del navegador) o de servidor. Si elige la integración del lado del cliente, debe crear un destino basado en cookies para las etiquetas de publicador de Google en Audience Manager.

* [Modificar la llamada de API de setTargeting de GPT](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Agregue una instrucción if para comprobar las cookies de Audience Manager antes de llamar al método Google Publisher Tag.setTargeting.

* [Código de Audience Manager para etiquetas de publicador de Google](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt es una función de JavaScript que lee los datos de cookies de Audience Manager y envía esa información a Google Publisher Tags.
