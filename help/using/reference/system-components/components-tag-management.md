---
description: Los componentes de administración de etiquetas de Audience Manager incluyen el portal del cliente, Adobe Tag Manager (obsoleto en favor de Adobe Experience Platform Launch), DIL, Akamai y la base de datos de control.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Componentes de Tag Management
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 1%

---

# Componentes de Tag Management{#tag-management-components}

Los componentes de administración de etiquetas de Audience Manager incluyen el portal del cliente, Adobe Tag Manager (obsoleto en favor de las etiquetas de Adobe Experience Platform), DIL, Akamai y la base de datos de control.

<!-- 

c_comptag.xml

 -->

Audience Manager contiene los siguientes componentes:

* [Portal de cliente](../../reference/system-components/components-tag-management.md#client-portal)
* [Contenedor de DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Biblioteca de información de datos (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Base de datos de control](../../reference/system-components/components-tag-management.md#control-database)

## Portal de clientes {#client-portal}

El portal del cliente es la interfaz de usuario (IU) principal para la administración de etiquetas y datos. Los clientes utilizan el portal para trabajar con etiquetas, crear características y segmentos, configurar destinos y supervisar el rendimiento de las campañas con informes.

## Contenedor de DIL/TIM {#dil-tim}

El contenedor [!UICONTROL DIL] ayuda a implementar el código de recopilación de datos [!DNL Audience Manager] en el sitio web. [!UICONTROL TIM] es el Administrador de inserción de etiquetas obsoleto. [!DNL Audience Manager] ya no la usa. En su lugar, utilice la extensión [!DNL Audience Manager] en [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=es) para configurar y generar el código de contenedor que coloque en las páginas de su inventario.

## Biblioteca de integración de datos (DIL) {#dil}

La [Biblioteca de información de datos](../../dil/dil-overview.md) (DIL) es un módulo de API independiente que recopila datos de su sitio web. [!UICONTROL DIL] ayuda a eliminar la necesidad de escribir código especial para la recopilación, integración, lectura de valores de cookies y recuperación de datos de páginas. [!UICONTROL DIL] realiza estas acciones automáticamente. Además, [!UICONTROL DIL] es compacto. Es una biblioteca de códigos independiente que ayuda a reducir la cantidad de código necesario para recopilar información. Por último, [!UICONTROL DIL] le ayuda a integrar [!DNL Audience Manager] con otros productos en el Experience Cloud [!DNL Adobe].

## Akamai {#akamai}

[!DNL Audience Manager] usa [Akamai](https://www.akamai.com/us/en/about/) para hospedar y entregar código de contenedor desde nuestra propia plataforma de administración de etiquetas conocida como [!UICONTROL TIM (Tag Insertion Manager)]. Sin embargo, la implementación de código con [!UICONTROL TIM] se ha eliminado gradualmente a favor de [!DNL Adobe Experience Platform Tags].

## Base de datos de control {#control-database}

La base de datos de control:

* Procesa los datos introducidos por el cliente desde el portal (por ejemplo, la creación de características y destinos).
* Transmite datos a Akamai, que incluye los datos utilizados para crear la plantilla contenedora y el iFrame de publicación de destino.
* Devuelve datos de los sistemas de informes de IU.
