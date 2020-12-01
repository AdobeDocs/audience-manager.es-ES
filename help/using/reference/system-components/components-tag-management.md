---
description: Los componentes de administración de etiquetas de Audience Manager incluyen el portal de cliente, Adobe Tag Manager (obsoleto en favor de Adobe Dynamic Tag Manager y Adobe Experience Platform Launch), DIL, Akamai y la base de datos de control.
seo-description: Los componentes de administración de etiquetas de Audience Manager incluyen el portal de cliente, Adobe Tag Manager (obsoleto en favor de Adobe Dynamic Tag Manager y Adobe Experience Platform Launch), DIL, Akamai y la base de datos de control.
seo-title: Componentes de Tag Management
solution: Audience Manager
title: Componentes de Tag Management
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 5%

---


# Componentes de Tag Management{#tag-management-components}

Los componentes de administración de etiquetas de Audience Manager incluyen el portal de cliente, Adobe Tag Manager (obsoleto en favor de Adobe Dynamic Tag Manager y Adobe Experience Platform Launch), DIL, Akamai y la base de datos de control.

<!-- 

c_comptag.xml

 -->

Audience Manager contiene los siguientes componentes:

* [Portal del cliente](../../reference/system-components/components-tag-management.md#client-portal)
* [CONTENEDOR DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Biblioteca de información de datos (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Base de datos de control](../../reference/system-components/components-tag-management.md#control-database)

## Portal del cliente {#client-portal}

El portal del cliente es la interfaz de usuario principal para la gestión de datos y la etiqueta. Los clientes utilizan el portal para trabajar con etiquetas, generar características y segmentos, configurar destinos y monitorear el rendimiento de la campaña con los informes.

## CONTENEDOR DIL/TIM {#dil-tim}

El contenedor [!UICONTROL DIL] ayuda a implementar el código de recopilación de datos [!DNL Audience Manager] en el sitio Web. [!UICONTROL TIM] es el Administrador de inserción de etiquetas obsoleto. Ya no se usa en [!DNL Audience Manager]. En su lugar, utilice [Administración dinámica de etiquetas](https://docs.adobe.com/content/help/es-ES/dtm/using/dtm-home.html) o la extensión [!DNL Audience Manager] en [Adobe Experience Platform Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) para configurar y generar el código de contenedor que coloca en las páginas del inventario. El contenedor [!UICONTROL DTM] funciona con [!UICONTROL Data Information Library (DIL)] para recopilar datos de su sitio y enviarlos a [!DNL Audience Manager].

## Biblioteca de integración de datos (DIL)  {#dil}

La [Biblioteca de información de datos](../../dil/dil-overview.md) (DIL) es un módulo API independiente que recopila datos de su sitio Web. [!UICONTROL DIL] ayuda a eliminar la necesidad de escribir código especial para la recopilación de datos, la integración, la lectura de valores de cookies y la recuperación de datos de páginas. [!UICONTROL DIL] realiza estas acciones automáticamente. Además, [!UICONTROL DIL] es compacto. Es una biblioteca de código independiente que ayuda a reducir la cantidad de código necesario para recopilar información. Por último, [!UICONTROL DIL] le ayuda a integrar [!DNL Audience Manager] con otros productos en el Experience Cloud [!DNL Adobe].

## Akamai {#akamai}

[!DNL Audience Manager] utiliza el host de  [](https://www.akamai.com/html/about/index.html) Akamaito y proporciona código de contenedor desde nuestra propia plataforma de administración de etiquetas conocida como  [!UICONTROL TIM (Tag Insertion Manager)]. Sin embargo, la implementación de código con [!UICONTROL TIM] se ha eliminado en favor de [!DNL Adobe Dynamic Tag Management] y [!DNL Adobe Experience Platform Launch].

## Base de datos de control {#control-database}

Base de datos de control:

* Procesa los datos introducidos por el cliente desde el portal (por ejemplo, la creación de características y destinos).
* Transmite datos a Akamai, que incluye datos utilizados para crear la plantilla de contenedor y el iFrame de publicación de destino.
* Devuelve datos para sistemas de sistema de informes de interfaz de usuario.

