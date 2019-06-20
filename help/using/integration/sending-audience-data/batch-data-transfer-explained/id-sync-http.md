---
description: Describe la sintaxis y los parámetros utilizados en la llamada HTTP inicial para sincronizar ID de usuario entre un proveedor y Audience Manager. La sincronización de ID puede comenzar después de enviar la taxonomía de datos a Audience Manager.
seo-description: Describe la sintaxis y los parámetros utilizados en la llamada HTTP inicial para sincronizar ID de usuario entre un proveedor y Audience Manager. La sincronización de ID puede comenzar después de enviar la taxonomía de datos a Audience Manager.
seo-title: Sincronización de ID para transferencias de datos de entrada
solution: Audience Manager
title: Sincronización de ID para transferencias de datos de entrada
uuid: 037 e 74 a 6-acfd -4 cef-b 693-16 b 7 aaa 8 e 976
translation-type: tm+mt
source-git-commit: 0fac081c93be36d2aa40023c7323ef1886b3860a

---


# ID Synchronization for Inbound Data Transfers{#id-synchronization-for-inbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between a vendor and Audience Manager. La sincronización de ID puede comenzar después de enviar la taxonomía de datos a Audience Manager.

<!-- c_id_sync_in.xml -->

La sincronización de ID es el primer paso del proceso de transferencia de datos asíncrono y asíncrono. En este paso, Audience Manager y el proveedor comparan y coinciden con los ID para sus respectivos visitantes del sitio. For example, an [!DNL Audience Manager] customer may know a user by ID 123. Sin embargo, el socio de datos podría identificar a este usuario con el ID 456. The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and your third-party partner should have corresponding IDs for each unique user seen on our networks.

You can use the following methods to get your data into [!DNL Audience Manager]:

* [Solicitud HTTP de sincronización de ID](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Evento de ID declarado](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [Sincronización de ID desde una imagen incrustada en correo electrónico](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID Synchronization `HTTP` Request {#id-sync-http}

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

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
  <tr> 
   <td colname="col1"> <code><i>&lt; VENDOR_ ID &gt;</i></code> </td> 
   <td colname="col2"> <p>Unique ID for the content provider (assigned by <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; VENDOR_ UUID &gt;</i></code> </td> 
   <td colname="col2"> <p>Representación codificada de URL (porcentaje) de su ID de usuario único. Además de codificar caracteres ASCII reservados, cualquier carácter que no sea ASCII debe estar codificado en porcentaje en función de la tabla de codificación de caracteres UTF -8. </p> <p>For more information, see the <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online</a> website. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL &gt;</i></code> </td> 
   <td colname="col2"> <p>An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. </p> <p>Nota: Se añade únicamente cuando el proveedor de contenido inicia la llamada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr = &lt; 0|1 &gt;</i></code> </td> 
   <td colname="col2"> <p>Opcional. Add this parameter if you are using the <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code> rdpr</code> puede ser 0 (el RGPD no se aplica) o 1 (se aplica RGPD). </p> <p> <b>Nota:</b> Este parámetro solo se puede utilizar junto <code>con gdpr_ permission</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_ permission = &lt; ENCODED STRING &gt;</i></code> </td> 
   <td colname="col2"> <p>Opcional. Add this parameter if you are using the <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code>gdpr_ permission</code> es la cadena de consentimiento del RDPD con codificación de URL segura 64 codificada (consulte <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> especificación IAB</a>). </p> <p> <b>Nota:</b> Este parámetro solo se puede utilizar junto <code>con gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Declared ID Event {#declared-id-event}

For more information, see [Declared IDs](../../../features/declared-ids.md).

## ID Synchronization From an Email Embedded Image {#id-sync-email-image}

El formato de coincidencia de ID mediante una imagen de correo electrónico es el mismo que se muestra arriba. Tenga en cuenta, no obstante, que las imágenes de un correo electrónico deben estar habilitadas para que funcionen. Esto puede afectar la sincronización de ID por correo electrónico porque la mayoría de los sistemas de correo deshabilita las imágenes de forma predeterminada.

>[!MORE_ LIKE_ THIS]
>
>* [Componentes de recopilación de datos](../../../reference/system-components/components-data-collection.md)

