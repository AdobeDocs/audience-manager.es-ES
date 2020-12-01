---
description: Código requerido por DART Enterprise (y otros tipos de destino) para capturar el valor de ID de usuario único (UUID) del Audience Manager.
seo-description: Código requerido por DART Enterprise (y otros tipos de destino) para capturar el valor de ID de usuario único (UUID) del Audience Manager.
seo-title: Código get_aamCookie
solution: Audience Manager
title: Código get_aamCookie
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 9%

---


# `get_aamCookie` Código {#get-aamcookie-code}

Código requerido por [!DNL DART Enterprise] (y otros tipos de destino) para capturar el valor de ID de usuario único del Audience Manager ([!DNL UUID]).

Defina esta función en la parte superior de la página, idealmente dentro del bloque de código `<head>`.

<!-- r_aam_de_cookie.xml -->

```js
<script type="text/javascript">
function get_aamCookie (c_name)
{
var i,x,y,ARRcookies=document.cookie.split(";");
for (i=0;i<ARRcookies.length;i++)
   {
   x=ARRcookies[i].substr(0,ARRcookies[i].indexOf("="));
   y=ARRcookies[i].substr(ARRcookies[i].indexOf("=")+1);
   x=x.replace(/^\s+|\s+$/g,"");
   if (x==c_name)
      { 
      return unescape(y);
      }
   }
}
</script>
```
