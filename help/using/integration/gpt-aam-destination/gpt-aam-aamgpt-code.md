---
description: AamGpt es una función de JavaScript que lee datos de cookies de Audience Manager y envía esa información a las etiquetas de publicador de Google.
seo-description: AamGpt is a JavaScript function that reads Audience Manager cookie data and sends that information to Google Publisher Tags.
seo-title: Audience Manager Code for Google Publisher Tags
solution: Audience Manager
title: Código de Audience Manager para etiquetas de publicador de Google
uuid: 24ff5d16-b360-46cc-a4c6-6db34d7fda75
feature: Third-party Integration
exl-id: 04e74399-7b6a-400e-a1e6-94fe296e7209
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 2%

---

# Código de Audience Manager para etiquetas de publicador de Google {#audience-manager-code-for-google-publisher-tags}

`AamGpt` es una función de [!DNL JavaScript] que lee datos de cookies de Audience Manager y envía esa información a [!DNL Google Publisher Tags].

>[!NOTE]
>
>Esta función no es necesaria si dispone de su propio código para leer los datos de cookies de Audience Manager de [!UICONTROL UUID] y las cookies de destino.

## Código de muestra

Coloque el código `AamGpt` en la parte superior de la página, idealmente dentro del bloque de código `<head>`. El código `AamGpt` está disponible a continuación:

```js
var AamGpt = {  
 strictEncode: function(str){ 
  return encodeURIComponent(str).replace(/[!'()]/g, escape).replace(/\*/g, "%2A"); 
 }, 
 getCookie: function(c_name) 
 { 
  var i,x,y,c=document.cookie.split(";"); 
  for (i=0;i<c.length;i++) 
  { 
   x=c[i].substr(0,c[i].indexOf("=")); 
   y=c[i].substr(c[i].indexOf("=")+1); 
   x=x.replace(/^\s+|\s+$/g,""); 
   if (x==c_name) 
   { 
    return unescape(y); 
   } 
  } 
 }, 
 getKey: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[0] != "undefined" && cList[0].match(/\w+/)) 
   { 
    return cList[0]; 
   } 
  }  
 }, 
 getValues: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D\w+/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[1] != "undefined" && cList[1].match(/\w+/)) 
   { 
    var vList=cList[1].split("%2C"); 
    if(typeof vList[0] != "undefined") 
    { 
     return vList; 
    } else { 
     return null; 
    }    
   } else { 
    return null; 
   } 
  } else { 
   return null; 
  } 
 } 
};
```
