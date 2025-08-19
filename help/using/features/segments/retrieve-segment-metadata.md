---
description: Cuando Audience Manager envía información de segmentos a un socio de datos, identifica estos objetos con ID numéricos. Como socio de datos, cuando comparte esta información con sus clientes (o trabaja con ellos mismos), un nombre y una descripción reales proporcionan una mejor experiencia a los clientes en informes, paneles u otras interfaces de usuario (IU). Los socios de datos pueden poner estos nombres descriptivos a disposición de sus clientes mediante los métodos manuales o automatizados descritos en esta sección.
seo-description: When Audience Manager sends segment information to a data partner, it identifies these objects with numeric IDs. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces (UI). Data partners can make these friendly names available to their customers with either the manual or automated methods described in this section.
seo-title: Retrieving Segment Metadata
solution: Audience Manager
title: Recuperación de metadatos del segmento
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
exl-id: 64922cf8-f7bf-4e33-871f-d33626b06360
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---

# Recuperación de metadatos del segmento {#retrieving-segment-metadata}

Cuando Audience Manager envía información de segmentos a un socio de datos, identifica estos objetos con ID numéricos. Como socio de datos, cuando comparte esta información con sus clientes (o trabaja con ellos), un nombre y una descripción reales proporcionan una mejor experiencia a los clientes en informes, paneles u otras interfaces de usuario ([!DNL UI]). Los socios de datos pueden poner estos nombres descriptivos a disposición de sus clientes mediante los métodos manuales o automatizados descritos en esta sección.

## Método manual {#manual-method}

Como socio de datos, probablemente esté acostumbrado a obtener metadatos de audiencia de sus clientes mediante procesos manuales. Esto podría incluir archivos adjuntos a correos electrónicos o de clientes que agregan esos datos a través de un(a) [!DNL UI] que ha creado y mantenido para este propósito. Estos procesos funcionan, pero a menudo son engorrosos y llevan mucho tiempo, y pueden requerir el trabajo manual de introducción de datos. Estos métodos se utilizan a menudo para ayudar a poner en marcha una integración rápidamente, pero no proporcionan la mejor experiencia del cliente a largo plazo. Como alternativa, puede usar [!DNL Audience Manager] [!DNL API] para obtener metadatos de segmentos automáticamente.

## Método automatizado {#automated-method}

[!DNL Audience Manager] proporciona un conjunto de [API de REST](../../api/rest-api-main/rest-api-main.md) que le permiten recuperar metadatos de segmento automáticamente. Con [!DNL API], puede crear trabajos que recuperen metadatos de segmentos a intervalos programados o automáticamente, siempre que procese datos de [!DNL Audience Manager] y encuentre un nuevo ID de segmento. Consulte los pasos a continuación para obtener más información.

### Paso 1: Revisar las API de Audience Manager

La sección [Introducción a las API de REST](../../api/rest-api-main/aam-api-getting-started.md) contiene información sobre requisitos generales, autenticación, métodos disponibles, etc. Este es un buen punto de partida si no ha trabajado anteriormente con [!DNL Audience Manager] [!DNL API].

### Paso 2: Solicitar credenciales de acceso a OAuth2

Necesita un ID de cliente y un secreto para realizar [!DNL API] llamadas. Puede obtener un ID de cliente y un secreto de su especialista en integración durante el proceso de configuración de la integración. También puede enviar una solicitud por correo electrónico a [!UICONTROL Audience Manager Customer Care] a las [!DNL amsupport@adobe.com].

### Paso 3: Recopilar información específica del cliente de cada cliente integrado

Solicite lo siguiente a cada cliente integrado:

* Nombre de usuario: para un usuario restringido que tenga permisos de solo lectura para el destino asociado a una integración específica.
* Contraseña: la contraseña de usuario.
* ID de destino: es el ID (un entero) asociado al destino creado para la integración específica servidor-a-servidor.

### Paso 4: Recuperar metadatos de segmento con una llamada de API

Después de completar los pasos anteriores, puede usar un método `GET` para recuperar los metadatos del segmento. Para ver una solicitud y una respuesta de ejemplo, vea [Asignaciones de destino de retorno](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). Esta llamada devuelve datos de segmento formateados como pares clave-valor en un objeto [!DNL JSON]. Algunos de los atributos de segmento importantes devueltos en la respuesta se enumeran en la siguiente tabla.

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
   <td colname="col2"> <p>Identificador de segmento <span class="keyword"> Audience Manager</span>. </p> </td> 
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
   <td colname="col2"> <p>Estado actual de la asignación de segmentos. Las opciones de estado devueltas incluyen: </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
