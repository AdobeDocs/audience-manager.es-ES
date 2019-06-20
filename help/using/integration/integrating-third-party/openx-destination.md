---
description: Configure openx como destino y envíe datos de segmentos de Audience Manager a esa plataforma.
seo-description: Configure openx como destino y envíe datos de segmentos de Audience Manager a esa plataforma.
seo-title: Openx como destino de Audience Manager
solution: Audience Manager
title: Openx como destino de Audience Manager
uuid: 5 e 86 ba 73-281 c -403 b-af 06-64 a 1 d 427526 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# OpenX as an Audience Manager Destination{#openx-as-an-audience-manager-destination}

Set up [!DNL OpenX] as a destination and send Audience Manager segment data to that platform.

>[!NOTE]
>
>Solo para objetivos del servidor de publicidad en el sitio.

## OpenX Destination Requirements {#openx-requirements}

Standards for code placement, supported key-value formats, reports, and the type of segment data sent to [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Review the following before setting up [!DNL OpenX] as an Audience Manager destination:

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library] debe implementarse en el sitio. [!UICONTROL DIL] ayuda a eliminar la necesidad de escribir código especial para la recopilación de datos, la integración, los valores de cookies de lectura y la recuperación de datos de página.
* **`get_aamCookie`Función:** Código que captura el ID de usuario de Audience Manager y los datos de cookies. Place [this code](../../features/destinations/get-aam-cookie-code.md) on the top of the page or inside the `<head>` codeblock.
* **Enviar registros de envío a Audience Manager:** Si desea un informe de entrega de segmentos (opcional), proporcione a Audience Manager un registro diario que contenga datos de entrega en el nivel de impresión. The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager can pick up or receive these via [!DNL FTP].

### Datos de valor clave: Requisitos de formato

Audience Manager envía datos en forma de pares clave-valor. Cree pares clave-valor de acuerdo con las siguientes especificaciones:

* Preface keys with `c.` (e.g., `c.color` or `c.price`).
* Separate serialized values attached to a single key with a comma (e.g., `c.color = red, green, blue`).
* Separate multiple key-value pairs with an ampersand (e.g., `c.color=red & c.price = 100 & c.condition = new`).
* Los nombres clave no deben contener caracteres especiales como signos de puntuación y puntuación u otros símbolos.

### Solo los segmentos cualificados se envían a openx

The amount data passed in to [!DNL OpenX] depends on how many segments a particular user qualifies for. Por ejemplo, supongamos que configura 100 segmentos de Gestión de público. If a site visitor qualifies for five of them, then only those five segments get sent to [!DNL OpenX] (not all 100).

## Create an OpenX Destination {#openx-destination}

Create a cookie destination for [!DNL OpenX] in Audience Management.

<!-- aam-openx-destination.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) a los que desee compartir datos. [!UICONTROL Destination Builder] proporciona las herramientas que permiten crear y administrar estos procesos de entrega de datos. Audience Manager destination features are located in *Audience Data &gt; Destinations*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

### Paso 1: Información básica

To complete the [!UICONTROL Basic Information] section:

1. Asigne un nombre al destino.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

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

## OpenX Setup {#openx-code-setup}

Modify [!DNL OpenX] settings to work with Audience Manager segment data.

<!-- aam-openx-code.xml -->

To set up [!DNL OpenX]:

* Install [!UICONTROL DIL] code across your site.
* Create [!DNL OpenX] as a cookie destination in Audience Manager.
* Place the `get_aamCookie` function at the top of the page, ideally within the `<head>` codeblock. `get_aamCookie` El código está disponible [aquí](../../features/destinations/get-aam-cookie-code.md).
* Modify your ad tag to call the `get_aamCookie` function and include the cookie name you provided when setting up the [!DNL OpenX] destination. For example, if you named the cookie `test_cookie`, then the ad tag should call `get_aamCookie` and reference the cookie name.
* La etiqueta de publicidad podría tener un aspecto similar al siguiente.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Remember to include `xid=` . It holds the actual unique user ID ([!UICONTROL UUID]) passed in during an ad call.

La llamada de publicidad completamente formada podría tener un aspecto similar al siguiente:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
