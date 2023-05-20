---
description: Configure Abrir servidor de publicidad como destino y envíe datos del Audience Manager a esa plataforma.
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: OAS como destino de Audience Manager
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 4%

---

# OAS como destino de Audience Manager {#oas-as-an-audience-manager-destination}

Configuración de [!DNL Open Ad Server] como destino y enviar datos del Audience Manager a esa plataforma.

## Requisitos de destino de OAS {#oas-requirements}

Estándares para la colocación de código, formatos de clave-valor admitidos, informes y el tipo de datos de segmento enviados a [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Este tipo de destino requiere lo siguiente:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] el código debe implementarse en el inventario. [!UICONTROL DIL] ayuda a eliminar la necesidad de escribir código especial para la recopilación, integración, lectura de valores de cookies y recuperación de datos de página.
* **`get_aamCookie`Función:** Código que captura el ID de usuario del Audience Manager y los datos de cookies. Lugar [este código](../../features/destinations/get-aam-cookie-code.md) en la parte superior de la página o dentro de `<head>` bloque de código.
* **Enviar registros de envío al Audience Manager:** Si desea un informe de entrega de segmentos (opcional), proporcione al Audience Manager un registro diario que contenga datos de entrega en el nivel de impresión. Los datos pueden estar en formato sin procesar, pero cada registro debe contener el Audience Manager [!UICONTROL UUID]. El Audience Manager puede recogerlos o recibirlos a través de [!DNL FTP].

### Formato de cookies y datos de clave-valor

El Audience Manager puede enviar datos de segmentos a una cookie del explorador de la siguiente manera:

* Claves únicas (`x=1&x=2`);
* Varias claves (`x=1&x=2&y=3&y=4`);
* Valores serializados (`x=1,2,3`);
* Un delimitador de valor estándar utilizado para separar pares clave-valor individuales.

### Solo se envían a OAS los segmentos calificados

La cantidad de datos transferidos a [!DNL OAS] depende de los segmentos a los que pertenezca un usuario en particular. Por ejemplo, supongamos que configura 100 segmentos de Audience Manager. Si el visitante de un sitio cumple los requisitos para cinco de ellos, solo se envían a OAS esos cinco segmentos (no todos los 100).

>[!MORELIKETHIS]
>
>* [Código get_aamCookie](../../features/destinations/get-aam-cookie-code.md)
>* [Pares de clave-valor explicados](../../reference/key-value-pairs-explained.md)


## Crear un destino de OAS {#oas-dest-setup}

Crear un destino basado en cookies para [!DNL OAS] en Audience Manager.

<!-- aam-oas-destination-setup.xml -->

En Audience Manager, una *destino* es cualquier otro sistema (servidor de publicidad, [!DNL DSP], red de anuncios, etc.) con el que se desea compartir datos. [!UICONTROL Destination Builder] proporciona las herramientas que le permiten crear y administrar estos procesos de entrega de datos. Las funciones de destino de Audience Manager se encuentran en *Datos de audiencia > Destinos*. Para empezar, haga clic en **[!UICONTROL Add New Destination]** y siga los pasos a continuación.

### Paso 1: Información básica

Para completar la [!UICONTROL Basic Information] sección:

1. Nombre el destino.
1. Seleccionar **[!UICONTROL "Cookie"]** desde el [!UICONTROL Type] lista desplegable.
1. Clic **[!UICONTROL Save]** y continúe con la [!UICONTROL Configuration] y [!UICONTROL Segment Mappings] secciones.

### Paso 2: Información de configuración

Para completar la [!UICONTROL Configuration] sección:

1. **Nombre de la cookie:** Proporcione un nombre corto y descriptivo para la cookie.
1. **Dominio de cookie:** Déjelo en blanco para establecer una cookie en el dominio de la página actual del usuario. Si desea especificar un dominio, añada un prefijo al nombre con un punto como este. `.mydomain.com`.
1. Elija una opción clave en la [!UICONTROL Data Format] sección.
1. Si las claves utilizan datos con valores serializados, seleccione la opción **[!UICONTROL Serialize]** y especifique el delimitador de serie (el carácter que separa los valores serializados).
1. Clic **[!UICONTROL Save]** y expanda el [!UICONTROL Segment Mappings] sección.

### Paso 3: Asignaciones de segmentos

Para añadir un segmento a un destino de cookie:

1. **Buscar segmentos:** El [!UICONTROL Segment Mappings] Esta sección proporciona dos herramientas de búsqueda para localizar segmentos. Para buscar un segmento:
   * Opción 1: Empiece a escribir un nombre de segmento en el campo de búsqueda. El campo se actualiza automáticamente en función del texto. Clic **[!UICONTROL Add]** una vez que encuentre el segmento que desea utilizar.
   * Opción 2: clic **[!UICONTROL Browse All Segments]** para abrir una ventana que le permita buscar segmentos por nombre o ubicación de almacenamiento. Clic **[!UICONTROL Add Selected Segments]** cuando termine.
1. **Agregar asignaciones:** En la ventana emergente de asignaciones, introduzca el ID de segmento en el campo de asignaciones y haga clic en **[!UICONTROL Save]**.
1. Haga clic **[!UICONTROL Done]**.

## Configuración de OAS {#oas-code-setup}

Modificar [!DNL OAS] configuración para trabajar con datos de segmentos del Audience Manager.

<!-- aam-oas-code.xml -->

Para configurar [!DNL OAS]

* Instalar [!UICONTROL DIL] código en todo el sitio.
* Cree OAS como destino de cookie en Audience Manager.
* Coloque el `get_aamCookie` función en la parte superior de la página, idealmente dentro de la `<head>` bloque de código. El `get_aamCookie` el código está disponible [aquí](../../features/destinations/get-aam-cookie-code.md).
* Modifique la etiqueta de anuncio para llamar a `get_aamCookie` e incluya el nombre de la cookie que proporcionó al configurar la función [!DNL OAS] destino. Por ejemplo, si le dio a la cookie el nombre `test_cookie`, la etiqueta de anuncio debe llamar a `get_aamCookie` y hacer referencia al nombre de la cookie.
* Su etiqueta de anuncio podría ser similar al ejemplo siguiente.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Recuerde incluir el `u=` variable. Contiene el ID único de usuario real ([!UICONTROL UUID]) transferido durante una llamada de anuncio.
