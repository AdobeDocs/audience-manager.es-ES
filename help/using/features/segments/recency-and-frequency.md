---
description: En el Generador de segmentos, la actualización y la frecuencia le permiten segmentar a los visitantes en función de las acciones que se producen o que se repiten a lo largo de un intervalo diario establecido.
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Recency and Frequency
solution: Audience Manager
title: Fecha de adquisición más frecuente y frecuencia.
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 2%

---

# Fecha de adquisición más frecuente y frecuencia. {#recency-and-frequency}

Entrada [!UICONTROL Segment Builder], actualización y frecuencia le permiten segmentar a los visitantes en función de las acciones que se producen o que se repiten a lo largo de un intervalo diario establecido.

El Audience Manager define [!DNL recency] y [!DNL frequency] como sigue:

* **[!UICONTROL Recency]:** Fecha en la que un usuario vio o calificó para uno (o más) [!UICONTROL traits].
* **[!UICONTROL Frequency]:** Frecuencia a la que un usuario vio o calificó para uno (o más) [!UICONTROL traits].

[!UICONTROL Recency] y [!UICONTROL Frequency] la configuración de le ayuda a segmentar a los visitantes en función de su nivel de interés real (o percibido) en un sitio, sección o creativo particular. Por ejemplo, los usuarios que cumplen los requisitos de un segmento con requisitos de alta actualización/frecuencia pueden estar más interesados en un sitio o producto que los usuarios que visitan con menos frecuencia o con menos frecuencia.

## Ubicación de [!UICONTROL Recency and Frequency] Configuración {#location}

Entrada [!UICONTROL Segment Builder], [!UICONTROL Recency] y [!UICONTROL Frequency] se encuentran en la sección [!UICONTROL Basic View] de la sección [!UICONTROL Traits] panel. Haga clic en el icono del reloj para mostrar estos controles.

![](assets/recency_frequency.png)

## Limitaciones y reglas {#limitations-rules}

Revise y comprenda estos límites y reglas cuando desee aplicar actualización y frecuencia a características de los segmentos.

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
   <td colname="col2"> <p>La actualización debe ser buena que 0. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Tipos de rasgos</b> </p> </td> 
   <td colname="col2"> <p>Puede aplicar controles de actualización solo a características de carpeta y basadas en reglas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Características de terceros</b> </p> </td> 
   <td colname="col2"> <p>No puede establecer reglas de actualización en rasgos de terceros individuales o grupos de rasgos que contengan rasgos de terceros. La actualización y la frecuencia solo se aplican a sus propios rasgos. </p> </td> 
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
   <td colname="col2"> <p>No puede establecer reglas de frecuencia en rasgos de terceros individuales o grupos de rasgos que contengan rasgos de terceros. La actualización y la frecuencia solo se aplican a sus propios rasgos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tipos de rasgos</b> </p> </td> 
   <td colname="col2"> <p>Solo puede aplicar controles de frecuencia a características de carpeta y basadas en reglas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Requisitos de actualización</b> </p> </td> 
   <td colname="col2"> <p>Puede configurar los requisitos de frecuencia <i>sin</i> configurar los requisitos de actualización. Solo tiene que establecer un valor de frecuencia y dejar el campo de actualización en blanco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Reglas de combinación de perfiles</b> </p> </td> 
   <td colname="col2"> <p>Consulte <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Frecuencia de rasgos, gráficos de dispositivos externos y reglas de combinación de perfiles</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplos de actualización {#recency-examples}

A continuación se muestran dos ejemplos de cómo funciona la actualización, según lo que haya seleccionado en la interfaz de usuario:

### Uso de un operador menor o igual que (&lt;=)

![Menor que igual a](assets/less-than-equal-to.png)

En este ejemplo, selecciona el operador &lt;=, como se muestra en la captura de pantalla. Esto califica al usuario para el [!UICONTROL segment] si cumplen los requisitos para cualquiera de los tres [!UICONTROL traits] un mínimo de tres veces en los últimos cinco días. La línea de tiempo siguiente muestra [!UICONTROL segment] calificación en el momento en que [!UICONTROL segment] se crea el 1 de octubre y diez días después.

![Últimos cinco días](assets/last-5-days.png)

### Uso de un operador bueno o igual a (=>)

![Bueno que igual a](assets/greater-than-equal-to.png)

En este ejemplo, selecciona el operador =>, como se muestra en la captura de pantalla. Esto califica al usuario para el [!UICONTROL segment] si cumplen los requisitos para cualquiera de los tres [!UICONTROL traits] un mínimo de tres veces en cualquier momento entre su primera calificación en la plataforma Audience Manager y el tiempo de corte hace cinco días. La línea de tiempo siguiente muestra [!UICONTROL segment] calificación en el momento en que [!UICONTROL segment] se crea el 1 de octubre y diez días después.

![Calificación anticipada](assets/earlier-qualification.png)


## Ejemplos de límite de frecuencia {#frequency-capping}

Las expresiones de límite de frecuencia incluyen todos los usuarios cuyo número de [!UICONTROL trait] las realizaciones están por debajo del valor deseado. Estos son algunos ejemplos de lo correcto y lo incorrecto:

* Incorrecto: la expresión `frequency([1000T]) <= 5` incluye a todos los usuarios que se han dado cuenta de la [!UICONTROL trait] con el ID &quot;1000&quot; un máximo de cinco veces, pero también incluye a los usuarios que no se han dado cuenta de la [!UICONTROL trait]. Por lo tanto, Audience Manager no valida esta expresión por motivos de rendimiento, ya que cumpliría los requisitos de demasiados usuarios para la [!UICONTROL segment].

* Correcto: si desea incluir a todos los usuarios que han realizado la [!UICONTROL trait] con el ID &quot;1000&quot; un máximo de cinco veces, agregue otra condición a la expresión para asegurarse de que los usuarios cumplen los requisitos para la expresión [!UICONTROL trait] al menos una vez:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Derecho: cuando necesite que los requisitos de actualización/frecuencia sean inferiores a un número específico de veces o días, únase a ellos [!UICONTROL trait] a otro con un `AND` operador. Si se utiliza el ejemplo en el primer punto de viñeta, esta expresión se vuelve válida cuando se une con otra [!UICONTROL trait] como se muestra aquí: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Correcto: en los casos de uso de restricción de frecuencia de publicidad, puede crear una [!UICONTROL segment] regla similar a esta: `(frequency([1000T] <= 2D) >= 5)`. Esta expresión incluye a todos los usuarios que se han dado cuenta de la [!UICONTROL trait] con el ID &quot;1000&quot; en los últimos dos días al menos cinco veces. Defina el límite de frecuencia enviando esto [!UICONTROL segment] al servidor de publicidad con un `NOT` se configura en el [!UICONTROL segment] en el servidor de publicidad. Este enfoque logra el bueno rendimiento en [!DNL Audience Manager] aunque sigue teniendo el mismo propósito para la restricción de frecuencia.

>[!MORELIKETHIS]
>
>* [Controles del Generador de segmentos: Sección Características](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintaxis del código utilizada en el Editor de Expresiones de segmentos](../../features/segments/segment-code-syntax.md)

