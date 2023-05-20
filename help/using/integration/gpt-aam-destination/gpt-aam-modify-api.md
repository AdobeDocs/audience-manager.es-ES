---
description: Agregue una instrucción if para buscar cookies de Audience Manager antes de llamar al método Google Publisher Tag .setTargeting.
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: Modificación de la llamada de API de setTargeting de GPT
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 7%

---

# Modificación del GPT `setTargeting` Llamada de API {#modify-the-gpt-settargeting-api-call}

Agregue una instrucción if para comprobar si hay cookies del Audience Manager antes de llamar al [!DNL Google Publisher Tag] `.setTargeting` método.

## Buscar cookies de Audience Manager con un `IF` Declaración

El `.setTargeting` obtiene datos de la cookie de destino del Audience Manager y de la cookie de ID de usuario único ( `aam_uuid`). Sin embargo, si `.setTargeting` se invoca antes de [!UICONTROL DIL] escribe estas cookies, o las cookies están vacías, puede ver errores cuando se carga la página. Para evitar esto, ajuste el `.setTargeting` método en una `if` que comprueba la existencia de estas cookies. Si no están configuradas, esta instrucción evita `.setTargeting` de llamar a `AamGpt` función.

### `IF` Ejemplo de código de instrucción

En este ejemplo, el nombre de la cookie de destino del Audience Manager es `Sample`. Este nombre se establece al crear la cookie de destino en la interfaz de usuario del Audience Manager. [!UICONTROL DIL] establece el `aam_uuid` y no se puede cambiar el nombre.

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
>Según la forma en que desee integrar con [!DNL Google Ad Manager], solo necesita algunas de las líneas del ejemplo de código anterior:
>
>* Integración del lado del cliente: utilice solo las líneas 1-3.
>* Integración del lado del servidor: no se necesita ninguna de las líneas.
>* Ingesta [!DNL Google Ad Manager] archivos de registro para informes en [!DNL Audience Manager]: utilice solo las líneas 4-6. Este código inserta el valor de `aam_uuid` en los registros para que se puedan introducir para la creación de informes.


### `AamGpt` Funciones y tipos de datos

Define las variables clave utilizadas en la variable `if` declaración.

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
   <td colname="col3"> <p>Devuelve valores en una matriz, por ejemplo, <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Devuelve el ID de usuario del Audience Manager, por ejemplo,. <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Crear un destino GPT](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Código de Audience Manager para etiquetas de Publicador de Google](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

