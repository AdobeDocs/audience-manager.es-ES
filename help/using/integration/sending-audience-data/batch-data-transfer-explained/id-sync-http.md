---
description: Describe la sintaxis y los parámetros utilizados en la llamada HTTP inicial para sincronizar los ID de usuario entre un proveedor y un Audience Manager. La sincronización de ID puede comenzar después de enviar la taxonomía de datos al Audience Manager.
seo-description: Describe la sintaxis y los parámetros utilizados en la llamada HTTP inicial para sincronizar los ID de usuario entre un proveedor y un Audience Manager. La sincronización de ID puede comenzar después de enviar la taxonomía de datos al Audience Manager.
seo-title: Sincronización de ID para transferencias de datos entrantes
solution: Audience Manager
title: Sincronización de ID para transferencias de datos entrantes
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: Inbound Data Transfers
exl-id: cd9be32f-f443-45bd-a906-ec4c8589f608
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 10%

---

# Sincronización de ID para transferencias de datos entrantes {#id-synchronization-for-inbound-data-transfers}

Describe la sintaxis y los parámetros utilizados en la llamada `HTTP` inicial para sincronizar los ID de usuario entre un proveedor y [!DNL Audience Manager]. La sincronización de ID puede comenzar después de enviar la taxonomía de datos a [!DNL Audience Manager].

La sincronización de ID es el primer paso en el proceso de transferencia de datos entrante y asincrónico. En este paso, [!DNL Audience Manager] y el proveedor comparan y hacen coincidir los ID de sus respectivos visitantes del sitio. Por ejemplo, un cliente [!DNL Audience Manager] puede conocer a un usuario mediante el ID 123. Sin embargo, su socio de datos podría identificar a este usuario con el ID 456. El proceso de sincronización permite a [!DNL Audience Manager] y a un proveedor de datos reconciliar estos distintos ID e identificar a los usuarios en sus respectivos sistemas. Una vez finalizado, [!DNL Audience Manager] y su socio de terceros deben tener los ID correspondientes para cada usuario único que se vea en nuestras redes.

Puede utilizar los siguientes métodos para introducir sus datos en [!DNL Audience Manager]:

* [Solicitud HTTP de sincronización de ID](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Evento de ID declarado](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [Sincronización de ID a partir de una imagen integrada de correo electrónico](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## Solicitud `HTTP` de sincronización de ID {#id-sync-http}

En un intercambio de ID, una cadena [!DNL URL] con formato correcto debería tener este aspecto:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

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
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>ID único para el proveedor de contenido (asignado por el Audience Manager <span class="keyword"></span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>Representación codificada de la URL (porcentaje) de su ID de usuario único. Además de codificar caracteres ASCII reservados, cualquier carácter que no sea ASCII debe estar codificado por porcentajes según la tabla de codificación de caracteres UTF-8. </p> <p>Para obtener más información, consulte el sitio web <a href="https://www.url-encode-decode.com" format="http" scope="external"> Codificar/descodificar en línea</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>Un redireccionamiento de URL codificado con la macro <code> ${DD_UUID}</code> incrustada dentro de ella. </p> <p>Nota:  Se agrega solamente cuando el proveedor de contenido inicia la llamada . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>Opcional. Añada este parámetro si está utilizando el complemento <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager para IAB TCF.</a></p> <p><code> gdpr</code> puede ser 0 (no se aplica el RGPD) o 1 (se aplica el RGPD). </p> <p> <b>Nota:</b> Este parámetro solo se puede usar junto con  <code>gdpr_consent</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>Opcional. Añada este parámetro si está utilizando el complemento <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager para IAB TCF.</a></p> <p><code>gdpr_consent</code> es la cadena de consentimiento RGPD con codificación URL base64 (consulte la <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> especificación IAB</a>). </p> <p> <b>Nota:</b> Este parámetro solo se puede usar junto con  <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Evento {#declared-id-event}

Para obtener más información, consulte [ID declarados](../../../features/declared-ids.md).

## Sincronización de ID a partir de una imagen integrada por correo electrónico {#id-sync-email-image}

El formato para los ID coincidentes a través de una imagen de correo electrónico es el mismo que se muestra arriba. Sin embargo, tenga en cuenta que las imágenes de un correo electrónico deben estar habilitadas para que esto funcione. Esto puede afectar a la sincronización de ID por correo electrónico, ya que la mayoría de los sistemas de correo desactivan las imágenes de forma predeterminada.

>[!MORELIKETHIS]
>
>* [Componentes de recopilación de datos](../../../reference/system-components/components-data-collection.md)

