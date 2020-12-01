---
description: Describe los pasos y las funciones de configuración específicos del proceso de creación de características basado en reglas y incorporado.
keywords: create trait;create traits
seo-description: Describe los pasos y las funciones de configuración específicos del proceso de creación de características basado en reglas y incorporado.
seo-title: Crear rasgos basados en normas o integrados
solution: Audience Manager
title: Crear rasgos basados en normas o integrados
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 8%

---


# Cree[!UICONTROL Rules-Based] o [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Describe los pasos y las funciones de configuración específicos del proceso de creación de características [!UICONTROL rules-based] y [!UICONTROL onboarded].

<!-- c_tb_rules_traits.xml -->

## Información básica para características {#basics}

En [!UICONTROL Trait Builder], la configuración [!UICONTROL Basic Information] permite crear o editar los [!UICONTROL traits] existentes. La configuración [!UICONTROL Basic Information] es la misma para [!UICONTROL rules-based], [!UICONTROL onboarded] y [!UICONTROL algorithmic traits]. Para crear un nuevo [!UICONTROL trait], proporcione un nombre (evitar caracteres especiales), un [!UICONTROL data source] y seleccione un [!UICONTROL storage folder]. Otros campos [!UICONTROL Basic Information] son opcionales.

<!-- c_tb_basics.xml -->

![create-trait](assets/create-trait.png)

### Campos de información básica definidos

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento Interfaz </th> 
   <th colname="col2" class="entry"> Explicación </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Nombre</span></b> </td> 
   <td colname="col2"> <p>El nombre del rasgo. Requerido. </p> <p>Longitud máxima: 255 caracteres. </p> <p> <p>Nota: Al asignar nombres a las características, evite estos caracteres especiales: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Comas </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Guiones </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Guiones </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Fichas </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Símbolo de barra vertical o barra vertical </li> 
      </ul> </p> </p> <p>Esto ayuda a reducir los errores de procesamiento al configurar una <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> transferencia de archivos de datos de entrada</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Descripción</span></b> </td> 
   <td colname="col2"> Unas pocas palabras para ayudar a describir el propósito o la función del rasgo. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Fuente de datos</span></b> </td> 
   <td colname="col2"> Asocia la característica a un proveedor de datos específico. Requerido. <p>Utilice el primer menú desplegable para filtrar entre fuentes de datos de Audience Manager, grupos de informes de Adobe Analytics o ambos. A continuación, utilice el segundo menú desplegable para elegir el origen de datos.</p><p> Si no utiliza grupos de informes de Adobe Analytics, el selector de tipo de fuente de datos se desactiva y se asigna de forma predeterminada únicamente a las fuentes de datos de Audience Manager.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Tipo de evento</span></b> </td> 
   <td colname="col2"> Asigna la característica a un tipo o categoría, generalmente según la función (por ejemplo: conversión, visitante del sitio, socio, vista de la página, etc.). Opcional. <p> Para obtener información sobre cómo crear características de conversión, consulte <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Creación de características de conversión en vídeo de Audience Manager</a>. </p></td> 
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
   <td colname="col2"> Determina a qué carpeta de almacenamiento pertenece la característica. Requerido. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Categoría de datos</span></b> </td> 
   <td colname="col2"> Clasifica las características según categorías comúnmente entendidas. <p>Nota:  Las características pertenecen a una sola categoría. Opcional. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Establecer un intervalo de caducidad [!UICONTROL Trait] {#set-expiration-interval}

En [!UICONTROL Trait Builder], el [!UICONTROL Advanced Options] permite establecer un intervalo de tiempo de vida ([!DNL TTL]) para un [!UICONTROL trait]. [!DNL TTL] define cuántos días permanece un visitante cualificado en un  [!UICONTROL trait] (120 días es el valor predeterminado). Cuando se establece en 0, la pertenencia [!UICONTROL trait] nunca caduca.

<!-- t_tb_ttl.xml -->

### Configure el TTL para un [!UICONTROL trait]

1. Expanda la sección [!UICONTROL Advanced Options] e introduzca un número para establecer un valor [!DNL TTL] para [!UICONTROL trait].
1. Haga clic **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Tiempo de vida del segmento explicado](../../features/traits/segment-ttl-explained.md)

