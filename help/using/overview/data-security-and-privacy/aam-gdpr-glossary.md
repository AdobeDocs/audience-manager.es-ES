---
description: En este artículo se explican los conceptos y la terminología utilizados por El Reglamento general de protección de datos (RGPD) y cómo Adobe Audience Manager, como procesador de datos, aborda los distintos requisitos del RGPD.
seo-description: This article explains the concepts and terminology used by the European General Data Protection Regulation (GDPR), and how Adobe Audience Manager, as a Data Processor, addresses various GDPR requirements.
seo-title: GDPR Glossary
solution: Audience Manager
title: Glosario del RGPD
uuid: e52cad27-6a44-45ee-8524-6080adb86cc8
feature: Data Governance & Privacy
exl-id: 36930703-745e-4fbd-ad18-ba9efb77eb7e
TQID: https://experienceleague.adobe.com/8Q7X36aX-rauQ64-8TFvZ5tEacTRcJooD-VPVMLW5cM
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: c814092e-2730-45e8-a12d-e084529f52cb
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 678
ht-degree: 96%

---

# Glosario del RGPD {#gdpr-glossary}

## Información general {#overview}

En este artículo se explican los conceptos y la terminología utilizados por El Reglamento general de protección de datos (RGPD) y cómo Adobe Audience Manager, como procesador de datos, aborda los distintos requisitos del RGPD.

El RGPD entró en vigor el 25 de mayo de 2018 con el objetivo primordial de dar a las personas en la UE (sujetos de datos) un mayor control sobre sus datos personales y, al mismo tiempo, simplificar el entorno regulador de las empresas internacionales unificando mejor la regulación dentro de la UE. Como parte de la preparación de Adobe para el RGPD, el equipo de Adobe Audience Manager ha mejorado los servicios y procesos según sea necesario para admitir el acceso y la eliminación de solicitudes de los sujetos de datos, sus consumidores.

Asegúrese de leer también acerca del RGPD en la [descripción general de las regulaciones de privacidad](https://experienceleague.adobe.com/docs/experience-platform/privacy/regulations/overview.html?lang=en) para comprender mejor cómo funciona el RGPD en Experience Cloud.

## Glosario del RGPD {#gdpr-glossay}

Familiarícese con los términos clave utilizados en relación con el RGPD. Seguidamente, subrayamos algunos de los términos más utilizados.

 

**Controlador de datos:** El RGPD define “Controlador” como “la persona jurídica que, por sí sola o conjuntamente con otros, determina los fines y medios del tratamiento de datos personales”. Los clientes de Audience Manager son controladores de datos. Los clientes controlan cómo se administran los datos en Audience Manager.

 

**Procesador de datos:** El “procesador” es “la persona jurídica que procesa los datos personales en nombre del controlador”. En el contexto de Audience Manager, Adobe, al operar el servicio, actúa como “Procesador de datos” para cualquier dato personal que procesa por cuenta del Controlador, a través de Audience Manager. Adobe solo procesa los datos personales de acuerdo con las instrucciones del controlador de datos (según lo establecido en nuestro acuerdo con el cliente o mediante acciones realizadas en Audience Manager).

 

**Sujeto de datos:** Persona con la que se relacionan los datos personales. En el contexto de Audience Manager, los sujetos de datos son consumidores o usuarios finales del cliente de Audience Manager. Si Adobe recibe solicitudes directamente de los sujetos de datos, estas solicitudes se reenviarán a los clientes correspondientes de Audience Manager.

 

**Consentimiento:** Consentimiento significa que “toda indicación libre, específica, informada e inequívoca de los deseos del interesado, con la cual, mediante una declaración o una acción afirmativa clara, se manifiesta el acuerdo con el tratamiento de los datos personales que le conciernan”. El consentimiento es responsabilidad del Controlador de datos, no de Adobe (a través de Audience Manager).

 

**Acceso:** Los Sujetos de datos tienen derecho a solicitar al Controlador de datos que confirme si se están procesando sus datos personales. Cuando el controlador de datos procesa los datos personales del interesado, debe proporcionar acceso a los datos personales y una copia de ellos. Los Controladores de datos pueden solicitar a Adobe ayuda con las solicitudes de acceso de los Sujetos de datos.

 

**Eliminación:** El RGPD describe el “Derecho al olvido” o el “Derecho de eliminación”. Los sujetos de datos tienen el derecho de exigir a los Controladores que borren sus datos personales. Los Controladores de datos trabajan con sus Procesadores, incluido Adobe, para admitir solicitudes de eliminación de parte de Sujetos de datos.

 

**Corrección:** Los Sujetos de datos tienen el derecho de exigir a los Controladores que corrijan datos personales inexactos. Los Controladores de datos trabajan con sus Procesadores, incluido Adobe, para admitir solicitudes de corrección de parte de Sujetos de datos.

 

**Identificadores (ID) de Audience Manager:** Adobe Audience Manager almacena varios tipos de ID. La página [Identificadores de Audience Manager](data-privacy-ids.md) proporciona un resumen de estos ID, sus fuentes de datos correspondientes y breves descripciones. Al enviar solicitudes al [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en), haga referencia a estos ID para realizar solicitudes de eliminación o acceso a los temas de datos.

 

**Datos personales:** El RGPD amplía la definición de datos personales. En el RGPD, cualquier dato de Audience Manager puede clasificarse como datos personales según el caso de uso del cliente.

 

**Datos prohibidos:** Audience Manager prohíbe a los clientes la ingesta de información de identificación directa, como el nombre y apellidos, el ID de correo electrónico o el ID de CRM, que puede utilizarse para identificar directamente a un individuo. Las soluciones de Adobe Experience Cloud también prohíben la información confidencial. Consulte su contrato con Adobe para obtener más información sobre estos requisitos. Si es necesario ingerir estos tipos de puntos de datos en Audience Manager, póngase en contacto con su equipo de consultoría de Adobe para obtener recomendaciones sobre cómo cifrar con hash estos ID antes de ingerirlos.
