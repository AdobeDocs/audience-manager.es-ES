---
description: Cuando el Audience Manager envía información de segmentos a un socio de datos, identifica estos objetos con ID numéricos. Como socio de datos, cuando comparte esta información con sus clientes (o trabaja con él mismo), un nombre y una descripción reales proporcionan una mejor experiencia a los clientes en informes, tableros u otras interfaces de usuario (IU). Los socios de datos pueden poner estos nombres descriptivos a disposición de sus clientes con los métodos manuales o automatizados que se describen en esta sección.
seo-description: Cuando el Audience Manager envía información de segmentos a un socio de datos, identifica estos objetos con ID numéricos. Como socio de datos, cuando comparte esta información con sus clientes (o trabaja con él mismo), un nombre y una descripción reales proporcionan una mejor experiencia a los clientes en informes, tableros u otras interfaces de usuario (IU). Los socios de datos pueden poner estos nombres descriptivos a disposición de sus clientes con los métodos manuales o automatizados que se describen en esta sección.
seo-title: Recuperación de metadatos del segmento
solution: Audience Manager
title: Recuperación de metadatos del segmento
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: 'Segmentos '
exl-id: 64922cf8-f7bf-4e33-871f-d33626b06360
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 2%

---

# Recuperación de metadatos del segmento {#retrieving-segment-metadata}

Cuando el Audience Manager envía información de segmentos a un socio de datos, identifica estos objetos con ID numéricos. Como socio de datos, cuando comparte esta información con sus clientes (o trabaja con él mismo), un nombre y una descripción reales proporcionan una mejor experiencia a los clientes en informes, tableros u otras interfaces de usuario ([!DNL UI]). Los socios de datos pueden poner estos nombres descriptivos a disposición de sus clientes con los métodos manuales o automatizados que se describen en esta sección.

## Método manual {#manual-method}

Como socio de datos, probablemente esté acostumbrado a obtener metadatos de audiencia de sus clientes a través de procesos manuales. Esto podría incluir archivos adjuntos a correos electrónicos o de clientes que agregan esos datos a través de un [!DNL UI] que haya creado y mantenido con este fin. Estos procesos funcionan, pero a menudo son engorrosos, consumen tiempo y pueden requerir un trabajo manual de entrada de datos. Estos métodos se utilizan a menudo para ayudar a poner en marcha una integración rápidamente, pero no proporcionan la mejor experiencia de cliente a largo plazo. Como alternativa, puede utilizar [!DNL Audience Manager] [!DNL API] para obtener metadatos de segmento automáticamente.

## Método automatizado {#automated-method}

[!DNL Audience Manager] proporciona un conjunto de  [API de ](../../api/rest-api-main/rest-api-main.md) REST que le permiten recuperar metadatos de segmento automáticamente. Con [!DNL API], puede crear trabajos que recuperen metadatos de segmento a intervalos programados o automáticamente, siempre que procese [!DNL Audience Manager] datos y busque un nuevo ID de segmento. Consulte los pasos a continuación para obtener más información.

### Paso 1: Consulte las API del Audience Manager

La sección [Introducción a las API de REST](../../api/rest-api-main/aam-api-getting-started.md) contiene información sobre requisitos generales, autenticación, métodos disponibles, etc. Este es un buen lugar para empezar si no ha trabajado con [!DNL Audience Manager] [!DNL API] antes.

### Paso 2: Solicitar credenciales de acceso a OAuth2

Necesita un ID de cliente y un secreto para realizar [!DNL API] llamadas. Puede obtener un ID de cliente y un secreto de su especialista en integración durante el proceso de configuración de la integración. También puede enviar una solicitud por correo electrónico a [!UICONTROL Audience Manager Customer Care] en [!DNL amsupport@adobe.com].

### Paso 3: Recopilar información específica del cliente de cada cliente integrado

Solicite lo siguiente a cada cliente integrado:

* Nombre de usuario: Esto es para un usuario restringido que tiene permisos de solo lectura para el destino asociado a una integración específica.
* Contraseña: La contraseña de usuario.
* ID de destino: Este es el ID (un entero) asociado al destino creado para la integración específica servidor a servidor.

### Paso 4: Recuperación de metadatos de segmentos con una llamada de API

Después de completar los pasos anteriores, puede utilizar un método `GET` para recuperar los metadatos del segmento. Para obtener una solicitud y una respuesta de ejemplo, consulte [Asignaciones de destino de retorno](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). Esta llamada devuelve datos de segmento formateados como pares clave-valor en un objeto [!DNL JSON]. Algunos de los atributos de segmento importantes devueltos en la respuesta se enumeran en la siguiente tabla.

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> destinationMappingId</code> </p> </td> 
   <td colname="col2"> <p>El ID de segmento <span class="keyword"> del Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>El nombre del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>Texto que describe brevemente el segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementStatus</code> </p> </td> 
   <td colname="col2"> <p>Estado actual de la asignación de segmentos. Las opciones de estado que se devuelven incluyen: </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
