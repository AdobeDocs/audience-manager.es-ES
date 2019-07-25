---
description: Este documento cubre los aspectos técnicos relacionados con el Reglamento General de Protección de Datos (RGPD) para Audience Manager y muestra cómo enviar solicitudes RDPD a Audience Manager.
seo-description: Este documento cubre los aspectos técnicos relacionados con el Reglamento General de Protección de Datos (RGPD) para Audience Manager y muestra cómo enviar solicitudes RDPD a Audience Manager.
seo-title: RGPD en Audience Manager
solution: Audience Manager
title: RGPD en Audience Manager
uuid: ed 23 a 478-32 be -460 d-bb 03-a 735317 f 7 c 0 f
translation-type: tm+mt
source-git-commit: b791e22e9c8c848a8fc14c6d6494f77c9e7335dc

---


# RGPD en Audience Manager{#gdpr-in-audience-manager}

Este documento cubre los aspectos técnicos relacionados con el Reglamento General de Protección de Datos (RGPD) para Audience Manager y muestra cómo enviar solicitudes RDPD a Audience Manager.

## GDPR Documentation in the Experience Cloud {#gdpr-documentation}

Antes de leer los detalles específicos de Audience Manager, le recomendamos que avance por el material de Experience Cloud para el Reglamento General Europeo de Protección de Datos (RGPD), que se vinculará a continuación:

