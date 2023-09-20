---
description: Etiquetas de encabezado de columna definidas.
seo-description: Column header labels defined.
seo-title: Bulk Management Tools Glossary
solution: Audience Manager
title: Glosario de herramientas de administración masiva
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: BAAAM
exl-id: 036d16c7-1546-4539-a318-455b98e10026
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 4%

---

# Glosario de herramientas de administración masiva{#bulk-management-tools-glossary}

Etiquetas de encabezado de columna definidas.

>[!IMPORTANT]
>
>Las herramientas de administración masiva no son una oferta de Adobe oficialmente admitida. La resolución de problemas y la asistencia técnica a través del Servicio de atención al cliente se gestionarán caso por caso.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[Permisos de grupo de RBAC](../../features/administration/administration-overview.md) asignado en el [!DNL Audience Manager] Las IU se respetan en la [!UICONTROL Bulk Management Tools].

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Encabezado de columna </th> 
   <th colname="col2" class="entry"> Definición </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> dataSourceId</span> </p> </td> 
   <td colname="col2"> <p>El ID de un <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> fuente de datos</a> desea devolver o asignar de forma masiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivatedSignalId</span> </p> </td> 
   <td colname="col2"> <p>A <a href="../../features/derived-signals.md"> señal derivada</a> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> description</span> </p> </td> 
   <td colname="col2"> <p>Descripción breve e informativa que se puede proporcionar a un objeto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>El ID del <a href="../../features/destinations/destinations.md"> destino</a> desea asignar o eliminar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>ID especial asignado a un segmento cuando se asigna a un destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>El ID de su carpeta de segmentos o rasgos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> name</span> </p> </td> 
   <td colname="col2"> <p>El nombre del objeto con el que está trabajando. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> parentFolderId</span> </p> </td> 
   <td colname="col2"> <p>El ID de una carpeta de segmentos o rasgos que contiene otras carpetas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>ID del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceKey</span> </p> </td> 
   <td colname="col2"> <p>Las señales son bits de datos que se pasan a <span class="keyword"> Audience Manager</span> según la actividad del usuario. Se transmiten como <a href="../../reference/key-value-pairs-explained.md"> pares clave-valor</a>. La clave de origen es una constante que no cambia. Ayuda a categorizar el valor de origen que puede cambiar. Consulte <a href="../../features/derived-signals.md"> Señales derivadas</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>El valor de origen es una variable que se pasa como parte a <a href="../../reference/key-value-pairs-explained.md"> par clave-valor</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Indica cuándo puede comenzar a enviarse un segmento a un destino. Usos <i>aaaa-mm-dd</i> formato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">La clave utilizada en la señal derivada. Consulte <a href="../../features/derived-signals.md"> Señales derivadas</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>El valor pasado con una clave de señal derivada. Consulte <a href="../../features/derived-signals.md"> Señales derivadas</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>ID transferido a un destino no basado en cookies. Para un destino basado en cookies, esta es la clave en un <a href="../../reference/key-value-pairs-explained.md"> par clave-valor</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule / segmentRule</span> </p> </td> 
   <td colname="col2"> <p>Rasgo real o regla de segmento utilizada para recopilar datos. Una solicitud masiva devuelve las reglas creadas en <span class="keyword"> Audience Manager</span> con el <a href="../../features/traits/about-trait-builder.md"> generador de reglas de rasgos</a> o el <a href="../../features/segments/segment-builder.md"> generador de reglas de segmentos</a>. También puede utilizar estas herramientas para crear reglas y aplicarlas por lotes al actualizar un segmento o característica. </p> <p>Consulte también. <a href="../../reference/bulk-management-tools/bulk-rules.md"> Creación o actualización de reglas de rasgos y reglas de segmentos</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitType</span> </p> </td> 
   <td colname="col2"> <p>Una cadena que identifica el tipo de rasgo. Las opciones incluyen: </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_BOARDED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>Píxel activado por el DIL cuando un usuario cumple los requisitos para un segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p>La clave de un <a href="../../reference/key-value-pairs-explained.md"> par clave-valor</a> pasado a un destino de cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>
