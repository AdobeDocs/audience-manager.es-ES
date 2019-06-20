---
description: Antes de que Audience Manager pueda habilitar Audience Optimization for Publishers, debe comprobar que se cumplan todos los requisitos descritos previamente en este artículo. Una vez que haya verificado que cumpla dichos requisitos, póngase en contacto con el servicio de atención al cliente.
seo-description: Antes de que Audience Manager pueda habilitar Audience Optimization for Publishers, debe comprobar que se cumplan todos los requisitos descritos previamente en este artículo. Una vez que haya verificado que cumpla dichos requisitos, póngase en contacto con el servicio de atención al cliente.
seo-title: Importación de archivos de datos DFP en Audience Manager
solution: Audience Manager
title: Importación de archivos de datos DFP en Audience Manager
uuid: c 685 f 34 f -3 e 50-4 c 4 b -99 fa-d 8 bbafe 0 b 268
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Importación de archivos de datos DFP en Audience Manager{#import-dfp-data-files-into-audience-manager}

Antes de que Audience Manager pueda habilitar Audience Optimization for Publishers, debe comprobar que se cumplan todos los requisitos descritos previamente en este artículo. Una vez que haya verificado que cumpla dichos requisitos, póngase en contacto con el servicio de atención al cliente.

## Prerequisites for DFP Log Ingestion {#prereqs-dfp-ingestion}

Note that the process described in this section must be completed *before* you move on to the prerequisites for log ingestion enablement.

In order to use DFP ( [!DNL DoubleClick For Publishers]) log files in [!DNL Audience Manager], you must first set our [Audience Manager Unique User ID (UUID)](../../../reference/ids-in-aam.md) in the ad tag call. By doing this, our ID is included in the DFP logs and we can match IDs between DFP and [!DNL Audience Manager]. Use [!DNL Audience Manager] [!UICONTROL DIL] code or the [!UICONTROL Audience Management Module] to set the [!DNL Audience Manager] UUID in a first party cookie.

Here is how to set the [!DNL Audience Manager] ID in the ad tag call, as explained in our documentation:

* [A través de la etiqueta de Google Publisher (GPT)](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
* [A través de un destino de cookie](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)

You need to set the [!DNL Audience Manager] ID yourself, and can work with [!DNL Audience Manager] consulting to check if everything works. You have set the [!DNL Audience Manager] ID correctly if:

* `'aamid'` es la clave utilizada como identificador.
* The User ID value is correctly formatted as the [!DNL Audience Manager] UUID, as described in our [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md).
* You have included the [!DNL Audience Manager] UUID in a defined field in your DFP logs (e.g. CustomTargeting).

## Prerequisites for Log Ingestion Enablement {#prereqs-ingestion-enablement}

<table id="table_C980A9F9B0FB4157B4908A64768B1571"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paso </th> 
   <th colname="col2" class="entry"> Detalles </th> 
   <th colname="col3" class="entry"> Propietario </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Paso 1 </p> </td> 
   <td colname="col2"> <p>Confirm that the required steps to set the <span class="keyword"> Audience Manager</span> UUID (outlined above) have been completed prior to moving to Step 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Servicio</span> de atención al cliente de Audience Manager o consultoría </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paso 2 </p> </td> 
   <td colname="col2"> <p>El administrador de DFP crea: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">A service account for ingesting DFP logs into <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Nuevas credenciales. <p>Nota: Esto puede requerir una única dirección de correo electrónico específica para este proyecto y se utilizará al suministrar acceso al bloque de almacenamiento de Google. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Una clave privada (credencial basada en JSON) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Administrador de DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paso 3 </p> </td> 
   <td colname="col2"> <p>El administrador de DFP concede acceso API a la cuenta de servicio. Este paso permite el acceso a los metadatos para delinear dimensiones (elementos de línea, pedidos, elementos creativos). <p>Nota: Utilice el acceso de correo electrónico de cuenta de servicio que configure en el paso 2 para otorgar permiso para acceder a la API. </p> </p> </td> 
   <td colname="col3"> <p>Administrador de DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paso 4 </p> </td> 
   <td colname="col2"> <p>El administrador de DFP establece el acceso al bloque de almacenamiento de Google. Recuerde: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Esto se puede hacer a través de un grupo de Google. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Asocie la dirección de correo electrónico exclusiva asignada a la cuenta de servicio al bloque de almacenamiento. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Administrador de DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paso 5 </p> </td> 
   <td colname="col2"> <p>El administrador de DFP proporciona el ID de red DFP. Esto permite pasar el ID de red al realizar llamadas a la API. </p> </td> 
   <td colname="col3"> <p>Administrador de DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paso 6 </p> </td> 
   <td colname="col2"> <p>Compile los requisitos previos en un mensaje de correo electrónico con el Servicio de atención al cliente de AAM (aamsupport@adobe.com) para desactivar el proceso de inserción de registro. Borrador del correo electrónico con la plantilla en la siguiente sección. </p> </td> 
   <td colname="col3"> <p>You, or <span class="keyword"> Audience Manager</span> Consulting on your behalf </p> </td> 
  </tr> 
 </tbody> 
</table>

## E-Mail Template {#email-template}

Para finalizar la activación de la inserción del registro, envíenos un mensaje de correo electrónico a aamsupport@adobe.com. Please use the [attached e-mail template](assets/enable_dfp_ingestion.txt).
