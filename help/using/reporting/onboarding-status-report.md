---
description: El Informe de estado de carga comprueba las tasas de éxito y error para procesar registros en los archivos de fuente de datos de entrada. Este informe muestra los datos en un gráfico de barras interactivo y proporciona métricas de resumen en forma de tabla. Además, incluye la opción de los archivos de muestra para un intervalo de tiempo fijo y muestra los errores más comunes para cada tipo de error. Puede encontrar este informe en Analytics > Informe de estado de integración. Este informe también está disponible cuando se crea una fuente de datos de entrada.
seo-description: The Onboarding Status Report checks success and failure rates for processing records in your inbound data source files. This report displays data in an interactive bar chart and provides summary metrics in tabular form. And, it includes an option that samples files for a fixed time interval and displays the most common errors for each error type. You can find this report in Analytics > Onboarding Status Report. This report is also available when you create an inbound data source.
seo-title: Onboarding Status Report
solution: Audience Manager
title: Informe de estado de integración
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
feature: Inbound and Outbound Reports
exl-id: 4517276f-5025-4779-917f-4a0bb22ca56c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1416'
ht-degree: 6%

---

# Informe de estado de integración{#onboarding-status-report-about}

El Informe de estado de carga comprueba las tasas de éxito y error para procesar registros en los archivos de fuente de datos de entrada. Este informe muestra los datos en un gráfico de barras interactivo y proporciona métricas de resumen en forma de tabla. Además, incluye la opción de los archivos de muestra para un intervalo de tiempo fijo y muestra los errores más comunes para cada tipo de error. Puede encontrar este informe en Analytics > Informe de estado de integración. Este informe también está disponible cuando se crea una fuente de datos de entrada.

