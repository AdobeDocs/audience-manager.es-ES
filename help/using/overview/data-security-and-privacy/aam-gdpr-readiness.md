---
description: Guía de preparación del RGPD para clientes Audience Manager
seo-description: Guía de preparación del RGPD para clientes Audience Manager
seo-title: Guía de preparación del RGPD para clientes Audience Manager
solution: Audience Manager
title: Guía de preparación del RGPD para clientes Audience Manager
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---


# Guía de preparación del RGPD para clientes Audience Manager (controladores de datos) {#gdpr-readiness-guidance}

El Audience Manager recomienda ser proactivo en las esferas de la gobernanza de los datos y la preparación institucional. Esto le ayudará a garantizar que los datos del consumidor se organizarán para los procesos relacionados con las solicitudes de acceso o eliminación, que los equipos estarán habilitados y habilitados para administrar estas solicitudes y que los consumidores (sujetos de datos) tendrán una experiencia positiva y diferenciada con su marca.

Como su procesador de datos, Adobe no puede proporcionar asesoramiento legal sobre los requisitos del RGPD ni sobre el proceso para obtener el consentimiento de los sujetos de datos. Consulte a su asesor legal para obtener instrucciones sobre el cumplimiento del RGPD para su organización.

## Administración de datos: Inicio que piensa en cómo se administran los datos de consumo en la instancia de Audience Manager

* Revise los distintos ID de cliente que sus equipos de mercadotecnia utilizan para identificar a los usuarios en Audience Manager, junto con las fuentes de datos en las que se almacenan. Esto optimizará el proceso de solicitudes (como eliminar o acceder), ya que determinados tipos de datos serán hash por los equipos antes de la ingestión en Audience Manager.
* Los ID de dispositivos móviles IDFA/GAID se utilizan en varios casos de uso en Audience Manager. Si utiliza el SDK de Adobe Mobile, asegúrese de enviar el ID de Experience Cloud (MID) junto con IDFA/GAID para asegurarse de que las respuestas del GDPR están completas.
* Con la definición de datos personales cada vez más amplia, las direcciones IP pueden considerarse datos personales en su región. Póngase en contacto de forma proactiva con el consultor de Adobe para ocultar el último octeto.
* Determinar una política y un proceso de validación/autenticación para confirmar la identidad de un sujeto de datos cuando realiza una solicitud de RGPD.
* Considere la posibilidad de utilizar [los controles](../../features/data-export-controls.md) de exportación de datos para bloquear la activación de audiencias a tecnologías que albergan datos personales. Por ejemplo, los segmentos con datos de terceros no deben estar sindicados a proveedores de servicio de correo electrónico. Configure un [!UICONTROL Data Export Control] para asegurarse de que nadie de su organización pueda activar accidentalmente estos datos.
* Empiece a utilizar Controles de acceso [basados en](../../features/administration/administration-overview.md) roles para garantizar que los equipos adecuados tengan acceso a los datos deseados.
* Considere períodos [de](../../faq/faq-privacy.md#data-retention-faq) retención adecuados para los datos.
* Revisar las políticas de vinculación de identidad y privacidad y los requisitos legales para ver cuándo y dónde es apropiado unir los conjuntos de identidades; utilice correctamente las reglas [de combinación de](../../features/profile-merge-rules/merge-rules-overview.md)Perfiles del Audience Manager.

## Preparación de la organización: Establecimiento de un proceso comercial

* Identifique un proceso para recibir/responder a las solicitudes del sujeto de datos. Considere la posibilidad de crear una herramienta automatizada para enviar solicitudes al Audience Manager.
* Designe un punto de contacto de privacidad dentro de su centro de excelencia de DMP. Conecte el punto de contacto de privacidad de su organización con el equipo de uso del producto Audience Manager para comprender cómo puede administrar los requisitos de ID de entrada.
* Realice una revisión de los datos antes de compartirlos con el sujeto de datos. Documento los pasos que ha puesto en marcha, para ayudarle a establecer la responsabilidad.
