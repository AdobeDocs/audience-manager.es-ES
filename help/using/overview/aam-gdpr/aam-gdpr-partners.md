---
description: Esta página describe la información proporcionada directamente por nuestros socios, ya que está disponible, junto con las implicaciones relacionadas con la práctica de Audience Manager. Las implicaciones clave para los socios que realizan estas actualizaciones son el resultado del GGPD (Reglamento General de Protección de Datos), que entró en vigor el 25 de mayo de 2018 y el nuevo Marco de transparencia y consentimiento IAB GDPR (IAB Framework).
seo-description: Esta página describe la información proporcionada directamente por nuestros socios, ya que está disponible, junto con las implicaciones relacionadas con la práctica de Audience Manager. Las implicaciones clave para los socios que realizan estas actualizaciones son el resultado del GGPD (Reglamento General de Protección de Datos), que entró en vigor el 25 de mayo de 2018 y el nuevo Marco de transparencia y consentimiento IAB GDPR (IAB Framework).
seo-title: Consideraciones del RGPD para destinos
solution: Audience Manager
title: Consideraciones del RGPD para destinos
uuid: e 8 a 40060-086 c -4 f 03-b 48 c -9 c 903 acb 7891
translation-type: tm+mt
source-git-commit: 69be038d0f2d31b6b5eda20041082c1890abc38f

---


# GDPR Considerations for Destinations{#gdpr-considerations-for-destinations}

Esta página describe la información proporcionada directamente por nuestros socios, ya que está disponible, junto con las implicaciones relacionadas con la práctica de Audience Manager. Las implicaciones clave para los socios que realizan estas actualizaciones son el resultado del GGPD (Reglamento General de Protección de Datos), que entró en vigor el 25 de mayo de 2018 y el nuevo Marco de transparencia y consentimiento IAB GDPR (IAB Framework).

Los socios de Adobe son propietarios de sus procesos empresariales y pueden decidir actualizar los requisitos de integración con Audience Manager cada cierto tiempo. Estamos trabajando activamente con nuestro ecosistema de socios de Audience Manager para mantener a nuestros clientes al día de los cambios.

## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

Algunos socios, según se enumeran en la tabla siguiente, han cambiado los requisitos de integración con Audience Manager para incluir la compatibilidad basada en el módulo IAB, para cumplir con los estándares del RGPD.

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
   <td colname="col1"> <p>Yahoo/Oath/datax </p> </td> 
   <td colname="col2"> <p>El socio retirará las sincronizaciones de ID para los usuarios de la Unión Europea </p> </td> 
   <td colname="col3"> <p>Activo desde el 22 de mayo de 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Oficina comercial </p> </td> 
   <td colname="col2"> <p>El socio retirará las sincronizaciones de ID para los usuarios de la Unión Europea </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>El socio retirará las sincronizaciones de ID para los usuarios de la Unión Europea </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Liveramp </p> </td> 
   <td colname="col2"> <p>El socio retirará las sincronizaciones de ID para los usuarios de la Unión Europea </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
 </tbody> 
</table>

## Audience Manager UI Update - Yahoo/Oath/DataX Integration {#ui-update}

In addition to the updates to the IAB Framework mentioned above, Yahoo/Oath/DataX has added new parameters, **gdpr** and **gdpr_mode**, to their taxonomy and Audience APIs. Sus parámetros informan a Yahoo/Oath/datax de que tienen los derechos para procesar un segmento determinado como procesador de datos o como controlador de datos. Como resultado, los clientes de Audience Manager que envían segmentos a un destino Yahoo/Oath/datax deben designar el parámetro apropiado (Procesador o Controlador), según su acuerdo con Oath.

Póngase en contacto con su consultor o Clientcare para establecer el parámetro correcto. Adobe no puede realizar esta actualización en nombre de un cliente a menos que reciba una correspondencia por escrito, solicitando esta actualización. Póngase en contacto con su representante de Yahoo/Oath/datax para comprender la definición completa de estos parámetros.

## Audience Manager Partners With Unsegmentation Capabilities {#aam-partners-with-unsegmentation}

Para ayudar a nuestros clientes a automatizar las solicitudes del RGPD, Audience Manager notifica a nuestros socios de activación de las solicitudes de eliminación de temas de datos enviándoles información descatalogada (o eliminando segmentos).

Sin embargo, algunos de nuestros socios de activación:

1. No es posible admitir solicitudes de segmentación de Adobe y/o
1. No se pueden recibir actualizaciones con más frecuencia de una en 30 días.

En estos casos, no puede enviar solicitudes de eliminación a socios de activación de forma automática a través de Audience Manager. Download our [Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx) to see which Audience Manager activation partners support unsegment.
