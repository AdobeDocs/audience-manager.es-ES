---
description: Es posible que su empresa desee complicar la dirección IP en muchos países debido a las normativas de privacidad globales. Audience Manager le permite complicar las direcciones IP de los visitantes en forma global o por país.
seo-description: Es posible que su empresa desee complicar la dirección IP en muchos países debido a las normativas de privacidad globales. Audience Manager le permite complicar las direcciones IP de los visitantes en forma global o por país.
solution: Audience Manager
title: Complicación de la dirección IP
translation-type: tm+mt
source-git-commit: f7206fda4b16a22c8a8bfcf97529cdaea24b0898

---


# Complicación de la dirección IP {#ip-obfuscation}

Utilice esta función para proteger las direcciones IP recopiladas en Audience Manager.

## Overview and Methodology {#overview-and-methodology}

Es posible que su empresa desee complicar la dirección IP en muchos países debido a las normativas de privacidad globales. Audience Manager le permite complicar las direcciones IP de los visitantes en forma global o por país.

### Metodología de confusión de IP

Siguiendo los principios de «Privacidad por diseño», Adobe Audience Manager permite a los clientes habilitar la confusión de IP desde la interfaz de usuario, ya sea globalmente entre todas las regiones geográficas o para países específicos. Cuando habilita esta configuración, el último octeto (la última parte) de la dirección IP se descarta inmediatamente cuando se ingesta la dirección IP en Audience Manager. Audience Manager descarta esta parte de la dirección IP antes de procesarla (incluso antes de cualquier registro geográfico opcional o registro de la dirección IP). Por ejemplo:

* Before obfuscation: `255.255.255.255`
* After obfuscation: `255.255.255.0`

See also, Collecting IP addresses and IP Address Obfuscation in our [Data Privacy section](/help/using/overview/data-security-and-privacy/data-privacy.md).

## IP Address Obfuscation Requirements {#ip-obfuscation-requirements}

La confusión de direcciones IP solo está disponible para las cuentas de administrador de Audience Manager. See [Create Users](/help/using/features/administration/administration-overview.md#create-users) to understand how to assign administrator privileges for a user.

>[!NOTE]
>
> Debido al gran volumen de datos procesados por Audience Manager, los cambios de confusión de IP pueden tardar hasta 4 horas en implementarse, desde el momento en que se actualiza la configuración.

## Configure IP Address Obfuscation {#configure-ip-obfuscation}

Siga los pasos a continuación para configurar la confusión de direcciones IP.

1. Log in to Audience Manager with an administrator account and go to **Administration &gt; Privacy**.
2. Elija el tipo de confusión de IP que desee utilizar.
   1. **Proteger todas las direcciones IP:** seleccione esta opción para que Audience Manager confunda el último octeto de todas las direcciones IP del visitante, independientemente de la región donde se originan.
   2. **Proteger direcciones IP para países específicos:** seleccione esta opción para que Audience Manager obtenga el último octeto de direcciones IP de visitantes para países específicos. Use the **List of Countries** or the corresponding **Search** field to find the countries to enable IP obfuscation for, and click the + icon to add them to the **Selected for Obfuscation** list. Once you've added all the required countries to the **Selected for Obfuscation** list, click **Save**.

![](assets/ip-obfuscation.png)

## Disable IP Address Obfuscation {#disable-ip-obfuscation}

To disable IP address obfuscation globally, go to **Administration &gt; Privacy**, select **Do not obfuscate IP addresses**, and click **Save**.

To disable IP address obfuscation for specific countries, find the countries in the **Selected for Obfuscation** list, then click their corresponding **X** icon. Click **Save** when you're done.

## Conceptos relacionados {#related-concepts}

* [Privacidad de datos](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Demostración de vídeo de confusión de direcciones IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=spa)

