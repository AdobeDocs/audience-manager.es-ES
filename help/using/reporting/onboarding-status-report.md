---
description: El informe de estado de carga comprueba el éxito y las tasas de errores para procesar los registros en los archivos de fuentes de datos de entrada. Este informe muestra los datos en un gráfico de barras interactivo y proporciona métricas de resumen en forma de tabla. Además, incluye la opción de los archivos de muestra para un intervalo de tiempo fijo y muestra los errores más comunes para cada tipo de error. Este informe se encuentra en Analytics > Informe de estado de carga. Este informe también está disponible cuando se crea una fuente de datos de entrada.
seo-description: El informe de estado de carga comprueba el éxito y las tasas de errores para procesar los registros en los archivos de fuentes de datos de entrada. Este informe muestra los datos en un gráfico de barras interactivo y proporciona métricas de resumen en forma de tabla. Además, incluye la opción de los archivos de muestra para un intervalo de tiempo fijo y muestra los errores más comunes para cada tipo de error. Este informe se encuentra en Analytics > Informe de estado de carga. Este informe también está disponible cuando se crea una fuente de datos de entrada.
seo-title: Informe de estado de carga
solution: Audience Manager
title: Informe de estado de carga
uuid: 6 ca 8 a 90 a -436 b -4 fce-adf 1-48 f 3 b 96 b 3 ed 2
translation-type: tm+mt
source-git-commit: dd5c3d28097251c58e1fb095aaf4076883d1c1a1

---


# Onboarding Status Report{#onboarding-status-report-about}

El informe de estado de carga comprueba el éxito y las tasas de errores para procesar los registros en los archivos de fuentes de datos de entrada. Este informe muestra los datos en un gráfico de barras interactivo y proporciona métricas de resumen en forma de tabla. Además, incluye la opción de los archivos de muestra para un intervalo de tiempo fijo y muestra los errores más comunes para cada tipo de error. Este informe se encuentra en Analytics &gt; Informe de estado de carga. Este informe también está disponible cuando se crea una fuente de datos de entrada.

