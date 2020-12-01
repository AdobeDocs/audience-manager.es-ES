---
description: Configure Open Ad Server como destino y envíe datos de Audience Manager a esa plataforma.
seo-description: Configure Open Ad Server como destino y envíe datos de Audience Manager a esa plataforma.
seo-title: OAS como destino de Audience Manager
solution: Audience Manager
title: OAS como destino de Audience Manager
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 4%

---


# OAS como destino de Audience Manager {#oas-as-an-audience-manager-destination}

Configure [!DNL Open Ad Server] como destino y envíe datos de Audience Manager a esa plataforma.

## Requisitos de destino de OAS {#oas-requirements}

Estándares para la ubicación del código, formatos de clave-valor admitidos, informes y el tipo de datos de segmento enviados a [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Este tipo de destino requiere lo siguiente:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] código debe implementarse en el inventario. [!UICONTROL DIL] ayuda a eliminar la necesidad de escribir código especial para la recopilación de datos, la integración, la lectura de valores de cookies y la recuperación de datos de páginas.
* **`get_aamCookie`Función:** Código que captura el ID de usuario y los datos de cookies del Audience Manager. Coloque [este código](../../features/destinations/get-aam-cookie-code.md) en la parte superior de la página o dentro del bloque de código `<head>`.
* **Enviar Registros de envío al Audience Manager:** si desea un informe de envío de segmentos (opcional), proporcione al Audience Manager un registro diario que contenga datos de envío de nivel de impresión. Los datos pueden tener un formato sin procesar, pero cada registro debe contener el Audience Manager [!UICONTROL UUID]. El Audience Manager puede recoger o recibir estos datos a través de [!DNL FTP].

### Formato de cookie y datos de valor clave

El Audience Manager puede enviar datos de segmentos a una cookie de explorador de la siguiente manera:

* Claves únicas (`x=1&x=2`);
* Varias claves (`x=1&x=2&y=3&y=4`);
* Valores serializados (`x=1,2,3`);
* Un delimitador de valor estándar que se utiliza para separar pares clave-valor individuales.

### Solo se envían segmentos cualificados a la OAS

La cantidad de datos pasados a [!DNL OAS] depende de la cantidad de segmentos para los que un usuario en particular califique. Por ejemplo, supongamos que configura 100 segmentos de Audience Manager. Si un visitante del sitio cumple los requisitos para cinco de ellos, sólo esos cinco segmentos se envían a la OEA (no todos los 100).

>[!MORELIKETHIS]
>
>* [Código get_aamCookie](../../features/destinations/get-aam-cookie-code.md)
>* [Pares de clave-valor explicados](../../reference/key-value-pairs-explained.md)


## Crear un destino de OAS {#oas-dest-setup}

Cree un destino basado en cookies para [!DNL OAS] en Audience Manager.

<!-- aam-oas-destination-setup.xml -->

En Audience Manager, un *destino* es cualquier otro sistema (servidor de publicidad, [!DNL DSP], red de publicidad, etc.) con el que se desea compartir datos. [!UICONTROL Destination Builder] proporciona las herramientas que permiten crear y administrar estos procesos de envío de datos. Las funciones de destino de Audience Manager se encuentran en *Datos de Audiencia > Destinos*. Para comenzar, haga clic en **[!UICONTROL Add New Destination]** y siga los pasos a continuación.

### Paso 1: Información básica

Para completar la sección [!UICONTROL Basic Information]:

1. Asigne un nombre al destino.
1. Seleccione **[!UICONTROL "Cookie"]** en la lista desplegable [!UICONTROL Type].
1. Haga clic en **[!UICONTROL Save]** y pase a las secciones [!UICONTROL Configuration] y [!UICONTROL Segment Mappings].

### Paso 2: Información de configuración

Para completar la sección [!UICONTROL Configuration]:

1. **Nombre de la cookie:** proporcione un nombre corto y descriptivo para la cookie.
1. **Dominio de la cookie:** deje en blanco para establecer una cookie en el dominio de la página actual del usuario. Si desea especificar un dominio, anteponga el nombre con un punto como éste, `.mydomain.com`.
1. Elija una opción clave en la sección [!UICONTROL Data Format].
1. Si las claves utilizan datos con valores serializados, seleccione el control **[!UICONTROL Serialize]** y especifique el delimitador de serie (el carácter que separa los valores serializados).
1. Haga clic en **[!UICONTROL Save]** y expanda la sección [!UICONTROL Segment Mappings].

### Paso 3: Asignaciones de segmentos

Para agregar un segmento a un destino de cookie:

1. **Buscar segmentos:** La  [!UICONTROL Segment Mappings] sección proporciona dos herramientas de búsqueda para ayudar a localizar segmentos. Para encontrar un segmento:
   * Opción 1: Inicio que escribe el nombre de un segmento en el campo de búsqueda. El campo se actualiza automáticamente en función del texto. Haga clic **[!UICONTROL Add]** una vez que encuentre el segmento que desee utilizar.
   * Opción 2: Haga clic **[!UICONTROL Browse All Segments]** para abrir una ventana que le permite buscar segmentos por nombre o ubicación de almacenamiento. Haga clic en **[!UICONTROL Add Selected Segments]** cuando termine.
1. **Añadir asignaciones:** en la ventana emergente de asignaciones, introduzca el ID de segmento en el campo de asignaciones y haga clic en  **[!UICONTROL Save]**.
1. Haga clic **[!UICONTROL Done]**.

## Configuración de OAS {#oas-code-setup}

Modifique la configuración [!DNL OAS] para que funcione con los datos de segmentos del Audience Manager.

<!-- aam-oas-code.xml -->

Para configurar [!DNL OAS]

* Instale el código [!UICONTROL DIL] en el sitio.
* Cree OAS como destino de cookie en Audience Manager.
* Coloque la función `get_aamCookie` en la parte superior de la página, idealmente dentro del bloque de código `<head>`. El código `get_aamCookie` está disponible [aquí](../../features/destinations/get-aam-cookie-code.md).
* Modifique la etiqueta de publicidad para llamar a la función `get_aamCookie` e incluya el nombre de la cookie que proporcionó al configurar el destino [!DNL OAS]. Por ejemplo, si ha asignado a la cookie el nombre `test_cookie`, la etiqueta de publicidad debe llamar a `get_aamCookie` y hacer referencia al nombre de la cookie.
* La etiqueta de publicidad podría tener un aspecto similar al del siguiente ejemplo.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Recuerde incluir la variable `u=`. Contiene el ID de usuario único real ([!UICONTROL UUID]) pasado durante una llamada de publicidad.
