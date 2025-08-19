---
description: añadir una instrucción if para comprobar si hay Audience Manager cookies antes de llamar al método .setTargeting de etiqueta de editor de Google.
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: Modificar la llamada a la API de GPT setTargeting
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# Modificar la llamada a la API de GPT `setTargeting` {#modify-the-gpt-settargeting-api-call}

añadir una instrucción if para comprobar si hay cookies de Audience Manager antes de llamar al [!DNL Google Publisher Tag] `.setTargeting` método.

## Compruebe si hay cookies de Audience Manager con un estado de `IF` cuenta

El `.setTargeting` método obtiene datos del cookie de destino Audience Manager y del ID de usuario único cookie ( `aam_uuid`). Sin embargo, si se invoca antes `.setTargeting` de escribir estas cookies, o si [!UICONTROL DIL] las cookies están vacías, es posible que vea errores cuando se cargue el Página. Para ayudar a evitar esto, ajuste el `.setTargeting` método en una `if` declaración que compruebe si hay estas cookies. Si no se establecen, esta instrucción impide `.setTargeting` llamar a la `AamGpt` función.

### `IF` Muestra de Code de declaración

En este ejemplo, el Audience Manager destino cookie nombre es `Sample`. Este nombre se establece al crear el cookie de destino en la interfaz de usuario de Audience Manager. [!UICONTROL DIL] Define el `aam_uuid` cookie y el nombre no se puede cambiar.

```js
if(typeof AamGpt.getCookie("Sample") != "undefined"){ 
  googletag.pubads().setTargeting(AamGpt.getKey("Sample"),AamGpt.getValues("Sample")); 
}; 
if(typeof AamGpt.getCookie("aam_uuid") != "undefined" ){ 
   googletag.pubads().setTargeting("aamId", AamGpt.getCookie("aam_uuid")); 
};
```

>[!IMPORTANT]
>
>En función de cómo desee integrar con [!DNL Google Ad Manager], solo necesitará algunas de las líneas del ejemplo de código anterior:
>
>* Integración del lado del cliente: utilice solo las líneas 1-3.
>* Integración del lado del servidor: no se necesita ninguna de las líneas.
>* Ingest [!DNL Google Ad Manager] log files for sistema de informes in : [!DNL Audience Manager]use las líneas 4-6 solamente. Este código inserta el valor de los `aam_uuid` cookie en los registros para que puedan ser ingeridos durante sistema de informes.

### `AamGpt` Funciones y tipos de datos

Define las variables clave utilizadas en la `if` instrucción.

<table id="table_881391C9BDDF4FACAFC37A47B14B31A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getKey </code> </p> </td> 
   <td colname="col2"> <p>Cadena </p> </td> 
   <td colname="col3"> <p>Devuelve la clave en el par de segmento clave-valor. Por ejemplo, si el par clave-valor consistió en <code> color=blue </code>, esto devuelve <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Matriz de cadenas </p> </td> 
   <td colname="col3"> <p>Devuelve valores en una matriz, por ejemplo, <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Devuelve el ID de usuario Audience Manager, p. ej., <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Crear un destino GPT](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Código de Audience Manager para etiquetas de Publicador de Google](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)
