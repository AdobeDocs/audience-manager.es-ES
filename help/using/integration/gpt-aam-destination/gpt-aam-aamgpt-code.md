---
description: AamGpt es una función de JavaScript que lee los datos de cookies de Audience Manager y envía esa información a Google Publisher Tags.
seo-description: AamGpt es una función de JavaScript que lee los datos de cookies de Audience Manager y envía esa información a Google Publisher Tags.
seo-title: Código de Audience Manager para etiquetas de publicador de Google
solution: Audience Manager
title: Código de Audience Manager para etiquetas de publicador de Google
uuid: 24ff5d16-b360-46cc-a4c6-6db34d7fda75
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Código de Audience Manager para etiquetas de publicador de Google {#audience-manager-code-for-google-publisher-tags}

`AamGpt` es una [!DNL JavaScript] función que lee los datos de cookies de Audience Manager y envía esa información a [!DNL Google Publisher Tags].

>[!NOTE]
>
>Esta función no es necesaria si tiene su propio código para leer los datos de cookies de Audience Manager desde las cookies [!UICONTROL UUID] y de destino.

## Código de muestra

Coloque el `AamGpt` código al principio de la página, idealmente dentro del bloque de `<head>` código. El `AamGpt` código está disponible a continuación:

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
