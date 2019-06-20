---
description: Información general sobre cómo integrar DFP mediante Etiquetas de editor de Google (GPT).
seo-description: Información general sobre cómo integrar DFP con etiquetas de Google Publisher (GPT) en Adobe Audience Manager (AAM).
seo-title: Integrar DFP con etiquetas de editor de Google (GPT) en Adobe Audience Manager (AAM)
title: Integrar DFP con etiquetas de editor de Google (GPT)
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Integrar DFP con etiquetas de editor de Google (GPT)

Los artículos enumerados a continuación proporcionan información general sobre cómo integrar DFP con Etiquetas de Google Publisher (GPT). Puede utilizar una integración en el servidor o configurar GPT como destino para enviar datos de segmentos de Audience Manager al DFP. También aprenderá los pasos necesarios para ingestar los archivos de registro DFP para los informes en Audience Manager.

* [Requisitos y métodos para enviar segmentos a DFP usando Google Publisher Tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Puede enviar segmentos cualificados a DFP a través de un lado del cliente o mediante una integración del lado del servidor. A continuación se enumeran los requisitos y la información relacionada con ambos métodos.

* [Crear un destino GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Puede enviar segmentos cualificados a DFP mediante una integración del lado del cliente (lado del explorador) o una integración del lado del servidor. Si elige la integración del lado del cliente, debe crear un destino basado en cookies para etiquetas de Google Publisher en Audience Manager.

* [Modificar la llamada de API de settargeting GPT](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Agregue una sentencia if para comprobar si hay cookies de Audience Manager antes de llamar al método Google Publisher Tag. settargeting.

* [Código de Audience Manager para etiquetas de editor de Google](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   Aamgpt es una función JavaScript que lee datos de cookies de Audience Manager y envía dicha información a Etiquetas de Google Publisher.
