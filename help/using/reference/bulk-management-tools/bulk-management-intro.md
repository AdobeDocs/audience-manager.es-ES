---
description: Las herramientas de administración masiva permiten crear y administrar varios objetos a la vez con una sola operación. Puede utilizar las herramientas de administración masiva para trabajar con fuentes de datos, señales derivadas, destinos, carpetas, segmentos y características.
keywords: baaam;BAAAM;descargar baaam
seo-description: Las herramientas de administración masiva permiten crear y administrar varios objetos a la vez con una sola operación. Puede utilizar las herramientas de administración masiva para trabajar con fuentes de datos, señales derivadas, destinos, carpetas, segmentos y características.
seo-title: Introducción a la administración en lote
solution: Audience Manager
title: Introducción a la administración en lote
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: BAAAM
exl-id: 5603146e-7172-4181-90ad-4606129176dd
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 4%

---

# Introducción a la administración en lote{#getting-started-with-bulk-management}

El [!DNL Bulk Management Tools] permite crear y administrar varios objetos a la vez con una sola operación. Puede utilizar [!DNL Bulk Management Tools] para trabajar con [!UICONTROL data sources], [!UICONTROL derived signals], [!UICONTROL destinations], [!UICONTROL folders], [!UICONTROL models], [!UICONTROL segments] y [!UICONTROL traits].

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[Los ](../../features/administration/administration-overview.md) permisos de grupo RBAC asignados en la interfaz de  [!DNL Audience Manager] usuario se respetan en  [!UICONTROL Bulk Management Tools].

## Información general {#overview}

Esta función utiliza una hoja de cálculo [!DNL Microsoft Excel] con macros que realizan llamadas seguras y autenticadas a las API [!DNL Audience Manager]. La API proporciona los métodos y servicios que le permiten realizar cambios de forma masiva. No tiene que saber cómo codificar o trabajar con nuestras API para utilizarla. La hoja de cálculo contiene encabezados de columna y fichas que realizan funciones específicas de cambio masivo. Para realizar cambios masivos, solo tiene que agregar los encabezados predefinidos a hojas de cálculo específicas, proporcionar la información que desea cambiar de forma masiva y hacer clic en un botón de acción. La hoja de cálculo y las API hacen el resto del trabajo por usted.

## Descargar {#download}

Descargue la última hoja de cálculo **[aquí](assets/BAAAM_V2_20200502.xlsm)**.

## Requisitos previos {#prereqs}

Para utilizar [!DNL Bulk Management Tools], necesita lo siguiente:

* Su inicio de sesión [!DNL Experience Cloud]. Como cliente, ya debería tener estas credenciales.
* La hoja de cálculo [!DNL Bulk Management Tools]. [Descargue la ](assets/BAAAM_V2_20200502.xlsm) hoja de cálculo para obtener la versión más reciente.
* [!DNL Microsoft Excel] se ejecuta en  [!DNL macOS] o 64 bits  [!DNL Microsoft Windows]. Le recomendamos que utilice la versión más reciente de [!DNL Microsoft Excel].
* Al abrir la hoja de cálculo, debe **Habilitar macros** para que [!DNL Bulk Management Tools] funcione.

## Requisitos y opciones de autenticación {#auth-reqs}

Los cambios masivos requieren autenticación. Antes de realizar cualquier acción, debe iniciar sesión. Como la hoja de cálculo realiza llamadas API, debe configurarla para autenticarse en la cuenta de usuario.

**Requisitos de autenticación de API**

La segunda versión de [!DNL Bulk Management Tools], publicada en octubre de 2019, simplifica el proceso de autenticación. Los pasos de autenticación en esta versión se describen a continuación:

1. Abra la hoja de cálculo y vaya a la **[!UICONTROL Config]** hoja.
2. Siga los pasos descritos en la hoja.
   ![](assets/baaam-authentication.png)
3. Después de completar los pasos, está autorizado a realizar cambios masivos.

Al realizar cambios masivos, tendrá que confirmar que está autorizado a realizar los cambios, pero la autenticación de API es automática.

**Opciones de autenticación de dominio**

La autenticación de dominio le ofrece la opción de probar solicitudes masivas o aplicarlas directamente a su cuenta de producción. Realizar cambios masivos en el entorno beta no afectará a su cuenta de producción. Los cambios de producción son efectivos de forma inmediata. La hoja de administración masiva le permite trabajar en los siguientes entornos:

* Beta
* Producción

## Acciones y operaciones {#actions-ops}

La hoja de cálculo [!UICONTROL Bulk Management Tools] consta de botones de autenticación, pestañas de acción, botones de acción y una pestaña **[!UICONTROL Headers]**. La pestaña **[!UICONTROL Headers]** contiene los encabezados de columna preformateados que utilizan las pestañas de acción. Las pestañas de acción contienen macros que realizan la operación masiva seleccionada. Para realizar una operación masiva, copie un conjunto de encabezados en la ficha de acción adecuada, introduzca los datos del encabezado y haga clic en un botón de acción.

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
   <td colname="col1"> <p>Las acciones masivas aparecen en fichas en la parte inferior de la hoja de cálculo e incluyen: </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Solicitudes </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Actualización </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Crear  </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Estimación </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Eliminar </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Los objetos que puede cambiar de forma masiva se encuentran en la pestaña <b><span class="uicontrol"> Headers</span></b> e incluyen: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Fuentes de datos</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> Señales derivadas</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md">Destinos </a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> Modelos</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Carpetas de rasgos </a> y carpetas de segmentos </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md">Segmentos </a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md">Rasgos </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ejemplo de operación masiva**

Por ejemplo, veamos cómo crear varios rasgos a la vez. Para crear varios rasgos en una operación masiva, debe hacer lo siguiente:

1. Haga clic en la pestaña **[!UICONTROL Headers]** y copie todas las etiquetas en la opción [!UICONTROL Create a Trait].
2. Haga clic en la pestaña **[!UICONTROL Create]** y pegue las etiquetas comenzando en la fila 1, columna A.
3. Proporcione información relacionada con cada encabezado de columna y haga clic en **[!UICONTROL Create Traits]**. Esta acción le pedirá que confirme la autenticación. El trabajo masivo se ejecuta después de confirmar la autenticación. Compruebe si hay una notificación de estado del trabajo en la esquina inferior izquierda de la hoja de cálculo.


>[!NOTE]
>
>Cuando se trabaja con solicitudes de gran tamaño, es posible que la hoja de cálculo no responda y parezca estar inactiva. En estos casos, simplemente déjelo en paz. La hoja de cálculo responderá cuando se complete la solicitud masiva. Si la hoja de cálculo no responde durante un largo período de tiempo, consulte la sección [solución de problemas](../../reference/bulk-management-tools/bulk-troubleshooting.md).
