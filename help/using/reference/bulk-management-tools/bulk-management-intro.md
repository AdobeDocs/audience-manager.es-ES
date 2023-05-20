---
description: Las herramientas Bulk Management permiten crear y gestionar varios objetos a la vez con una sola operación. Puede utilizar herramientas de administración masiva para trabajar con fuentes de datos, señales derivadas, destinos, carpetas, segmentos y rasgos.
keywords: baaam;BAAAM;descargar baaam
seo-description: The Bulk Management Tools let you create and manage multiple objects at once with single operation. You can use Bulk Management Tools to work with data sources, derived signals, destinations, folders, segments, and traits.
seo-title: Getting Started With Bulk Management
solution: Audience Manager
title: Introducción a la administración en lote
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: BAAAM
exl-id: 5603146e-7172-4181-90ad-4606129176dd
source-git-commit: 911eab2d661907c6f1e2ffc08603d994bd346395
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 3%

---

# Introducción a la administración en lote{#getting-started-with-bulk-management}

El [!DNL Bulk Management Tools] permite crear y administrar varios objetos a la vez con una sola operación. Puede utilizar [!DNL Bulk Management Tools] para trabajar con [!UICONTROL data sources], [!UICONTROL derived signals], [!UICONTROL destinations], [!UICONTROL folders], [!UICONTROL models], [!UICONTROL segments], y [!UICONTROL traits].

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[Permisos de grupo de RBAC](../../features/administration/administration-overview.md) asignado en el [!DNL Audience Manager] La interfaz de usuario de se respeta en [!UICONTROL Bulk Management Tools].

## Información general {#overview}

Esta función utiliza un [!DNL Microsoft Excel] hoja de cálculo con macros que realizan llamadas seguras y autenticadas a [!DNL Audience Manager] API. La API proporciona los métodos y servicios que le permiten realizar cambios de forma masiva. No tiene que saber codificar o trabajar con nuestras API para utilizarlo. La hoja de cálculo contiene encabezados de columna y fichas que realizan funciones específicas de cambio masivo. Para realizar cambios masivos, lo único que debe hacer es agregar los encabezados predefinidos a hojas de cálculo específicas, proporcionar la información que desee cambiar de forma masiva y hacer clic en un botón de acción. La hoja de cálculo y las API hacen el resto del trabajo por usted.

## Descargar {#download}

Descargar la hoja de cálculo más reciente **[aquí](assets/BAAAM_V2_20210609.xlsm)** (última actualización en junio de 2021).

## Requisitos previos {#prereqs}

Para usar la variable [!DNL Bulk Management Tools], necesita lo siguiente:

* Su [!DNL Experience Cloud] iniciar sesión. Como cliente, ya debería tener estas credenciales.
* El [!DNL Bulk Management Tools] hoja de cálculo. [Descargar hoja de cálculo](assets/BAAAM_V2_20200502.xlsm) para obtener la versión más reciente.
* [!DNL Microsoft Excel] ejecución en [!DNL macOS] o de 64 bits [!DNL Microsoft Windows]. Le recomendamos que utilice la versión más reciente de [!DNL Microsoft Excel].
* Al abrir la hoja de cálculo, debe **Habilitar macros** para el [!DNL Bulk Management Tools] para trabajar.

## Requisitos y opciones de autenticación {#auth-reqs}

Los cambios masivos requieren autenticación. Antes de realizar cualquier acción, debe iniciar sesión. Dado que la hoja de cálculo realiza llamadas a la API, debe configurarla para autenticarse en la cuenta de usuario.

**Requisitos de autenticación de API**

La segunda versión de [!DNL Bulk Management Tools], publicado en octubre de 2019, simplifica el proceso de autenticación. Los pasos de autenticación de esta versión se describen a continuación:

1. Abra la hoja de cálculo y vaya a **[!UICONTROL Config]** hoja.
2. Siga los pasos descritos en la hoja.
   ![](assets/baaam-authentication.png)
3. Después de completar los pasos, está autorizado para realizar cambios masivos.

Al realizar cambios masivos, seguirá teniendo que confirmar que está autorizado para realizar los cambios, pero la autenticación de API es automática.

**Opciones de autenticación de dominio**

La autenticación de dominios le da la opción de probar solicitudes masivas o aplicarlas directamente a su cuenta de producción. Realizar cambios masivos en el entorno beta no afectará a su cuenta de producción. Los cambios en la producción entran en vigor inmediatamente. La hoja de gestión masiva le permite trabajar en los siguientes entornos:

* Beta
* Producción

## Acciones y operaciones {#actions-ops}

El [!UICONTROL Bulk Management Tools] La hoja de cálculo consta de botones de autenticación, pestañas de acción, botones de acción y un **[!UICONTROL Headers]** pestaña. El **[!UICONTROL Headers]** contiene los encabezados de columna con formato previo que utilizan las pestañas de acción. Las pestañas de acción contienen macros que realizan la operación masiva seleccionada. Para realizar una operación masiva, copie un conjunto de encabezados en la pestaña de acciones correspondiente, introduzca los datos del encabezado y haga clic en un botón de acción.

Después [autentificación](#auth-reqs), haga clic en un botón de acción para comenzar.

![](assets/baaam-worksheet.png)

En la tabla siguiente se enumeran las operaciones que se pueden realizar y los elementos que se pueden manipular con [!UICONTROL Bulk Management Tools] hojas de cálculo.

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Acciones </th> 
   <th colname="col2" class="entry"> Objetos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Las acciones masivas aparecen en pestañas en la parte inferior de la hoja de cálculo e incluyen: </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Solicitudes </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Actualización </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Crear  </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Estimación </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Eliminar </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Los objetos que puede cambiar de forma masiva se encuentran en la <b><span class="uicontrol"> Encabezados</span></b> e incluir: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Fuentes de datos</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> Señales derivadas</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md">Destinos </a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> Modelos</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Carpetas de rasgos</a> Carpetas de segmentos y </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md">Segmentos </a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md">Rasgos </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ejemplo de operación masiva**

Por ejemplo, echemos un vistazo a cómo crear varios rasgos a la vez. Para crear varias características en una operación masiva, debe hacer lo siguiente:

1. Haga clic en **[!UICONTROL Headers]** y copie todas las etiquetas de la pestaña [!UICONTROL Create a Trait] opción.
2. Haga clic en **[!UICONTROL Create]** y pegue las etiquetas a partir de la fila 1, columna A.
3. Proporcione información relacionada con el encabezado de cada columna y haga clic en **[!UICONTROL Create Traits]**. Esta acción le pedirá que confirme su autenticación. El trabajo por lotes se ejecuta después de confirmar la autenticación. Busque una notificación de estado de trabajo en la esquina inferior izquierda de la hoja de cálculo.


>[!NOTE]
>
>Al trabajar con solicitudes grandes, es posible que la hoja de cálculo no responda y parezca inactiva. En estos casos, déjalo en paz. La hoja de cálculo responderá cuando se complete la solicitud masiva. Si la hoja de cálculo no responde durante un período de tiempo largo, vea el [sección solución de problemas](../../reference/bulk-management-tools/bulk-troubleshooting.md).
