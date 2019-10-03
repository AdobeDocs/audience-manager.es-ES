---
description: Describe la integración de Audience Manager y el cumplimiento de las optimizaciones generalmente aceptadas relacionadas con los procedimientos de privacidad del consumidor y exclusión.
seo-description: Describe la integración de Audience Manager y el cumplimiento de las optimizaciones generalmente aceptadas relacionadas con los procedimientos de privacidad del consumidor y exclusión.
seo-title: Privacidad de datos
solution: Audience Manager
title: Privacidad de datos
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# Privacidad de datos{#data-privacy}

Describe la integración de Audience Manager y el cumplimiento de las optimizaciones generalmente aceptadas relacionadas con los procedimientos de privacidad del consumidor y exclusión.

## Privacidad de datos {#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## Protección de la privacidad del consumidor {#consumer-privacy-protection}

Audience Manager reconoce el pacto implícito entre los consumidores y las marcas en línea con las que interactúan. Ambas partes se benefician del intercambio transparente de elementos de datos anónimos:

* Los consumidores reciben contenido personalizado, ofertas de productos con descuento y experiencias de usuario optimizadas.
* Las marcas reciben flujos de ingresos vitales que admiten varios modelos comerciales en línea.

En nuestro continuo apoyo a este modelo, Audience Manager sigue comprometido a proporcionar transparencia y control a los consumidores, y a cumplir o superar los Principios de autorregulación de la publicidad de comportamiento en línea (OBA).

## Administración de exclusión {#opt-out-management}

La documentación de exclusión se ha ampliado y se ha trasladado a una parte separada de nuestra documentación. Consulte Administración [de exclusión](../../overview/data-security-and-privacy/opt-out-management.md).

<!-- 

<p>  </p>
<table id="table_A1FF33B328BD451FAFF6C6B8422F928B"> 
 <tgroup cols="2">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="2.74*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Opt-Out For </th> 
    <th colname="col2" class="entry"> Description </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
    <td colname="col2"> <p>The <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices page</a> provides 1-click features that let you control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section</a> of the Privacy Choices page. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Browsers that do not support third-party cookies </p> </td> 
    <td colname="col2"> <p>See <a href="../../features/declared-ids.md#declared-id-targeting"> Declared ID Targeting</a>. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Mobile devices </p> </td> 
    <td colname="col2"> <p>See the opt-out and privacy settings for: </p> <p> 
      <ul id="ul_86EFAB879215403D937B5148C26A41D9"> 
       <li id="li_C0B544E8F4FE473B94A5436D3A60BDB1"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android devices</a> </li> 
       <li id="li_26C787BAB729499A9FEDF055E9AB0637"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS devices</a> </li> 
      </ul> </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

## Recopilación de direcciones IP y confusión de direcciones IP {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**** IP Obfuscation Methodology: Following the principles of "Privacy By Design", Adobe Audience Manager allows customers to enable  obfuscation from the UI, either globally across all geographic regions or for specific countries. [!DNL IP] When you enable this setting, the last octet (the last portion) of the  address is immediately discarded when the  address is ingested into Audience Manager. [!DNL IP][!DNL IP] Audience Manager discards this part of the  address prior to processing (including before any optional geographic lookup or logging of the  address). [!DNL IP][!DNL IP] Por ejemplo:

* Antes de registrar los valores de: `255.255.255.255`
* Después: `255.255.255.0`

>[!NOTE]
>
>See IP Address Obfuscation to learn how to enable  address obfuscation in the Audience Manager UI.[](/help/using/features/administration/ip-obfuscation.md)[!DNL IP]

Watch the video below to understand how  address obfuscation works in Audience Manager.[!DNL IP]

>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=spa)

**** Geographic Segmentation: If you enable  address obfuscation, the remaining octets of the  address can still be used for geo-segmentation and reporting in Audience Manager. [!DNL IP][!DNL IP] Si no habilita [!DNL IP] la confusión de direcciones, Audience Manager utiliza la [!DNL IP] dirección completa. Puede utilizar la función Segmentación geográfica que le permite identificar una [!DNL IP] ubicación por área geográfica en cualquier caso, pero con una ligera pérdida de precisión cuando se utiliza [!DNL IP] confusión. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. La obtención de información a nivel regional y nacional sólo debería verse ligeramente afectada. Los datos de segmentación geográfica solo son granulares a nivel de ciudad o de código postal y no a nivel individual. Obtenga más información sobre [targeting](/help/using/features/traits/trait-geotarget-keys.md) geográfico y cómo configurar características con variables geográficas.

## Conceptos relacionados {#related-concepts}

* [Administración de exclusión](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [Preguntas más frecuentes sobre privacidad y retención de datos](/help/using/faq/faq-privacy.md)