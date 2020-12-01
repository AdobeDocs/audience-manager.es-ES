---
description: Cada vez que se procesa un archivo de servidor a servidor entrante, se envía un recibo por correo electrónico a las soluciones de socios y, si se configura, al socio.
seo-description: Cada vez que se procesa un archivo de servidor a servidor entrante, se envía un recibo por correo electrónico a las soluciones de socios y, si se configura, al socio.
seo-title: Mensaje de muestra a los socios después del procesamiento entrante
solution: Audience Manager
title: Mensaje de muestra a los socios después del procesamiento entrante
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 3%

---


# Mensaje de muestra a los socios después del procesamiento entrante{#sample-message-to-partners-after-inbound-processing}

Cada vez que se procesa un archivo [!UICONTROL Server-to-Server] entrante, se envía un recibo por correo electrónico a las soluciones de socios y, si se configura, al socio.

<!-- r_inbound_message.xml -->

El siguiente ejemplo es un mensaje de correo electrónico de ejemplo. En la tabla que aparece debajo del mensaje se describen las distintas líneas del mensaje.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Desde: aam-noreply@adobe.com  </b> </p> <p> <b>Asunto: Resultado de procesamiento de servidor a servidor de Adobe Audience Manager:</b> </p> <p> <b>Estimado socio Adobe: (ID:7)</b> <b></b> </p> <p> <b>Hemos recibido su envío de archivos de servidor a servidor de Adobe Audience Manager</b> </p> <p> <b>Nombre del archivo:</b> <i></i> </p> <p> <b> s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b><i> </i></p> <p> <b> s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b><i> </i></p> <p> <b>Registros recibidos: 40669900</b> </p> <p><b>Errores de formato: 0</b> </p> <p> <b>ID de AAM no válido: 112  </b> </p> <p> <b>Sin ID de AAM coincidente: 0  </b> </p> <p> <b>No se ha realizado ninguna característica: 26730823  </b> </p> <p> <b>Registros procesados: 40669900  </b> </p> <p> <b>Registros almacenados: 13938958  </b> </p> <p> <b>Total de dispositivos: 21  </b> </p> <p> <b>Señales totales: 918878926  </b> </p> <p> <b>Total de señales no utilizadas: 660348376  </b> </p> <p> <b>Características totales realizadas: 258086908  </b> </p> <p> <b>Características totales eliminadas: 0  </b> </p> <p> <b>Error de validación de características totales: 0  </b> </p> <p> <b>Número total de usuarios con características que no pudieron validarse: 0  </b> </p> <p> <b>Tiempo de inicio del trabajo: 2018-05-17 18:07:49  </b> </p> <p> <b>Hora de finalización del trabajo: 2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

La siguiente tabla contiene las filas correspondientes a las líneas del mensaje de correo electrónico recibido.

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Líneas </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nombre del archivo </td> 
   <td colname="col2"> <p>Lista de todos los archivos de entrada que Adobe recibió para este socio que se procesaron juntos. En el mensaje de correo electrónico de ejemplo anterior, el ID del socio es 7 y el ID del propietario de los datos es 901. </p> <p>El número de cola (1,2,3...) es el número de división añadido por el cliente o por el distribuidor entrante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros recibidos </td> 
   <td colname="col2"> <p>Número total de Adobes de registros recibidos en todos los archivos. En la mayoría de los casos, debe ser el número total de líneas en los archivos de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errores de formato </td> 
   <td colname="col2"> <p>Número de líneas que no coinciden con el formato esperado. Estas líneas no eran reconocibles por el trabajo entrante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de AAM no válido </td> 
   <td colname="col2"> <p>Número de UUID de Audience Manager que no coinciden con el formato de 38 dígitos esperado. O bien, los UUID de Audience Manager enviados en el archivo no son números. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sin ID de AAM coincidente </td> 
   <td colname="col2"> <p>Número total de usuarios para los que el Audience Manager no encontró un UUID coincidente. Estos archivos no se han sincronizado con ID, por lo que el Audience Manager no puede buscar el UUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> No se ha realizado ninguna característica </td> 
   <td colname="col2"> <p>Número de registros en los que ninguna de las señales de la línea se asigna a una característica de Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros procesados </td> 
   <td colname="col2"> <p>Número total de registros procesados por el Audience Manager. En la mayoría de los casos, este número debe ser el mismo que "Registros recibidos". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros almacenados </td> 
   <td colname="col2"> <p>Número de registros que resultan en que los datos se carguen en el sistema = Registros procesados - Errores de formato - ID de AAM no válidos - ID de AAM no coincidentes - No se ha realizado ninguna característica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dispositivos totales </td> 
   <td colname="col2"> <p>Número de dispositivos para los que se cargaron datos en el sistema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Señales totales </td> 
   <td colname="col2"> <p> Número total de señales para todos los usuarios en todos los archivos de entrada (número total de pares clave/valor en los registros procesados). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de señales no utilizadas </td> 
   <td colname="col2"> <p>Número total de señales no utilizadas para todos los usuarios en todos los archivos de entrada (pares clave/valor que no se asignaron a características de Audience Manager). En la mayoría de los casos, esto significa que el Audience Manager no tiene reglas definidas para la señal. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Características totales realizadas </td> 
   <td colname="col2"> <p>Número de características de Audience Manager para todos los usuarios en todos los archivos de entrada según las señales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de características eliminadas </td> 
   <td colname="col2"> <p> Número total de características eliminadas para todos los usuarios en todos los archivos de entrada. Para sincronizaciones completas, esto sucede si el usuario tenía la característica en una ejecución anterior pero no en la ejecución actual. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de características con error en la validación </td> 
   <td colname="col2"> <p>Representa el número de características que no pertenecen al origen de datos declarado en el nombre del archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Número total de usuarios con características que no superaron la validación </td> 
   <td colname="col2"> <p>Número de registros que tienen características que no se pudieron validar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tiempo de inicio del trabajo </td> 
   <td colname="col2"> <p>La hora a la que inicio el trabajo entrante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de finalización del trabajo </td> 
   <td colname="col2"> <p>Hora a la que finaliza el trabajo entrante. </p> </td> 
  </tr> 
 </tbody> 
</table>