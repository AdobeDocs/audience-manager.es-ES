---
description: Configure Open Ad Server como destino y envíe datos de Audience Manager a esa plataforma.
seo-description: Configure Open Ad Server como destino y envíe datos de Audience Manager a esa plataforma.
seo-title: OAS como destino de Audience Manager
solution: Audience Manager
title: OAS como destino de Audience Manager
uuid: 5891 a 063-5 a 4 b -4 ea 7-865 f-b 24 e 17 ca 735 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# OAS as an Audience Manager Destination {#oas-as-an-audience-manager-destination}

Set up [!DNL Open Ad Server] as a destination and send Audience Manager data to that platform.

## OAS Destination Requirements {#oas-requirements}

Standards for code placement, supported key-value formats, reports, and the type of segment data sent to [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Este tipo de destino requiere lo siguiente:

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library] debe implementarse en el inventario. [!UICONTROL DIL] ayuda a eliminar la necesidad de escribir código especial para la recopilación de datos, la integración, los valores de cookies de lectura y la recuperación de datos de página.
* **`get_aamCookie`Función:** Código que captura el ID de usuario de Audience Manager y los datos de cookies. Place [this code](../../features/destinations/get-aam-cookie-code.md) on the top of the page or inside the `<head>` codeblock.
* **Enviar registros de envío a Audience Manager:** Si desea un informe de entrega de segmentos (opcional), proporcione a Audience Manager un registro diario que contenga datos de entrega en el nivel de impresión. The data can be in a raw format, but each record must contain the Audience Manager [!UICONTROL UUID]. Audience Manager can pick up or receive these via [!DNL FTP].

### Formato de la cookie y datos de valor clave

Audience Manager puede enviar datos de segmentos a una cookie del explorador de la siguiente manera:

* Single keys (`x=1&x=2`);
* Multiple keys (`x=1&x=2&y=3&y=4`);
* Serialized values (`x=1,2,3`);
* Delimitador de valores estándar utilizado para separar pares de clave-valor individuales.

### Solo se envían a OAS segmentos cualificados

The amount data passed in to [!DNL OAS] depends on how many segments a particular user qualifies for. Por ejemplo, supongamos que configura 100 segmentos de Gestión de público. Si un visitante del sitio cumple los requisitos de cinco, solo se envían a OAS los cinco segmentos (no todos los 100).

>[!MORE_ LIKE_ THIS]
>
>* [get_ aamcookie Code](../../features/destinations/get-aam-cookie-code.md)
>* [Pares de clave-valor explicados](../../reference/key-value-pairs-explained.md)


## Create an OAS Destination {#oas-dest-setup}

Create a cookie-based destination for [!DNL OAS] in Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) a los que desee compartir datos. [!UICONTROL Destination Builder] proporciona las herramientas que permiten crear y administrar estos procesos de entrega de datos. Audience Manager destination features are located in *Audience Data &gt; Destinations*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

### Paso 1: Información básica

To complete the [!UICONTROL Basic Information] section:

1. Asigne un nombre al destino.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Save]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

### Paso 2: Información de configuración

To complete the [!UICONTROL Configuration] section:

1. **Nombre de la cookie:** Proporcione un nombre corto y descriptivo para la cookie.
1. **Dominio de la cookie:** Deje en blanco para configurar una cookie en el dominio de la página actual del usuario. If you want to specify a domain, prefix the name with a period like this, `.mydomain.com`.
1. Choose a key option in the [!UICONTROL Data Format] section.
1. If your keys use data with serialized values, select the **[!UICONTROL Serialize]** control and specify the serial delimiter (the character that separates the serialized values).
1. Click **[!UICONTROL Save]** and expand the [!UICONTROL Segment Mappings] section.

### Paso 3: Asignaciones de segmentos

Para agregar un segmento a un destino de cookie:

1. **Buscar segmentos:** La [!UICONTROL Segment Mappings] sección proporciona dos herramientas de búsqueda para ayudar a localizar segmentos. Para encontrar un segmento:
   * Opción 1: Empiece a escribir un nombre de segmento en el campo de búsqueda. El campo se actualiza automáticamente en función del texto. Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.
1. **Agregar asignaciones:** En las asignaciones pop, introduzca el ID de segmento en el campo Asignaciones y haga clic **[!UICONTROL Save]** en.
1. Haga clic en **[!UICONTROL Done]**.

## OAS Setup {#oas-code-setup}

Modify [!DNL OAS] settings to work with Audience Manager segment data.

<!-- aam-oas-code.xml -->

To set up [!DNL OAS]

* Install [!UICONTROL DIL] code across your site.
* Cree OAS como destino de cookie en Audience Manager.
* Place the `get_aamCookie` function at the top of the page, ideally within the `<head>` codeblock. `get_aamCookie` El código está disponible [aquí](../../features/destinations/get-aam-cookie-code.md).
* Modify your ad tag to call the `get_aamCookie` function and include the cookie name you provided when setting up the [!DNL OAS] destination. For example, if you named the cookie `test_cookie`, then the ad tag should call `get_aamCookie` and reference the cookie name.
* La etiqueta de publicidad podría tener un aspecto similar al siguiente.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Remember to include the `u=` variable. It holds the actual unique user ID ([!UICONTROL UUID]) passed in during an ad call.
