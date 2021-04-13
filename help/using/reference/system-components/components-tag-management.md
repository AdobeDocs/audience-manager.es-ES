---
description: Los componentes de administración de etiquetas de Audience Manager incluyen el portal del cliente, Adobe Tag Manager (obsoleto en favor de Adobe Dynamic Tag Manager y Adobe Experience Platform Launch), DIL, Akamai y la base de datos de control.
seo-description: Los componentes de administración de etiquetas de Audience Manager incluyen el portal del cliente, Adobe Tag Manager (obsoleto en favor de Adobe Dynamic Tag Manager y Adobe Experience Platform Launch), DIL, Akamai y la base de datos de control.
seo-title: Componentes de Tag Management
solution: Audience Manager
title: Componentes de Tag Management
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: 'Componentes del sistema '
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 6%

---

# Componentes de Tag Management{#tag-management-components}

Los componentes de administración de etiquetas de Audience Manager incluyen el portal del cliente, Adobe Tag Manager (obsoleto en favor de Adobe Dynamic Tag Manager y Adobe Experience Platform Launch), DIL, Akamai y la base de datos de control.

<!-- 

c_comptag.xml

 -->

El Audience Manager contiene los siguientes componentes:

* [Portal de cliente](../../reference/system-components/components-tag-management.md#client-portal)
* [Contenedor de DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Biblioteca de información de datos (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Base de datos de control](../../reference/system-components/components-tag-management.md#control-database)

## Portal de cliente {#client-portal}

El portal del cliente es la interfaz de usuario principal para la administración de etiquetas y datos. Los clientes utilizan el portal para trabajar con etiquetas, crear características y segmentos, configurar destinos y monitorizar el rendimiento de las campañas con informes.

## Contenedor de DIL/TIM {#dil-tim}

El contenedor [!UICONTROL DIL] ayuda a implementar el código de recopilación de datos [!DNL Audience Manager] en el sitio web. [!UICONTROL TIM] es el Administrador de inserción de etiquetas obsoleto. Ya no se utiliza en [!DNL Audience Manager]. En su lugar, se utiliza [Dynamic Tag Management](https://docs.adobe.com/content/help/es-ES/dtm/using/dtm-home.html) o la extensión [!DNL Audience Manager] en [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html) para configurar y generar el código de contenedor que se coloca en las páginas del inventario. El contenedor [!UICONTROL DTM] funciona con [!UICONTROL Data Information Library (DIL)] para recopilar datos del sitio y enviarlos a [!DNL Audience Manager].

## Biblioteca de integración de datos (DIL)  {#dil}

El [Data Information Library](../../dil/dil-overview.md) (DIL) es un módulo de API independiente que recopila datos de su sitio web. [!UICONTROL DIL] ayuda a eliminar la necesidad de escribir código especial para la recopilación de datos, la integración, la lectura de valores de cookies y la recuperación de datos de páginas. [!UICONTROL DIL] realiza estas acciones automáticamente. Además, [!UICONTROL DIL] es compacto. Es una biblioteca de código independiente que ayuda a reducir la cantidad de código necesario para recopilar información. Por último, [!UICONTROL DIL] le ayuda a integrar [!DNL Audience Manager] con otros productos en el Experience Cloud [!DNL Adobe].

## Akamai {#akamai}

[!DNL Audience Manager] utiliza el host de  [](https://www.akamai.com/us/en/about/) Akamaito y entrega el código de contenedor desde nuestra propia plataforma de administración de etiquetas conocida como  [!UICONTROL TIM (Tag Insertion Manager)]. Sin embargo, la implementación de código con [!UICONTROL TIM] se ha eliminado gradualmente en favor de [!DNL Adobe Dynamic Tag Management] y [!DNL Adobe Experience Platform Launch].

## Base de datos de control {#control-database}

La base de datos de control:

* Procesa la entrada del cliente desde el portal (por ejemplo, la creación de características y destinos).
* Transmite datos a Akamai, que incluye datos utilizados para crear la plantilla de contenedor y el iFrame de publicación de destino.
* Devuelve datos para sistemas de informes de interfaz de usuario.
