---
description: Describe la sintaxis y los parámetros utilizados en la llamada HTTP inicial para sincronizar los ID de usuario entre Audience Manager y un proveedor de datos de terceros. Póngase en contacto con el consultor de Adobe Audience Manager antes de intentar la primera sincronización de ID.
seo-description: Describe la sintaxis y los parámetros utilizados en la llamada HTTP inicial para sincronizar los ID de usuario entre Audience Manager y un proveedor de datos de terceros. Póngase en contacto con el consultor de Adobe Audience Manager antes de intentar la primera sincronización de ID.
seo-title: Sincronización de ID para transferencias de datos de salida
solution: Audience Manager
title: Sincronización de ID para transferencias de datos de salida
uuid: f3849be8-1094-47db-9296-7482f020af18
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Sincronización de ID para transferencias de datos de salida{#id-synchronization-for-outbound-data-transfers}

Describe la sintaxis y los parámetros utilizados en la llamada inicial `HTTP` para sincronizar los ID de usuario entre Audience Manager y un proveedor de datos de terceros. Póngase en contacto con el consultor de Adobe Audience Manager antes de intentar la primera sincronización de ID.

<!-- c_id_sync_out.xml -->

## Finalidad de la sincronización de ID

La sincronización de ID es el primer paso en el proceso de transferencia de datos asincrónica y saliente. En este paso, [!DNL Audience Manager] y el proveedor compara y hace coincidir las ID de sus respectivos visitantes del sitio. Por ejemplo, un [!DNL Audience Manager] cliente puede conocer a un usuario por ID 123. Sin embargo, su socio de datos podría identificar a este usuario con el ID 456. El proceso de sincronización permite [!DNL Audience Manager] y un proveedor de datos reconciliar estos distintos ID e identificar a los usuarios en sus respectivos sistemas. Una vez finalizado, [!DNL Audience Manager] y el proveedor de datos de terceros debe tener ID correspondientes para cada usuario único que se vea en nuestras redes.

## Sintaxis de URL

En un intercambio de ID, una [!DNL URL] cadena con el formato correcto debería tener este aspecto:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## Parámetros de URL

La [!DNL URL] llamada de sincronización de ID de entrada debe contener variables que se describen en la tabla siguiente.

>[!NOTE]
>
>Reemplazar contenido en cursiva con valores de parámetro reales.

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
   <td colname="col2">ID única para el proveedor de datos (asignado por <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> ID de usuario único. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">Redirección URL codificada con la macro <code> ${DD_UUID}</code> incrustada. <p><b></b> Nota: Se agrega solamente cuando el proveedor de datos inicia la llamada. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> puede ser 0 (no se aplica el RGPD) o 1 (se aplica el RGPD).</p><p><b>Nota:</b> <ul><li>Los parámetros <code>gdpr</code> y <code>gdpr_consent</code> se implementan gradualmente en direcciones URL de sincronización de ID con socios de activación. Consulte Socios de activación que admiten TCF de IAB en el complemento <a href="../../overview/aam-gdpr/aam-iab-plugin.md#aam-activation-partners">Audience Manager para TCF de IAB.</a></li><li>Este parámetro solo se puede usar junto con <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> es la cadena de consentimiento GDPR con codificación URL base64 (consulte la especificación <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"></a>IAB).</p><p><b></b> Nota: Este parámetro solo se puede usar junto con <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Métodos y código de la API del servidor de recopilación de datos (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Componentes de recopilación de datos](../../reference/system-components/components-data-collection.md)

