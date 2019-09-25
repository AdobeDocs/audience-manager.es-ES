---
description: Responde a las preguntas comunes sobre privacidad en relación con los datos, además de proporcionar soluciones para los problemas relacionados.
seo-description: Responde a las preguntas comunes sobre privacidad en relación con los datos, además de proporcionar soluciones para los problemas relacionados.
seo-title: Preguntas más frecuentes sobre privacidad y retención de datos
solution: Audience Manager
title: Preguntas más frecuentes sobre privacidad y retención de datos
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
translation-type: tm+mt
source-git-commit: 3a4f23bc853a2324a4c91c6e65b14455293a5b1b

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

Responde a las preguntas comunes sobre privacidad en relación con los datos, además de proporcionar soluciones para los problemas relacionados.

<!-- faq_privacy.xml -->

## Preguntas más frecuentes sobre privacidad {#privacy-faq}

>[!TIP]
>
>Visite el Centro de privacidad de [Adobe](https://www.adobe.com/privacy.html) para obtener más información.

**¿Cómo utiliza Audience Manager las cookies y qué cookies establece?**

See [Audience Manager Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html).

**¿Pueden los clientes de Audience Manager en EE. UU. dirigirse a usuarios en propiedades de la UE?**

Sí. Audience Manager trabaja con clientes que tienen propiedades e inventario internacionales. La UE tiene leyes estrictas de privacidad, pero Audience Manager tiene clientes que utilizan datos de origen para segmentar audiencias en Europa. Audience Manager puede admitir la segmentación a audiencias de la UE, pero es responsabilidad suya cumplir con las normativas locales de privacidad.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Preguntas frecuentes sobre la retención de datos {#data-retention-faq}

La siguiente tabla enumera los tiempos de retención para diferentes tipos de datos y sistemas de almacenamiento.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de datos, fuente o almacenamiento </th> 
   <th colname="col2" class="entry"> Período de retención de datos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Servidores back-end </p> </td> 
   <td colname="col2"> <p>120-days. </p> <p> Audience Manager elimina los datos de usuario de nuestros servidores back-end 120 días después de ver por última vez a un usuario en la plataforma Audience Manager. Si <span class="keyword"> Audience Manager</span> registra la actividad de los usuarios en este ciclo de 120 días, conservaremos estos datos durante otros 120 días. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores Edge </p> </td> 
   <td colname="col2"> <p> 14-days. </p> <p>Audience Manager elimina los datos de usuario de nuestros servidores Edge 14 días después de ver por última vez a un usuario en la plataforma de Audience Manager. Si <span class="keyword"> Audience Manager</span> registra la actividad de los usuarios en este ciclo de 14 días, conservaremos estos datos durante otros 14 días. Si el usuario vuelve a estar activo después del período de 14 días, se producirá un retraso entre la primera vista de página nueva y el momento en que el usuario podrá realizar acciones. Se tardan entre 6 y 18 horas en devolver el perfil completo al centro de Edge después de más de 14 días de inactividad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registros sin procesar </p> </td> 
   <td colname="col2"> <p>180-days (removed after 180-days of no activity). </p> <p>Raw logs are data received by an edge server via HTTP calls or from onboarded files sent in to <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ad Server Logs </p> </td> 
   <td colname="col2"> <p><b>Informes</b> </p> <p>Log files are retained for reporting purposes for up to 30 days. We do not persist unmatched logs (i.e. logs for which there is no ID sync between a visitor's ad server ID and  Audience Manager ID) in our backend storage, and matched logs stored in  Amazon S3 are retained for up to 30 days.<span class="keyword"></span><span class="keyword"></span> </p> <p><b>Archivos de registro procesables</b> </p> <p>Both matched and unmatched logs are retained for up to 30 days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM-level profiles (authenticated profiles) </p> </td> 
   <td colname="col2"> <p>The default time-to-live (TTL) interval for inactive CRM-level profiles (Customer IDs) is 24 months. Sin embargo, puede utilizar la interfaz de usuario de Audience Manager para reducir o ampliar el intervalo TTL para perfiles de nivel CRM inactivos entre un mes y 5 años. You can accomplish this when creating or editing a Cross-Device data source.</p> <p>For more information, see Data Source Settings in  Create a Cross-Device Data Source .<a href="../features/profile-merge-rules/merge-rules-start.md#settings"></a></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile Device IDs </p> </td> 
   <td colname="col2"> <p>Las condiciones de retención para los ID de dispositivos móviles (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) siguen a la cadencia descrita en las dos primeras filas, servidores back-end y servidores Edge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Customer Data Feeds (CDF) </p> </td> 
   <td colname="col2"> <p>A CDF file contains the same data that an  Audience Manager event call (/event) sends to our servers. <span class="keyword"></span> El período de retención es de 8 días. Para obtener más información sobre CDF, consulte <a href="../features/cdf-files.md"> CDF Intro</a> y <a href="../faq/faq-cdf.md"> CDF FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Asignaciones entre ID sincronizados </p> </td> 
   <td colname="col2"> <p>The lifespan of the  ID mappings between Audience Manager cookie IDs (Audience Manager Unique User IDs or AAM UUIDs) and 3rd party cookie IDs is limited to 120 days. <a href="../features/administration/usage-limits.md#id-mapping-limits"></a><a href="../reference/ids-in-aam.md"></a> La duración de la asignación de ID se restablece cada vez que se ve la cookie de Audience Manager en la red de Audience Manager. La sincronización de asignación de ID más reciente se conservará durante toda la vida del ID de usuario único de <a href="../reference/ids-in-aam.md">Audience Manager (AAM UUID)</a>asociado.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datos de entrada </p> </td> 
   <td colname="col2"> <p>Se trata de datos de entrada que se envían a <span class="keyword"> Audience Manager</span> por FTP o directamente a un directorio <span class="keyword"> Amazon S3</span> . Consulte las <a href="../faq/faq-inbound-data-ingestion.md"> Preguntas más frecuentes</a>sobre la introducción de datos de clientes entrantes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datos de salida </p> </td> 
   <td colname="col2"> <p>This is the batch data that  Audience Manager sends to third party activation partners. <span class="keyword"></span> El período de retención es de 8 días. Para obtener más información sobre los datos salientes, consulte <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> Transferencias</a>por lotes salientes. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retención de datos de calificación de características {#trait-qual}

En la tabla siguiente se enumeran las opciones de retención de cualificaciones de características.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operación de características </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eliminar una característica </p> </td> 
   <td colname="col2"> <p>Al eliminar una característica, se eliminan los datos de cualificación de características de todos los perfiles de usuario que ya habían cumplido los requisitos para la característica en el pasado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Límite de características alcanzado </p> </td> 
   <td colname="col2"> <p>Imponemos un límite de 100.000 cualificaciones por cada perfil de usuario. El límite se aplica a perfiles autenticados y perfiles de dispositivo. Si un perfil de usuario alcanza este límite, se eliminarán las cualificaciones de rasgos más antiguas, según la primera entrada y la primera salida. </p> <p>Para obtener más información, lea nuestro <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"> Límite</a>de calificación de características. </p> </td> 
  </tr> 
 </tbody> 
</table>

