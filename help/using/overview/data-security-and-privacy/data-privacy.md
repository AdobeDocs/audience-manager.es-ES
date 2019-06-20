---
description: Describe la integración de Audience Manager y la compatibilidad con las prácticas recomendadas aceptadas generalmente relacionadas con la privacidad del consumidor y los procedimientos de exclusión.
seo-description: Describe la integración de Audience Manager y la compatibilidad con las prácticas recomendadas aceptadas generalmente relacionadas con la privacidad del consumidor y los procedimientos de exclusión.
seo-title: Privacidad de datos
solution: Audience Manager
title: Privacidad de datos
uuid: 865 e 7 b 4 e-fee 1-4 fa 4-8035-1595 fc 77 cd 96
translation-type: tm+mt
source-git-commit: e6dcd0a33489ae388df25a95d3ad4841030afe31

---


# Privacidad de datos{#data-privacy}

Describe la integración de Audience Manager y la compatibilidad con las prácticas recomendadas aceptadas generalmente relacionadas con la privacidad del consumidor y los procedimientos de exclusión.

## Privacidad de datos {#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## Consumer Privacy Protection {#consumer-privacy-protection}

Audience Manager reconoce el pacto implícito entre los consumidores y las marcas en línea con las que interactúan. Ambas partes se benefician del intercambio transparente de elementos de datos anónimos:

* Los consumidores reciben contenido personalizado, ofrecen ofertas de productos y optimizan las experiencias de usuario.
* Las marcas reciben flujos de ingresos vitales que admiten múltiples modelos comerciales en línea.

Al continuar con la asistencia de este modelo, Audience Manager permanece comprometido con proporcionar transparencia y control a los consumidores y a superar o superar los principios de autorregulación de publicidad en línea (OBA).

## Opt-Out Management {#opt-out-management}

La documentación de exclusión se ha ampliado y trasladado a una parte independiente de nuestra documentación. See [Opt-out Management](../../overview/data-security-and-privacy/opt-out-management.md).

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

## Collecting IP Addresses and IP Address Obfuscation {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

La dirección IP de un visitante en el sitio web de un cliente se transmite a Adobe Data Processing Center (DPC) donde la dirección IP puede ser almacenada. Según la configuración de red del visitante, es posible que la dirección IP no represente necesariamente la dirección IP del equipo del visitante. Por ejemplo, la dirección IP puede ser una dirección IP externa de un cortafuegos de traducción de direcciones de red (NAT), un proxy HTTP o una puerta de enlace de Internet.

**Metodología de confusión de IP:** Siguiendo los principios de «Privacidad por diseño», Adobe Audience Manager permite a los clientes habilitar la confusión de IP desde la interfaz de usuario, ya sea globalmente entre todas las regiones geográficas o para países específicos. Cuando habilita esta configuración, el último octeto (la última parte) de la dirección IP se descarta inmediatamente cuando se ingesta la dirección IP en Audience Manager. Audience Manager descarta esta parte de la dirección IP antes de procesarla (incluso antes de cualquier registro geográfico opcional o registro de la dirección IP). Por ejemplo:

* Antes de registrar los valores de: `255.255.255.255`
* Después: `255.255.255.0`

>[!NOTE]
>
>See [IP Address Obfuscation](/help/using/features/administration/ip-obfuscation.md) to learn how to enable IP address obfuscation in the Audience Manager UI.

**Segmentación geográfica:** Si activa la confusión de direcciones IP, los bytes restantes de la dirección IP pueden seguir utilizándose para segmentación geográfica e informes en Audience Manager. Si no habilita la confusión de direcciones IP, Audience Manager utiliza la dirección IP completa. Puede utilizar la función Segmentación geográfica que permite identificar una ubicación IP por área geográfica en ambos casos, pero con ligeras pérdidas de precisión cuando se utiliza la confusión de IP. Es muy probable que la obtención de información por nivel de ciudad vea significativamente afectada por la confusión de la dirección IP. La obtención de información de región y país solamente debería verse ligeramente afectada. Los datos de segmentación geográfica solo son granulares a nivel de ciudad o código postal, y no al nivel individual. Read more about [geo-targeting](/help/using/features/traits/trait-geotarget-keys.md) and how to set up traits with geographic variables.

## Conceptos relacionados {#related-concepts}

* [Administración de exclusión](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [Preguntas frecuentes sobre retención de datos y privacidad](/help/using/faq/faq-privacy.md)