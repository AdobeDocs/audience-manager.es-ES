---
description: Agregue una instrucción if para comprobar si hay cookies de Audience Manager antes de llamar al método Google Publisher Tag .setTargeting .
seo-description: Agregue una instrucción if para comprobar si hay cookies de Audience Manager antes de llamar al método Google Publisher Tag .setTargeting .
seo-title: Modificación de la llamada de API de setTargeting de GPT
solution: Audience Manager
title: Modificación de la llamada de API de setTargeting de GPT
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 9%

---

# Modificación de la llamada de API `setTargeting` GPT {#modify-the-gpt-settargeting-api-call}

Agregue una sentencia if para comprobar si hay cookies de Audience Manager antes de llamar al método [!DNL Google Publisher Tag] `.setTargeting` .

## Comprobar las cookies del Audience Manager con una instrucción `IF`

El método `.setTargeting` obtiene datos de la cookie de destino del Audience Manager y la cookie de ID de usuario único ( `aam_uuid`). Sin embargo, si `.setTargeting` se invoca antes de que [!UICONTROL DIL] escriba estas cookies o las cookies están vacías, puede que se observen errores al cargar la página. Para evitar esto, ajuste el método `.setTargeting` en una instrucción `if` que compruebe estas cookies. Si no están configurados, esta instrucción evita que `.setTargeting` llame a la función `AamGpt`.

### `IF` Ejemplo de código de instrucción

En este ejemplo, el nombre de la cookie de destino del Audience Manager es `Sample`. Este nombre se establece al crear la cookie de destino en la interfaz de usuario del Audience Manager. [!UICONTROL DIL] establece la  `aam_uuid` cookie y no se puede cambiar el nombre.

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
>Dependiendo de cómo desee integrar con [!DNL Google Ad Manager], solo necesita algunas de las líneas del ejemplo de código anterior:
>
>* Integración del lado del cliente: utilice únicamente las líneas 1-3.
>* Integración del lado del servidor: no se necesita ninguna de las líneas.
>* Ingesta de [!DNL Google Ad Manager] archivos de registro para informes en [!DNL Audience Manager]: utilice únicamente las líneas 4-6. Este código inserta el valor de la cookie `aam_uuid` en los registros para que se puedan ingerir en los informes.


### `AamGpt` Funciones y tipos de datos

Define las variables clave utilizadas en la instrucción `if`.

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
   <td colname="col3"> <p>Devuelve la clave en el par de segmentos clave-valor. Por ejemplo, si el par clave-valor consiste en <code> color=blue </code>, esto devuelve <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Matriz de cadenas </p> </td> 
   <td colname="col3"> <p>Devuelve valores de una matriz, por ejemplo, <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Devuelve el ID de usuario del Audience Manager, por ejemplo, <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Crear un destino GPT](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Código de Audience Manager para etiquetas de Publicador de Google](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

