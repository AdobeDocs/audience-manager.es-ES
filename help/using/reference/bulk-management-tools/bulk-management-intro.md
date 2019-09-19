---
description: Las herramientas de administración masiva permiten crear y administrar varios objetos a la vez con una sola operación. Puede utilizar las herramientas de administración masiva para trabajar con fuentes de datos, señales derivadas, destinos, carpetas, segmentos y características.
keywords: baaam;BAAAM
seo-description: Las herramientas de administración masiva permiten crear y administrar varios objetos a la vez con una sola operación. Puede utilizar las herramientas de administración masiva para trabajar con fuentes de datos, señales derivadas, destinos, carpetas, segmentos y características.
seo-title: Introducción a la administración masiva
solution: Audience Manager
title: Introducción a la administración masiva
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
translation-type: tm+mt
source-git-commit: 215054718e9248bd44ba99baeb2a10236701d98e

---


# Getting Started With Bulk Management{#getting-started-with-bulk-management}

Las herramientas de administración masiva permiten crear y administrar varios objetos a la vez con una sola operación. Puede utilizar las herramientas de administración masiva para trabajar con fuentes de datos, señales derivadas, destinos, carpetas, segmentos y características.

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>Los [!UICONTROL Bulk Management Tools] no *son* compatibles con [!DNL Audience Manager]. Esta herramienta se proporciona por conveniencia y sólo por cortesía. Para los cambios masivos, se recomienda trabajar con las API [de](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager en su lugar. [Los permisos](../../features/administration/administration-overview.md) de grupo RBAC asignados en la [!DNL Audience Manager] interfaz de usuario se respetan en la [!UICONTROL Bulk Management Tools].

## Información general {#overview}

Esta función utiliza una hoja de cálculo de Microsoft Excel con macros que realizan llamadas seguras y autenticadas a las [!DNL Audience Manager] API. La API proporciona los métodos y servicios que permiten realizar cambios de forma masiva. No es necesario que sepa cómo codificar o trabajar con nuestras API para usarlas. La hoja de cálculo contiene encabezados de columna y fichas que realizan funciones específicas de cambio masivo. Para realizar cambios masivos, solo tiene que agregar los encabezados predefinidos a hojas de cálculo específicas, proporcionar la información que desea cambiar de forma masiva y hacer clic en un botón de acción. La hoja de cálculo y las API realizan el resto del trabajo por usted.

## Descargar {#download}

Descargue la hoja de cálculo más reciente **[aquí](assets/BAAAM_August_2018.xlsm)**.

## Requisitos previos {#prereqs}

Para usar el [!DNL Bulk Management Tools], necesita lo siguiente:

* Su nombre [!DNL Audience Manager] de usuario y contraseña. Como cliente, ya debería tener estas credenciales.
* Un ID de cliente de API y una clave secreta. El administrador de cuentas puede proporcionarle estos datos.
* La [!UICONTROL Bulk Management Tools] hoja de cálculo. [Descargue la hoja de cálculo](/help/using/reference/bulk-management-tools/bulk-management-intro.md#download) para obtener la versión más reciente.

* Microsoft Excel se ejecuta en [!DNL Windows] o en una máquina [!DNL Microsoft Windows] virtual en ejecución [!DNL macOS X]. Debe utilizar Excel de 32 bits para que [!UICONTROL Bulk Management Tools] funcione.

## Acciones y operaciones {#actions-ops}

La [!UICONTROL Bulk Management Tools] hoja de cálculo consta de fichas de acción, botones de acción y una **[!UICONTROL Headers]** ficha. La **[!UICONTROL Headers]** ficha contiene los encabezados de columna con formato previo que utilizan las fichas de acción. Las fichas de acción contienen macros que realizan la operación masiva seleccionada. Para realizar una operación masiva, copie un conjunto de encabezados en la ficha de acción correspondiente, introduzca los datos del encabezado y haga clic en un botón de acción.

Abra la hoja de cálculo y haga clic en un botón de acción para comenzar.

![](assets/bamwrkbk.png)

La tabla siguiente muestra las operaciones que puede realizar y los elementos que puede manipular con las [!UICONTROL Bulk Management Tools] hojas de cálculo.

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
   <td colname="col2"> <p>Los objetos que puede cambiar de forma masiva se encuentran en la ficha <b><span class="uicontrol"> Encabezados</span></b> e incluyen: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Fuentes de datos</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> Señales derivadas</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> Destinos</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Carpetas</a> de características y carpetas de segmentos </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> Segmentos</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> Características</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ejemplo de operación masiva**

Como ejemplo, veamos cómo crear varias características a la vez. Para crear varias características en una operación masiva, debe:

1. Haga clic en la **[!UICONTROL Headers]** ficha y copie todas las etiquetas de la [!UICONTROL Create a Trait] opción.

2. Haga clic en la **[!UICONTROL Create]** ficha y pegue las etiquetas comenzando en la fila 1, columna A.
3. Proporcione información relacionada con cada encabezado de columna y haga clic en **[!UICONTROL Create Traits]**. Esta acción le solicita que inicie sesión. El trabajo masivo se ejecuta después de autenticarse correctamente (consulte los requisitos [de](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) autenticación a continuación). Compruebe en la esquina inferior izquierda de la hoja de cálculo si hay una notificación de estado del trabajo.

>[!NOTE]
>
>Cuando se trabaja con solicitudes grandes, la hoja de cálculo podría no responder y parecer inactiva. En estos casos, déjalo en paz. La hoja de cálculo responderá cuando se complete la solicitud masiva. Si la hoja de cálculo no responde durante un largo período de tiempo, consulte la sección [de](../../reference/bulk-management-tools/bulk-troubleshooting.md)solución de problemas.

## Requisitos y opciones de autenticación {#auth-reqs}

Los cambios masivos requieren autenticación. Cuando selecciona una acción, la hoja de cálculo le solicita que inicie sesión. Dado que la hoja de cálculo realiza llamadas API, debe configurarla para que lea la clave secreta. Además, el **[!UICONTROL Domain]** campo permite realizar cambios masivos en un entorno de ensayo/prueba o en su cuenta de producción activa.

![](assets/bamauth.png)

**Requisitos de autenticación de API**

Para configurar la autenticación de API, debe:

* Copie y guarde la clave secreta en un archivo de texto (.txt).
* Asigne un nombre al archivo de texto con su ID de cliente de API. Por ejemplo, si su ID de cliente es "Usuario masivo", guarde la clave en un archivo llamado "Usuario masivo.txt".
* Guarde la clave secreta y la hoja de cálculo juntos en la misma carpeta.

Al realizar cambios masivos, tendrá que introducir un nombre de usuario, una contraseña, un ID de cliente y un dominio, pero la autenticación de API es automática.

**Opciones de autenticación de dominio**

La autenticación de dominio le ofrece la opción de probar solicitudes masivas o aplicarlas directamente a su cuenta de producción. La realización de cambios masivos en el entorno de prueba no afectará a la cuenta de producción. Los cambios en la producción son efectivos inmediatamente. El **[!UICONTROL Domain]** campo acepta las siguientes direcciones, según el entorno en el que desee trabajar:

* Pruebas: `api-beta.demdex.com`
* Producción: `api.demdex.com`

>[!MORE_LIKE_THIS]
>
>* [Descargar la hoja de cálculo de administración masiva](assets/BAAAM_August_2018.xlsm)

