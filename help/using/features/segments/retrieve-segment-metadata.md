---
description: Cuando Audience Manager envía información de segmentos a un socio de datos, identifica estos objetos con ID numéricos. Como socio de datos, al compartir esta información con sus clientes (o trabajar con ella usted mismo), un nombre y descripción reales proporcionan una mejor experiencia para los clientes en informes, tableros u otras interfaces de usuario (IU). Los socios de datos pueden poner estos nombres prácticos a disposición de sus clientes con los métodos manuales o automatizados descritos en esta sección.
seo-description: Cuando Audience Manager envía información de segmentos a un socio de datos, identifica estos objetos con ID numéricos. Como socio de datos, al compartir esta información con sus clientes (o trabajar con ella usted mismo), un nombre y descripción reales proporcionan una mejor experiencia para los clientes en informes, tableros u otras interfaces de usuario (IU). Los socios de datos pueden poner estos nombres prácticos a disposición de sus clientes con los métodos manuales o automatizados descritos en esta sección.
seo-title: Recuperación de metadatos de segmentos
solution: Audience Manager
title: Recuperación de metadatos de segmentos
uuid: 719 e 2 c 41-8788-4 e 8 a -967 a-e 367421 f 9 f 84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Retrieving Segment Metadata {#retrieving-segment-metadata}

Cuando Audience Manager envía información de segmentos a un socio de datos, identifica estos objetos con ID numéricos. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces ([!DNL UI]). Los socios de datos pueden poner estos nombres prácticos a disposición de sus clientes con los métodos manuales o automatizados descritos en esta sección.

## Manual method {#manual-method}

Como partner de datos, probablemente se utilice para obtener los metadatos de audiencia de sus clientes a través de procesos manuales. This could include files attached to emails or from customers adding that data through a [!DNL UI] you&#39;ve built and maintained for this purpose. Estos procesos funcionan, pero a menudo son borrosos, requieren tiempo y pueden requerir una entrada manual de datos. Estos métodos se utilizan a menudo para ayudar a agilizar la integración, pero no proporcionan la mejor experiencia del cliente a largo plazo. As an alternative, you can use the [!DNL Audience Manager] [!DNL API] to get segment metadata automatically.

## Automated method {#automated-method}

[!DNL Audience Manager] proporciona un conjunto de [API](../../api/rest-api-main/rest-api-main.md) de REST que permite recuperar metadatos de segmentos automáticamente. With the [!DNL API], you can create jobs that retrieve segment metadata at scheduled intervals or automatically, whenever you process [!DNL Audience Manager] data and find a new segment ID. Consulte los pasos siguientes para obtener más información.

### Paso 1: Consulte las API de Audience Manager

The [Getting Started with REST APIs](../../api/rest-api-main/aam-api-getting-started.md) section contains information about general requirements, authentication, available methods, etc. This is a good place to begin if you haven&#39;t worked with the [!DNL Audience Manager] [!DNL API] before.

### Paso 2: Solicitar credenciales de acceso a oauth 2

You need a client ID and secret to make [!DNL API] calls. Puede obtener un ID de cliente y un secreto de su especialista de integración durante el proceso de configuración de integración. You can also send an email request to [!UICONTROL Audience Manager Customer Care] at [!DNL amsupport@adobe.com].

### Paso 3: Recopilación de información específica del cliente de cada cliente integrado

Solicite lo siguiente a cada cliente integrado:

* Nombre de usuario: Esto es para un usuario restringido que tiene permisos de solo lectura para el destino asociado con una integración específica.
* Contraseña: La contraseña de usuario.
* ID de destino: Es el ID (un entero) asociado con el destino creado para la integración servidor a servidor específica.

### Paso 4: Recuperar metadatos de segmentos con una llamada de API

After completing the previous steps, you can use a `GET` method to retrieve segment metadata. For a sample request and response, see [Return Destination Mappings](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). This call returns segment data formatted as key-value pairs in a [!DNL JSON] object. Algunos de los atributos de segmento importantes devueltos en la respuesta se enumeran en la siguiente tabla.

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Destinationmappingid</code> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> Audience Manager</span> segment ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementname</code> </p> </td> 
   <td colname="col2"> <p>El nombre del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementdescription</code> </p> </td> 
   <td colname="col2"> <p>Texto que describe brevemente el segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementstatus</code> </p> </td> 
   <td colname="col2"> <p>Estado actual de la asignación de segmentos. Las opciones de estado que se devuelven son: </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> activo</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactivo</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> eliminado</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>