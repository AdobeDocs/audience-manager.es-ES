---
description: Los componentes de administración de etiquetas del Administrador de Audiencias incluyen el portal del cliente, el Administrador de etiquetas de Adobe (obsoleto en favor de Adobe Dynamic Tag Manager y Adobe Experience Platform Launch), DIL, Akamai y la base de datos de control.
seo-description: Los componentes de administración de etiquetas del Administrador de Audiencias incluyen el portal del cliente, el Administrador de etiquetas de Adobe (obsoleto en favor de Adobe Dynamic Tag Manager y Adobe Experience Platform Launch), DIL, Akamai y la base de datos de control.
seo-title: Componentes de administración de etiquetas
solution: Audience Manager
title: Componentes de administración de etiquetas
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Componentes de administración de etiquetas{#tag-management-components}

Los componentes de administración de etiquetas del Administrador de Audiencias incluyen el portal del cliente, el Administrador de etiquetas de Adobe (obsoleto en favor de Adobe Dynamic Tag Manager y Adobe Experience Platform Launch), DIL, Akamai y la base de datos de control.

<!-- 

c_comptag.xml

 -->

El Administrador de Audiencias contiene los siguientes componentes:

* [Portal del cliente](../../reference/system-components/components-tag-management.md#client-portal)
* [Contenedor DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Biblioteca de información de datos (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Base de datos de control](../../reference/system-components/components-tag-management.md#control-database)

## Portal del cliente {#client-portal}

El portal del cliente es la interfaz de usuario principal para la gestión de datos y la etiqueta. Los clientes utilizan el portal para trabajar con etiquetas, generar características y segmentos, configurar destinos y monitorear el rendimiento de la campaña con los informes.

## Contenedor DIL/TIM {#dil-tim}

El [!UICONTROL DIL] contenedor ayuda a implementar el código [!DNL Audience Manager] de recopilación de datos en el sitio web. [!UICONTROL TIM] es el Administrador de inserción de etiquetas obsoleto. Ya no se usa en [!DNL Audience Manager]. En su lugar, se utiliza la administración [](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) dinámica de etiquetas o la [!DNL Audience Manager] extensión de [Adobe Experience Platform Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) para configurar y generar el código de contenedor que se coloca en las páginas del inventario. El [!UICONTROL DTM] contenedor trabaja con el [!UICONTROL Data Information Library (DIL)] para recopilar datos del sitio y enviarlos a [!DNL Audience Manager].

## Biblioteca de integración de datos (DIL) {#dil}

La biblioteca [de información](../../dil/dil-overview.md) de datos (DIL) es un módulo de API independiente que recopila datos de su sitio web. [!UICONTROL DIL] ayuda a eliminar la necesidad de escribir código especial para la recopilación de datos, la integración, la lectura de valores de cookies y la recuperación de datos de páginas. [!UICONTROL DIL] realiza estas acciones automáticamente. Además, [!UICONTROL DIL] es compacta. Es una biblioteca de código independiente que ayuda a reducir la cantidad de código necesario para recopilar información. Por último, [!UICONTROL DIL] le ayuda a integrarse [!DNL Audience Manager] con otros productos en [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] utiliza [Akamai](https://www.akamai.com/html/about/index.html) para alojar y entregar código de contenedor desde nuestra propia plataforma de administración de etiquetas conocida como [!UICONTROL TIM (Tag Insertion Manager)]. Sin embargo, la implementación de código con [!UICONTROL TIM] se ha eliminado en favor de [!DNL Adobe Dynamic Tag Management] y [!DNL Adobe Experience Platform Launch].

## Base de datos de control {#control-database}

Base de datos de control:

* Procesa los datos introducidos por el cliente desde el portal (por ejemplo, la creación de características y destinos).
* Transmite datos a Akamai, que incluye datos utilizados para crear la plantilla de contenedor y el iFrame de publicación de destino.
* Devuelve datos para sistemas de sistema de informes de interfaz de usuario.

