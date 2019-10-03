---
description: Esta página describe la información proporcionada directamente por nuestros socios, a medida que está disponible, junto con las implicaciones relacionadas con la práctica de Audience Manager. Las implicaciones clave para los socios que realizan estas actualizaciones son el resultado del RGPD (Reglamento General de Protección de Datos), que entró en vigor el 25 de mayo de 2018 y del nuevo Marco de Transparencia y Consentimiento del RGPD de la IAB (Marco de IAB).
seo-description: Esta página describe la información proporcionada directamente por nuestros socios, a medida que está disponible, junto con las implicaciones relacionadas con la práctica de Audience Manager. Las implicaciones clave para los socios que realizan estas actualizaciones son el resultado del RGPD (Reglamento General de Protección de Datos), que entró en vigor el 25 de mayo de 2018 y del nuevo Marco de Transparencia y Consentimiento del RGPD de la IAB (Marco de IAB).
seo-title: Consideraciones del RGPD para destinos
solution: Audience Manager
title: Consideraciones del RGPD para destinos
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: c238a37e1a72edb0679f657d0178e04b8d848ec2

---


# Consideraciones del RGPD para destinos{#gdpr-considerations-for-destinations}

Esta página describe la información proporcionada directamente por nuestros socios, a medida que está disponible, junto con las implicaciones relacionadas con la práctica de Audience Manager. Las implicaciones clave para los socios que realizan estas actualizaciones son el resultado del RGPD (Reglamento General de Protección de Datos), que entró en vigor el 25 de mayo de 2018 y del nuevo Marco de Transparencia y Consentimiento del RGPD de la IAB (Marco de IAB).

Los socios de Adobe son propietarios de sus procesos empresariales y pueden decidir actualizar sus requisitos de integración con Audience Manager de vez en cuando. Estamos trabajando de forma proactiva con nuestro ecosistema de socios de Audience Manager para mantener a nuestros clientes informados de los cambios.

## Actualizaciones de socios de Audience Manager: Sincronizaciones de ID {#partner-updates-id-syncs}

Algunos asociados, como se indica en el cuadro que figura a continuación, han modificado sus requisitos de integración con Audience Manager para incluir el apoyo basado en el marco de la IAB, a fin de cumplir las normas del RGPD.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nombre del socio </p> </th> 
   <th colname="col2" class="entry"> <p>Impacto previsto </p> </th> 
   <th colname="col3" class="entry"> <p>Estado del cambio </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>El socio elimina las sincronizaciones de ID de los usuarios de la Unión Europea </p> </td> 
   <td colname="col3"> <p>Activo desde el 22 de mayo de 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Oficina de Comercio </p> </td> 
   <td colname="col2"> <p>El socio elimina las sincronizaciones de ID de los usuarios de la Unión Europea </p> </td> 
   <td colname="col3"> <p>Aún no está activo </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>El socio elimina las sincronizaciones de ID de los usuarios de la Unión Europea </p> </td> 
   <td colname="col3"> <p>Aún no está activo </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>El socio elimina las sincronizaciones de ID de los usuarios de la Unión Europea </p> </td> 
   <td colname="col3"> <p>Aún no está activo </p> </td> 
  </tr> 
 </tbody> 
</table>

## Actualización de la interfaz de usuario de Audience Manager: Integración de Yahoo/Oath/DataX {#ui-update}

Además de las actualizaciones del marco de IAB mencionadas anteriormente, Yahoo/Oath/DataX ha agregado nuevos parámetros, **gdpr** y **gdpr_mode**, a sus API de taxonomía y audiencia. Sus parámetros informan a Yahoo/Oath/DataX de que tienen derechos para procesar un determinado segmento como procesador de datos o como controlador de datos. As a result, Audience Manager customers sending segments to a Yahoo/Oath/DataX destination must designate the appropriate parameter (Processor or Controller), based on their agreement with Oath.

Please reach out to your Consultant or Client Care to set the correct parameter. Adobe cannot make this update on behalf of a customer unless we receive written correspondence, requesting this update. Please reach out to your Yahoo/Oath/DataX representative to understand the full definition of these parameters.

## Audience Manager Partners With Unsegmentation Capabilities {#aam-partners-with-unsegmentation}

In order to help our customers automate GDPR requests, Audience Manager notifies our activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

However, some of our activation partners:

1. Cannot support unsegment requests from Adobe and/or
1. Are not able to receive updates from us more frequently than once in 30 days.

In those cases, you are not able to send delete requests to activation partners in an automated way through Audience Manager. Download our [Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-October2019.xlsx) to see which Audience Manager activation partners support unsegment.
