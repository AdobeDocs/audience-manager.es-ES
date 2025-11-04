---
description: Es posible que su empresa desee complicar la dirección IP en muchos países debido a las normativas de privacidad globales. Audience Manager le permite complicar las direcciones IP de los visitantes en forma global o por país.
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: Ofuscación de direcciones IP
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 12%

---

# Ofuscación de direcciones IP {#ip-obfuscation}

Utilice esta función para ocultar las direcciones IP recopiladas en Audience Manager.

## Información general y metodología {#overview-and-methodology}

Es posible que su empresa desee complicar la dirección IP en muchos países debido a las normativas de privacidad globales. Audience Manager le permite complicar las direcciones IP de los visitantes en forma global o por país.

### Metodología de confusión de IP

Siguiendo los principios de &quot;Privacidad por diseño&quot;, Adobe Audience Manager permite a los clientes activar la ocultación de IP desde la interfaz de usuario, ya sea globalmente en todas las regiones geográficas o para países específicos. Al habilitar esta configuración, el último octeto (la última parte) de la dirección IP se descarta inmediatamente cuando la dirección IP se incorpora en Audience Manager. Audience Manager descarta esta parte de la dirección IP antes del procesamiento (incluso antes de cualquier búsqueda geográfica opcional o registro de la dirección IP). Por ejemplo:

* Antes de la ofuscación: `255.255.255.255`
* Después de la ofuscación: `255.255.255.0`

Consulte también Recopilación de direcciones IP y Ofuscación de direcciones IP en nuestra [sección Privacidad de datos](/help/using/overview/data-security-and-privacy/data-privacy.md).

### Prioridad de confusión de IP {#precedence}

[La confusión de IP en el nivel de secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#create) tiene prioridad sobre cualquier opción de confusión de IP establecida en Audience Manager y se aplica a todas las direcciones IP. Cualquier búsqueda de geolocalización realizada por Audience Manager se ve afectada por la opción [!UICONTROL IP obfuscation] del nivel de secuencia de datos. Una búsqueda de geolocalización en Audience Manager, basada en una IP totalmente ofuscada, dará como resultado una región desconocida y no se realizará ningún segmento basado en los datos de geolocalización resultantes.

## Requisitos de ofuscación de direcciones IP {#ip-obfuscation-requirements}

La ocultación de direcciones IP solo está disponible para cuentas de administrador de Audience Manager. Consulte [Crear usuarios](/help/using/features/administration/administration-overview.md#create-users) para saber cómo asignar privilegios de administrador a un usuario.

>[!NOTE]
>
> Debido al gran volumen de datos procesados por Audience Manager, los cambios de confusión de IP pueden tardar hasta 4 horas en entrar en vigor, desde el momento en que actualice la configuración.

## Configurar la confusión de direcciones IP {#configure-ip-obfuscation}

Siga los pasos a continuación para configurar la ofuscación de direcciones IP.

1. Inicie sesión en Audience Manager con una cuenta de administrador y vaya a **Administración > Privacidad**.
2. Elija el tipo de confusión de IP que desea utilizar.
   1. **Oscurecer todas las direcciones IP:** seleccione esta opción para que Audience Manager ofusque el último octeto de todas las direcciones IP de visitantes, independientemente de la región de la que procedan.
   2. **Oscurecer direcciones IP de países específicos:** seleccione esta opción para que Audience Manager ofusque el último octeto de direcciones IP de visitantes de países específicos. Use la **Lista de países** o el campo **Buscar** correspondiente para encontrar los países para habilitar la confusión de IP y haga clic en el icono + para agregarlos a la lista **Seleccionados para la confusión**. Una vez que hayas agregado todos los países requeridos a la lista **Seleccionado para ofuscación**, haz clic en **Guardar**.

![](assets/ip-obfuscation.png)

## Deshabilitar confusión de direcciones IP {#disable-ip-obfuscation}

Para deshabilitar la ofuscación de direcciones IP de forma global, ve a **Administración > Privacidad**, selecciona **No ofuscar direcciones IP** y haz clic en **Guardar**.

Para deshabilitar la ofuscación de direcciones IP en países específicos, busque los países en la lista **Seleccionado para ofuscación** y luego haga clic en el icono **X** correspondiente. Haz clic en **Guardar** cuando hayas terminado.

## Conceptos relacionados {#related-concepts}

* [Privacidad de datos](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Demostración en vídeo de ofuscación de direcciones IP

>[!VIDEO](https://video.tv.adobe.com/v/27218/)
