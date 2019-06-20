---
description: Los componentes de administración de etiquetas de Audience Manager incluyen el portal de cliente, Adobe Tag Manager (obsoleto en favor del administrador dinámico de etiquetas de Adobe y Adobe Launch), DIL, Akamai y la base de datos de control.
seo-description: Los componentes de administración de etiquetas de Audience Manager incluyen el portal de cliente, Adobe Tag Manager (obsoleto en favor del administrador dinámico de etiquetas de Adobe y Adobe Launch), DIL, Akamai y la base de datos de control.
seo-title: Componentes de administración de etiquetas
solution: Audience Manager
title: Componentes de administración de etiquetas
uuid: e 5059478-6 ba 7-4 e 1 a-afec-e 41 ad 7 a 27750
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Tag Management Components{#tag-management-components}

Los componentes de administración de etiquetas de Audience Manager incluyen el portal de cliente, Adobe Tag Manager (obsoleto en favor del administrador dinámico de etiquetas de Adobe y Adobe Launch), DIL, Akamai y la base de datos de control.

<!-- 

c_comptag.xml

 -->

Audience Manager contiene los componentes siguientes:

* [Portal de cliente](../../reference/system-components/components-tag-management.md#client-portal)
* [Contenedor DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Biblioteca de información de datos (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Base de datos de control](../../reference/system-components/components-tag-management.md#control-database)

## Client Portal {#client-portal}

El portal de cliente es la interfaz de usuario principal (IU) para la administración de etiquetas y datos. Los clientes utilizan el portal para trabajar con etiquetas, crear características y segmentos, configurar destinos y supervisar el rendimiento de las campañas con los informes.

## DIL/TIM Container {#dil-tim}

[!UICONTROL DIL] El contenedor ayuda a implementar [!DNL Audience Manager] el código de recopilación de datos en el sitio web. [!UICONTROL TIM] es el administrador de inserción de etiquetas obsoleto. It is no longer used by [!DNL Audience Manager]. Instead, you use [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) or the [!DNL Audience Manager] extension in [Adobe Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) to configure and generate container code that you place on pages in your inventory. [!UICONTROL DTM] El contenedor trabaja con [!UICONTROL Data Information Library (DIL)] para recopilar datos de su sitio y enviarlos a [!DNL Audience Manager].

## Biblioteca de integración de datos (DIL) {#dil}

The [Data Information Library](../../dil/dil-overview.md) (DIL) is a self-contained API module that collects data from your website. [!UICONTROL DIL] ayuda a eliminar la necesidad de escribir código especial para la recopilación de datos, la integración, los valores de cookies de lectura y la recuperación de datos de página. [!UICONTROL DIL] realiza estas acciones automáticamente. Additionally, [!UICONTROL DIL] is compact. Es una biblioteca de código independiente que ayuda a reducir la cantidad de código necesaria para recopilar información. Finally, [!UICONTROL DIL] helps you integrate [!DNL Audience Manager] with other products in the [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] utiliza [Akamai](https://www.akamai.com/html/about/index.html) para alojar y entregar código de contenedor desde nuestra propia plataforma de administración de etiquetas conocida como [!UICONTROL TIM (Tag Insertion Manager)]. However, code deployment with [!UICONTROL TIM] has been phased out in favor of [!UICONTROL Adobe Dynamic Tag Management] and [!UICONTROL Adobe Launch].

## Control Database {#control-database}

La base de datos de control:

* Procesa la entrada del cliente desde el portal (por ejemplo, creando características y destinos).
* Transmite datos a Akamai, que incluye datos utilizados para crear el iframe de publicación de contenedor y de publicación de destino.
* Devuelve datos para sistemas de informes de interfaz de usuario.

