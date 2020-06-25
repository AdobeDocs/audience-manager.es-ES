---
description: Esta página describe la información proporcionada directamente por nuestros socios, a medida que está disponible, junto con las implicaciones relacionadas con la práctica del Audience Manager. Las implicaciones clave para los socios que realizan estas actualizaciones son el resultado del RGPD (Reglamento General de Protección de Datos), que entró en vigor el 25 de mayo de 2018 y del nuevo Marco de Transparencia y Consentimiento del RGPD de la IAB (Marco de la IAB).
seo-description: Esta página describe la información proporcionada directamente por nuestros socios, a medida que está disponible, junto con las implicaciones relacionadas con la práctica del Audience Manager. Las implicaciones clave para los socios que realizan estas actualizaciones son el resultado del RGPD (Reglamento General de Protección de Datos), que entró en vigor el 25 de mayo de 2018 y del nuevo Marco de Transparencia y Consentimiento del RGPD de la IAB (Marco de la IAB).
seo-title: Consideraciones del RGPD para destinos
solution: Audience Manager
title: Consideraciones del RGPD para destinos
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 0%

---


# Consideraciones del RGPD para destinos{#gdpr-considerations-for-destinations}

Esta página describe la información proporcionada directamente por nuestros socios, a medida que está disponible, junto con las implicaciones relacionadas con la práctica del Audience Manager. Las implicaciones clave para los socios que realizan estas actualizaciones son el resultado del RGPD (Reglamento General de Protección de Datos), que entró en vigor el 25 de mayo de 2018 y del nuevo Marco de Transparencia y Consentimiento del RGPD de la IAB (Marco de la IAB).

Los socios de Adobe son propietarios de sus procesos empresariales y pueden decidir actualizar sus requisitos de integración con Audience Manager de vez en cuando. Estamos trabajando de manera proactiva con nuestro ecosistema de socios Audience Manager para mantener a nuestros clientes informados de los cambios.

<!-- ## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

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
</table> -->

## Actualización de la interfaz de usuario de Audience Manager: Integración de Yahoo/Oath/DataX {#ui-update}

Además de las actualizaciones del marco de trabajo de la IAB mencionadas anteriormente, Yahoo/Oath/DataX ha agregado nuevos parámetros, **gdpr** y **gdpr_mode**, a sus API de taxonomía y Audiencia. Sus parámetros informan a Yahoo/Oath/DataX de que tienen derechos para procesar un determinado segmento como procesador de datos o como controlador de datos. Como resultado, los clientes Audience Manager que envían segmentos a un destino de Yahoo/Oath/DataX deben designar el parámetro apropiado (Procesador o Controlador), según su acuerdo con el juramento.

Póngase en contacto con el consultor o con Client Care para establecer el parámetro correcto. Adobe no puede realizar esta actualización en nombre de un cliente a menos que recibamos una correspondencia por escrito en la que se solicite esta actualización. Comuníquese con el representante de Yahoo/Oath/DataX para comprender la definición completa de estos parámetros.
