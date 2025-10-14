---
description: Audience Manager componentes de administración de etiquetas incluyen client portal, Adobe Tag Manager (obsoleta en favor de Adobe Experience Platform Launch), DIL, Akamai y la base de datos de control.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Componentes de administración de etiquetas
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 1%

---

# Componentes de administración de etiquetas{#tag-management-components}

Audience Manager componentes administración de etiquetas incluyen el portal del cliente, Adobe Tag Manager (obsoleto en favor de las etiquetas Adobe Experience Platform), DIL, Akamai y la base de datos de control.

<!-- 

c_comptag.xml

 -->

Audience Manager contiene los siguientes componentes:

* [Portal del cliente](../../reference/system-components/components-tag-management.md#client-portal)
* [Contenedor DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Biblioteca de información de datos (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Base de datos de control](../../reference/system-components/components-tag-management.md#control-database)

## Portal del cliente {#client-portal}

El portal del cliente es la principal interfaz de usuario (IU) para etiqueta y gestión de datos. Los clientes usan el portal para trabajar con etiquetas, rasgos versión y segmentos, configurar destinos y monitor rendimiento de la campaña con informes.

## Contenedor DIL/TIM {#dil-tim}

El [!UICONTROL DIL] contenedor ayuda a implementar [!DNL Audience Manager] código recopilación de datos a su sitio Web. [!UICONTROL TIM] es el administrador de inserción de etiquetas obsoleto. Ya no es utilizado por [!DNL Audience Manager]. En su lugar, utilice la [!DNL Audience Manager] extensión de Etiquetas[&#x200B; de &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=es)Adobe Experience Platform para configurar y generar código contenedor que coloque en las páginas de su inventario.

## Biblioteca de integración de datos (DIL) {#dil}

La [biblioteca](../../dil/dil-overview.md) de información de datos (DIL) es un módulo API autónomo que recopila datos de su sitio web. [!UICONTROL DIL] Ayuda a eliminar la necesidad de escribir código especial para la recopilación de datos, la integración, la lectura de valores de cookie y la recuperación de datos Página. [!UICONTROL DIL] realiza estas acciones automáticamente. Además, [!UICONTROL DIL] es compacto. Se trata de un biblioteca de código autónomo que ayuda a reducir la cantidad de código necesario para recopilar información. Por último, [!UICONTROL DIL] le ayuda a integrarse [!DNL Audience Manager] con otros productos del [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] utiliza [Akamai](https://www.akamai.com/us/en/about/) para host y entregar código contenedor desde nuestra propia plataforma de administración de etiquetas conocida como [!UICONTROL TIM (Tag Insertion Manager)]. Sin embargo, el código con [!UICONTROL TIM] implementación se ha eliminado en favor de [!DNL Adobe Experience Platform Tags].

## Base de datos de control {#control-database}

La base de datos de control:

* Procesa las entradas del cliente desde el portal (por ejemplo, creando características y destinos).
* Transmite datos a Akamai, lo que incluye los datos utilizados para versión el contenedor plantilla y el iFrame de publicación de destino.
* Devuelve datos de IU sistemas sistema de informes.
