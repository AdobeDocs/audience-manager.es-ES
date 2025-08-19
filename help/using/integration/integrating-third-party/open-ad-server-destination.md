---
description: Configure Abrir servidor de publicidad como destino y envíe datos de Audience Manager a esa plataforma.
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: OAS como destino de Audience Manager
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 0%

---

# OAS como destino de Audience Manager {#oas-as-an-audience-manager-destination}

Configure [!DNL Open Ad Server] como destino y envíe datos de Audience Manager a esa plataforma.

## Requisitos de destino de OAS {#oas-requirements}

Estándares para la colocación de código, formatos de clave-valor admitidos, informes y el tipo de datos de segmento enviados a [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Este tipo de destino requiere lo siguiente:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] código debe implementarse en el inventario. [!UICONTROL DIL] ayuda a eliminar la necesidad de escribir código especial para la recopilación, integración, lectura de valores de cookies y recuperación de datos de páginas.
* Función **`get_aamCookie`:** código que captura el ID de usuario de Audience Manager y los datos de cookies. Coloque [este código](../../features/destinations/get-aam-cookie-code.md) en la parte superior de la página o dentro del bloque de código `<head>`.
* **Enviar registros de envío a Audience Manager:** Si desea un informe de envío de segmento (opcional), proporcione a Audience Manager un registro diario que contenga los datos de envío en el nivel de impresión. Los datos pueden estar en formato sin procesar, pero cada registro debe contener el Audience Manager [!UICONTROL UUID]. Audience Manager puede recogerlos o recibirlos a través de [!DNL FTP].

### Formato de cookies y datos de clave-valor

Audience Manager puede enviar datos de segmentos a una cookie del explorador de la siguiente manera:

* Claves únicas (`x=1&x=2`);
* Claves múltiples (`x=1&x=2&y=3&y=4`);
* Valores serializados (`x=1,2,3`);
* Un delimitador de valor estándar utilizado para separar pares clave-valor individuales.

### Solo se envían a OAS los segmentos calificados

La cantidad de datos pasados a [!DNL OAS] depende de para cuántos segmentos califica un usuario en particular. Por ejemplo, supongamos que configura 100 segmentos de Audience Manager. Si el visitante de un sitio cumple los requisitos para cinco de ellos, solo se envían a OAS esos cinco segmentos (no todos los 100).

>[!MORELIKETHIS]
>
>* [Código get_aamCookie](../../features/destinations/get-aam-cookie-code.md)
>* [Pares de clave-valor explicados](../../reference/key-value-pairs-explained.md)

## Crear un destino de OAS {#oas-dest-setup}

Cree un destino basado en cookies para [!DNL OAS] en Audience Manager.

<!-- aam-oas-destination-setup.xml -->

En Audience Manager, un *destino* es cualquier otro sistema (servidor de publicidad, [!DNL DSP], red de publicidad, etc.) con el que desee compartir datos. [!UICONTROL Destination Builder] proporciona las herramientas que le permiten crear y administrar estos procesos de entrega de datos. Las características de destino de Audience Manager se encuentran en *Datos de audiencia > Destinos*. Para comenzar, haga clic en **[!UICONTROL Add New Destination]** y siga los pasos a continuación.

### Paso 1: Información básica

Para completar la sección [!UICONTROL Basic Information]:

1. Nombre el destino.
1. Seleccione **[!UICONTROL "Cookie"]** de la lista desplegable [!UICONTROL Type].
1. Haga clic en **[!UICONTROL Save]** y continúe con las secciones [!UICONTROL Configuration] y [!UICONTROL Segment Mappings].

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

## Configuración de OAS {#oas-code-setup}

Modifique la configuración de [!DNL OAS] para que funcione con los datos de segmentos de Audience Manager.

<!-- aam-oas-code.xml -->

Para configurar [!DNL OAS]

* Instale el código [!UICONTROL DIL] en todo el sitio.
* Cree OAS como destino de cookie en Audience Manager.
* Coloque la función `get_aamCookie` en la parte superior de la página, idealmente dentro del bloque de código `<head>`. El código `get_aamCookie` está disponible [aquí](../../features/destinations/get-aam-cookie-code.md).
* Modifique la etiqueta de anuncio para llamar a la función `get_aamCookie` e incluir el nombre de cookie que proporcionó al configurar el destino [!DNL OAS]. Por ejemplo, si asignó un nombre a la cookie `test_cookie`, la etiqueta de publicidad debe llamar a `get_aamCookie` y hacer referencia al nombre de la cookie.
* Su etiqueta de anuncio podría ser similar al ejemplo siguiente.

  ```js
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&u=" + get_aamCookie('aam_uuid')
  ```

Recuerde incluir la variable `u=`. Contiene el identificador de usuario único real ([!UICONTROL UUID]) que se pasó durante una llamada de anuncio.
