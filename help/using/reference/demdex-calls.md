---
description: Audience Manager y el servicio Experience Cloud ID realizan llamadas al dominio demdex.net y reciben datos de él. Esto puede parecer que Adobe está trabajando con un dominio de terceros inusual, pero no es el caso. Esta sección describe los elementos de una llamada demdex.net.
seo-description: Audience Manager y el servicio Experience Cloud ID realizan llamadas al dominio demdex.net y reciben datos de él. Esto puede parecer que Adobe está trabajando con un dominio de terceros inusual, pero no es el caso. Esta sección describe los elementos de una llamada demdex.net.
seo-title: Explicación de las llamadas al dominio Demdex
solution: Audience Manager
title: Explicación de las llamadas al dominio Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Explicación de las llamadas al dominio Demdex{#understanding-calls-to-the-demdex-domain}

Audience Manager y el servicio Experience Cloud ID realizan llamadas al dominio demdex.net y reciben datos de él. Esto puede parecer que Adobe está trabajando con un dominio de terceros inusual, pero no es el caso. Esta sección describe los elementos de una llamada demdex.net.

<table id="table_B846CBEDDA4C4AD19416F7C27FC325C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de llamada </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> demdex.net</code> </p> </td> 
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. Refleja <span class="keyword"> el nombre original de Audience Manager</span>, anterior a la adquisición (<span class="keyword"> Demdex</span>). <span class="keyword"> Adobe</span> adquirió <span class="keyword"> Demdex</span> en 2011 y cambió la marca de la empresa a <span class="keyword"> Audience Manager</span>. Es difícil cambiar este dominio porque está estrechamente vinculado con <span class="keyword"> Audience Manager</span>, el servicio <span class="wintitle"> de</span>ID y nuestra base de usuarios instalada. Consulte <a href="../overview/aam-overview.md#history-and-background"> Historial y fondo</a>. </p> <p>Puede ver otros prefijos adjuntos a <code> demdex.net</code> llamadas preexistentes (por ejemplo, <code> dcs.demdex.net</code>, <code> fast.demdex.net</code>, etc.). Independientemente del prefijo, una llamada a <code><i>something</i>.demdex.net</code> es siempre una llamada a <span class="keyword"> Adobe</span> y no a un dominio de terceros desconocido o sospechoso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> es una abreviatura de Coincidencia <span class="wintitle"> del proveedor</span>de datos. Indica a los sistemas internos de Adobe <span class="keyword"></span> que una llamada desde <span class="keyword"> Audience Manager</span> o el servicio <span class="wintitle"> de</span> ID está pasando datos de clientes para la sincronización o para solicitar un ID. Esta es la llamada más común <code> demdex.net</code> que verá desde <span class="keyword"> Audience Manager</span> o desde el servicio <span class="wintitle"> de</span>ID. </p> <p><span class="wintitle"> Conceptos básicos de llamadas de DPM</span> : </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> <span class="keyword"> Audience Manager</span> </b>: Una llamada de <span class="wintitle"> DPM</span> desde <span class="keyword"> Audience Manager</span> envía datos a los servidores <span class="wintitle"> de recopilación de datos y a los servidores</span> de caché de <span class="wintitle"></span>perfiles. Consulte <a href="../reference/system-components/components-data-collection.md"> Componentes</a>de recopilación de datos. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> <span class="wintitle"> Servicio</span> de ID </b>: Una llamada de <span class="wintitle"> DPM</span> desde el servicio <span class="wintitle"> de</span> ID es una solicitud de ID de visitante. Consulte <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies y el servicio</a> Experience Cloud ID y <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="https" scope="external"> Cómo solicita y establece los ID</a>el servicio Experience Cloud ID. </li> 
     </ul> </p> <p> <p>Nota:  Los clientes del servicio <span class="wintitle"> de</span> ID pueden cambiar el prefijo <span class="wintitle"> DPM</span> en el nombre de dominio. Consulte <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-subdomain-config.html" format="https" scope="external"> audienceManager Server y audienceManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Servicio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/)
>* [Cookies de Audience Manager](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)

