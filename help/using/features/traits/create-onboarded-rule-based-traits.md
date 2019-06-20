---
description: Describe los pasos y las características específicas del proceso de creación de rasgos basados en reglas e integradas.
keywords: crear trait; crear características
seo-description: Describe los pasos y las características específicas del proceso de creación de rasgos basados en reglas e integradas.
seo-title: Crear características basadas en reglas o integradas
solution: Audience Manager
title: Crear características basadas en reglas o integradas
uuid: 4243 e 09 f -1 f 96-443 a -864 a-d 6 e 6918079 fa
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create Rules-Based or Onboarded Traits {#create-rules-based-or-onboarded-traits}

Describes set up steps and features specific to the [!UICONTROL rules-based] and [!UICONTROL onboarded] trait creation process.

<!-- c_tb_rules_traits.xml -->

## Basic Information for Traits {#basics}

In [!UICONTROL Trait Builder], the [!UICONTROL Basic Information] settings let you create new, or edit existing traits. [!UICONTROL Basic Information] La configuración es la misma para características basadas en reglas, integradas y algorítmicos. Para crear un nuevo rasgo, proporcione un nombre (evite caracteres especiales), un origen de datos y seleccione una carpeta de almacenamiento. Other [!UICONTROL Basic Information] fields are optional.

<!-- c_tb_basics.xml -->

### Campos básicos de información definidos

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
   <td colname="col2"> <p>El nombre de la característica. Requerido. </p> <p>Longitud máxima: 255 caracteres. </p> <p> <p>Nota: Al asignar nombres a características, evite estos caracteres especiales: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Comas </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Guiones </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Guiones </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Fichas </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Barras verticales o símbolo de barra vertical </li> 
      </ul> </p> </p> <p>This helps reduce processing errors when you set up an <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> inbound data file transfer</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Descripción</span></b> </td> 
   <td colname="col2"> Algunas palabras para describir el propósito o la función de características. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Tipo de evento</span></b> </td> 
   <td colname="col2"> Asigna la característica a un tipo o categoría, generalmente según la función (por ejemplo: conversión, visitante del sitio, socio, vista de página, etc.). Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Fuente de datos</span></b> </td> 
   <td colname="col2"> Asocia la característica con un proveedor de datos específico. Requerido. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Código de integración</span></b> </td> 
   <td colname="col2"> Campo de ID, SKU u otro valor utilizado por los procesos empresariales internos. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Comentarios</span></b> </td> 
   <td colname="col2"> Notas generales sobre un rasgo. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Almacenado en</span></b> </td> 
   <td colname="col2"> Determina a qué carpeta de almacenamiento pertenece la característica. Requerido. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Categoría de datos</span></b> </td> 
   <td colname="col2"> Clasifica las características según las categorías comúnmente interpretadas. <p>Nota: Las características pertenecen solo a una única categoría. Opcional. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Set a Trait Expiration Interval {#set-expiration-interval}

In [!UICONTROL Trait Builder], the [!UICONTROL Advanced Options] lets you set a time-to-live ([!DNL TTL]) interval for a trait. [!DNL TTL] define cuántos días un visitante cualificado permanece en una característica (es de 120 días predeterminado). Cuando se establece en 0, la pertenencia a características nunca caduca.

<!-- t_tb_ttl.xml -->

### Definir el TTL para un rasgo

1. Expand the [!UICONTROL Advanced Options] section and enter a number to set a [!DNL TTL] value for the trait.
1. Haga clic en **[!UICONTROL Save]**.
   ![](assets/TTL.png)

>[!MORE_ LIKE_ THIS]
>
>* [Tiempo de segmentación en vivo explicado](../../features/traits/segment-ttl-explained.md)

