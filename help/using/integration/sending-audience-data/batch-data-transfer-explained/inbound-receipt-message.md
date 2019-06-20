---
description: Cuando se procesa un archivo de servidor a servidor de entrada, se envía un recibo por correo electrónico a las soluciones de socio y, si se ha configurado, al socio.
seo-description: Cuando se procesa un archivo de servidor a servidor de entrada, se envía un recibo por correo electrónico a las soluciones de socio y, si se ha configurado, al socio.
seo-title: Mensaje de muestra a socios después del procesamiento de entrada
solution: Audience Manager
title: Mensaje de muestra a socios después del procesamiento de entrada
uuid: 69 e 3 a 8 b 3-8465-4 f 4 c -8005-8 a 9 ff 15 ae 19 a
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Sample Message to Partners after Inbound Processing{#sample-message-to-partners-after-inbound-processing}

Whenever an inbound [!UICONTROL Server-to-Server] file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.

<!-- r_inbound_message.xml -->

El siguiente ejemplo es un mensaje de correo electrónico de muestra. La tabla debajo del mensaje describe las diversas líneas del mensaje.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Desde: aam-noreply@adobe.com </b> </p> <p> <b>Asunto: Resultado de procesamiento de servidor a servidor de Adobe Audience Manager:</b> </p> <p> <b>Estimado socio de Adobe: (ID: 7)</b><b></b> </p> <p> <b>Hemos recibido su entrega de archivos de servidor a servidor de Adobe Audience Manager</b> </p> <p> <b>Nombre del archivo:</b><i></i> </p> <p> <b> s 3 n:// &lt;<i>nombre_ paquete &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806402. sync</b> </p> <p> <b> s 3 n:// &lt;<i>nombre_ paquete &gt;</i>/2018-05-16/ftp_ dpm_ 7_ 901_ 1368655202. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nombre_ paquete &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784804. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nombre_ paquete &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806403. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nombre_ paquete &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784802. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nombre_ de_ bucket &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784803. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nombre_ paquete &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806404. sync</b> </p> <p> <b>Registros recibidos: 40669900</b> </p> <p><b>Errores de formato: 0</b> </p> <p> <b>ID de AAM no válido: 112 </b> </p> <p> <b>No coincide con AAM ID: 0 </b> </p> <p> <b>Sin características obtenidas: 26730823 </b> </p> <p> <b>Registros procesados: 40669900 </b> </p> <p> <b>Registros almacenados: 13938958 </b> </p> <p> <b>Dispositivos totales: 21 </b> </p> <p> <b>Señales totales: 918878926 </b> </p> <p> <b>Total de señales no utilizadas: 660348376 </b> </p> <p> <b>Características totales obtenidas: 258086908 </b> </p> <p> <b>Total de características eliminadas: 0 </b> </p> <p> <b>Total de características erróneas de validación: 0 </b> </p> <p> <b>Usuarios totales que tienen características que han fallado la validación: 0 </b> </p> <p> <b>Hora de inicio del trabajo: 2018-05-17 18:07:49 </b> </p> <p> <b>Hora de finalización del trabajo: 2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

La siguiente tabla contiene filas correspondientes a líneas del mensaje de correo electrónico recibido.

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
   <td colname="col2"> <p>Lista de todos los archivos de entrada que Adobe recibió para este socio que se procesaron juntos. En el mensaje de correo electrónico de ejemplo anterior, el ID de socio es 7 y el ID de propietario de datos es 901. </p> <p>El número de cola (1,2,3…) es el número dividido que ha agregado el cliente o el distribuidor entrante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros recibidos </td> 
   <td colname="col2"> <p>Número total de registros recibidos por Adobe en todos los archivos. En la mayoría de los casos, debe ser el número total de líneas en archivos de entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errores de formato </td> 
   <td colname="col2"> <p>Número de líneas que no coinciden con el formato esperado. Estas líneas no eran reconocibles por el trabajo entrante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID de AAM no válido </td> 
   <td colname="col2"> <p>Número de UUID de Audience Manager que no coinciden con el formato esperado de 38 dígitos. Los UUID de Audience Manager enviados en el archivo no son números. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> No coincide con AAM ID </td> 
   <td colname="col2"> <p>La cantidad total de usuarios para los que Audience Manager no encontró un UUID coincidente. Estos archivos no se han sincronizado, por lo que Audience Manager no puede buscar el UUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> No se ha realizado ninguna característica </td> 
   <td colname="col2"> <p>Número de registros donde ninguna de las señales de la línea se asigna a un rasgo de Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros procesados </td> 
   <td colname="col2"> <p>Número total de registros procesados por Audience Manager. En la mayoría de los casos, este número debe ser el mismo que "Registros recibidos". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Registros almacenados </td> 
   <td colname="col2"> <p>Número de registros que resultan en que se carguen datos en el sistema = Registros procesados - Errores de formato - ID de AAM no válidos - No coincide con AAM ID - Sin características obtenidas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dispositivos totales </td> 
   <td colname="col2"> <p>Número de dispositivos para los que se cargaron datos en el sistema. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de señales </td> 
   <td colname="col2"> <p> Número total de señales para todos los usuarios en todos los archivos de entrada (número total de pares clave/valor en los registros procesados). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de señales no utilizadas </td> 
   <td colname="col2"> <p>Número total de señal no utilizada para todos los usuarios en todos los archivos de entrada (pares clave/valor que no se asignaron a características de Audience Manager). En la mayoría de los casos, esto significa que Audience Manager no tiene reglas definidas para la señal. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Características totales obtenidas </td> 
   <td colname="col2"> <p>Número de características de Audience Manager para todos los usuarios en todos los archivos de entrada en función de las señales. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de características eliminadas </td> 
   <td colname="col2"> <p> La cantidad total de características eliminadas para todos los usuarios en todos los archivos de entrada. Para las sincronizaciones completas, esto sucede si el usuario tuvo la característica en una ejecución anterior pero no en la ejecución actual. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total de características erróneas de validación </td> 
   <td colname="col2"> <p>Representa el número de características que no pertenecen al origen de datos declarado en el nombre del archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usuarios totales que tienen características que han fallado la validación </td> 
   <td colname="col2"> <p>Número de registros que tuvieron características que no se validaron. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de inicio del trabajo </td> 
   <td colname="col2"> <p>Hora en que empieza el trabajo entrante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de finalización del trabajo </td> 
   <td colname="col2"> <p>Hora de finalización del trabajo de entrada. </p> </td> 
  </tr> 
 </tbody> 
</table>