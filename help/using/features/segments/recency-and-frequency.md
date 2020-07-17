---
description: En el Generador de segmentos, la actualización y la frecuencia le permiten segmentar visitantes en función de acciones que se producen o se repiten a lo largo de un intervalo diario establecido.
seo-description: En el Generador de segmentos, la actualización y la frecuencia le permiten segmentar visitantes en función de acciones que se producen o se repiten a lo largo de un intervalo diario establecido.
seo-title: Fecha de adquisición más frecuente y frecuencia.
solution: Audience Manager
title: Fecha de adquisición más frecuente y frecuencia.
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 3%

---


# Fecha de adquisición más frecuente y frecuencia.{#recency-and-frequency}

En [!UICONTROL Segment Builder], la actualización y la frecuencia le permiten segmentar visitantes en función de acciones que se producen o se repiten a lo largo de un intervalo diario establecido.

Audience Manager define [!DNL recency] y [!DNL frequency] como sigue:

* **[!UICONTROL Recency]::**Última vez que un usuario ha visualizado o calificado para uno (o más)[!UICONTROL traits].
* **[!UICONTROL Frequency]::**Frecuencia con la que un usuario ha visualizado o calificado uno (o más)[!UICONTROL traits].

[!UICONTROL Recency] y [!UICONTROL Frequency] le ayudan a segmentar los visitantes en función de su nivel de interés real (o percibido) en un sitio, sección o elemento creativo en particular. Por ejemplo: los usuarios que califican para un segmento con requisitos de alta frecuencia y actualización pueden estar más interesados en un sitio o producto que los usuarios que visitan con menos frecuencia o con menos frecuencia.

## Ubicación de la [!UICONTROL Recency and Frequency] configuración {#location}

En [!UICONTROL Segment Builder], [!UICONTROL Recency] los ajustes y [!UICONTROL Frequency] se encuentran en la [!UICONTROL Basic View] sección del [!UICONTROL Traits] panel. Haga clic en el icono del reloj para mostrar estos controles.

![](assets/recency_frequency.png)

## Limitaciones y reglas {#limitations-rules}

Revise y comprenda estos límites y reglas cuando desee aplicar actualización y frecuencia a las características de los segmentos.

### [!UICONTROL Recency] {#recency}

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Límite o regla </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Valor mínimo</b> </p> </td> 
   <td colname="col2"> <p>La actualización debe ser buena a 0. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Tipos de características</b> </p> </td> 
   <td colname="col2"> <p>Puede aplicar controles de actualización solo a características de carpeta y basadas en reglas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Características de terceros</b> </p> </td> 
   <td colname="col2"> <p>No se pueden establecer reglas de actualización en rasgos individuales de terceros ni en grupos de características que contengan características de terceros. La actualización y la frecuencia solo se aplican a sus propias características. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Frequency] {#frequency}

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Límite o regla </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Características de terceros</b> </p> </td> 
   <td colname="col2"> <p>No puede establecer reglas de frecuencia en rasgos individuales de terceros o en grupos de características que contengan características de terceros. La actualización y la frecuencia solo se aplican a sus propias características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tipos de características</b> </p> </td> 
   <td colname="col2"> <p>Puede aplicar controles de frecuencia solo a características de carpetas y reglas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Requisitos de actualización</b> </p> </td> 
   <td colname="col2"> <p>Puede configurar los requisitos de frecuencia <i>sin</i> configurar los requisitos de actualización. Solo tiene que establecer un valor de frecuencia y dejar el campo de actualización en blanco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Reglas de combinación de perfiles</b> </p> </td> 
   <td colname="col2"> <p>See <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Trait Frequency, External Device Graphs, and Profile Merge Rules</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplos de actualización {#recency-examples}

Estos son dos ejemplos de cómo funciona la actualización, según la selección realizada en la interfaz de usuario:

### Uso de un operador menor o igual que (&lt;=)

![Menor que igual a](assets/less-than-equal-to.png)

En este ejemplo, se selecciona el operador &lt;=, como se muestra en la captura de pantalla. Esto califica a su usuario para el [!UICONTROL segment] que cumple los requisitos para cualquiera de los tres [!UICONTROL traits] como mínimo tres veces en los últimos cinco días. La línea de tiempo siguiente muestra la [!UICONTROL segment] cualificación en el momento de crear el [!UICONTROL segment] evento, el 1 de octubre y diez días después.

![Últimos cinco días](assets/last-5-days.png)

### Usar un operador bueno o igual que (=>)

![Bueno-que-igual-a](assets/greater-than-equal-to.png)

En este ejemplo, se selecciona el operador =>, como se muestra en la captura de pantalla. Esto califica a su usuario para el [!UICONTROL segment] que cumple los requisitos para cualquiera de los tres [!UICONTROL traits] como mínimo tres veces en cualquier momento entre su primera cualificación en la plataforma de Audience Manager y el tiempo de corte hace cinco días. La línea de tiempo siguiente muestra la [!UICONTROL segment] cualificación en el momento de crear el [!UICONTROL segment] evento, el 1 de octubre y diez días después.

![Calificación previa](assets/earlier-qualification.png)


## Ejemplos de límite de frecuencia {#frequency-capping}

Las expresiones de límite de frecuencia incluyen todos los usuarios cuyo número de [!UICONTROL trait] realizaciones está por debajo del valor deseado. Estos son algunos ejemplos de Right and Wrong:

* Incorrecto: la expresión `frequency([1000T]) <= 5` incluye a todos los usuarios que se han dado cuenta [!UICONTROL trait] con el ID &quot;1000&quot; cinco veces como máximo, pero también a los usuarios que no han realizado el [!UICONTROL trait]. Por lo tanto, Audience Manager no valida esta expresión por motivos de rendimiento, ya que calificaría a demasiados usuarios para la [!UICONTROL segment].

* Derecha: Si desea incluir a todos los usuarios que han realizado el evento [!UICONTROL trait] con el ID &quot;1000&quot; un máximo de cinco veces, agregue otra condición a la expresión para asegurarse de que los usuarios cumplen los requisitos para el [!UICONTROL trait] menos una vez:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Derecha: Cuando necesite que los requisitos de actualización y frecuencia sean menores que un número específico de veces o días, únase eso [!UICONTROL trait] a otro con un `AND` operador. Con el ejemplo del primer punto de viñeta, esta expresión pasa a ser válida cuando se une con otra [!UICONTROL trait] , como se muestra a continuación: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Derecha: En los casos de uso de límite de frecuencia de publicidad, puede crear una [!UICONTROL segment] regla similar a esta: `(frequency([1000T] <= 2D) >= 5)`. Esta expresión incluye a todos los usuarios que se han dado cuenta [!UICONTROL trait] con la ID &quot;1000&quot; en los últimos 2 días al menos cinco veces. Establezca el límite de frecuencia enviando esto [!UICONTROL segment] al servidor de publicidad con un `NOT` conjunto en el [!UICONTROL segment] servidor de publicidad. Este enfoque logra un rendimiento bueno [!DNL Audience Manager] al tiempo que sigue cumpliendo el mismo propósito para el límite de frecuencia.

>[!MORELIKETHIS]
>
>* [Controles del Generador de segmentos: Sección de características](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintaxis del código utilizada en el Editor de Expresiones de segmentos](../../features/segments/segment-code-syntax.md)

