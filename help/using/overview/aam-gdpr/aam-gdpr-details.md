---
description: Este documento trata los tecnicismos relacionados con el Reglamento General de Protección de Datos (RGPD) para Audience Manager y le muestra cómo enviar solicitudes RGPD a Audience Manager.
seo-description: Este documento trata los tecnicismos relacionados con el Reglamento General de Protección de Datos (RGPD) para Audience Manager y le muestra cómo enviar solicitudes RGPD a Audience Manager.
seo-title: RGPD en Audience Manager
solution: Audience Manager
title: RGPD en Audience Manager
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 98914987331ce31bc8d3e67647d5b8273b287d4c

---


# RGPD en Audience Manager{#gdpr-in-audience-manager}

Este documento trata los tecnicismos relacionados con el Reglamento General de Protección de Datos (RGPD) para Audience Manager y le muestra cómo enviar solicitudes RGPD a Audience Manager.

## Documentación del RGPD en Experience Cloud {#gdpr-documentation}

Antes de leer los detalles específicos de Audience Manager, le recomendamos que consulte el material de Experience Cloud para el Reglamento General Europeo de Protección de Datos (RGPD), que se incluye en el siguiente enlace:

* [RGPD y su empresa](https://www.adobe.com/privacy/general-data-protection-regulation.html)
* [Documento técnico del RGPD](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md)
* [Terminología del RGPD](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

Las secciones siguientes explican qué significa RGPD para Audience Manager y cómo puede enviar solicitudes RGPD a Audience Manager.

## Tipos de solicitudes del RGPD y cómo hacer una solicitud del RGPD {#types-of-gdpr-requests}

Como cliente de Audience Manager, puede enviar solicitudes individuales de RGPD para acceder y eliminar datos de clientes, ya sea a través de la interfaz de usuario **[de servicios al cliente de](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** RGPD o llamando a la API **[de](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** RGPD. You can submit any Audience Manager identifiers (IDs), as described in the section **[Audience Manager Identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**, in the requests along with their respective namespace IDs (data source IDs). Si tiene alguna pregunta, póngase en contacto con el Servicio de atención al cliente en gdprsupport@adobe.com.

## Acceso a datos {#access-data}

Comprendemos su compromiso de cumplir con sus peticiones de clientes del RGPD en un plazo de 30 días a partir de la recepción. Por este motivo, intentamos procesar su solicitud de acceso a datos lo antes posible.

**Solicitud**

Puede registrar solicitudes de acceso a datos a través de la interfaz de usuario **[de los servicios al cliente de](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** GDPR o llamando a la API **[de](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** GDPR (consulte `access` acción). En cualquier caso, debe cargar un JSON con los identificadores de Audience Manager para los que envía la solicitud de acceso a datos. Vea el aspecto que tiene un JSON bien formado en la documentación **[de GDPR de](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** Experience Cloud (específicamente, busque "formato de solicitud POST" en la página). O bien, puede **[descargar un JSON](assets/access_request.json)** de muestra.

**Respuesta**

Las respuestas a las solicitudes de datos de acceso contienen un resumen del número total de características y segmentos, el tipo de característica, las descripciones de características y segmentos, junto con los respectivos nombres de fuentes de datos. La respuesta de Access también incluirá datos de terceros y de terceros accesibles para el controlador de datos, junto con datos de origen. Cuando [!UICONTROL declared IDs] como ID de CRM entre dispositivos o ID de cookies de cliente se envían en solicitudes GDPR, Audience Manager incluirá la respuesta de Access de todos los dispositivos vinculados (hasta 100 dispositivos por ID declarado).

**Estado de respuesta**

Si hay algún error de Audience Manager en la respuesta, estos se muestran como códigos de error en la respuesta. Tenemos una [lista de códigos](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)de error, donde puede encontrar más información sobre los errores devueltos.

**Respuesta de ejemplo**

Una respuesta de acceso de muestra podría tener el aspecto siguiente. En este ejemplo, el ID del sujeto de datos es un ID de cookie. Cumplen varios requisitos y pertenecen a algunos segmentos. El ID de cookie está vinculado a un ID móvil. El ejemplo también contiene metadatos para el teléfono que utilizan.

```
{
  "id": "45338264191156397602180946733455975613",
  "namespace": {
    "id": 0,
    "integration code": "",
    "data provider name": "Demdex, Inc",
    "type": "COOKIE"
  },
  "warnings": [{
    "title": "Device Data",
    "description": "Contains data from all users of this device"
  }],
  "data": {
    "traits": [{
      "name": "Website Visitors",
      "type": "1st party",
      "description": "All Active Visitors",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Interested in Italian Holidays",
      "type": "1st party",
      "description": "Query string contains holidays/bella_italia",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Lifestyle>Recreational>Garden Party",
      "type": "3rd party",
      "description": "Survey respondents that have expressed an interest in hosting garden parties",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:36"
    }],
    "segments": [{
      "name": "test",
      "description": "Interested in Photography",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "false"
    }, {
      "name": "Traveler and Frequent Flier",
      "description": "",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }, {
      "name": "Interested in Sports",
      "description": "",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }]
  },
  "links": [{
    "id": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2",
    "namespace": {
      "id": 20914,
      "integration code": "DSID_20914",
      "data provider name": "Google",
      "type": "MOBILE"
    },
    "linking datetime": "2018-04-10 17:00:37"
  }],
  "deviceMetadata": {
    "hardware": "Mobile Phone",
    "manufacturer": "Samsung",
    "marketing name": "Galaxy S8 Plus",
    "model": "",
    "os name": "Android",
    "os version": "7.0",
    "vendor": "Samsung"
  }
}
```

La tabla siguiente contiene descripciones de todos los campos devueltos en la respuesta de acceso a datos, en el orden en que aparecen arriba.

<table id="table_DF08231257F64588B98BD71A088C50DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo </p> </th> 
   <th colname="col2" class="entry"> <p>Descripción </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>ID de usuario de los datos siguientes. Se trata de un ID que se proporciona en la solicitud de acceso a datos del RGPD o de un ID vinculado a uno de los ID declarados que se han proporcionado. The ID types are described in the  Audience Manager Identifiers section.<a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"></a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>También conocido como la fuente de datos. See the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>El ID de la fuente de datos/espacio de nombres. See <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers (IDs)</a> for all the accepted values. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> integration code </code> </p> </td> 
   <td colname="col2"> <p>Los códigos de integración son nombres descriptivos para las fuentes de datos y le ayudan a rastrear las fuentes de datos con mayor facilidad que con las ID de fuentes de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>nombre del proveedor de datos </code> </p> </td> 
   <td colname="col2"> <p>The name of the owner of the data source. 
     <ul id="ul_5CEAF23C28154662AFC443D3494107D3"> 
      <li id="li_EC2DA09F618D4225B655ADF455C0D654">For first party data, this is the customer's own company name. </li> 
      <li id="li_C4A5E1BD2A994109BBCD839DDC4B2E64">For second party data, this is the name of the partner company. </li> 
      <li id="li_1AA1246B7E40443CB18108512FBB8B19">For third party data, this is the name of the data partner. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type </code> </p> </td> 
   <td colname="col2"> <p>El tipo de ID para el cual solicitó acceso de datos del RGPD. Accepted types are listed in the  Audience Manager Identifiers section.<a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"></a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> warnings</code> </p> </td> 
   <td colname="col2"> <p>Warnings return further information related to the data access request. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> title </code> </p> </td> 
   <td colname="col2"> <p>Brief information about the warning. </p> <p>The two warnings you may receive are: </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">Device Data </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">Incomplete request </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description </code> </p> </td> 
   <td colname="col2"> <p>Una descripción más detallada de la advertencia recibida: </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">Datos del dispositivo: contiene datos de todos los usuarios de este dispositivo </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">Solicitud incompleta: no se completó la recuperación de datos de Audience Manager. Some information may be missing. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data </code> </p> </td> 
   <td colname="col2"> <p>Características y segmentos asociados a este ID de usuario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> traits </code> </p> </td> 
   <td colname="col2"> <p>Características asociadas con el ID de usuario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>Nombre del rasgo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type</code> </p> </td> 
   <td colname="col2"> <p>El tipo de característica. Los valores posibles son: </p> <p> 
     <ul id="ul_DBAC618D9FE94B17B2494B83832A969F"> 
      <li id="li_740F2DCA8F2A4A22A7D9988ECD2FC976"> <i>Primer nivel</i> para sus propios rasgos. </li> 
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>Segundo nivel</i> para características que pertenecen a sus socios. Lea nuestro <a href="../../overview/data-types-collected.md#second-party-data"> artículo de datos</a> de terceros para obtener más información. </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>Terceros</i> para las características obtenidas de los socios de datos, a través del <a href="../../features/audience-marketplace/audience-marketplace.md"> Mercado de audiencias</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>Unas pocas palabras para ayudar a describir el propósito o la función del rasgo. Se trata de un campo opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> controles de exportación de datos</code> </p> </td> 
   <td colname="col2"> <p>Controles <a href="../../features/data-export-controls.md"> de exportación de datos aplicados</a> a la fuente de datos de esta característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>nombre del proveedor de datos </code> </p> </td> 
   <td colname="col2"> <p>Nombre del propietario del origen de datos al que pertenece esta característica. 
     <ul id="ul_D2D424E903A143779342D35D6F625656"> 
      <li id="li_55B3A40A6CD24A25B5AAFD07AD28F662">Para los datos de origen, éste es el nombre de la empresa del cliente. </li> 
      <li id="li_BC6A9F52543D4532BC7D90948D1EB35F">Para datos de terceros, este es el nombre de la empresa asociada. </li> 
      <li id="li_DFD35A3E3E844E4993B59A62DB3C38D9">Para datos de terceros, este es el nombre del socio de datos. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> última realización</code> </p> </td> 
   <td colname="col2"> <p>Hora exacta en la que el sujeto de datos calificó por última vez para esta característica. El formato de fecha es AAAA-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segmentos </code> </p> </td> 
   <td colname="col2"> <p>Segmentos a los que pertenece este usuario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>Nombre del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>Algunas palabras para ayudar a describir este segmento. Se trata de un campo opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> controles de exportación de datos</code> </p> </td> 
   <td colname="col2"> <p>Controles <a href="../../features/data-export-controls.md"></a> de exportación de datos aplicados a la fuente de datos de este segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>nombre del proveedor de datos </code> </p> </td> 
   <td colname="col2"> <p>Nombre del propietario del origen de datos al que pertenece este segmento. 
     <ul id="ul_D437D149BDBE470489D1DD03CF47841C"> 
      <li id="li_90133644911A49AEB0DB209BCAC8E789">Para los datos de origen, éste es el nombre de la empresa del cliente. </li> 
      <li id="li_788AAFCDA9914235830F0440DF9982E5">Para datos de terceros, este es el nombre de la empresa asociada. </li> 
      <li id="li_F59FD714746E46BEB27FDF6B7245A7D1">Para datos de terceros, este es el nombre del socio de datos. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> last realization</code> </p> </td> 
   <td colname="col2"> <p>The exact time that the Data Subject last qualified for this segment. The date format is YYYY-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> activo</code> </p> </td> 
   <td colname="col2"> <p>Indicates whether the Data Subject is currently qualified for this segment. Returns <code><i>true</i></code> or <code><i>false</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> vínculos </code> </p> </td> 
   <td colname="col2"> <p>Additional ID that this ID has been linked to. Information is returned on: </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">namespace (data source) </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">namespace ID </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">integration code </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971">nombre del proveedor de datos  </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">ID type </li> 
     </ul> </p> <p>All these fields are described in the first rows of this table. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> linking datetime</code> </p> </td> 
   <td colname="col2"> <p>The exact time that an ID sync event made the link between IDs. The date format is YYYY-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> device metadata </code> </p> </td> 
   <td colname="col2"> <p>Information about the device. This information includes the fields below. Note that not all fields are returned for all device types. </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>Información de hardware </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>Fabricante del dispositivo </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>El nombre de marketing del dispositivo </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>El modelo de dispositivo </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>Nombre del sistema operativo (SO) del dispositivo </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>Versión del SO </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>El proveedor del dispositivo </p> </li> 
     </ul> </p> <p> <p>Nota: Solo se devuelven metadatos de dispositivo cuando se envía uno de los siguientes elementos: 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">ID móviles </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">ID de Audience Manager </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">Experience Cloud ID </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Eliminación de datos {#delete-data}

Comprendemos su compromiso de cumplir con sus peticiones de clientes del RGPD en un plazo de 30 días a partir de la recepción. Por este motivo, intentamos procesar su solicitud de eliminación de datos lo antes posible.

**Solicitud**

Puede registrar solicitudes de eliminación de datos a través de la interfaz de usuario **[de los servicios al cliente de](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** GDPR o llamando a la API **[de](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** GDPR (consulte `delete` acción). En cualquier caso, debe cargar un JSON con los identificadores de Audience Manager para los que envía la solicitud de acceso a datos. Vea el aspecto que tiene un JSON bien formado en la documentación [de GDPR de](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) Experience Cloud (específicamente, busque "formato de solicitud POST" en la página). O bien, puede **[descargar un JSON](assets/delete_request.json)** de muestra.

**Respuesta**

En respuesta a las solicitudes de eliminación de datos, eliminamos características y segmentos asociados al identificador de Audience Manager correspondiente. Además, Audience Manager excluirá de forma permanente los identificadores de Audience Manager correspondientes para el sujeto de datos y se eliminarán las asignaciones de ID correspondientes. Cuando se envían ID declarados como ID de CRM entre dispositivos o ID de cookies de cliente en solicitudes GDPR, Audience Manager realizará las acciones de eliminación necesarias en todos los dispositivos vinculados (hasta 100 dispositivos por ID declarado).

## Solicitud de exclusión {#opt-out-request}

Para solicitudes de exclusión, consulte nuestra documentación sobre la administración [de](../../overview/data-security-and-privacy/opt-out-management.md)exclusión.

## Identificadores (ID) de Audience Manager {#aam-ids}

Al enviar solicitudes GDPR a Adobe Audience Manager, debe incluir uno de los identificadores (ID) que se enumeran a continuación. Puede encontrar más información sobre los formatos de ID en nuestro [índice de ID](../../reference/ids-in-aam.md)de Audience Manager.

###  ID de usuario único de Adobe Audience Manager

**ID** de usuario: aam_uuid

**Definición**: ID de usuario único de Adobe Audience Manager

**Namespace ID**: 0

>[!NOTE]
>
>También puede utilizar el espacio de nombres CORE. Consulte el segundo ejemplo de JSON.

**Example in JSON:**

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

### Adobe Experience Cloud ID

**User ID: mid**

**Definition**: Adobe Experience Cloud ID, formerly known as Visitor ID or Marketing Cloud ID

**Namespace ID**: 4

>[!NOTE]
>
>You can also use the ECID namespace. See the second JSON example.

**Example in JSON:**

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

### Customer ID

**User ID: cid**

**Definition: Customer ID, such as a cookie you set for anonymous site visitors or a CRM ID from an offline system or a hashed username**

**Namespace ID: Customer-specific.** Please find it from your Audience Manager instance.

**Example in JSON:**

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

### ID de publicidad móvil

**User ID: d_cid**

**Definition: Mobile advertising IDs.**
>[!IMPORTANT]
>
> If you are using the Mobile SDK, then you should also send the Experience Cloud ID (MID) along with mobile advertising IDs for complete GDPR Access and Delete responses.

**ID de espacio de nombres**:

* IDFA: 20915
* GAID: 20914

**Ejemplo en JSON**:

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

### Integration code

**ID** de usuario: d_cid_ic

**Definición**: Código de integración para el origen de datos. Esto se puede usar en lugar de ID de fuente de datos o ID de espacio de nombres en la solicitud de API al servicio principal de privacidad de Adobe Experience Cloud.

**ID** de espacio de nombres: No aplicable

Ejemplo en JSON:

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
