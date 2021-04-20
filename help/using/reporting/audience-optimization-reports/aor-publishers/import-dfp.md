---
description: Antes de que Audience Manager pueda habilitar Audience Optimization for Publishers, debe comprobar que se cumplan todos los requisitos descritos previamente en este artículo. Una vez que haya verificado que cumpla dichos requisitos, póngase en contacto con el servicio de atención al cliente.
seo-description: Antes de que Audience Manager pueda habilitar Audience Optimization for Publishers, debe comprobar que se cumplan todos los requisitos descritos previamente en este artículo. Una vez que haya verificado que cumpla dichos requisitos, póngase en contacto con el servicio de atención al cliente.
seo-title: Importar archivos de datos de Google Ad Manager en el Audience Manager
solution: Audience Manager
title: Importar archivos de datos de Google Ad Manager en el Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: Audience Optimization Reports
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 17%

---

# Importar archivos de datos de Google Ad Manager (anteriormente DFP) en el Audience Manager{#import-dfp-data-files-into-audience-manager}

Antes de que Audience Manager pueda habilitar Audience Optimization for Publishers, debe comprobar que se cumplan todos los requisitos descritos previamente en este artículo. Una vez que haya verificado que cumpla dichos requisitos, póngase en contacto con el servicio de atención al cliente.

## Requisitos previos para la ingesta de registros de Google Ad Manager {#prereqs-dfp-ingestion}

Tenga en cuenta que el proceso descrito en esta sección debe completarse *antes* de pasar a los requisitos previos para la activación de la ingesta de registros.

Para utilizar archivos de registro [!DNL Google Ad Manager] (anteriormente DFP de Google) en [!DNL Audience Manager], primero debe configurar nuestro [ID de usuario único de Audience Manager (UUID)](../../../reference/ids-in-aam.md) en la llamada de etiqueta de anuncio. Al hacerlo, nuestro ID se incluye en los registros [!DNL Google Ad Manager] y podemos hacer coincidir los ID entre [!DNL Google Ad Manager] y [!DNL Audience Manager]. Utilice el código [!DNL Audience Manager] [!UICONTROL DIL] o el [!UICONTROL Audience Management Module] para establecer el UUID [!DNL Audience Manager] en una cookie de origen.

A continuación se muestra cómo configurar el ID [!DNL Audience Manager] en la llamada de etiqueta de anuncio, tal como se explica en nuestra documentación:

* [A través de Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Mediante un destino de cookie](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

Debe configurar usted mismo el [!DNL Audience Manager] ID y puede trabajar con la asesoría [!DNL Audience Manager] para comprobar si todo funciona. Ha configurado correctamente el [!DNL Audience Manager] ID si:

* `'aamid'` es la clave utilizada como identificador.
* El valor del ID de usuario tiene el formato correcto como UUID [!DNL Audience Manager], tal como se describe en nuestro [Índice de ID en Audience Manager](../../../reference/ids-in-aam.md).
* Ha incluido el UUID [!DNL Audience Manager] en un campo definido en los registros [!DNL Google Ad Manager] (por ejemplo, CustomTargeting).

## Requisitos previos para la habilitación de ingesta de registros {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>Confirme que los pasos necesarios para establecer el UUID de <span class="keyword"> Audience Manager</span> (descritos anteriormente) se han completado antes de pasar al paso 2. </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience </span> ManagerServicio de atención al cliente o consultoría </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paso 2 </p> </td> 
   <td colname="col2"> <p>El administrador de Google Ad Manager crea: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Cuenta de servicio para la ingesta de registros de Google Ad Manager en el <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Credenciales nuevas. <p>Nota:  Esto puede requerir una dirección de correo electrónico única específica para este proyecto y se utilizará al provisioning del acceso a Google Storage Bucket. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Una clave privada (credencial basada en JSON) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>El administrador de Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paso 3 </p> </td> 
   <td colname="col2"> <p>El administrador de Google Ad Manager concede acceso de API a la cuenta de servicio. Este paso permite acceder a los metadatos para delinear dimensiones (elementos de línea, pedidos, elementos creativos). <p>Nota:  Utilice el acceso de correo electrónico de la cuenta de servicio que configuró en el paso 2 para conceder permiso para acceder a la API. </p> </p> </td> 
   <td colname="col3"> <p>El administrador de Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paso 4 </p> </td> 
   <td colname="col2"> <p>El administrador de Google Ad Manager establece el acceso al espacio de almacenamiento de Google. Recuerde: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Esto se puede hacer a través de un grupo de Google. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Asocie la dirección de correo electrónico única asignada a la cuenta de servicio al espacio de almacenamiento. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>El administrador de Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paso 5 </p> </td> 
   <td colname="col2"> <p>El administrador de Google Ad Manager proporciona el ID de red de Google Ad Manager. Esto nos permite pasar el ID de red al realizar llamadas a la API. </p> </td> 
   <td colname="col3"> <p>El administrador de Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paso 6 </p> </td> 
   <td colname="col2"> <p>Compile los requisitos previos en un mensaje de correo electrónico a AAM Servicio de atención al cliente (aamsupport@adobe.com) para iniciar el proceso de ingesta de registros. Borre el correo electrónico utilizando la plantilla en la siguiente sección. </p> </td> 
   <td colname="col3"> <p>Usted o <span class="keyword"> Audience Manager</span> Consultoría en su nombre </p> </td> 
  </tr> 
 </tbody> 
</table>

## Plantilla de correo electrónico {#email-template}

Para finalizar la habilitación de ingesta de registros, envíenos un correo electrónico a aamsupport@adobe.com. Utilice la [plantilla de correo electrónico adjunta](assets/enable_dfp_ingestion.txt).