>[!NOTE]
>
>Solo los usuarios con privilegios de administrador pueden ver este informe en la interfaz de usuario del Audience Manager. Puede hacer que se notifique a los usuarios que no son administradores del estado de los archivos de entrada cargados añadiendo sus correos electrónicos al informe. Consulte [Recibir notificaciones por correo electrónico](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## Informe de estado de carga: Acerca de {#onboarding-status-about}

El [!UICONTROL Onboarding Status Report] comprueba las tasas de éxito y error para procesar registros en los archivos de fuente de datos de entrada. Este informe muestra los datos en un gráfico de barras interactivo y proporciona métricas de resumen en forma de tabla. Además, incluye la opción de los archivos de muestra para un intervalo de tiempo fijo y muestra los errores más comunes para cada tipo de error. Puede encontrar este informe en **[!UICONTROL Analytics > Onboarding Status Report]**. Este informe también está disponible cuando se crea una fuente de datos de entrada.

## Informes de errores y muestreo de errores {#error-reporting-sampling}

Los informes de errores y el muestreo de errores son dos características independientes del [!UICONTROL Onboarding Status] informe.

<table id="table_4706D891D4C545E8BF9D8A0CC052CC48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Función </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Informes de errores</b> </p> </td>
   <td colname="col2"> <p>Los informes de errores muestran las tasas de éxito y error correspondientes al número de registros procesados en una fuente de datos de entrada. Devuelve datos en un gráfico de barras apiladas interactivo y como métricas de resumen en tablas debajo del gráfico. </p> <p>El informe de errores es automático. Se ejecuta continuamente para todas las fuentes de datos de entrada. Devuelve datos en función del intervalo de intervalos de tiempo preestablecidos o de un intervalo de tiempo personalizado que haya establecido con un widget de calendario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Muestreo de errores</b> </p> </td>
   <td colname="col2"> <p>El muestreo de errores analiza el contenido de los archivos de datos y devuelve los 10 errores más comunes para cada tipo de error. Los errores en los archivos de datos de entrada impiden que se procesen registros individuales. Utilice este informe como herramienta de solución de problemas para ayudar a reducir el número de errores de archivo y mejorar las tasas de procesamiento. </p> <p>Se debe activar el muestreo de errores manualmente. Se ejecuta durante 14 días a partir del día de la activación y luego se apaga a sí mismo. Puede volver a activar el muestreo de errores una vez transcurrido el intervalo de 14 días. El muestreo de errores se activa al <a href="../features/manage-datasources.md#create-data-source"> crear una fuente de datos de entrada</a> o comprobando la <b><span class="uicontrol"> Muestreo de errores</span></b> de la pestaña <span class="wintitle"> Configuración de fuente de datos</span> de una fuente de datos de entrada existente. </p> <p>El muestreo de errores es un proceso que requiere cálculo. Como resultado, solo devuelve los 10 primeros errores para cada categoría de error. No está diseñado para devolver todos los errores contenidos en una fuente de datos de entrada. Estos errores son una muestra representativa de un grupo potencialmente mayor de errores similares. Revise todo el archivo en busca de los tipos de errores que marca este informe, vuelva a dar formato al archivo y envíelo de nuevo. </p> <p>Consulte <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Contenido del archivo de datos de entrada: sintaxis, variables y ejemplos</a> para obtener más información sobre cómo dar formato correctamente a un archivo de datos para un origen de datos de entrada. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Gráfico de barras de informe de errores {#error-report-bar-chart}

El informe de errores crea gráficos de los índices de éxito y error para el procesamiento de registros en un gráfico de barras apiladas, como se muestra en el siguiente ejemplo. El gráfico es interactivo. Al hacer clic en una barra, se muestran las métricas de resumen de ese día en una tabla debajo del gráfico.

![](assets/stacked-graph.png)

## Tablas de informe de errores {#error-report-tables}

El informe de errores muestra datos tabulares debajo del gráfico de barras. La tabla muestra las tasas de éxito y fracaso junto con los totales y porcentajes.

**Registros correctos y fallidos**

Esta vista predeterminada muestra un recuento de frecuencia del total de registros del informe e incluye un desglose de los errores por tipo de error.

![](assets/success-failure.png)

**Totales y porcentajes**

Clic **[!UICONTROL Totals & Percentages]** para ver qué % de sus archivos se procesaron correctamente.

![](assets/totals-percentages.png)

## Informe de muestreo de errores durante 14 días {#error-reporting-14-days}

Con el muestreo de errores activo, el informe mostrará los 10 errores principales para cada tipo de error. Haga clic en un botón de tipo de error en la parte superior del informe para ver cada conjunto de datos muestreados.

>[!NOTE]
>
>El informe no resalta los errores de registro con esta versión actual. Para buscar y corregir errores de archivos, debe revisar los resultados y compararlos con las especificaciones de la [Contenido de archivo de datos entrantes](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) documentación.

![](assets/error-samples.png)

## Recibir notificaciones por correo electrónico {#receive-email-notifications}

Puede añadir las direcciones de correo electrónico de los destinatarios a los que desea que se notifique el estado de los archivos de entrada cargados. Tenga en cuenta que puede seleccionar diferentes destinatarios para diferentes fuentes de datos.

![](assets/mail-notifications.png)

## Creación de un informe de estado de integración {#create-onboard-status-report}

A [!UICONTROL Sample Error Report] devuelve el número de registros de un origen de datos que se procesaron correctamente y el número de errores. Siga estos pasos para generar una [!UICONTROL Sample Error Report].

<!-- 

create-onboarding-status-report.xml

 -->


1. Ir a **[!UICONTROL Analytics > Onboarding Status Report]**. Busque una fuente de datos o elija una en la lista.

2. Seleccione un intervalo de fecha. Las opciones incluyen:

   * Un conjunto de intervalos de informes fijos.
   * Widgets de calendario que permiten crear un intervalo de fechas personalizado.

3. Haga clic **[!UICONTROL OK]**.

## Términos y definiciones del informe de estado de integración {#report-terms-conditions}

Una guía de referencia para las etiquetas y los términos utilizados en este informe.

<table id="table_1D44A2E6B4C847848B818190DD336841"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Término </th> 
   <th colname="col2" class="entry"> Definición </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Nombre del archivo de sincronización de datos</b> </p> </td> 
   <td colname="col2"> <p>Muestra los archivos que <span class="keyword"> Audience Manager</span> recibido y procesado desde la fuente de datos de entrada seleccionada. </p> <p>El procesamiento de archivos fallará si el nombre de archivo tiene un formato incorrecto. Los requisitos de nombre de archivo varían en función de cómo envíe estos datos a <span class="keyword"> Audience Manager</span>. Los métodos de envío incluyen <span class="keyword"> Amazon S3</span> y FTP. Para obtener instrucciones sobre cómo asignar un nombre a los archivos, consulte: </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> Requisitos de nombre de Amazon S3 para archivos de datos de entrada </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Errores de formato</b> </p> </td> 
   <td colname="col2"> <p>Indica el número de registros que no se procesaron correctamente porque no coinciden con los requisitos de sintaxis o formato. Consulte <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Contenido del archivo de datos de entrada: sintaxis, variables y ejemplos</a> para obtener información sobre el formato de los datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>AAM ID no válido</b> </p> </td> 
   <td colname="col2"> <p>Indica el número de formularios con formato incorrecto <span class="keyword"> Audience Manager</span> ID de usuario (UUID). Normalmente, esto indica los ID: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">No coincide con el formato esperado de 38 dígitos. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">Contener caracteres alfabéticos. Los ID solo deben ser números. </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>ID de dispositivo no válido</b> </p> </td> 
   <td colname="col2"> <p>Indica el número de ID de dispositivo globales con formato incorrecto. Consulte <a href="../reference/ids-in-aam.md">Índice de ID en el Audience Manager</a> y <a href="../features/global-data-sources.md">Fuentes de datos globales</a>  para obtener más información sobre cómo se debe dar formato a los ID de dispositivo y qué fuentes de datos globales se deben utilizar, en función del tipo de dispositivo.</p>
  <p>La sección de muestreo de errores del informe incluye información detallada sobre los ID de dispositivo no válidos, como:</p>
   <ul>
    <li>ID de la fuente de datos correspondiente al ID del dispositivo no válido;</li>
    <li>ID de dispositivo no válido;</li>
    <li>El tipo de ID de dispositivo esperado, según la fuente de datos.</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>AAM No hay coincidencias con ID de</b> </p> </td> 
   <td colname="col2"> <p>Son ID incorporados <span class="keyword"> Audience Manager</span> no puede coincidir con un ID existente. Los ID incorporados pueden tener este estado cuando <span class="keyword"> Audience Manager</span> aún no ha realizado una sincronización de ID o sigue sin poder coincidir con el ID incluso después de una sincronización. </p> <p>En el caso de ID de móviles no coincidentes, <span class="keyword"> Audience Manager</span> hará: </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">Continúe almacenando e intente sincronizar este ID. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Grabarlo como un <span class="wintitle"> Registro almacenado</span> en el informe si el ID no se puede sincronizar. </li> 
    </ul> <p>Si el archivo incorporado contiene ID móviles, puede tratar estos números un poco más a la ligera que las demás métricas. No afectarán al éxito ni a las tasas de coincidencia de los archivos posteriores. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Sin rasgo realizado</b> </p> </td> 
   <td colname="col2"> <p>Enumera los rasgos que <span class="keyword"> Audience Manager</span> no puede coincidir con un rasgo incorporado. Este podría ser el resultado de: </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">Características con formato incorrecto en el archivo de datos de entrada. Para obtener más información sobre cómo dar formato al archivo de datos, consulte <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Contenido del archivo de datos de entrada: sintaxis, variables y ejemplos</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Características que aún no se han definido en <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Porcentaje de éxito</b> </p> </td> 
   <td colname="col2"> <p>El porcentaje de registros del archivo que se almacenaron correctamente. Porcentaje de éxito = registros procesados / número de registros en un archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Registros recibidos</b> </p> </td> 
   <td colname="col2"> <p>Número total de registros recibidos. En la mayoría de los casos, este número debe coincidir con el número total de registros (líneas) del archivo de datos de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Registros almacenados</b> </p> </td> 
   <td colname="col2"> <p>Número de registros almacenados correctamente. Debido a errores de formato de archivo, es posible que algunos de los registros recibidos no estén almacenados por <span class="keyword"> Audience Manager</span>. El número de registros almacenados puede ser menor que el número de registros recibidos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Rasgos realizados totales</b> </p> </td> 
   <td colname="col2"> <p>El número de características de todos los usuarios en todos los archivos de entrada que se almacenan en la variable <span class="keyword"> Audience Manager</span> plataforma. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Total de señales no utilizadas</b> </p> </td> 
   <td colname="col2"> <p>Número total de señales no utilizadas recibidas en el informe. Este total se basa en el número total de registros almacenados correctamente. </p> <p>Consulte <a href="../reporting/dynamic-reports/unused-signals.md"> Informe de señales no utilizadas</a> para obtener más información. </p> </td> 
  </tr> 
 </tbody> 
</table>
