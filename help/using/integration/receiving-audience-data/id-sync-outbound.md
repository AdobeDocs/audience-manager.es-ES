---
description: Describe la sintaxis y los parámetros utilizados en la llamada HTTP inicial para sincronizar los ID de usuario entre el Audience Manager y un proveedor de datos de terceros. Póngase en contacto con su consultor de Adobe Audience Manager antes de intentar realizar la primera sincronización de ID.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.
seo-title: ID Synchronization for Outbound Data Transfers
solution: Audience Manager
title: Sincronización de ID para transferencias de datos salientes
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
exl-id: 02cca19a-eebf-43b2-b034-24f072fe2efb
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 2%

---

# Sincronización de ID para transferencias de datos salientes{#id-synchronization-for-outbound-data-transfers}

Describe la sintaxis y los parámetros utilizados en la llamada inicial `HTTP` para sincronizar los identificadores de usuario entre el Audience Manager y un proveedor de datos de terceros. Póngase en contacto con su consultor de Adobe Audience Manager antes de intentar realizar la primera sincronización de ID.

<!-- c_id_sync_out.xml -->

## Objetivo de la sincronización de ID

La sincronización de ID es el primer paso en el proceso de transferencia de datos saliente y asincrónico. En este paso, [!DNL Audience Manager] y el proveedor comparan y hacen coincidir los identificadores de sus respectivos visitantes del sitio. Por ejemplo, un cliente de [!DNL Audience Manager] puede conocer un usuario por el ID 123. Sin embargo, su socio de datos podría identificar a este usuario con el ID 456. El proceso de sincronización permite que [!DNL Audience Manager] y un proveedor de datos reconcilien estos identificadores diferentes e identifiquen a los usuarios en sus sistemas respectivos. Una vez finalizado, [!DNL Audience Manager] y el proveedor de datos de terceros deben tener los ID correspondientes para cada usuario único que se vea en nuestras redes.

## Sintaxis de URL

En un intercambio de ID, una cadena [!DNL URL] con el formato correcto debería tener este aspecto:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## Parámetros de URL

La [!DNL URL] de su llamada de sincronización de ID entrante debe contener variables que se describen en la tabla siguiente.

>[!NOTE]
>
>Reemplace el contenido en cursiva por los valores de parámetro reales.

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
   <td colname="col2">ID único del proveedor de datos (asignado por el Audience Manager <span class="keyword"> </span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> ID de usuario único. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">Redireccionamiento de URL codificado con la macro <code> ${DD_UUID}</code> incrustada en ella. <p><b>Nota:</b> Se agregó solamente cuando el proveedor de datos inicia la llamada. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> puede ser 0 (no se aplica el RGPD) o 1 (se aplica el RGPD).</p><p><b>Nota:</b> <ul><li>Los parámetros <code>gdpr</code> y <code>gdpr_consent</code> se están implementando gradualmente en las direcciones URL de sincronización de ID con los asociados de activación. Consulte los socios de activación que admiten el TCF de IAB en el complemento de Audience Manager <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">para el TCF de IAB.</a></li><li>Este parámetro solo se puede usar junto con <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> es la cadena de consentimiento RGPD con codificación URL base64 (consulte <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> especificación IAB</a>).</p><p><b>Nota:</b> Este parámetro solo se puede usar junto con <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Métodos y código de la API del servidor de recopilación de datos (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Componentes de recopilación de datos](../../reference/system-components/components-data-collection.md)
