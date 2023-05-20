---
description: Describe los pasos y las funciones de configuración específicos del proceso de creación de rasgos basado en reglas e incorporado.
keywords: crear característica;crear característica
seo-description: Describes set up steps and features specific to the rules-based and onboarded trait creation process.
seo-title: Create Rules-Based or Onboarded Traits
solution: Audience Manager
title: Crear rasgos basados en normas o integrados
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
exl-id: cad318ee-93b2-4afa-8a2f-a67b068eec0a
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 7%

---

# Cree[!UICONTROL Rules-Based] o [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Describe los pasos y características de la configuración específicos de [!UICONTROL rules-based] y [!UICONTROL onboarded] proceso de creación de rasgos.

<!-- c_tb_rules_traits.xml -->

## Información básica sobre características {#basics}

Entrada [!UICONTROL Trait Builder], el [!UICONTROL Basic Information] La configuración de permite crear o editar elementos nuevos o existentes [!UICONTROL traits]. El [!UICONTROL Basic Information] La configuración es la misma para [!UICONTROL rules-based], [!UICONTROL onboarded] y [!UICONTROL algorithmic traits]. Para crear un nuevo [!UICONTROL trait], proporcione un nombre (evite los caracteres especiales), [!UICONTROL data source]y seleccione una [!UICONTROL storage folder]. Otros [!UICONTROL Basic Information] Los campos de son opcionales.

<!-- c_tb_basics.xml -->

![create-trait](assets/create-trait.png)

### Campos de información básica definidos

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento de interfaz </th> 
   <th colname="col2" class="entry"> Explicación </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Nombre</span></b> </td> 
   <td colname="col2"> <p>El nombre del rasgo. Requerido. </p> <p>Longitud máxima: 255 caracteres. </p> <p> <p>Nota: Al nombrar las características, evite estos caracteres especiales: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Comas </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Guiones </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Guiones </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Fichas </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Símbolo de barra vertical o barra vertical </li> 
      </ul> </p> </p> <p>Esto ayuda a reducir los errores de procesamiento al configurar una <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> transferencia de archivos de datos entrantes</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Descripción</span></b> </td> 
   <td colname="col2"> Unas pocas palabras para ayudar a describir el propósito o la función del rasgo. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Fuente de datos</span></b> </td> 
   <td colname="col2"> Asocia el rasgo a un proveedor de datos específico. Requerido. <p>Utilice el primer menú desplegable para filtrar entre fuentes de datos del Audience Manager, grupos de informes de Adobe Analytics o ambos. A continuación, utilice el segundo menú desplegable para elegir la fuente de datos.</p><p> Si no utiliza grupos de informes de Adobe Analytics, el selector de tipo de fuente de datos está desactivado y solo tiene valores predeterminados de fuentes de datos de Audience Manager.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Tipo de evento</span></b> </td> 
   <td colname="col2"> Asigna el rasgo a un tipo o categoría, normalmente según la función (por ejemplo, conversión, visitante del sitio, socio, vista de página, etc.). Opcional. <p> Para obtener información sobre cómo crear rasgos de conversión, consulte la <a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Creación de rasgos de conversión en vídeo de Audience Manager</a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Código de integración</span></b> </td> 
   <td colname="col2"> Campo para un ID, SKU u otro valor utilizado por los procesos empresariales internos. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Comentarios</span></b> </td> 
   <td colname="col2"> Notas generales sobre un rasgo. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Almacenar en</span></b> </td> 
   <td colname="col2"> Determina a qué carpeta de almacenamiento pertenece el rasgo. Requerido. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Categoría de datos</span></b> </td> 
   <td colname="col2"> Clasifica los rasgos según las categorías que se entienden con más frecuencia. <p>Nota: Los rasgos pertenecen a una sola categoría. Opcional. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Establezca un [!UICONTROL Trait] Intervalo de caducidad {#set-expiration-interval}

Entrada [!UICONTROL Trait Builder], el [!UICONTROL Advanced Options] permite establecer un tiempo de vida ([!DNL TTL]) intervalo para un [!UICONTROL trait]. [!DNL TTL] define cuántos días permanece un visitante clasificado en una [!UICONTROL trait] (120 días es el valor predeterminado). Cuando se establece en 0, [!UICONTROL trait] la membresía nunca caduca.

<!-- t_tb_ttl.xml -->

### Establezca el TTL para una [!UICONTROL trait]

1. Expanda el [!UICONTROL Advanced Options] y escriba un número para establecer una [!DNL TTL] valor para [!UICONTROL trait].
1. Haga clic **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Tiempo de vida del segmento explicado](../../features/traits/segment-ttl-explained.md)

