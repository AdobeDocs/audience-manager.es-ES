---
description: Responde a las preguntas comunes sobre privacidad en relación con los datos, además de proporcionar soluciones para los problemas relacionados.
seo-description: Answers to common privacy- and data-related questions or issues.
seo-title: Privacy and Data Retention FAQ
solution: Audience Manager
title: Preguntas frecuentes sobre la privacidad y retención de datos
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
feature: Data Governance & Privacy
exl-id: bccf49d7-1a3b-4286-86fb-59e472af4501
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 83%

---

# Preguntas frecuentes sobre la privacidad y retención de datos{#privacy-and-data-retention-faq}

Responde a las preguntas comunes sobre privacidad en relación con los datos, además de proporcionar soluciones para los problemas relacionados.

<!-- faq_privacy.xml -->

## Preguntas frecuentes sobre privacidad {#privacy-faq}

>[!TIP]
>
>Visite el [Centro de privacidad de Adobe](https://www.adobe.com/es/privacy.html) para obtener más información.

**¿Cómo utiliza Audience Manager las cookies y qué cookies establece?**

Consulte [Cookies de Audience Manager](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html).

**¿Pueden los clientes de Audience Manager de EE. UU. segmentar campañas para usuarios de la UE?**

Sí. Audience Manager trabaja con clientes que tienen propiedades e inventarios en todo el mundo. La UE tiene leyes estrictas de privacidad, pero Audience Manager tiene clientes que utilizan datos de origen para segmentar audiencias en Europa. Audience Manager puede permitir segmentar audiencias de la UE, pero es responsabilidad del cliente cumplir con las normas locales de privacidad.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Preguntas frecuentes sobre la retención de datos {#data-retention-faq}

La siguiente tabla incluye los tiempos de retención para diferentes tipos de datos y sistemas de almacenamiento.

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
   <td colname="col2"> <p>120 días </p> <p> Audience Manager elimina los datos de usuario de nuestros servidores back-end 120 días después de ver por última vez a un usuario en la plataforma de Audience Manager. If <span class="keyword"> Audience Manager</span> registra la actividad del usuario dentro de este ciclo de 120 días, conservaremos estos datos durante otros 120 días más. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servidores Edge </p> </td> 
   <td colname="col2"> <p> 14 días </p> <p>Audience Manager elimina los datos de usuarios de nuestros servidores Edge 14 días después de ver por última vez a un usuario en la plataforma de Audience Manager. If <span class="keyword"> Audience Manager</span> registra la actividad de los usuarios en este ciclo de 14 días, y conservaremos estos datos durante otros 14 días más. Si el usuario vuelve a estar activo después del ciclo de 14 días, se producirá un retraso entre la primera vista de página nueva y el momento en que el usuario podrá realizar acciones. Se tardan entre 6 y 18 horas en devolver el perfil completo al centro de Edge después de más de 14 días de inactividad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registros sin procesar </p> </td> 
   <td colname="col2"> <p>60 días (se eliminan después de 60 días sin actividad) </p> <p>Los registros sin procesar son datos recibidos por un servidor Edge a través de llamadas HTTP o desde archivos incorporados enviados a <span class="keyword">Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registros del servidor de publicidad </p> </td> 
   <td colname="col2"> <p><b>Informes</b> </p> <p>Los archivos de registro se conservan con fines de creación de informes durante un máximo de 30 días. No conservamos los registros no coincidentes (es decir, los registros para los que no hay sincronización de ID entre el ID de servidor de anuncios de un visitante y el ID de <span class="keyword">Audience Manager</span>) en nuestro almacenamiento de back-end. Los registros coincidentes almacenados en <span class="keyword">Amazon S3</span> se conservan durante un máximo de 30 días. </p> <p><b>Archivos de registro procesables</b> </p> <p>Los registros coincidentes y no coincidentes se conservan durante un máximo de 30 días. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Perfiles de nivel CRM (perfiles autenticados) </p> </td> 
   <td colname="col2"> <p>El intervalo predeterminado de tiempo de vida (TTL) para perfiles inactivos de nivel CRM (ID de cliente) es de 24 meses. Sin embargo, puede utilizar la interfaz de usuario de Audience Manager para reducir o ampliar el intervalo TTL para perfiles inactivos de nivel CRM entre un mes y 5 años. Esto se puede lograr al crear o editar una fuente de datos entre dispositivos.</p> <p>Para obtener más información, consulte Configuración de fuentes de datos en <a href="../features/profile-merge-rules/merge-rules-start.md#settings">Crear una fuente de datos entre dispositivos </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de dispositivos móviles </p> </td> 
   <td colname="col2"> <p>Las condiciones de retención para los ID de dispositivos móviles (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) siguen la cadencia descrita en las dos primeras filas, servidores back-end y servidores Edge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fuentes de datos del cliente (CDF) </p> </td> 
   <td colname="col2"> <p>Un archivo CDF contiene los mismos datos que los que se envían a nuestros servidores en una llamada de evento de <span class="keyword">Audience Manager</span> (/event). El período de retención es de 8 días. Para obtener más información sobre CDF, consulte <a href="../features/cdf-files.md"> Introducción a CDF</a> y <a href="../faq/faq-cdf.md">Preguntas frecuentes sobre CDF</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Asignaciones entre ID sincronizados </p> </td> 
   <td colname="col2"> <p>El periodo de conservación de las <a href="../features/administration/usage-limits.md#id-mapping-limits">asignaciones de ID</a> entre los ID de cookies de Audience Manager (<a href="../reference/ids-in-aam.md">ID de usuario único de Audience Manager o UUID de AAM</a>) y los ID de cookies de terceros está limitado a 120 días. La duración de la asignación de ID se restablece cada vez que aparezca la cookie de Audience Manager en la red de Audience Manager. La sincronización de asignación de ID más reciente se conservará durante toda la vida del <a href="../reference/ids-in-aam.md">ID de usuario único de Audience Manager (UUID de AAM)</a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datos de entrada </p> </td> 
   <td colname="col2"> <p>Se trata de datos de entrada que se envían a <span class="keyword">Audience Manager</span> por FTP o directamente a un directorio de <span class="keyword">Amazon S3</span>. Consulte las <a href="../faq/faq-inbound-data-ingestion.md">Preguntas frecuentes sobre la ingestión de datos de clientes entrantes</a>.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datos salientes </p> </td> 
   <td colname="col2"> <p>Estos son los datos en lote que <span class="keyword">Audience Manager</span> envía a los socios de activación. El período de retención es de 8 días. Para obtener más información sobre los datos salientes, consulte <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md">Transferencias de lotes salientes</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retención de datos de clasificación de rasgos {#trait-qual}

En la tabla siguiente se incluyen las opciones de retención para las clasificaciones de rasgos.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operación de rasgos </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eliminación de rasgos </p> </td> 
   <td colname="col2"> <p>Al eliminar un rasgo, se eliminan los datos de clasificación de todos los perfiles de usuario que hayan cumplido los requisitos para este rasgo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Límite de rasgos alcanzado </p> </td> 
   <td colname="col2"> <p>Imponemos un límite de 100 000 clasificaciones por cada perfil de usuario. El límite se aplica a perfiles autenticados y perfiles de dispositivos. Si un perfil de usuario alcanza este límite, eliminaremos las clasificaciones de rasgos más antiguas, según el primer ingreso y el primer envío. </p> <p>Para obtener más información, consulte <a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit">Límite de clasificación de rasgos</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
