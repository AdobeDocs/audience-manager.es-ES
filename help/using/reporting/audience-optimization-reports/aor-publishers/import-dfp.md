---
description: Antes de que Audience Manager pueda habilitar Audience Optimization for Publishers, debe comprobar que se cumplan todos los requisitos descritos previamente en este artículo. Una vez que haya verificado que cumpla dichos requisitos, póngase en contacto con el servicio de atención al cliente.
seo-description: Antes de que Audience Manager pueda habilitar Audience Optimization for Publishers, debe comprobar que se cumplan todos los requisitos descritos previamente en este artículo. Una vez que haya verificado que cumpla dichos requisitos, póngase en contacto con el servicio de atención al cliente.
seo-title: Importación de archivos de datos DFP en Audience Manager
solution: Audience Manager
title: Importación de archivos de datos DFP en Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Importación de archivos de datos DFP en Audience Manager{#import-dfp-data-files-into-audience-manager}

Antes de que Audience Manager pueda habilitar Audience Optimization for Publishers, debe comprobar que se cumplan todos los requisitos descritos previamente en este artículo. Una vez que haya verificado que cumpla dichos requisitos, póngase en contacto con el servicio de atención al cliente.

## Requisitos previos para la ingesta de registros de DFP {#prereqs-dfp-ingestion}

Tenga en cuenta que el proceso descrito en esta sección debe completarse *antes* de pasar a los requisitos previos para habilitar la ingesta de registros.

Para utilizar los archivos de registro de DFP ( [!DNL DoubleClick For Publishers]) en [!DNL Audience Manager], primero debe establecer el ID de usuario único (UUID) [de](../../../reference/ids-in-aam.md) Audience Manager en la llamada de etiqueta de anuncio. Al hacer esto, nuestro ID se incluye en los registros de DFP y podemos hacer coincidir los ID entre DFP y [!DNL Audience Manager]. Utilice [!DNL Audience Manager] código o [!UICONTROL DIL] para establecer el [!UICONTROL Audience Management Module] [!DNL Audience Manager] UUID en una cookie de origen.

A continuación se muestra cómo configurar el [!DNL Audience Manager] ID en la llamada de etiqueta de publicidad, según se explica en nuestra documentación:

* [Mediante la etiqueta de publicador de Google (GPT)](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
* [Mediante un destino de cookie](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)

Debe configurar usted mismo la [!DNL Audience Manager] ID y puede trabajar con [!DNL Audience Manager] asesoría para comprobar si todo funciona. Ha configurado la [!DNL Audience Manager] ID correctamente si:

* `'aamid'` es la clave utilizada como identificador.
* El valor de ID de usuario tiene el formato correcto como [!DNL Audience Manager] UUID, tal como se describe en nuestro [índice de ID en Audience Manager](../../../reference/ids-in-aam.md).
* Ha incluido el [!DNL Audience Manager] UUID en un campo definido en los registros de DFP (por ejemplo, CustomTargeting).

## Requisitos previos para la habilitación de la ingesta de registros {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>Confirme que los pasos necesarios para establecer el UUID de <span class="keyword"> Audience Manager</span> (descrito anteriormente) se han completado antes de pasar al paso 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Servicio de atención al cliente o consultoría de Audience Manager</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paso 2 </p> </td> 
   <td colname="col2"> <p>El administrador de DFP crea: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Cuenta de servicio para la ingesta de registros de DFP en <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Nuevas credenciales. <p>Nota:  Esto puede requerir una dirección de correo electrónico única específica para este proyecto y se utilizará al aprovisionar el acceso al bloque de almacenamiento de Google. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Una clave privada (credencial basada en JSON) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Su administrador de DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paso 3 </p> </td> 
   <td colname="col2"> <p>El administrador de DFP concede a la API acceso a la cuenta de servicio. Este paso permite acceder a los metadatos para delimitar las dimensiones (elementos de línea, pedidos, elementos creativos). <p>Nota:  Utilice el acceso por correo electrónico a la cuenta de servicio que configuró en el paso 2 para conceder permiso para acceder a la API. </p> </p> </td> 
   <td colname="col3"> <p>Su administrador de DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paso 4 </p> </td> 
   <td colname="col2"> <p>El administrador de DFP establece el acceso a Google Storage Bucket. Recuerde: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Esto se puede hacer a través de un grupo de Google. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Asocie la dirección de correo electrónico única asignada a la cuenta de servicio al bloque de almacenamiento. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Su administrador de DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paso 5 </p> </td> 
   <td colname="col2"> <p>El administrador de DFP proporciona el ID de red de DFP. Esto nos permite pasar el ID de red al realizar llamadas a la API. </p> </td> 
   <td colname="col3"> <p>Su administrador de DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paso 6 </p> </td> 
   <td colname="col2"> <p>Compile los requisitos previos en un mensaje de correo electrónico al Servicio de atención al cliente de AAM (aamsupport@adobe.com) para iniciar el proceso de ingesta de registros. Borre el correo electrónico con la plantilla de la siguiente sección. </p> </td> 
   <td colname="col3"> <p>Usted o <span class="keyword"> Consultoría de Audience Manager</span> en su nombre </p> </td> 
  </tr> 
 </tbody> 
</table>

## Plantilla de correo electrónico {#email-template}

Para finalizar la habilitación de inserción de registros, envíenos un correo electrónico a aamsupport@adobe.com. Utilice la plantilla [de correo electrónico](assets/enable_dfp_ingestion.txt)adjunta.
