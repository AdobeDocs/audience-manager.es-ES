---
description: Esta página describe la información proporcionada directamente por nuestros socios, a medida que está disponible, junto con las implicaciones relacionadas con la práctica de Audience Manager. Las implicaciones clave para los socios que realizan estas actualizaciones son el resultado del RGPD (Reglamento General de Protección de Datos), que entró en vigor el 25 de mayo de 2018 y del nuevo Marco de Transparencia y Consentimiento del RGPD de la IAB (Marco de IAB).
seo-description: Esta página describe la información proporcionada directamente por nuestros socios, a medida que está disponible, junto con las implicaciones relacionadas con la práctica de Audience Manager. Las implicaciones clave para los socios que realizan estas actualizaciones son el resultado del RGPD (Reglamento General de Protección de Datos), que entró en vigor el 25 de mayo de 2018 y del nuevo Marco de Transparencia y Consentimiento del RGPD de la IAB (Marco de IAB).
seo-title: Consideraciones del RGPD para destinos
solution: Audience Manager
title: Consideraciones del RGPD para destinos
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: 69be038d0f2d31b6b5eda20041082c1890abc38f

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
   <td colname="col1"> <p> LiveRamp </p> </td> 
   <td colname="col2"> <p>El socio elimina las sincronizaciones de ID de los usuarios de la Unión Europea </p> </td> 
   <td colname="col3"> <p>Aún no está activo </p> </td> 
  </tr> 
 </tbody> 
</table>

## Actualización de la interfaz de usuario de Audience Manager: Integración de Yahoo/Oath/DataX {#ui-update}

Además de las actualizaciones del marco de IAB mencionadas anteriormente, Yahoo/Oath/DataX ha agregado nuevos parámetros, **gdpr** y **gdpr_mode**, a sus API de taxonomía y audiencia. Sus parámetros informan a Yahoo/Oath/DataX de que tienen derechos para procesar un determinado segmento como procesador de datos o como controlador de datos. Como resultado, los clientes de Audience Manager que envían segmentos a un destino de Yahoo/Oath/DataX deben designar el parámetro apropiado (Procesador o Controlador), según su acuerdo con el juramento.

Póngase en contacto con el consultor o con Client Care para establecer el parámetro correcto. Adobe no puede realizar esta actualización en nombre de un cliente a menos que recibamos una correspondencia por escrito en la que se solicite esta actualización. Comuníquese con el representante de Yahoo/Oath/DataX para comprender la definición completa de estos parámetros.

## Audience Manager Se Asocia Con Funciones De Dessegmentación {#aam-partners-with-unsegmentation}

Con el fin de ayudar a nuestros clientes a automatizar las solicitudes de RGPD, Audience Manager notifica a nuestros socios de activación las solicitudes de eliminación de los sujetos de datos enviándoles información de dessegmentación (o eliminación de segmentos).

Sin embargo, algunos de nuestros socios de activación:

1. No se pueden admitir solicitudes de dessegmentación de Adobe y/o
1. No podemos recibir actualizaciones de nosotros más de una vez en 30 días.

En estos casos, no puede enviar solicitudes de eliminación a socios de activación de forma automatizada a través de Audience Manager. Descargue nuestra hoja [de Excel de](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx) socio para ver qué socios de activación de Audience Manager admiten la dessegmentación.
