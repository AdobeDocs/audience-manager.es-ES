---
description: Audiencia Manager y Adobe Experience Platform Identity Service realizan llamadas y reciben datos del dominio demdex.net. Esto puede parecer que Adobe está trabajando con un dominio de terceros inusual, pero no es el caso. Esta sección describe los elementos de una llamada demdex.net.
seo-description: Audiencia Manager y Adobe Experience Platform Identity Service realizan llamadas y reciben datos del dominio demdex.net. Esto puede parecer que Adobe está trabajando con un dominio de terceros inusual, pero no es el caso. Esta sección describe los elementos de una llamada demdex.net.
seo-title: Explicación de las llamadas al dominio Demdex
solution: Audience Manager
title: Explicación de las llamadas al dominio Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Explicación de las llamadas al dominio Demdex{#understanding-calls-to-the-demdex-domain}

Audiencia Manager y Adobe Experience Platform Identity Service realizan llamadas y reciben datos del dominio demdex.net. Esto puede parecer que Adobe está trabajando con un dominio de terceros inusual, pero no es el caso. Esta sección describe los elementos de una llamada demdex.net.

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
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. Refleja <span class="keyword"> el nombre original del administrador</span>de Audiencias previo a la adquisición (<span class="keyword"> Demdex</span>). <span class="keyword"> Adobe</span> adquirió <span class="keyword"> Demdex</span> en 2011 y cambió la marca de la compañía como Administrador <span class="keyword"> de</span>Audiencias. Es difícil cambiar este dominio porque está estrechamente vinculado con el Administrador <span class="keyword"> de</span>Audiencias, el servicio <span class="wintitle"> de</span>ID y nuestra base de usuarios instalada. Consulte <a href="../overview/aam-overview.md#history-and-background"> Historial y fondo</a>. </p> <p>Puede ver otros prefijos adjuntos a <code> demdex.net</code> llamadas preexistentes (por ejemplo, <code> dcs.demdex.net</code>, <code> fast.demdex.net</code>, etc.). Independientemente del prefijo, una llamada a <code><i>something</i>.demdex.net</code> es siempre una llamada a <span class="keyword"> Adobe</span> y no a un dominio de terceros desconocido o sospechoso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> es una abreviatura de Coincidencia <span class="wintitle"> del proveedor</span>de datos. Indica a los sistemas internos de Adobe <span class="keyword"></span> que una llamada desde el Administrador <span class="keyword"> de</span> Audiencias o el servicio <span class="wintitle"> de</span> ID está pasando los datos del cliente para la sincronización o para solicitar un ID. Esta es la llamada más común <code> demdex.net</code> que verá desde el Administrador <span class="keyword"> de</span> Audiencias o desde el servicio <span class="wintitle"> de</span>ID. </p> <p><span class="wintitle"> Conceptos básicos de llamadas de DPM</span> : </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> <span class="keyword"> Administrador</span> de Audiencias </b>: Una llamada de <span class="wintitle"> DPM</span> desde el Administrador <span class="keyword"> de</span> Audiencias envía datos a los servidores <span class="wintitle"> de recopilación de datos y a los servidores</span> de caché de <span class="wintitle"></span>Perfil. Consulte <a href="../reference/system-components/components-data-collection.md"> Componentes</a>de recopilación de datos. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> <span class="wintitle"> Servicio</span> de ID </b>: Una llamada de <span class="wintitle"> DPM</span> desde el servicio <span class="wintitle"> de</span> ID es una solicitud de ID de visitante. Consulte <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies y el servicio</a> de identidad de Adobe Experience Platform y <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html" format="https" scope="external"> Cómo solicita y establece los ID</a>el servicio de identidad de Adobe Experience Platform. </li> 
     </ul> </p> <p> <p>Nota:  <span class="wintitle"> Los clientes del servicio</span> de ID pueden cambiar el prefijo <span class="wintitle"> DPM</span> en el nombre de dominio. Consulte <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html" format="https" scope="external"> audienceManager Server y audienceManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Cookies de Audience Manager](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html)

