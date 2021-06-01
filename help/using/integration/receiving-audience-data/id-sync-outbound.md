---
description: Describe la sintaxis y los parámetros utilizados en la llamada HTTP inicial para sincronizar los ID de usuario entre un Audience Manager y un proveedor de datos de terceros. Póngase en contacto con su consultor de Adobe Audience Manager antes de intentar la primera sincronización de ID.
seo-description: Describe la sintaxis y los parámetros utilizados en la llamada HTTP inicial para sincronizar los ID de usuario entre un Audience Manager y un proveedor de datos de terceros. Póngase en contacto con su consultor de Adobe Audience Manager antes de intentar la primera sincronización de ID.
seo-title: Sincronización de ID para transferencias de datos de salida
solution: Audience Manager
title: Sincronización de ID para transferencias de datos de salida
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Transferencias de datos de salida
exl-id: 02cca19a-eebf-43b2-b034-24f072fe2efb
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 14%

---

# Sincronización de ID para transferencias de datos de salida{#id-synchronization-for-outbound-data-transfers}

Describe la sintaxis y los parámetros utilizados en la llamada `HTTP` inicial para sincronizar los ID de usuario entre un Audience Manager y un proveedor de datos de terceros. Póngase en contacto con su consultor de Adobe Audience Manager antes de intentar la primera sincronización de ID.

<!-- c_id_sync_out.xml -->

## Objetivo de la sincronización de ID

La sincronización de ID es el primer paso en el proceso de transferencia de datos asincrónico y saliente. En este paso, [!DNL Audience Manager] y el proveedor comparan y hacen coincidir los ID de sus respectivos visitantes del sitio. Por ejemplo, un cliente [!DNL Audience Manager] puede conocer a un usuario mediante el ID 123. Sin embargo, su socio de datos podría identificar a este usuario con el ID 456. El proceso de sincronización permite a [!DNL Audience Manager] y a un proveedor de datos reconciliar estos distintos ID e identificar a los usuarios en sus respectivos sistemas. Una vez finalizado, [!DNL Audience Manager] y el proveedor de datos de terceros deben tener los ID correspondientes para cada usuario único que se vea en nuestras redes.

## Sintaxis de URL

En un intercambio de ID, una cadena [!DNL URL] con formato correcto debería tener este aspecto:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## Parámetros de URL

El [!DNL URL] para la llamada de sincronización de ID de entrada debe contener variables que se describen en la tabla siguiente.

>[!NOTE]
>
>Reemplace el contenido en cursiva con valores de parámetro reales.

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">ID único para el proveedor de datos (asignado por el Audience Manager <span class="keyword"></span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> ID de usuario único. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">Un redireccionamiento de URL codificado con la macro <code> ${DD_UUID}</code> incrustada dentro de ella. <p><b>Nota:</b> Se agrega solamente cuando el proveedor de datos inicia la llamada. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> puede ser 0 (no se aplica el RGPD) o 1 (se aplica el RGPD).</p><p><b>Nota:</b> <ul><li>Los parámetros <code>gdpr</code> y <code>gdpr_consent</code> se implementan gradualmente en las direcciones URL de sincronización de ID con socios de activación. Consulte Socios de activación compatibles con TCF de IAB en <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">complemento Audience Manager para TCF de IAB.</a></li><li>Este parámetro solo puede usarse junto con <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> es la cadena de consentimiento RGPD con codificación URL base64 (consulte la <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> especificación IAB</a>).</p><p><b>Nota:</b> Este parámetro solo se puede usar junto con  <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Métodos y código de la API del servidor de recopilación de datos (DCS) ](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
* [Componentes de recopilación de datos](../../reference/system-components/components-data-collection.md)

