---
description: Agregue una instrucción if para comprobar las cookies de Audience Manager antes de llamar al método Google Publisher Tag.setTargeting.
seo-description: Agregue una instrucción if para comprobar las cookies de Audience Manager antes de llamar al método Google Publisher Tag.setTargeting.
seo-title: Modificar la llamada de API de setTargeting de GPT
solution: Audience Manager
title: Modificar la llamada de API de setTargeting de GPT
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Modificación de la llamada de `setTargeting` API de GPT {#modify-the-gpt-settargeting-api-call}

Agregue una instrucción if para comprobar las cookies de Audience Manager antes de llamar al [!DNL Google Publisher Tag] método `.setTargeting` .

## Buscar cookies de Audience Manager con una `IF` instrucción

El `.setTargeting` método obtiene datos de la cookie de destino de Audience Manager y de la cookie de ID de usuario única ( `aam_uuid`). Sin embargo, si `.setTargeting` se invoca antes de [!UICONTROL DIL] escribir estas cookies, o si las cookies están vacías, es posible que se produzcan errores al cargar la página. Para evitar esto, ajuste el `.setTargeting` método en una `if` instrucción que compruebe si hay cookies. Si no están configurados, esta instrucción evita `.setTargeting` llamar a la `AamGpt` función.

### `IF` Ejemplo de código de instrucción

En este ejemplo, el nombre de la cookie de destino de Audience Manager es `Sample`. Este nombre se establece al crear la cookie de destino en la interfaz de usuario de Audience Manager. [!UICONTROL DIL] establece la `aam_uuid` cookie y no se puede cambiar el nombre.

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
>Según la integración con [!DNL DFP], solo necesita algunas de las líneas del ejemplo de código anterior:
>
>* Integración del cliente: utilice únicamente las líneas 1-3.
>* Integración del lado del servidor: no se necesita ninguna de las líneas.
>* Ingestar archivos [!DNL DFP] de registro para crear informes en [!DNL Audience Manager]: utilice únicamente las líneas 4-6. Este código inserta el valor de la `aam_uuid` cookie en los registros para que se puedan ingerir en los informes.


### `AamGpt` Funciones y tipos de datos

Define las variables clave utilizadas en la `if` sentencia.

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
   <td colname="col3"> <p>Devuelve la clave del par de segmentos clave-valor. Por ejemplo, si el par clave-valor consistió en <code> color=blue </code>, se devuelve <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Matriz de cadenas </p> </td> 
   <td colname="col3"> <p>Devuelve valores en una matriz, por ejemplo, <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Devuelve el ID de usuario de Audience Manager, por ejemplo <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Crear un destino GPT](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Código de Audience Manager para etiquetas de publicador de Google](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