* [RGPD y su negocio](https://www.adobe.com/privacy/general-data-protection-regulation.html)
* [Documento técnico de RDPD](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md)
* [Terminología del RGPD](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

Las secciones siguientes explican qué significa el RGPD para Audience Manager y cómo puede enviar solicitudes GDPR a Audience Manager.

## Types of GDPR Requests and How to Make a GDPR Request {#types-of-gdpr-requests}

As an Audience Manager customer, you can submit individual GDPR requests to access and delete customer data, either through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)**. You can submit any Audience Manager identifiers (IDs), as described in the section **[Audience Manager Identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**, in the requests along with their respective namespace IDs (data source IDs). Si tiene alguna pregunta, póngase en contacto con el Servicio de atención al cliente en gdprsupport@adobe.com.

## Acceso a datos {#access-data}

Comprendemos su compromiso de cumplir con las solicitudes de los clientes del RGPD en los 30 días posteriores a la recepción. Por este motivo, tratamos de procesar la solicitud de acceso a los datos lo antes posible.

**Solicitud**

You can log data access requests through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (see `access` action). En ambos casos, debe cargar un JSON con los identificadores de Audience Manager para los que esté enviando la solicitud de acceso de datos. See what a well-formed JSON looks like in the **[Experience Cloud GDPR documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (specifically, search in page for "POST request format"). Or, you can **[download a sample JSON](assets/access_request.json)**.

**Respuesta**

Las respuestas para acceder a las solicitudes de datos contienen un resumen del número total de características y segmentos, tipo de características, descripciones de características y segmentos junto con los nombres de fuentes de datos respectivos. La respuesta Acceso también incluirá datos de terceros y de terceros accesibles al Controlador de datos junto con los datos de origen. When [!UICONTROL declared IDs] such as cross device CRM IDs or customer cookie IDs are sent in GDPR requests, Audience Manager will include the Access response from all the linked devices (up to 100 devices per declared ID).

**Estado de respuesta**

Si hay algún error de Audience Manager en la respuesta, aparecen como códigos de error en la respuesta. We have a [list of error codes](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md), where you can find more information about the returned errors.

**Respuesta de ejemplo**

Una respuesta de acceso de ejemplo podría tener el aspecto siguiente. En este ejemplo, el ID del sujeto de datos es un ID de cookie. Se califican para varias características y pertenecen a algunos segmentos. La ID de cookie está vinculada a un ID móvil. El ejemplo también contiene metadatos para el teléfono que utilizan.

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

La tabla siguiente contiene descripciones para todos los campos devueltos en la respuesta de acceso a datos, en el orden en que aparecen arriba.

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
   <td colname="col2"> <p>ID de usuario de los datos siguientes. Es una ID que se proporciona en la solicitud de acceso a los datos del RGPD o un ID vinculado a uno de los ID declarados que ha proporcionado. The ID types are described in the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
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
   <td colname="col2"> <p>Los códigos de integración son nombres descriptivos para las fuentes de datos y ayudan a rastrear las fuentes de datos más fácilmente que usar ID de fuentes de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>nombre del proveedor de datos </code> </p> </td> 
   <td colname="col2"> <p>Nombre del propietario del origen de datos. 
     <ul id="ul_5CEAF23C28154662AFC443D3494107D3"> 
      <li id="li_EC2DA09F618D4225B655ADF455C0D654">Para los datos de origen, es el propio nombre de empresa del cliente. </li> 
      <li id="li_C4A5E1BD2A994109BBCD839DDC4B2E64">Para los datos de terceros, es el nombre de la empresa asociada. </li> 
      <li id="li_1AA1246B7E40443CB18108512FBB8B19">Para los datos de terceros, es el nombre del socio de datos. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type </code> </p> </td> 
   <td colname="col2"> <p>El tipo de ID para el cual solicitó acceso de datos del RGPD. Accepted types are listed in the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> advertencias</code> </p> </td> 
   <td colname="col2"> <p>Las advertencias devuelven información adicional relacionada con la solicitud de acceso a datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> title </code> </p> </td> 
   <td colname="col2"> <p>Breve información sobre la advertencia. </p> <p>Las dos advertencias que puede recibir son: </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">Datos del dispositivo </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">Solicitud incompleta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description </code> </p> </td> 
   <td colname="col2"> <p>Una descripción más detallada de la advertencia recibida: </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">Datos de dispositivo: Contiene datos de todos los usuarios de este dispositivo </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">Solicitud incompleta: no se completó la recuperación de datos de Audience Manager. Puede que falte cierta información. </li> 
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
   <td colname="col2"> <p>El nombre de la característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type</code> </p> </td> 
   <td colname="col2"> <p>El tipo de característica. Los valores posibles son: </p> <p> 
     <ul id="ul_DBAC618D9FE94B17B2494B83832A969F"> 
      <li id="li_740F2DCA8F2A4A22A7D9988ECD2FC976"> <i>Primera parte</i> para sus propias características. </li> 
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>Segundo nivel</i> de características que pertenecen a sus socios. Read our <a href="../../overview/data-types-collected.md#second-party-data"> Second Party Data</a> article for more information. </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>Tercero</i> para características obtenidas de socios de datos, a través de <a href="../../features/audience-marketplace/audience-marketplace.md"> Audience Marketplace</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>Algunas palabras para describir el propósito o la función de características. Es un campo opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> controles de exportación de datos</code> </p> </td> 
   <td colname="col2"> <p>The <a href="../../features/data-export-controls.md"> data export controls</a> applied to this trait's data source. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>nombre del proveedor de datos </code> </p> </td> 
   <td colname="col2"> <p>Nombre del propietario del origen de datos al que pertenece esta característica. 
     <ul id="ul_D2D424E903A143779342D35D6F625656"> 
      <li id="li_55B3A40A6CD24A25B5AAFD07AD28F662">Para los datos de origen, es el propio nombre de empresa del cliente. </li> 
      <li id="li_BC6A9F52543D4532BC7D90948D1EB35F">Para los datos de terceros, es el nombre de la empresa asociada. </li> 
      <li id="li_DFD35A3E3E844E4993B59A62DB3C38D9">Para los datos de terceros, es el nombre del socio de datos. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> última realización</code> </p> </td> 
   <td colname="col2"> <p>El tiempo exacto que el sujeto de datos cualificó para esta característica. El formato de fecha es AAAA-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segmentos </code> </p> </td> 
   <td colname="col2"> <p>Segmentos a los que pertenece este usuario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>El nombre del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>Algunas palabras para describir este segmento. Es un campo opcional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> controles de exportación de datos</code> </p> </td> 
   <td colname="col2"> <p>The <a href="../../features/data-export-controls.md"> data export controls</a> applied to this segment's data source. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>nombre del proveedor de datos </code> </p> </td> 
   <td colname="col2"> <p>Nombre del propietario del origen de datos al que pertenece este segmento. 
     <ul id="ul_D437D149BDBE470489D1DD03CF47841C"> 
      <li id="li_90133644911A49AEB0DB209BCAC8E789">Para los datos de origen, es el propio nombre de empresa del cliente. </li> 
      <li id="li_788AAFCDA9914235830F0440DF9982E5">Para los datos de terceros, es el nombre de la empresa asociada. </li> 
      <li id="li_F59FD714746E46BEB27FDF6B7245A7D1">Para los datos de terceros, es el nombre del socio de datos. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> última realización</code> </p> </td> 
   <td colname="col2"> <p>El tiempo exacto que el sujeto de datos cualificó para este segmento. El formato de fecha es AAAA-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> activo</code> </p> </td> 
   <td colname="col2"> <p>Indica si el asunto de datos está cualificado actualmente para este segmento. Returns <code><i>true</i></code> or <code><i>false</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> vínculos </code> </p> </td> 
   <td colname="col2"> <p>ID adicional a la que se ha vinculado este ID. La información se devuelve en: </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">namespace (fuente de datos) </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">ID de espacio de nombre </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">integration code </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971">nombre del proveedor de datos  </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">ID type </li> 
     </ul> </p> <p>Todos estos campos se describen en las primeras filas de esta tabla. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> vincular datetime</code> </p> </td> 
   <td colname="col2"> <p>El tiempo exacto que un evento de sincronización de ID realizó el vínculo entre ID. El formato de fecha es AAAA-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> metadatos del dispositivo </code> </p> </td> 
   <td colname="col2"> <p>Información sobre el dispositivo. Esta información incluye los campos siguientes. Tenga en cuenta que no se devuelven todos los campos para todos los tipos de dispositivos. </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>Información de hardware </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>Fabricante del dispositivo </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>El nombre de mercadotecnia del dispositivo </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>Modelo de dispositivo </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>Nombre del sistema operativo (SO) del dispositivo </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>La versión del sistema operativo </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>El proveedor del dispositivo </p> </li> 
     </ul> </p> <p> <p>Nota: Solo se devuelven metadatos de dispositivo cuando se envía uno de los siguientes datos: 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">ID móviles </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">ID de Audience Manager </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">ID de Experience Cloud </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Eliminación de datos {#delete-data}

Comprendemos su compromiso de cumplir con las solicitudes de los clientes del RGPD en los 30 días posteriores a la recepción. Por este motivo, tratamos de procesar la solicitud de eliminación de datos lo antes posible.

**Solicitud**

You can log data deletion requests through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (see `delete` action). En ambos casos, debe cargar un JSON con los identificadores de Audience Manager para los que esté enviando la solicitud de acceso de datos. See what a well-formed JSON looks like in the [Experience Cloud GDPR documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md) (specifically, search in page for "POST request format"). Or, you can **[download a sample JSON](assets/delete_request.json)**.

**Respuesta**

Como respuesta a las solicitudes de eliminación de datos, eliminamos características y segmentos asociados con el identificador correspondiente de Audience Manager. Además, los identificadores correspondientes de Audience Manager para el asunto de los datos se excluirán permanentemente de la recopilación de datos de Audience Manager y se eliminarán las asignaciones de ID correspondientes. Cuando se envían ID declarados como ID de CRM cruzado de dispositivos o ID de cookies de cliente en solicitudes GDPR, Audience Manager realizará las acciones Eliminar necesarias en todos los dispositivos vinculados (hasta 100 dispositivos por ID declarado).

## Opt-out Request {#opt-out-request}

For opt-out requests, please refer to our documentation on [Opt-out Management](../../overview/data-security-and-privacy/opt-out-management.md).

## Audience Manager Identifiers (IDs) {#aam-ids}

Al enviar solicitudes GDPR a Adobe Audience Manager, debe incluir uno de los identificadores (ID) enumerados a continuación. You can find more information on the ID formats in our [Index of Audience Manager IDs](../../reference/ids-in-aam.md).

### ID de usuario único de Adobe Audience Manager

**ID de usuario**: aam_ uuid

**Definición**: ID de usuario único de Adobe Audience Manager

**ID de espacio de nombres**: 0

>[!NOTE]
>
>También puede utilizar el espacio de nombres PRINCIPAL. Consulte el segundo ejemplo JSON.

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

**ID de usuario**: mid

**Definición**: Adobe Experience Cloud ID, anteriormente conocido como ID de visitante o Marketing Cloud ID

**ID de espacio de nombres**: 4

>[!NOTE]
>
>También puede utilizar el espacio de nombres ECID. Consulte el segundo ejemplo JSON.

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

**ID de usuario**: cid

**Definición**: ID de cliente, como una cookie configurada para visitantes anónimos del sitio o un ID de CRM desde un sistema sin conexión o un nombre de usuario con hash

**ID de espacio de nombres**: Específica del cliente. Consulte la instancia de Audience Manager.

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

**ID de usuario**: d_ cid

**Definición**: ID de anuncios móviles.
>[!IMPORTANT]
>
> Si utiliza el SDK de Mobile, también debe enviar el ID de Experience Cloud (MID) junto con las ID de publicidad móviles para acceder a las respuestas completas de RDPD Access y Eliminar.

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

### Código de integración

**ID de usuario**: d_ cid_ ic

**Definición**: Código de integración para la fuente de datos. Se puede utilizar en lugar de ID de fuente de datos/ID de espacio de nombres en la solicitud de API al servicio principal de privacidad de Adobe Experience Cloud.

**ID de espacio de nombres**: No aplicable

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
