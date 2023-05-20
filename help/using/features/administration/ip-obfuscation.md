---
description: Es posible que su empresa desee complicar la dirección IP en muchos países debido a las normativas de privacidad globales. Audience Manager le permite complicar las direcciones IP de los visitantes en forma global o por país.
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: Complicación de la dirección IP
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 16%

---

# Complicación de la dirección IP {#ip-obfuscation}

Utilice esta función para ocultar las direcciones IP recopiladas en Audience Manager.

## Información general y metodología {#overview-and-methodology}

Es posible que su empresa desee complicar la dirección IP en muchos países debido a las normativas de privacidad globales. Audience Manager le permite complicar las direcciones IP de los visitantes en forma global o por país.

### Metodología de confusión de IP

Siguiendo los principios de &quot;Privacidad por diseño&quot;, Adobe Audience Manager permite a los clientes activar la ocultación de IP desde la interfaz de usuario, ya sea globalmente en todas las regiones geográficas o para países específicos. Al habilitar esta configuración, el último octeto (la última parte) de la dirección IP se descarta inmediatamente cuando la dirección IP se incorpora en Audience Manager. El Audience Manager descarta esta parte de la dirección IP antes del procesamiento (incluso antes de cualquier búsqueda geográfica opcional o registro de la dirección IP). Por ejemplo:

* Antes de la confusión: `255.255.255.255`
* Después de la ofuscación: `255.255.255.0`

Consulte también Recopilación de direcciones IP y Ofuscación de direcciones IP en nuestro [Sección Privacidad de datos](/help/using/overview/data-security-and-privacy/data-privacy.md).

## Requisitos de ofuscación de direcciones IP {#ip-obfuscation-requirements}

La ofuscación de direcciones IP solo está disponible para cuentas de administrador de Audience Manager. Consulte [Crear usuarios](/help/using/features/administration/administration-overview.md#create-users) para obtener información sobre cómo asignar privilegios de administrador a un usuario.

>[!NOTE]
>
> Debido al gran volumen de datos procesados por el Audience Manager, los cambios de confusión de IP pueden tardar hasta 4 horas en entrar en vigor, desde el momento en que actualice la configuración.

## Configurar la confusión de direcciones IP {#configure-ip-obfuscation}

Siga los pasos a continuación para configurar la ofuscación de direcciones IP.

1. Inicie sesión en Audience Manager con una cuenta de administrador de y vaya a **Administración > Privacidad**.
2. Elija el tipo de confusión de IP que desea utilizar.
   1. **Proteja todas las direcciones IP:** seleccione esta opción para que Audience Manager ofusque el último octeto de todas las direcciones IP de visitantes, independientemente de la región desde la que se originen.
   2. **Oscurezca las direcciones IP de países específicos:** seleccione esta opción para que el Audience Manager ofusque el último octeto de direcciones IP de visitantes para países específicos. Utilice el **Lista de países** o el correspondiente **Buscar** para buscar los países en los que se habilita la ocultación de la IP y haga clic en el icono + para agregarlos al **Seleccionado para confusión** lista. Una vez que haya agregado todos los países requeridos a **Seleccionado para confusión** , haga clic en **Guardar**.

![](assets/ip-obfuscation.png)

## Deshabilitar confusión de direcciones IP {#disable-ip-obfuscation}

Para deshabilitar la ofuscación de direcciones IP globalmente, vaya a **Administración > Privacidad**, seleccione **No proteger las direcciones IP** y haga clic en **Guardar**.

Para deshabilitar la ofuscación de direcciones IP para países específicos, busque los países en la **Seleccionado para confusión** y, a continuación, haga clic en su correspondiente **X** icono. Clic **Guardar** cuando hayas terminado.

## Conceptos relacionados {#related-concepts}

* [Privacidad de datos](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Demostración en vídeo de ofuscación de direcciones IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
