---
description: Las herramientas Bulk Management permiten crear y gestionar varios objetos a la vez con una sola operación. Puede utilizar herramientas de administración masiva para trabajar con fuentes de datos, señales derivadas, destinos, carpetas, segmentos y rasgos.
keywords: baaam;BAAAM;descargar baaam
seo-description: The Bulk Management Tools let you create and manage multiple objects at once with single operation. You can use Bulk Management Tools to work with data sources, derived signals, destinations, folders, segments, and traits.
seo-title: Getting Started With Bulk Management
solution: Audience Manager
title: Introducción A La Administración En Lotes
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: BAAAM
exl-id: 5603146e-7172-4181-90ad-4606129176dd
source-git-commit: 0c9c333f4e8d6d416d497f336e3e447e2e251d47
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 1%

---


# Introducción A La Administración En Lotes{#getting-started-with-bulk-management}

[!DNL Bulk Management Tools] le permite crear y administrar varios objetos a la vez con una sola operación. Puede usar [!DNL Bulk Management Tools] para trabajar con [!UICONTROL data sources], [!UICONTROL derived signals], [!UICONTROL destinations], [!UICONTROL folders], [!UICONTROL models], [!UICONTROL segments] y [!UICONTROL traits].

>[!IMPORTANT]
>
>Las herramientas de administración masiva no son una oferta de Adobe oficialmente compatible. La resolución de problemas y la asistencia técnica a través del Servicio de atención al cliente se gestionarán caso por caso.

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[Los permisos de grupo RBAC](../../features/administration/administration-overview.md) asignados en la interfaz de usuario [!DNL Audience Manager] se respetan en [!UICONTROL Bulk Management Tools].

## Información general {#overview}

Esta característica usa una hoja de cálculo de [!DNL Microsoft Excel] con macros que realizan llamadas seguras y autenticadas a las API de [!DNL Audience Manager]. La API proporciona los métodos y servicios que le permiten realizar cambios de forma masiva. No tiene que saber codificar o trabajar con nuestras API para utilizarlo. La hoja de cálculo contiene encabezados de columna y fichas que realizan funciones específicas de cambio masivo. Para realizar cambios masivos, lo único que debe hacer es agregar los encabezados predefinidos a hojas de cálculo específicas, proporcionar la información que desee cambiar de forma masiva y hacer clic en un botón de acción. La hoja de cálculo y las API hacen el resto del trabajo por usted.

## Descargar {#download}

Descargue la hoja de cálculo más reciente **[aquí](assets/BAAAM_V2_20210609.xlsm)** (actualizada por última vez en junio de 2021).

## Requisitos previos {#prereqs}

Para usar [!DNL Bulk Management Tools], necesita lo siguiente:

* Su inicio de sesión de [!DNL Experience Cloud]. Como cliente, ya debería tener estas credenciales.
* La hoja de cálculo [!DNL Bulk Management Tools]. [Descargue la hoja de cálculo](assets/BAAAM_V2_20210609.xlsm) para obtener la versión más reciente.
* [!DNL Microsoft Excel] se ejecuta en [!DNL Microsoft Windows] de 64 bits. Le recomendamos que utilice la versión más reciente de [!DNL Microsoft Excel]. Las herramientas de administración masiva no son compatibles con [!DNL macOS].
* Al abrir la hoja de cálculo, debe **Habilitar macros** para que funcione [!DNL Bulk Management Tools].

## Requisitos y opciones de autenticación {#auth-reqs}

Los cambios masivos requieren autenticación. Antes de realizar cualquier acción, debe iniciar sesión. Dado que la hoja de cálculo realiza llamadas a la API, debe configurarla para autenticarse en la cuenta de usuario.

**Requisitos de autenticación de API**

La segunda versión de [!DNL Bulk Management Tools], lanzada en octubre de 2019, simplifica el proceso de autenticación. Los pasos de autenticación de esta versión se describen a continuación:

1. Abra la hoja de cálculo y vaya a la hoja **[!UICONTROL Config]**.
2. Siga los pasos descritos en la hoja.
   ![](assets/baaam-authentication.png)
3. Después de completar los pasos, está autorizado para realizar cambios masivos.

Al realizar cambios masivos, seguirá teniendo que confirmar que está autorizado para realizar los cambios, pero la autenticación de API es automática.

**Opciones de autenticación de dominio**

La autenticación de dominios le da la opción de probar solicitudes masivas o aplicarlas directamente a su cuenta de producción. Realizar cambios masivos en el entorno beta no afectará a su cuenta de producción. Los cambios en la producción entran en vigor inmediatamente. La hoja de gestión masiva le permite trabajar en los siguientes entornos:

* Beta
* Producción

## Acciones y operaciones {#actions-ops}

La hoja de cálculo [!UICONTROL Bulk Management Tools] consta de botones de autenticación, fichas de acción, botones de acción y una ficha **[!UICONTROL Headers]**. La ficha **[!UICONTROL Headers]** contiene los encabezados de columna con formato previo que utilizan las fichas de acción. Las pestañas de acción contienen macros que realizan la operación masiva seleccionada. Para realizar una operación masiva, copie un conjunto de encabezados en la pestaña de acciones correspondiente, introduzca los datos del encabezado y haga clic en un botón de acción.

Después de [autenticarse](#auth-reqs), haga clic en un botón de acción para comenzar.

![](assets/baaam-worksheet.png)

En la tabla siguiente se enumeran las operaciones que puede realizar y los elementos que puede manipular con las hojas de cálculo [!UICONTROL Bulk Management Tools].

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
   <td colname="col2"> <p>Los objetos que puede cambiar de forma masiva se encuentran en la ficha <b><span class="uicontrol"> Encabezados</span></b> e incluyen: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> orígenes de datos</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> señales derivadas</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> destinos</a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> modelos</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> carpetas de rasgos</a> y carpetas de segmentos </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> segmentos</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> rasgos</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ejemplo de operación masiva**

Por ejemplo, echemos un vistazo a cómo crear varios rasgos a la vez. Para crear varias características en una operación masiva, debe hacer lo siguiente:

1. Haga clic en la ficha **[!UICONTROL Headers]** y copie todas las etiquetas de la opción [!UICONTROL Create a Trait].
2. Haga clic en la ficha **[!UICONTROL Create]** y pegue las etiquetas que comienzan en la fila 1, columna A.
3. Proporcione información relacionada con el encabezado de cada columna y haga clic en **[!UICONTROL Create Traits]**. Esta acción le pedirá que confirme su autenticación. El trabajo por lotes se ejecuta después de confirmar la autenticación. Busque una notificación de estado de trabajo en la esquina inferior izquierda de la hoja de cálculo.


>[!NOTE]
>
>Al trabajar con solicitudes grandes, es posible que la hoja de cálculo no responda y parezca inactiva. En estos casos, déjalo en paz. La hoja de cálculo responderá cuando se complete la solicitud masiva. Si la hoja de cálculo no responde durante mucho tiempo, vea la [sección de solución de problemas](../../reference/bulk-management-tools/bulk-troubleshooting.md).
