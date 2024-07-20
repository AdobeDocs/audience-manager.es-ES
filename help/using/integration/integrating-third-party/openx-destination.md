---
description: Configure OpenX como destino y envíe datos de segmentos del Audience Manager a esa plataforma.
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX como destino de Audience Manager
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 1%

---

# OpenX como destino de Audience Manager{#openx-as-an-audience-manager-destination}

Configure [!DNL OpenX] como destino y envíe datos de segmentos del Audience Manager a esa plataforma.

>[!NOTE]
>
>Solo para direccionamiento de servidor de publicidad in situ.

## Requisitos de destino de OpenX {#openx-requirements}

Estándares para la colocación de código, formatos de clave-valor admitidos, informes y el tipo de datos de segmento enviados a [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Revise lo siguiente antes de configurar [!DNL OpenX] como destino de Audience Manager:

* **[!UICONTROL DIL]:** El código [!UICONTROL Data Integration Library] debe implementarse en el sitio. [!UICONTROL DIL] ayuda a eliminar la necesidad de escribir código especial para la recopilación, integración, lectura de valores de cookies y recuperación de datos de páginas.
* Función **`get_aamCookie`:** código que captura el identificador de usuario Audience Manager y los datos de cookies. Coloque [este código](../../features/destinations/get-aam-cookie-code.md) en la parte superior de la página o dentro del bloque de código `<head>`.
* **Enviar registros de envío al Audience Manager:** Si desea un informe de envío de segmento (opcional), proporcione al Audience Manager un registro diario que contenga los datos de envío en el nivel de impresión. Los datos pueden estar en formato sin procesar, pero cada registro debe contener el Audience Manager `UUID`. El Audience Manager puede recogerlos o recibirlos a través de [!DNL FTP].

### Datos de clave-valor: requisitos de formato

El Audience Manager envía datos en forma de pares clave-valor. Cree pares clave-valor según las siguientes especificaciones:

* Prefacio de claves con `c.` (por ejemplo, `c.color` o `c.price`).
* Separe los valores serializados adjuntos a una sola clave con una coma (por ejemplo, `c.color = red, green, blue`).
* Separe varios pares clave-valor con un signo &amp; (por ejemplo, `c.color=red & c.price = 100 & c.condition = new`).
* Los nombres de clave no deben contener caracteres especiales como acentos, signos de puntuación u otros símbolos.

### Solo se envían a OpenX segmentos cualificados

La cantidad de datos pasados a [!DNL OpenX] depende de para cuántos segmentos califica un usuario en particular. Por ejemplo, supongamos que configura 100 segmentos de Audience Manager. Si el visitante de un sitio califica para cinco de ellos, entonces solo esos cinco segmentos se envían a [!DNL OpenX] (no todos los 100).

## Crear un destino OpenX {#openx-destination}

Cree un destino de cookie para [!DNL OpenX] en el Audience Manager.

<!-- aam-openx-destination.xml -->

En el Audience Manager, *destination* es cualquier otro sistema (servidor de publicidad, [!DNL DSP], red de publicidad, etc.) con el que se desea compartir datos. [!UICONTROL Destination Builder] proporciona las herramientas que le permiten crear y administrar estos procesos de entrega de datos. Las características de destino de Audience Manager se encuentran en *Datos de audiencia > Destinos*. Para comenzar, haga clic en **[!UICONTROL Add New Destination]** y siga los pasos a continuación.

### Paso 1: Información básica

Para completar la sección [!UICONTROL Basic Information]:

1. Nombre el destino.
1. Seleccione **[!UICONTROL "Cookie"]** de la lista desplegable [!UICONTROL Type].
1. Haga clic en **[!UICONTROL Next]** y continúe con las secciones [!UICONTROL Configuration] y [!UICONTROL Segment Mappings].

### Paso 2: Información de configuración

Para completar la sección [!UICONTROL Configuration]:

1. **Nombre de cookie:** Proporcione un nombre corto y descriptivo para su cookie.
1. **Dominio de cookies:** Déjelo en blanco para establecer una cookie en el dominio de la página actual del usuario. Si desea especificar un dominio, agregue un prefijo al nombre con un punto como este, `.mydomain.com`.
1. Elija una opción clave en la sección [!UICONTROL Data Format].
1. Si las claves utilizan datos con valores serializados, seleccione el control **[!UICONTROL Serialize]** y especifique el delimitador de serie (el carácter que separa los valores serializados).
1. Haga clic en **[!UICONTROL Save]** y expanda la sección [!UICONTROL Segment Mappings].

### Paso 3: Asignaciones de segmentos

Para añadir un segmento a un destino de cookie:

1. **Buscar segmentos:** La sección [!UICONTROL Segment Mappings] proporciona dos herramientas de búsqueda que le ayudarán a localizar segmentos. Para buscar un segmento:
   * Opción 1: Empiece a escribir un nombre de segmento en el campo de búsqueda. El campo se actualiza automáticamente en función del texto. Haga clic en **[!UICONTROL Add]** cuando encuentre el segmento que desea utilizar.
   * Opción 2: haga clic en **[!UICONTROL Browse All Segments]** para abrir una ventana que le permita buscar segmentos por nombre o ubicación de almacenamiento. Haga clic en **[!UICONTROL Add Selected Segments]** cuando termine.
1. **Agregar asignaciones:** En la ventana emergente de asignaciones, escriba el identificador del segmento en el campo de asignaciones y haga clic en **[!UICONTROL Save]**.
1. Haga clic en **[!UICONTROL Done]**.

## Configuración de OpenX {#openx-code-setup}

Modifique la configuración de [!DNL OpenX] para que funcione con los datos de segmentos del Audience Manager.

<!-- aam-openx-code.xml -->

Para configurar [!DNL OpenX]:

* Instale el código [!UICONTROL DIL] en todo el sitio.
* Crear [!DNL OpenX] como destino de cookie en el Audience Manager.
* Coloque la función `get_aamCookie` en la parte superior de la página, idealmente dentro del bloque de código `<head>`. El código `get_aamCookie` está disponible [aquí](../../features/destinations/get-aam-cookie-code.md).
* Modifique la etiqueta de anuncio para llamar a la función `get_aamCookie` e incluir el nombre de cookie que proporcionó al configurar el destino [!DNL OpenX]. Por ejemplo, si asignó un nombre a la cookie `test_cookie`, la etiqueta de publicidad debe llamar a `get_aamCookie` y hacer referencia al nombre de la cookie.
* Su etiqueta de anuncio podría ser similar al ejemplo siguiente.

  ```
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&xid=" + get_aamCookie('aam_uuid')
  ```

Recuerde incluir `xid=` Contiene el identificador de usuario único real ([!UICONTROL UUID]) que se pasó durante una llamada de anuncio.

La llamada de anuncio completamente formada podría tener un aspecto similar al siguiente:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
