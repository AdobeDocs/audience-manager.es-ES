---
description: Los componentes de administración de etiquetas de Audience Manager incluyen el portal del cliente, Adobe Tag Manager (obsoleto en favor de Adobe Experience Platform Launch), el DIL, Akamai y la base de datos de control.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Componentes de Tag Management
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 3%

---

# Componentes de Tag Management{#tag-management-components}

Los componentes de administración de etiquetas de Audience Manager incluyen el portal del cliente, Adobe Tag Manager (obsoleto en favor de Adobe Experience Platform Tags), el DIL, Akamai y la base de datos de control.

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

La variable [!UICONTROL DIL] container ayuda a implementar [!DNL Audience Manager] código de recopilación de datos en el sitio web. [!UICONTROL TIM] es el Administrador de inserción de etiquetas obsoleto. Ya no se utiliza en [!DNL Audience Manager]. En su lugar, utilice el [!DNL Audience Manager] extensión en [Etiquetas de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) para configurar y generar el código de contenedor que coloca en las páginas del inventario.

## Biblioteca de integración de datos (DIL) {#dil}

La variable [Biblioteca de información de datos](../../dil/dil-overview.md) (DIL) es un módulo de API independiente que recopila datos de su sitio web. [!UICONTROL DIL] ayuda a eliminar la necesidad de escribir código especial para la recopilación de datos, la integración, la lectura de valores de cookies y la recuperación de datos de páginas. [!UICONTROL DIL] realiza estas acciones automáticamente. Además, [!UICONTROL DIL] es compacta. Es una biblioteca de código independiente que ayuda a reducir la cantidad de código necesario para recopilar información. Finalmente, [!UICONTROL DIL] ayuda a integrar [!DNL Audience Manager] con otros productos de [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] uses [Akamai](https://www.akamai.com/us/en/about/) para alojar y entregar código de contenedor desde nuestra propia plataforma de administración de etiquetas conocida como [!UICONTROL TIM (Tag Insertion Manager)]. Sin embargo, la implementación de código con [!UICONTROL TIM] se ha eliminado gradualmente en favor de [!DNL Adobe Experience Platform Tags].

## Base de datos de control {#control-database}

La base de datos de control:

* Procesa la entrada del cliente desde el portal (por ejemplo, la creación de características y destinos).
* Transmite datos a Akamai, que incluye datos utilizados para crear la plantilla de contenedor y el iFrame de publicación de destino.
* Devuelve datos para sistemas de informes de interfaz de usuario.
