---
description: Describe los pasos y las características específicas del proceso de creación de rasgos basados en reglas e integradas.
keywords: crear trait; crear características
seo-description: Describe los pasos y las características específicas del proceso de creación de rasgos basados en reglas e integradas.
seo-title: Crear características basadas en reglas o integradas
solution: Audience Manager
title: Crear características basadas en reglas o integradas
uuid: 4243 e 09 f -1 f 96-443 a -864 a-d 6 e 6918079 fa
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# Crear características basadas en reglas o integradas {#create-rules-based-or-onboarded-traits}

Describe los pasos y funciones específicos del proceso de creación [!UICONTROL rules-based] y [!UICONTROL onboarded] de creación.

<!-- c_tb_rules_traits.xml -->

## Información básica para características {#basics}

En [!UICONTROL Trait Builder], [!UICONTROL Basic Information] la configuración permite crear nuevas características o editarlas. [!UICONTROL Basic Information] La configuración es la misma para características basadas en reglas, integradas y algorítmicos. Para crear un nuevo rasgo, proporcione un nombre (evite caracteres especiales), un origen de datos y seleccione una carpeta de almacenamiento. Otros [!UICONTROL Basic Information] campos son opcionales.

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
      </ul> </p> </p> <p>Esto ayuda a reducir los errores de procesamiento cuando se configura una transferencia de archivos de datos <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> de entrada</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Descripción</span></b> </td> 
   <td colname="col2"> Algunas palabras para describir el propósito o la función de características. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Tipo de evento</span></b> </td> 
   <td colname="col2"> Asigna la característica a un tipo o categoría, generalmente según la función (por ejemplo: conversión, visitante del sitio, socio, vista de página, etc.). Opcional. <p> Para aprender a crear características de conversión, consulte <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Creación de características de conversión en Audience Manager video</a>. </p></td> 
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

## Configurar un intervalo de caducidad de características {#set-expiration-interval}

En [!UICONTROL Trait Builder], la [!UICONTROL Advanced Options] opción permite establecer un intervalo de tiempo a lanzamiento para un rasgo[!DNL TTL]. [!DNL TTL] define cuántos días un visitante cualificado permanece en una característica (es de 120 días predeterminado). Cuando se establece en 0, la pertenencia a características nunca caduca.

<!-- t_tb_ttl.xml -->

### Definir el TTL para un rasgo

1. Expanda [!UICONTROL Advanced Options] la sección e introduzca un número para definir [!DNL TTL] un valor para la característica.
2. Haga clic en **[!UICONTROL Save]**.
   ![](assets/TTL.png)

>[!MORE_ LIKE_ THIS]
>
>* [Tiempo de segmentación en vivo explicado](../../features/traits/segment-ttl-explained.md)

