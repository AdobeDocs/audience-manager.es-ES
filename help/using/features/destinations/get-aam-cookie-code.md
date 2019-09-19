---
description: Código requerido por DART Enterprise (y otros tipos de destino) para capturar el valor de ID de usuario único (UUID) de Audience Manager.
seo-description: Código requerido por DART Enterprise (y otros tipos de destino) para capturar el valor de ID de usuario único (UUID) de Audience Manager.
seo-title: get_aamCookie Code
solution: Audience Manager
title: get_aamCookie Code
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
translation-type: tm+mt
source-git-commit: abb66d75a0d47f5257ea8c63bdb59e604db801d3

---


# `get_aamCookie` Código {#get-aamcookie-code}

Código requerido por [!DNL DART Enterprise] (y otros tipos de destino) para capturar el valor de ID de usuario único ([!DNL UUID]) de Audience Manager.

Defina esta función en la parte superior de la página, idealmente dentro del bloque de `<head>` código.

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
