---
description: Configure OpenX como destino y envíe datos de segmentos de Audience Manager a esa plataforma.
seo-description: Configure OpenX como destino y envíe datos de segmentos de Audience Manager a esa plataforma.
seo-title: OpenX como destino de Audience Manager
solution: Audience Manager
title: OpenX como destino de Audience Manager
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 3%

---


# OpenX como destino de Audience Manager{#openx-as-an-audience-manager-destination}

Configure [!DNL OpenX] como destino y envíe datos de segmentos de Audience Manager a esa plataforma.

>[!NOTE]
>
>Solo para objetivos de servidor de publicidad en el sitio.

## Requisitos de destino de OpenX {#openx-requirements}

Estándares para la ubicación del código, formatos de clave-valor admitidos, informes y el tipo de datos de segmento enviados a [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Revise lo siguiente antes de configurar [!DNL OpenX] como destino de Audience Manager:

* **[!UICONTROL DIL]::**[!UICONTROL Data Integration Library]debe implementarse en el sitio.[!UICONTROL DIL]ayuda a eliminar la necesidad de escribir código especial para la recopilación de datos, la integración, la lectura de valores de cookies y la recuperación de datos de páginas.
* **`get_aamCookie`Función:**Código que captura el ID de usuario y los datos de cookies del Audience Manager. Coloque[este código](../../features/destinations/get-aam-cookie-code.md)en la parte superior de la página o dentro del`<head>`bloque de código.
* **Enviar Registros de envío al Audience Manager:** Si desea un informe de envío de segmentos (opcional), proporcione al Audience Manager un registro diario que contenga datos de envío de nivel de impresión. Los datos pueden tener un formato sin procesar, pero cada registro debe contener al Audience Manager `UUID`. El Audience Manager puede recogerlos o recibirlos a través de [!DNL FTP].

### Datos de valor clave: Requisitos de formato

Audience Manager envía datos en forma de pares clave-valor. Cree pares clave-valor según las siguientes especificaciones:

* Prefacio de las claves con `c.` (por ejemplo, `c.color` o `c.price`).
* Separe los valores serializados adjuntos a una sola clave con una coma (por ejemplo, `c.color = red, green, blue`).
* Separe varios pares clave-valor con un símbolo (por ejemplo, `c.color=red & c.price = 100 & c.condition = new`).
* Los nombres de las claves no deben contener caracteres especiales como acento y signos de puntuación u otros símbolos.

### Solo se envían segmentos cualificados a OpenX

La cantidad de datos pasados [!DNL OpenX] depende de la cantidad de segmentos para los que un usuario en particular califique. Por ejemplo, supongamos que configura 100 segmentos de Audience Manager. Si un visitante del sitio cumple los requisitos para cinco de ellos, solo se envían a esos cinco segmentos [!DNL OpenX] (no a todos los 100).

## Crear un destino OpenX {#openx-destination}

Cree un destino de cookie para [!DNL OpenX] en Audience Manager.

<!-- aam-openx-destination.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) con el que se desea compartir datos. [!UICONTROL Destination Builder] proporciona las herramientas que permiten crear y administrar estos procesos de envío de datos. Las funciones de destino de Audience Manager se encuentran en Datos de *Audiencia > Destinos*. Para comenzar, haga clic en **[!UICONTROL Add New Destination]** y siga los pasos a continuación.

### Paso 1: Información básica

Para completar la [!UICONTROL Basic Information] sección:

1. Asigne un nombre al destino.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Haga clic **[!UICONTROL Next]** y continúe con las secciones [!UICONTROL Configuration] y [!UICONTROL Segment Mappings] .

### Paso 2: Información de configuración

Para completar la [!UICONTROL Configuration] sección:

1. **Nombre de la cookie:** Proporcione un nombre corto y descriptivo para la cookie.
1. **Dominio de la cookie:** Deje en blanco para configurar una cookie en el dominio de la página actual del usuario. Si desea especificar un dominio, anteponga el nombre con un punto como este, `.mydomain.com`.
1. Elija una opción clave en la [!UICONTROL Data Format] sección.
1. Si las claves utilizan datos con valores serializados, seleccione el **[!UICONTROL Serialize]** control y especifique el delimitador de serie (el carácter que separa los valores serializados).
1. Haga clic **[!UICONTROL Save]** y expanda la [!UICONTROL Segment Mappings] sección.

### Paso 3: Asignaciones de segmentos

Para agregar un segmento a un destino de cookie:

1. **Buscar segmentos:** La [!UICONTROL Segment Mappings] sección proporciona dos herramientas de búsqueda para ayudar a localizar segmentos. Para encontrar un segmento:
   * Opción 1: Inicio que escribe el nombre de un segmento en el campo de búsqueda. El campo se actualiza automáticamente en función del texto. Haga clic **[!UICONTROL Add]** cuando encuentre el segmento que desee utilizar.
   * Opción 2: Haga clic en **[!UICONTROL Browse All Segments]** para abrir una ventana que le permite buscar segmentos por nombre o ubicación de almacenamiento. Haga clic **[!UICONTROL Add Selected Segments]** cuando termine.
1. **Añadir asignaciones:** En la ventana emergente de asignaciones, introduzca el ID de segmento en el campo de asignaciones y haga clic en **[!UICONTROL Save]**.
1. Haga clic **[!UICONTROL Done]**.

## Configuración de OpenX {#openx-code-setup}

Modifique [!DNL OpenX] la configuración para trabajar con datos de segmentos de Audience Manager.

<!-- aam-openx-code.xml -->

To set up [!DNL OpenX]:

* Instalar [!UICONTROL DIL] código en el sitio.
* Crear [!DNL OpenX] como destino de cookie en Audience Manager.
* Coloque la `get_aamCookie` función en la parte superior de la página, idealmente dentro del `<head>` bloque de código. El `get_aamCookie` código está disponible [aquí](../../features/destinations/get-aam-cookie-code.md).
* Modifique la etiqueta de publicidad para llamar a la `get_aamCookie` función e incluir el nombre de la cookie que proporcionó al configurar el [!DNL OpenX] destino. Por ejemplo, si ha asignado un nombre a la cookie `test_cookie`, la etiqueta de publicidad debe llamar `get_aamCookie` y hacer referencia al nombre de la cookie.
* La etiqueta de publicidad podría tener un aspecto similar al del siguiente ejemplo.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Recuerde incluir `xid=` . Contiene el ID de usuario único ([!UICONTROL UUID]) real que se transfiere durante una llamada de publicidad.

La llamada de publicidad completamente formada podría tener un aspecto similar al siguiente:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
