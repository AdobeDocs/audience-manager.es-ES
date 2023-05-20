---
description: Guía de preparación del RGPD para clientes de Audience Manager
seo-description: GDPR Readiness Guidance for Audience Manager Customers
seo-title: GDPR Readiness Guidance for Audience Manager Customers
solution: Audience Manager
title: Guía de preparación del RGPD para clientes de Audience Manager
feature: Data Governance & Privacy
exl-id: 353b9035-20f3-41ff-819c-71f161e6b1e1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 99%

---

# Guía de preparación del RGPD para clientes de Audience Manager (Controladores de datos) {#gdpr-readiness-guidance}

Audience Manager recomienda una actitud proactiva en la administración de los datos y en la preparación de la organización. Esto contribuye a garantizar que los datos de los consumidores están bien organizados para hacer frente a solicitudes de acceso o supresión, que sus equipos estarán listos para gestionar dichas solicitudes y que sus clientes (sujetos de datos) tendrán una experiencia positiva y diferenciada con su marca.

Adobe, como responsable del procesamiento de sus datos, no puede proporcionar asesoramiento legal sobre los requisitos del RGPD ni sobre la forma de obtener el consentimiento de los sujetos de los datos. Consulte a su asesor legal en lo que respecta al cumplimiento del RGPD en su organización.

## Administración de los datos: tenga en cuenta la forma en que se administran los datos de los consumidores en la instancia de Audience Manager

* Revise los diferentes ID de cliente que utilizan sus equipos de marketing para identificar a los usuarios en Audience Manager, junto con las fuentes de datos en las que se almacenan. Esto agilizará el proceso de solicitudes (por ejemplo, de supresión o acceso), ya que sus equipos aplicarán un cifrado hash a determinados tipos de datos antes de incorporarlos en Audience Manager.
* Los identificadores IDFA y GAID de dispositivos móviles se emplean en diversos tipos de uso en Audience Manager. Si utiliza el SDK de Adobe Mobile, asegúrese de enviar el Experience Cloud ID (MID) junto con el IDFA/GAID para garantizar que las respuestas relativas al RGPD son completas.
* Como la definición de datos personales cada vez es más amplia, puede que en su área geográfica una dirección IP se considere un dato personal. Acuda al servicio de consultoría de Adobe para ocultar el último octeto.
* Determine una política y un proceso de validación y autenticación para confirmar la identidad de un sujeto de datos cuando este realiza una solicitud relacionada con el RGPD.
* Considere la opción de utilizar [Controles de exportación de datos](../../features/data-export-controls.md) para bloquear la activación de audiencias en tecnologías que albergan datos personales. Por ejemplo, los segmentos con datos de terceros no deben estar sindicados a proveedores de correo electrónico. Configure un [!UICONTROL Data Export Control] para garantizar que ningún miembro de su organización pueda activar accidentalmente estos datos.
* Introduzca el [control de acceso basado en funciones](../../features/administration/administration-overview.md) para garantizar que los equipos adecuados tengan acceso a los datos deseados.
* Aplique [periodos de retención](../../faq/faq-privacy.md#data-retention-faq) de datos adecuados.
* Revise las políticas de vinculación de identidad y de privacidad, así como los requisitos legales, para saber cuándo y dónde conviene unir los grupos de identidades. Utilice correctamente las [reglas de combinación de perfiles](../../features/profile-merge-rules/merge-rules-overview.md) de Audience Manager.

## Preparación de la organización: establezca un proceso empresarial.

* Identifique un proceso para recibir y responder a las solicitudes de los sujetos de datos. Considere la opción de crear una herramienta automatizada para enviar solicitudes a Audience Manager.
* Designe un punto de contacto sobre privacidad como atributo de excelencia de su plataforma de gestión de datos (DMP). Conecte el punto de contacto sobre privacidad de su organización con su equipo de uso de Audience Manager para averiguar la forma de administrar los requisitos de ID de entrada.
* Revise los datos antes de compartirlos con el sujeto interesado. Registre los pasos realizados; de esta manera, le resultará más fácil cumplir con su responsabilidad.
