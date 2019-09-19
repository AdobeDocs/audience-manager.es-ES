---
description: Describe los pasos y las funciones de configuración específicos del proceso de creación de características basado en reglas y incorporado.
keywords: crear característica;crear características
seo-description: Describe los pasos y las funciones de configuración específicos del proceso de creación de características basado en reglas y incorporado.
seo-title: Crear características basadas en reglas o integradas
solution: Audience Manager
title: Crear características basadas en reglas o integradas
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# Crear características basadas en reglas o integradas {#create-rules-based-or-onboarded-traits}

Describe los pasos y las funciones de configuración específicos del proceso de creación [!UICONTROL rules-based] y [!UICONTROL onboarded] características.

<!-- c_tb_rules_traits.xml -->

## Información básica sobre características {#basics}

En [!UICONTROL Trait Builder], la [!UICONTROL Basic Information] configuración permite crear nuevas características o editar las existentes. La [!UICONTROL Basic Information] configuración es la misma para las características algorítmicas, integradas y basadas en reglas. Para crear una nueva característica, especifique un nombre (evitar caracteres especiales), un origen de datos y seleccione una carpeta de almacenamiento. Otros [!UICONTROL Basic Information] campos son opcionales.

<!-- c_tb_basics.xml -->

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
      </ul> </p> </p> <p>Esto ayuda a reducir los errores de procesamiento al configurar una transferencia <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> de archivos de datos de</a>entrada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Descripción</span></b> </td> 
   <td colname="col2"> Unas pocas palabras para ayudar a describir el propósito o la función del rasgo. Opcional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Tipo de evento</span></b> </td> 
   <td colname="col2"> Asigna la característica a un tipo o categoría, generalmente según la función (por ejemplo: conversión, visitante del sitio, socio, vista de página, etc.). Opcional. <p> Para obtener información sobre cómo crear características de conversión, consulte el vídeo <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html"></a>Creación de características de conversión en Audience Manager. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Fuente de datos</span></b> </td> 
   <td colname="col2"> Asocia la característica a un proveedor de datos específico. Requerido. </td> 
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
   <td colname="col1"> <b><span class="uicontrol"> Almacenado en</span></b> </td> 
   <td colname="col2"> Determina a qué carpeta de almacenamiento pertenece la característica. Requerido. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Categoría de datos</span></b> </td> 
   <td colname="col2"> Clasifica las características según categorías comúnmente conocidas. <p>Nota:  Las características pertenecen a una sola categoría. Opcional. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Configurar un intervalo de caducidad de características {#set-expiration-interval}

En [!UICONTROL Trait Builder], [!UICONTROL Advanced Options] permite establecer un intervalo de tiempo de vida ([!DNL TTL]) para una característica. [!DNL TTL] define cuántos días permanece un visitante cualificado en una característica (120 días es el valor predeterminado). Cuando se establece en 0, la pertenencia a rasgos nunca caduca.

<!-- t_tb_ttl.xml -->

### Establecer el TTL para una característica

1. Expanda la [!UICONTROL Advanced Options] sección e introduzca un número para establecer un [!DNL TTL] valor para la característica.
2. Haga clic en **[!UICONTROL Save]**.
   ![](assets/TTL.png)

>[!MORE_LIKE_THIS]
>
>* [Tiempo de vida del segmento explicado](../../features/traits/segment-ttl-explained.md)