>[!NOTE]
>
>Solo los usuarios con privilegios de administrador pueden ver este informe en la interfaz de usuario de Audience Manager. Para avisar a los usuarios no administradores del estado de los archivos de entrada cargados, agregue sus correos electrónicos al informe. See [Receive E-mail Notifications](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## Onboarding Status Report: About {#onboarding-status-about}

[!UICONTROL Onboarding Status Report] Las comprobaciones de éxito y tasas de error para procesar registros en los archivos de fuentes de datos de entrada. Este informe muestra los datos en un gráfico de barras interactivo y proporciona métricas de resumen en forma de tabla. Además, incluye la opción de los archivos de muestra para un intervalo de tiempo fijo y muestra los errores más comunes para cada tipo de error. You can find this report in **[!UICONTROL Analytics > Onboarding Status Report]**. Este informe también está disponible cuando se crea una fuente de datos de entrada.

## Error Reporting and Error Sampling {#error-reporting-sampling}

Error reporting and error sampling are 2 separate features of the [!UICONTROL Onboarding Status] report.

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
   <td colname="col2"> <p>El informe de errores muestra las tasas de éxito y fracaso del número de registros procesados en una fuente de datos de entrada. Devuelve datos en un gráfico de barras apiladas y apiladas y como métricas de resumen en tablas debajo del gráfico. </p> <p>El informe de errores es automático. Se ejecuta de forma continua para todas las fuentes de datos entrantes. Devuelve datos basados en intervalos de intervalos de tiempo preestablecidos o en un intervalo de tiempo personalizado que se establece con una utilidad Calendario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Muestra de errores</b> </p> </td>
   <td colname="col2"> <p>El muestreo de errores analiza el contenido de los archivos de datos y devuelve los 10 errores más comunes para cada tipo de error. Los errores en los archivos de datos entrantes impiden que se procesen registros individuales. Utilice este informe como herramienta de solución de problemas para reducir el número de errores de archivo y mejorar las tasas de procesamiento. </p> <p>Debe activar el muestreo de errores manualmente. Se ejecuta durante 14 días desde el día de activación y, a continuación, se desactiva. Puede volver a activar el muestreo de error tras caducar el intervalo de 14 días. You activate error sampling when you <a href="../features/manage-datasources.md#create-data-source"> create an inbound data source</a> or by checking the <b><span class="uicontrol"> Error Sampling</span></b> check box from the <span class="wintitle"> Data Source Settings</span> section of an existing inbound data source. </p> <p>El muestreo de errores es un proceso exigente para los computadores. Como resultado, solo devuelve los 10 primeros errores para cada categoría de error. No está diseñado para devolver todos los errores contenidos en una fuente de datos de entrada. Estos errores son una muestra representativa de un grupo potencialmente mayor de errores similares. Revise todo el archivo de los tipos de errores que marca este informe, vuelva a formatear el archivo y envíelo nuevamente. </p> <p>See <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a> for more information about how to properly format an data file for an inbound data source. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Error Report Bar Chart {#error-report-bar-chart}

El informe de errores grafica las tasas de éxito y fracaso para el procesamiento de registros en un gráfico de barras apiladas, como se muestra en el siguiente ejemplo. El gráfico es interactivo. Al hacer clic en una barra, se muestran las métricas de resumen de ese día en una tabla debajo del gráfico.

![](assets/stacked-graph.png)

## Error Report Tables {#error-report-tables}

El informe de errores muestra los datos tabulares debajo del gráfico de barras. La tabla muestra tasas de éxito y fracaso junto con totales y porcentajes.

**Registros fallidos y fallidos**

Esta vista predeterminada muestra un recuento de frecuencia del total de registros del informe e incluye un desglose de los errores por tipo de error.

![](assets/success-failure.png)

**Totales y porcentajes**

Click **[!UICONTROL Totals & Percentages]** to see what % of your files were processed successfully.

![](assets/totals-percentages.png)

## Error Sampling Report for 14 Days {#error-reporting-14-days}

Con el muestreo de errores activo, el informe mostrará los 10 errores principales para cada tipo de error. Haga clic en un botón de tipo de error en la parte superior del informe para ver cada conjunto de datos de muestra.

>[!NOTE]
>
>El informe no resalta los errores de registro con esta versión actual. To find and fix file errors, you should review the results and compare those to the specifications in the [Inbound Data File Contents](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) documentation.

![](assets/error-samples.png)

## Receive E-mail Notifications {#receive-email-notifications}

Puede agregar las direcciones de correo electrónico de los destinatarios que desee que se le notifiquen del estado de los archivos de entrada cargados. Tenga en cuenta que puede seleccionar destinatarios diferentes para diferentes fuentes de datos.

![](assets/mail-notifications.png)

## Create an Onboarding Status Report {#create-onboard-status-report}

A [!UICONTROL Sample Error Report] returns the number records in a data source were processed successfully and how many failed. Follow these steps to generate a [!UICONTROL Sample Error Report].

<!-- 

create-onboarding-status-report.xml

 -->


1. Go to **[!UICONTROL Analytics > Onboarding Status Report]**. Busque un origen de datos o elija uno de la lista.

2. Seleccione un intervalo de fechas. Las opciones incluyen:

   * Conjunto de intervalos de informes fijos.
   * Widgets de calendario que permiten crear un intervalo de fechas personalizado.

3. Haga clic en **[!UICONTROL OK]**.

## Onboarding Status Report Terms and Definitions {#report-terms-conditions}

Guía de referencia para las etiquetas y los términos utilizados en este informe.

<table id="table_1D44A2E6B4C847848B818190DD336841"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Término </th> 
   <th colname="col2" class="entry"> Definición </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Nombre de archivo de sincronización de datos</b> </p> </td> 
   <td colname="col2"> <p>Lists files that <span class="keyword"> Audience Manager</span> received and processed from you selected inbound data source. </p> <p>El procesamiento de archivos fallará si el nombre del archivo no tiene el formato correcto. File name requirements vary depending on how you send this data to <span class="keyword"> Audience Manager</span>. Delivery methods include <span class="keyword"> Amazon S3</span> and FTP. Para obtener instrucciones sobre cómo asignar nombres a los archivos, consulte: </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> Requisitos de nombre de Amazon S3 para archivos de datos de entrada </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Errores de formato</b> </p> </td> 
   <td colname="col2"> <p>Muestra el número de registros que fallaron debido a que no coinciden con los requisitos de formato o de sintaxis. See <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a> for information on how to format your data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>ID de AAM no válido</b> </p> </td> 
   <td colname="col2"> <p>Lists the number of improperly formatted <span class="keyword"> Audience Manager</span> user IDs (UUID). Normalmente, esto indica los ID: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">No coincide con el formato esperado de 38 dígitos. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">Contener caracteres alfabéticos. Los ID deben ser números solamente. </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>ID de dispositivo no válido</b> </p> </td> 
   <td colname="col2"> <p>Muestra el número de ID de dispositivos globales con formato incorrecto. See <a href="../reference/ids-in-aam.md">Index of IDs in Audience Manager</a> and <a href="../features/global-data-sources.md">Global Data Sources</a>  for details on how device IDs should be formatted and what global data sources you should use, based on the device type.</p>
  <p>La sección de muestra de errores del informe incluye información detallada sobre los ID de dispositivo no válidos, como:</p>
   <ul>
    <li>ID de fuente de datos correspondiente al ID del dispositivo no válido;</li>
    <li>ID del dispositivo no válido;</li>
    <li>Tipo de ID del dispositivo esperado, basado en la fuente de datos.</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>No coincide con AAM ID</b> </p> </td> 
   <td colname="col2"> <p>These are onboarded IDs <span class="keyword"> Audience Manager</span> cannot match to an existing ID. Onboarded IDs can have this status when <span class="keyword"> Audience Manager</span> has not yet performed an ID sync or it still can't match the ID even after a synch. </p> <p>In the case of unmatched mobile IDs, <span class="keyword"> Audience Manager</span> will: </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">Continúe almacenando e intentando sincronizar este ID. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Record it as a <span class="wintitle"> Stored Record</span> in the report if the ID cannot be synched. </li> 
    </ul> <p>Si el archivo integrado contiene ID móviles, puede tratar estos números un poco más ligero que las demás métricas. No afectarán el éxito y las tasas de coincidencia de los archivos subsiguientes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>No se ha realizado ninguna característica</b> </p> </td> 
   <td colname="col2"> <p>Lists traits that <span class="keyword"> Audience Manager</span> cannot match to an onboarded trait. Esto podría ser el resultado de: </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">Características formateadas incorrectamente en el archivo de datos de entrada. For on how to format your data file, see <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Traits that have not yet been defined in <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Porcentaje de éxito</b> </p> </td> 
   <td colname="col2"> <p>El porcentaje de registros del archivo que se almacenó correctamente. Porcentaje de éxito = registros procesados/número de registros en un archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Registros recibidos</b> </p> </td> 
   <td colname="col2"> <p>Número total de registros recibidos. En la mayoría de los casos, este número debe coincidir con el número total de registros (líneas) del archivo de datos de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Registros almacenados</b> </p> </td> 
   <td colname="col2"> <p>Número de registros almacenados correctamente. Because of file format errors, some of the records received may not be stored by <span class="keyword"> Audience Manager</span>. El número de registros almacenados puede ser menor que el número de registros recibidos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Características totales resultantes</b> </p> </td> 
   <td colname="col2"> <p>The number of traits for all users across all inbound files that get stored in the <span class="keyword"> Audience Manager</span> platform. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Total de señales no utilizadas</b> </p> </td> 
   <td colname="col2"> <p>La cantidad total de señales no utilizadas recibidas en el informe. Este total se basa en el número total de registros almacenados correctamente. </p> <p>See <a href="../reporting/dynamic-reports/unused-signals.md"> Unused Signals Report</a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>
