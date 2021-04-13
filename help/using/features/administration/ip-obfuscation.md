---
description: Es posible que su empresa desee complicar la dirección IP en muchos países debido a las normativas de privacidad globales. Audience Manager le permite complicar las direcciones IP de los visitantes en forma global o por país.
seo-description: Es posible que su empresa desee complicar la dirección IP en muchos países debido a las normativas de privacidad globales. Audience Manager le permite complicar las direcciones IP de los visitantes en forma global o por país.
solution: Audience Manager
title: Complicación de la dirección IP
feature: Administración de datos y privacidad
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 22%

---

# Complicación de la dirección IP {#ip-obfuscation}

Utilice esta función para proteger las direcciones IP recopiladas en el Audience Manager.

## Información general y metodología {#overview-and-methodology}

Es posible que su empresa desee complicar la dirección IP en muchos países debido a las normativas de privacidad globales. Audience Manager le permite complicar las direcciones IP de los visitantes en forma global o por país.

### Metodología de confusión de IP

Siguiendo los principios de &quot;Privacidad por diseño&quot;, Adobe Audience Manager permite a los clientes activar la confusión de IP desde la interfaz de usuario, ya sea globalmente en todas las regiones geográficas o para países específicos. Al habilitar esta configuración, el último octeto (la última parte) de la dirección IP se descarta inmediatamente cuando la dirección IP se incorpora en el Audience Manager. El Audience Manager descarta esta parte de la dirección IP antes del procesamiento (incluso antes de cualquier búsqueda geográfica opcional o registro de la dirección IP). Por ejemplo:

* Antes de la confusión: `255.255.255.255`
* Después de la confusión: `255.255.255.0`

Consulte también Recopilación de direcciones IP y ofuscación de direcciones IP en nuestra [sección Privacidad de datos](/help/using/overview/data-security-and-privacy/data-privacy.md).

## Requisitos de confusión de direcciones IP {#ip-obfuscation-requirements}

La confusión de direcciones IP solo está disponible para cuentas de administrador del Audience Manager. Consulte [Crear usuarios](/help/using/features/administration/administration-overview.md#create-users) para comprender cómo asignar privilegios de administrador a un usuario.

>[!NOTE]
>
> Debido al gran volumen de datos procesados por el Audience Manager, los cambios de confusión de IP pueden tardar hasta 4 horas en entrar en vigor, desde el momento en que actualiza la configuración.

## Configurar la confusión de direcciones IP {#configure-ip-obfuscation}

Siga los pasos a continuación para configurar la confusión de direcciones IP.

1. Inicie sesión en el Audience Manager con una cuenta de administrador y vaya a **Administration > Privacy**.
2. Elija el tipo de confusión de IP que desea utilizar.
   1. **Proteger todas las direcciones IP:** seleccione esta opción para que el Audience Manager confunda el último octeto de todas las direcciones IP del visitante, independientemente de la región desde la que se originan.
   2. **Proteger direcciones IP para países específicos:** seleccione esta opción para que el Audience Manager confunda el último octeto de direcciones IP de visitantes para países específicos. Utilice la **Lista de países** o el campo correspondiente **Buscar** para encontrar los países para habilitar la confusión de IP y haga clic en el icono + para agregarlos a la lista **Seleccionados para la confusión**. Una vez que haya agregado todos los países requeridos a la lista **Seleccionado para ofuscación**, haga clic en **Guardar**.

![](assets/ip-obfuscation.png)

## Desactivar confusión de direcciones IP {#disable-ip-obfuscation}

Para desactivar la ofuscación global de direcciones IP, vaya a **Administration > Privacy**, seleccione **Do not obfuscate IP addresses** y haga clic en **Save**.

Para desactivar la ofuscación de direcciones IP para países específicos, busque los países en la lista **Seleccionado para ofuscación** y, a continuación, haga clic en su icono **X** correspondiente. Haga clic en **Guardar** cuando haya terminado.

## Conceptos relacionados {#related-concepts}

* [Privacidad de datos](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Demostración de vídeo de confusión de direcciones IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
