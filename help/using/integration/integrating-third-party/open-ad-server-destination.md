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

## Requisitos de destino de la OAS {#oas-requirements}

Estándares para la ubicación del código, formatos de clave-valor admitidos, informes y el tipo de datos de segmento enviados a [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Este tipo de destino requiere lo siguiente:

* **[!UICONTROL DIL]::**[!UICONTROL Data Integration Library]el código debe implementarse en el inventario.[!UICONTROL DIL]ayuda a eliminar la necesidad de escribir código especial para la recopilación de datos, la integración, la lectura de valores de cookies y la recuperación de datos de páginas.
* **`get_aamCookie`Función:**Código que captura el ID de usuario y los datos de cookies del Audience Manager. Coloque[este código](../../features/destinations/get-aam-cookie-code.md)en la parte superior de la página o dentro del`<head>`bloque de código.
* **Enviar Registros de envío al Audience Manager:** Si desea un informe de envío de segmentos (opcional), proporcione al Audience Manager un registro diario que contenga datos de envío de nivel de impresión. Los datos pueden tener un formato sin procesar, pero cada registro debe contener al Audience Manager [!UICONTROL UUID]. El Audience Manager puede recogerlos o recibirlos a través de [!DNL FTP].

### Formato de cookie y datos de valor clave

El Audience Manager puede enviar datos de segmentos a una cookie de explorador de la siguiente manera:

* Claves únicas (`x=1&x=2`);
* Claves múltiples (`x=1&x=2&y=3&y=4`);
* Valores serializados (`x=1,2,3`);
* Un delimitador de valor estándar que se utiliza para separar pares clave-valor individuales.

### Solo se envían segmentos cualificados a la OAS

La cantidad de datos pasados [!DNL OAS] depende de la cantidad de segmentos para los que un usuario en particular califique. Por ejemplo, supongamos que configura 100 segmentos de Audience Manager. Si un visitante del sitio cumple los requisitos para cinco de ellos, sólo esos cinco segmentos se envían a la OEA (no todos los 100).

>[!MORELIKETHIS]
>
>* [Código get_aamCookie](../../features/destinations/get-aam-cookie-code.md)
>* [Pares de clave-valor explicados](../../reference/key-value-pairs-explained.md)


## Crear un destino de OAS {#oas-dest-setup}

Cree un destino basado en cookies para [!DNL OAS] en Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) con el que se desea compartir datos. [!UICONTROL Destination Builder] proporciona las herramientas que permiten crear y administrar estos procesos de envío de datos. Las funciones de destino de Audience Manager se encuentran en Datos de *Audiencia > Destinos*. Para comenzar, haga clic en **[!UICONTROL Add New Destination]** y siga los pasos a continuación.

### Paso 1: Información básica

Para completar la [!UICONTROL Basic Information] sección:

1. Asigne un nombre al destino.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Haga clic **[!UICONTROL Save]** y continúe con las secciones [!UICONTROL Configuration] y [!UICONTROL Segment Mappings] .

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

## Configuración de OAS {#oas-code-setup}

Modifique [!DNL OAS] la configuración para trabajar con datos de segmentos de Audience Manager.

<!-- aam-oas-code.xml -->

To set up [!DNL OAS]

* Instalar [!UICONTROL DIL] código en el sitio.
* Cree OAS como destino de cookie en Audience Manager.
* Coloque la `get_aamCookie` función en la parte superior de la página, idealmente dentro del `<head>` bloque de código. El `get_aamCookie` código está disponible [aquí](../../features/destinations/get-aam-cookie-code.md).
* Modifique la etiqueta de publicidad para llamar a la `get_aamCookie` función e incluir el nombre de la cookie que proporcionó al configurar el [!DNL OAS] destino. Por ejemplo, si ha asignado un nombre a la cookie `test_cookie`, la etiqueta de publicidad debe llamar `get_aamCookie` y hacer referencia al nombre de la cookie.
* La etiqueta de publicidad podría tener un aspecto similar al del siguiente ejemplo.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Recuerde incluir la `u=` variable. Contiene el ID de usuario único ([!UICONTROL UUID]) real que se transfiere durante una llamada de publicidad.
