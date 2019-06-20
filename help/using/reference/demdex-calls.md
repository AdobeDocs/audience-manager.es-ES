---
description: Audience Manager y el servicio Experience Cloud ID realizan llamadas al dominio demdex.net y reciben datos de él. Esto puede parecer que Adobe funciona con un dominio de terceros inusual, pero esto no sucede. Esta sección describe los elementos en una llamada demdex. net.
seo-description: Audience Manager y el servicio Experience Cloud ID realizan llamadas al dominio demdex.net y reciben datos de él. Esto puede parecer que Adobe funciona con un dominio de terceros inusual, pero esto no sucede. Esta sección describe los elementos en una llamada demdex. net.
seo-title: Explicación de las llamadas al dominio Demdex
solution: Audience Manager
title: Explicación de las llamadas al dominio Demdex
uuid: c 06 dae 3 a-f 169-4712-80 fb-d 6 d 448 dce 51 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Explicación de las llamadas al dominio Demdex{#understanding-calls-to-the-demdex-domain}

Audience Manager y el servicio Experience Cloud ID realizan llamadas al dominio demdex.net y reciben datos de él. Esto puede parecer que Adobe funciona con un dominio de terceros inusual, pero esto no sucede. Esta sección describe los elementos en una llamada demdex. net.

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
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. It reflects <span class="keyword"> Audience Manager</span>'s original, pre-acquisition name (<span class="keyword"> Demdex</span>). <span class="keyword"> Adobe</span> adquirió <span class="keyword"> Demdex</span> en 2011 y volvió a personalizar la empresa como <span class="keyword"> Audience Manager</span>. It is difficult to change this domain because it is entwined deeply with <span class="keyword"> Audience Manager</span>, the <span class="wintitle"> ID service</span>, and our installed user base. See <a href="../overview/aam-overview.md#history-and-background"> History and Background</a>. </p> <p>You may see other prefixes attached to legacy <code> demdex.net</code> calls (e.g., <code> dcs.demdex.net</code>, <code> fast.demdex.net</code>, etc.). Regardless of the prefix, a call to <code><i>something</i>.demdex.net</code> is always a call to <span class="keyword"> Adobe</span> and not to some unknown or suspicious third-party domain. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> es una abreviatura de <span class="wintitle"> Coincidencia del proveedor de datos</span>. It tells internal, <span class="keyword"> Adobe</span> systems that a call from <span class="keyword"> Audience Manager</span> or the <span class="wintitle"> ID service</span> is passing in customer data for synchronization or requesting an ID. This is the most common <code> demdex.net</code> call you'll see from <span class="keyword"> Audience Manager</span> or the <span class="wintitle"> ID service</span>. </p> <p><span class="wintitle"> Conceptos básicos</span> de llamada DPM: </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b><span class="keyword"> Audience Manager</span></b>: Una llamada <span class="wintitle"> DPM</span> desde <span class="keyword"> Audience Manager</span> envía datos a los <span class="wintitle"> servidores de recopilación de datos</span> y <span class="wintitle"> a los servidores de caché de perfil</span>. See <a href="../reference/system-components/components-data-collection.md"> Data Collection Components</a>. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b><span class="wintitle"> Servicio</span> </b>de ID: Una llamada <span class="wintitle"> DPM</span> desde el <span class="wintitle"> servicio de ID</span> es una solicitud de ID de visitante. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID Service</a> and <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="https" scope="external"> How the Experience Cloud ID Service Requests and Sets IDs</a>. </li> 
     </ul> </p> <p> <p>Note:  <span class="wintitle"> ID service</span> customers can change the <span class="wintitle"> DPM</span> prefix in the domain name. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-subdomain-config.html" format="https" scope="external"> audienceManager Server and audienceManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Servicio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/)
>* [Cookies de Audience Manager](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)

