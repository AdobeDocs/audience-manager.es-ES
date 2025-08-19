---
description: Cada vez que se procesa un archivo entrante de servidor a servidor, se envía una confirmación por correo electrónico a las soluciones de socios y, si se configura, al socio.
seo-description: Whenever an inbound Server-to-Server file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.
seo-title: Sample Message to Partners after Inbound Processing
solution: Audience Manager
title: Mensaje de muestra a los socios después del procesamiento entrante
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Inbound Data Transfers
exl-id: acfc788f-63e6-445f-a086-0a2cc6c8865b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 0%

---

# Mensaje de muestra a los socios después del procesamiento entrante{#sample-message-to-partners-after-inbound-processing}

Cada vez que se procesa un archivo [!UICONTROL Server-to-Server] entrante, se envía una confirmación por correo electrónico a las soluciones del socio y, si se configura, al socio.

<!-- r_inbound_message.xml -->

El siguiente ejemplo es un mensaje de correo electrónico de ejemplo. La tabla debajo del mensaje describe las distintas líneas del mensaje.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>De: aam-noreply@adobe.com </b> </p> <p> <b>Asunto: Resultado Del Procesamiento Servidor A Servidor De Adobe Audience Manager:</b> </p> <p> <b>Estimado socio de Adobe: (ID:7)</b> <b></b> </p> <p> <b>Hemos recibido su envío de archivos de servidor a servidor de Adobe Audience Manager</b> </p> <p> <b>Nombre de archivo:</b> <i></i> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b> </p> <p> <b>Registros recibidos: 40669900</b> </p> <p><b>Errores de formato: 0</b> </p> <p> <b>ID de AAM no válido: 112 </b> </p> <p> <b>No hay ninguna AAM que coincida con el ID: 0 </b> </p> <p> <b>Ningún rasgo realizado: 26730823 </b> </p> <p> <b>Registros procesados: 40669900 </b> </p> <p> <b>Registros almacenados: 13938958 </b> </p> <p> <b>Total de dispositivos: 21 </b> </p> <p> <b>Señales totales: 918878926 </b> </p> <p> <b>Total de señales no utilizadas: 660348376 </b> </p> <p> <b>Rasgos totales realizados: 258086908 </b> </p> <p> <b>Total de rasgos eliminados: 0 </b> </p> <p> <b>Error en la validación del total de rasgos: 0 </b> </p> <p> <b>Usuarios totales que tienen características con error de validación: 0 </b> </p> <p> <b>Hora de inicio del trabajo: 17-05-2018 18:07:49 </b> </p> <p> <b>Hora de finalización del trabajo: 17-05-2018 18:45:02</b> </p> </td> 
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
   <td colname="col1"> Nombre de archivo </td> 
   <td colname="col2"> <p>Lista de todos los archivos entrantes que Adobe recibió para este socio y que se procesaron juntos. En el mensaje de correo electrónico de ejemplo anterior, el ID del socio es 7 y el ID del propietario de datos es 901. </p> <p>El número de cola (1,2,3...) es el número de división añadido por el cliente o por el distribuidor entrante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros recibidos </td> 
   <td colname="col2"> <p>Número total de registros recibidos por Adobe en todos los archivos. En la mayoría de los casos, este debe ser el número total de líneas en los archivos de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errores de formato </td> 
   <td colname="col2"> <p>Número de líneas que no coinciden con el formato esperado. Estas líneas no eran reconocibles por el trabajo entrante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de AAM no válido </td> 
   <td colname="col2"> <p>Número de UUID de Audience Manager que no coinciden con el formato esperado de 38 dígitos. O los UUID de Audience Manager enviados en el archivo no son números. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> No hay AAM ID coincidente </td> 
   <td colname="col2"> <p>Número total de usuarios para los que Audience Manager no ha podido encontrar un UUID coincidente. Estos archivos no se han sincronizado con el ID, por lo que Audience Manager no puede buscar el UUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sin rasgo realizado </td> 
   <td colname="col2"> <p>Número de registros en los que ninguna de las señales de la línea se asigna a un rasgo de Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros procesados </td> 
   <td colname="col2"> <p>Número total de registros procesados por Audience Manager. En la mayoría de los casos, este número debe ser el mismo que "Registros recibidos". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros almacenados </td> 
   <td colname="col2"> <p>Número de registros que hacen que se carguen datos en el sistema = Registros procesados - Errores de formato - ID de AAM no válidos - Sin ID de AAM coincidente - Sin rasgo realizado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de dispositivos </td> 
   <td colname="col2"> <p>Número de dispositivos para los que se cargaron datos en el sistema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Señales totales </td> 
   <td colname="col2"> <p> Número total de señales para todos los usuarios en todos los archivos de entrada (número total de pares clave/valor en los registros procesados). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de señales no utilizadas </td> 
   <td colname="col2"> <p>Número total de señales no utilizadas para todos los usuarios en todos los archivos de entrada (pares clave/valor que no se asignaron a características de Audience Manager). En la mayoría de los casos, esto significa que Audience Manager no tiene reglas definidas para la señal. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Características totales realizadas </td> 
   <td colname="col2"> <p>Número de rasgos de Audience Manager para todos los usuarios en todos los archivos de entrada en función de las señales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de rasgos eliminados </td> 
   <td colname="col2"> <p> Número total de rasgos eliminados para todos los usuarios en todos los archivos de entrada. Para las sincronizaciones completas, esto sucede si el usuario tenía el rasgo en una ejecución anterior pero no en la ejecución actual. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Validación de rasgos totales fallida </td> 
   <td colname="col2"> <p>Representa el número de características que no pertenecen al origen de datos declarado en el nombre del archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de usuarios con rasgos que no superaron la validación </td> 
   <td colname="col2"> <p>El número de registros con características que no superaron la validación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de inicio del trabajo </td> 
   <td colname="col2"> <p>Hora a la que se inicia el trabajo entrante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de finalización del trabajo </td> 
   <td colname="col2"> <p>Hora a la que finaliza el trabajo entrante. </p> </td> 
  </tr> 
 </tbody> 
</table>
