---
description: Describe la integración de Audience Manager y el cumplimiento de las prácticas recomendadas generalmente aceptadas en relación con los procedimientos de privacidad del consumidor y exclusión.
seo-description: Describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.
seo-title: Data Privacy Overview
solution: Audience Manager
title: Información general sobre la privacidad de datos
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: Data Governance & Privacy
exl-id: 051de369-e762-49fb-b65f-6faf94db48a4
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 68%

---

# Información general sobre la privacidad de datos {#data-privacy}

## Información general

La documentación de privacidad de datos describe [!DNL Audience Manager] integración y cumplimiento de las prácticas recomendadas generalmente aceptadas en relación con los procedimientos de privacidad del consumidor y exclusión.

[!DNL Audience Manager] reconoce la importancia de la relación que existe entre los consumidores y las marcas en línea con las que interactúan. Ambas partes se benefician del intercambio transparente de elementos de datos seudónimos:

* Los consumidores reciben un contenido personalizado, ofertas de productos con descuento y experiencias de usuario optimizadas.
* Las marcas reciben flujos de ingresos fundamentales, compatibles con diversos modelos de comercio en línea.

En nuestro continuo apoyo a este modelo, [!DNL Audience Manager] mantiene su compromiso de proporcionarle las herramientas necesarias para que pueda proporcionar transparencia y control a los consumidores, enviando publicidad personalizada sujeta a la [Principios de autorregulación de la publicidad en línea basada en el comportamiento (OBA)](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/).

## [!DNL GDPR] {#gdpr}

El [Reglamento General de Protección de Datos (RGPD)](https://gdpr.eu/data-privacy/) incluyó nuevos derechos sobre privacidad de datos para los miembros de la Unión Europea, como el **derecho de acceso** y el **derecho al olvido**. Esto significa que cualquier [!DNL EU] Los ciudadanos cuyos datos personales hayan sido recopilados por su empresa pueden solicitar el acceso o la eliminación de sus datos en cualquier momento. El incumplimiento de estas solicitudes puede resultar en multas de varios millones de dólares para su organización.

Para cumplir con [!DNL GDPR], [!DNL Audience Manager] admite acceso a datos y eliminación [solicitudes](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

La [Ley de Privacidad del Consumidor de California (CCPA)](https://www.caprivacy.org/about), que entró en vigor el 1 de enero de 2020, otorga a los residentes de California nuevos derechos con respecto a su información personal e impone obligaciones de protección de datos a ciertas entidades que llevan a cabo actividades comerciales en California.

[!DNL CCPA]La concede nuevos derechos de privacidad de datos a los residentes de California, como el derecho a acceder y eliminar datos personales y a saber si estos son vendidos o revelados (y a quién). Para cumplir con [!DNL CCPA], [!DNL Audience Manager] admite [!DNL CCPA] acceso y eliminación [solicitudes](data-privacy-requests.md).

Consulte el [Centro de privacidad de Adobe](https://www.adobe.com/es/privacy/opt-out.html) para obtener más información.

## Cumplimiento de normas {#compliance}

[!DNL Audience Manager] le ayuda a cumplir con las obligaciones derivadas de determinadas normas de privacidad, gracias a herramientas de privacidad como [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) para gestionar las solicitudes de acceso y eliminación de datos.

Este servicio proporciona una interfaz de usuario y una [!DNL RESTful API] para ayudarle a administrar las solicitudes de datos de los clientes. Mediante [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en), puede enviar solicitudes para acceder a datos personales y eliminarlos, de acuerdo a la solicitud presentada por un cliente. Así se facilita la automatización de esta parte de las obligaciones que establece la normativa.

Mientras que las solicitudes de acceso y eliminación de datos se gestionan a través del Privacy Service, [solicitudes de exclusión](data-privacy-requests.md#opt-out-requests) son compatibles actualmente mediante el [API de DCS](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md). Consulte [Solicitudes sobre privacidad de datos](data-privacy-requests.md) para obtener más información.

## Conceptos relacionados {#related-concepts}

* [Solicitudes de privacidad de datos](data-privacy-requests.md)
* [Gestión del consentimiento](data-privacy-consent.md)
* [Complemento de Audience Manager para el TCF de IAB](aam-iab-plugin.md)
* [Identificadores de Audience Manager](data-privacy-ids.md)
* [Glosario de la CCPA](aam-ccpa-glossary.md)
* [Glosario del RGPD](aam-gdpr-glossary.md)
* [Consideraciones del RGPD para destinos](aam-gdpr-partners.md)
* [Guía de preparación del RGPD para clientes de Audience Manager](aam-gdpr-readiness.md)
* [Administración de datos](data-governance.md)
* [Preguntas frecuentes sobre la privacidad y retención de datos](../../faq/faq-privacy.md)
