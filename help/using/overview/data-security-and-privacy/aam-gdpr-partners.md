---
description: Esta página incluye la información proporcionada directamente por nuestros socios, a medida que está disponible, junto con las implicaciones relacionadas con el uso de Audience Manager. Las implicaciones clave para los socios que realizan estas actualizaciones son el resultado del RGPD (Reglamento General de Protección de Datos), vigente desde el 25 de mayo de 2018 y del nuevo Marco de transparencia y consentimiento del RGPD de la IAB (Marco de la IAB).
seo-description: This page outlines information provided directly by our partners, as it becomes available, along with any implications related to your Audience Manager practice. Key implications for partners making these updates are the result of GDPR (General Data Protection Regulation), which went into effect on May 25th, 2018 and the new IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: GDPR Considerations for Destinations
solution: Audience Manager
title: Consideraciones del RGPD para destinos
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: Data Governance & Privacy
exl-id: ff2aa030-94cd-45dc-a9a2-283b38ab5e46
TQID: https://experienceleague.adobe.com/QJr4SR9ZcwBH-xkX-0CJ23GQ09SDmkgTeN7Vl4djSb4
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 3c88464c2249b7848c9ae80ca4c0ed58fcb81070
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 96%

---

# Consideraciones del RGPD para destinos{#gdpr-considerations-for-destinations}

Esta página incluye la información proporcionada directamente por nuestros socios, a medida que está disponible, junto con las implicaciones relacionadas con el uso de Audience Manager. Las implicaciones clave para los socios que realizan estas actualizaciones son el resultado del RGPD (Reglamento General de Protección de Datos), vigente desde el 25 de mayo de 2018 y del nuevo Marco de transparencia y consentimiento del RGPD de la IAB (Marco de la IAB).

Los socios de Adobe son propietarios de sus procesos comerciales y pueden decidir actualizar sus requisitos de integración con Audience Manager periódicamente. Estamos trabajando proactivamente con los socios de Audience Manager para mantener informados a nuestros clientes sobre todos los cambios.

<!--
## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

Some partners, as listed in the table below, have changed their integration requirements with Audience Manager to include support based on the IAB Framework, in order to comply with GDPR standards.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Partner Name </p> </th> 
   <th colname="col2" class="entry"> <p>Expected Impact </p> </th> 
   <th colname="col3" class="entry"> <p>Status of the change </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Live since May 22nd 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trade Desk </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
 </tbody> 
</table>
-->

## Actualización de la interfaz de usuario de Audience Manager: integración de Yahoo/Oath/DataX {#ui-update}

Además de las actualizaciones del marco de la IAB mencionadas anteriormente, Yahoo/Oath/DataX ha añadido nuevos parámetros, **gdpr** y **gdpr_mode**, a sus API de taxonomía y audiencias. Sus parámetros informan a Yahoo/Oath/DataX de que tienen derechos para procesar un determinado segmento como procesador de datos o como controlador de datos. Como resultado, los clientes de Audience Manager que envían segmentos a un destino de Yahoo/Oath/DataX deben designar el parámetro adecuado (Procesador o Controlador), según su acuerdo con Oath.

Póngase en contacto con el consultor o con Atención al cliente para establecer el parámetro correcto. Adobe no puede realizar esta actualización en nombre de un cliente a menos que recibamos una correspondencia por escrito en la que se solicite dicha actualización. Póngase en contacto con el representante de Yahoo/Oath/DataX para entender la definición completa de estos parámetros.
