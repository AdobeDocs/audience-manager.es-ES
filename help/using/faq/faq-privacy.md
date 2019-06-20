---
description: Responde a las preguntas comunes sobre privacidad en relación con los datos, además de proporcionar soluciones para los problemas relacionados.
seo-description: Responde a las preguntas comunes sobre privacidad en relación con los datos, además de proporcionar soluciones para los problemas relacionados.
seo-title: Preguntas frecuentes sobre retención de datos y privacidad
solution: Audience Manager
title: Preguntas frecuentes sobre retención de datos y privacidad
uuid: ef 558 fca -35 ff -44 f 1-8527-f 8 bee 9 f 2 c 7 e 9
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

Responde a las preguntas comunes sobre privacidad en relación con los datos, además de proporcionar soluciones para los problemas relacionados.

<!-- faq_privacy.xml -->

## Privacy FAQ {#privacy-faq}

>[!TIP]
>
>Visit the [Adobe Privacy Center](https://www.adobe.com/privacy.html) for more information.

**¿Cómo utiliza Audience Manager las cookies y las cookies que se establecen?**

See [Audience Manager Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html).

**¿Pueden los clientes de Audience Manager en los Estados Unidos centrarse en las propiedades de la UE?**

Sí. Audience Manager funciona con clientes que tienen propiedades e inventario internacionales. La UE tiene estrictas leyes de privacidad, pero Audience Manager tiene clientes que utilizan datos de origen para segmentación de audiencia en Europa. Audience Manager puede admitir la segmentación a audiencias de la UE, pero es su responsabilidad cumplir con las normativas de privacidad local.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Preguntas frecuentes sobre la retención de datos {#data-retention-faq}

En la tabla siguiente se muestran los tiempos de retención para diferentes tipos de datos y sistemas de almacenamiento.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de datos, Fuente o Almacenamiento </th> 
   <th colname="col2" class="entry"> Período de retención de datos </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Servidores back-end </p> </td> 
   <td colname="col2"> <p>120 días. </p> <p> Audience Manager elimina los datos de usuario de nuestros servidores back-end 120 días después de ver el último usuario en la plataforma de Audience Manager. If <span class="keyword"> Audience Manager</span> records user activity within this 120-day cycle, we will keep this data for another 120-days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores Edge </p> </td> 
   <td colname="col2"> <p> 14 días. </p> <p>Audience Manager elimina los datos de usuario de nuestros servidores Edge 14 días después de ver un usuario en la plataforma de Audience Manager. If <span class="keyword"> Audience Manager</span> records user activity in within this 14-day cycle, we will keep this data for another 14-days. Si el usuario vuelve a activarse después del período de 14 días, habrá un retraso entre la primera vista de página nueva y cuando el usuario pasa a ser procesable. Se tarda entre 6 y 18 horas en volver a colocar el perfil completo en el centro tras más de 14 días de inactividad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registros sin procesar </p> </td> 
   <td colname="col2"> <p>180 días (se eliminan después de 180 días sin actividad). </p> <p>Raw logs are data received by an edge server via HTTP calls or from onboarded files sent in to <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registros de servidor de publicidad </p> </td> 
   <td colname="col2"> <p><b>Informes</b> </p> <p>Los archivos de registro se conservan con fines de informes durante un máximo de 30 días. We do not persist unmatched logs (i.e. logs for which there is no ID sync between a visitor's ad server ID and <span class="keyword"> Audience Manager</span> ID) in our backend storage, and matched logs stored in <span class="keyword"> Amazon S3</span> are retained for up to 30 days. </p> <p><b>Archivos de registro procesables</b> </p> <p>Los registros que coincidan y los que no coinciden se conservan durante 30 días. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Perfiles de nivel CRM (perfiles autenticados) </p> </td> 
   <td colname="col2"> <p>El intervalo predeterminado de tiempo a vida (TTL) de perfiles inactivos de nivel CRM (ID de cliente) es de 24 meses. Sin embargo, puede utilizar la interfaz de usuario de Audience Manager para reducir o ampliar el intervalo de TTL de perfiles inactivos de nivel CRM entre un mes y 5 años. Puede hacerlo al crear o editar una fuente de datos entre dispositivos.</p> <p>For more information, see Data Source Settings in <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de dispositivos móviles </p> </td> 
   <td colname="col2"> <p>The retention conditions for mobile device IDs (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) follow the cadence described in the first two rows, back-end servers and edge servers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fuentes de datos de clientes (CDF) </p> </td> 
   <td colname="col2"> <p>A CDF file contains the same data that an <span class="keyword"> Audience Manager</span> event call (/event) sends to our servers. El período de retención es de 8 días. For more details about CDF, please refer to <a href="../features/cdf-files.md"> CDF Intro</a> and <a href="../faq/faq-cdf.md"> CDF FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Asignaciones entre ID sincronizados </p> </td> 
   <td colname="col2"> <p>Mappings between synchronized IDs may be kept for the life of the associated <a href="../reference/ids-in-aam.md"> Audience Manager Unique User ID (AAM UUID)</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datos de entrada </p> </td> 
   <td colname="col2"> <p>This is inbound data you send to <span class="keyword"> Audience Manager</span> by FTP or directly to an <span class="keyword"> Amazon S3</span> directory. See the <a href="../faq/faq-inbound-data-ingestion.md"> Inbound Customer Data Ingestion FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datos salientes </p> </td> 
   <td colname="col2"> <p>This is the batch data that <span class="keyword"> Audience Manager</span> sends to third party activation partners. El período de retención es de 8 días. For more details about Outbound data, please refer to <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> Outbound Batch Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait Qualification Data Retention {#trait-qual}

La tabla siguiente enumera las opciones de retención para las calificaciones de características.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operación de características </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eliminar un rasgo </p> </td> 
   <td colname="col2"> <p>Al eliminar una característica, se eliminan los datos de cualificación de características de todos los perfiles de usuario que se califican para la característica pasada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Límite alcanzado </p> </td> 
   <td colname="col2"> <p>Se impone un límite de 100 000 cualificaciones de características para cada perfil de usuario. El límite se aplica a perfiles autenticados y perfiles de dispositivo. Si un perfil de usuario alcanza este límite, eliminaremos las calificaciones de características más antiguas, por primera vez. </p> <p>For more details, read our <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"> Trait Qualification Limit</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

