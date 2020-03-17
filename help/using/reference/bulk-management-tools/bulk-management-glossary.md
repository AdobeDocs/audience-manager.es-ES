---
description: Etiquetas de encabezado de columna definidas.
seo-description: Etiquetas de encabezado de columna definidas.
seo-title: Glosario de herramientas de administración masiva
solution: Audience Manager
title: Glosario de herramientas de administración masiva
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
translation-type: tm+mt
source-git-commit: 8cc3d9d629536c48b7013ffede16c0b112704c89

---


# Glosario de herramientas de administración masiva{#bulk-management-tools-glossary}

Etiquetas de encabezado de columna definidas.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[Los permisos](../../features/administration/administration-overview.md) de grupo RBAC asignados en la [!DNL Audience Manager] interfaz de usuario se respetan en la [!UICONTROL Bulk Management Tools].

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
   <td colname="col2"> <p>ID de un origen <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"></a> de datos que desea devolver o asignar de forma masiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivadoSignalId</span> </p> </td> 
   <td colname="col2"> <p>ID de señal <a href="../../features/derived-signals.md"></a> derivada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> description</span> </p> </td> 
   <td colname="col2"> <p>Una descripción breve e informativa que puede dar a un objeto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>ID del <a href="../../features/destinations/destinations.md"> destino</a> que desea asignar o eliminar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>ID especial asignado a un segmento cuando se asigna a un destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>ID del segmento o la carpeta de características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> name</span> </p> </td> 
   <td colname="col2"> <p>Nombre del objeto con el que está trabajando. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> parentFolderId</span> </p> </td> 
   <td colname="col2"> <p>ID de un segmento o carpeta de características que contiene otras carpetas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>ID del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceKey</span> </p> </td> 
   <td colname="col2"> <p>Las señales son bits de datos pasados a <span class="keyword"> Audience Manager</span> en función de la actividad del usuario. Se transmiten como pares <a href="../../reference/key-value-pairs-explained.md"> clave-valor</a>. La clave de origen es una constante que no cambia. Ayuda a categorizar el valor de origen que puede cambiar. Consulte <a href="../../features/derived-signals.md"> Señales</a>derivadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>El valor de origen es una variable que se pasa como parte de un par <a href="../../reference/key-value-pairs-explained.md"></a>clave-valor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Indica cuándo se puede empezar a enviar un segmento a un destino. Utiliza el formato <tt>aaaa-mm-dd</tt> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">Clave utilizada en la señal derivada. Consulte <a href="../../features/derived-signals.md"> Señales</a>derivadas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>El valor pasado con una clave de señal derivada. Consulte <a href="../../features/derived-signals.md"> Señales</a>derivadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>ID que se pasa a un destino no basado en cookies. Para un destino basado en cookies, ésta es la clave de un par <a href="../../reference/key-value-pairs-explained.md"></a>clave-valor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule / segmentRule</span> </p> </td> 
   <td colname="col2"> <p>La característica o regla de segmento real que se utiliza para recopilar datos. Una solicitud masiva devuelve las reglas creadas en <span class="keyword"> Audience Manager</span> con el <a href="../../features/traits/about-trait-builder.md"> generador</a> de reglas de características o el <a href="../../features/segments/segment-builder.md"> generador</a>de reglas de segmentos. También puede utilizar estas herramientas para crear reglas y aplicarlas de forma masiva al actualizar un segmento o rasgo. </p> <p>Consulte también Creación o actualización de reglas de características y reglas <a href="../../reference/bulk-management-tools/bulk-rules.md"></a>de segmentos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitType</span> </p> </td> 
   <td colname="col2"> <p>Una cadena que identifica el tipo de característica. Las opciones incluyen: </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_BOARDED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>Píxel activado por DIL cuando un usuario cumple los requisitos para un segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p>La clave de un par <a href="../../reference/key-value-pairs-explained.md"></a> clave-valor que se pasa a un destino de cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>

