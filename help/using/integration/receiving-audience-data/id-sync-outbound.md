---
description: Describe la sintaxis y los parámetros utilizados en la llamada HTTP inicial para sincronizar ID de usuario entre Audience Manager y un proveedor de datos de terceros. Póngase en contacto con su asesor de Adobe Audience Manager antes de intentar la primera sincronización de ID.
seo-description: Describe la sintaxis y los parámetros utilizados en la llamada HTTP inicial para sincronizar ID de usuario entre Audience Manager y un proveedor de datos de terceros. Póngase en contacto con su asesor de Adobe Audience Manager antes de intentar la primera sincronización de ID.
seo-title: Sincronización de ID para transferencias de datos salientes
solution: Audience Manager
title: Sincronización de ID para transferencias de datos salientes
uuid: f 3849 be 8-1094-47 db -9296-7482 f 020 af 18
translation-type: tm+mt
source-git-commit: e206d3a3cba259dc215f2f4190c9b4e03264f080

---


# ID Synchronization for Outbound Data Transfers{#id-synchronization-for-outbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between Audience Manager and a third-party data provider. Póngase en contacto con su asesor de Adobe Audience Manager antes de intentar la primera sincronización de ID.

<!-- c_id_sync_out.xml -->

## Objetivo de sincronización de ID

La sincronización de ID es el primer paso del proceso de transferencia de datos asíncrono y saliente. In this step, [!DNL Audience Manager] and the vendor compare and match IDs for their respective site visitors. For example, an [!DNL Audience Manager] customer may know a user by ID 123. Sin embargo, el socio de datos podría identificar a este usuario con el ID 456. The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and the third-party data provider should have corresponding IDs for each unique user seen on our networks.

## Sintaxis URL

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## Parámetros de URL

The [!DNL URL] for your inbound ID synchronization call should contain variables described in the table below.

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
   <td colname="col1"> <code><i>&lt; VENDOR_ ID &gt;</i></code> </td> 
   <td colname="col2">Unique ID for the data provider (assigned by <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; VENDOR_ UUID &gt;</i></code> </td> 
   <td colname="col2"> ID de usuario único. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL &gt;</i></code> </td> 
   <td colname="col2">An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. <p><b>Nota:</b> Se añade únicamente cuando el proveedor de datos inicia la llamada. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr = &lt; 0|1 &gt;</i></code> </td> 
   <td colname="col2"> <p><code>rdpr</code> puede ser 0 (el RGPD no se aplica) o 1 (se aplica RGPD).</p><p><b>Nota:</b> <ul><li>The <code>gdpr</code> and <code>gdpr_consent</code> parameters are being gradually rolled out in ID sync URLs with activation partners. See Activation partners that support IAB TCF in <a href="../../overview/aam-gdpr/aam-iab-plugin.md#aam-activation-partners">Audience Manager Plug-in for IAB TCF.</a></li><li>This parameter can only be used together with <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_ permission = &lt; ENCODED STRING &gt;</i></code> </td> 
   <td colname="col2"><p><code>gdpr_ permission</code> es la cadena de consentimiento del RDPD con codificación de URL segura 64 codificada (consulte <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> especificación IAB</a>).</p><p><b>Nota:</b> Este parámetro solo se puede utilizar junto <code>con gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Métodos y código de API de Data Collection Server (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Componentes de recopilación de datos](../../reference/system-components/components-data-collection.md)

