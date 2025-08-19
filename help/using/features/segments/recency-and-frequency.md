---
description: En el Generador de segmentos, lo reciente y Frecuencia le permiten segmento visitantes en función de las acciones que ocurren o se repiten durante un intervalo diario establecido.
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Recency and Frequency
solution: Audience Manager
title: actualización y frecuencia
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 1%

---

# actualización y frecuencia {#recency-and-frequency}

, [!UICONTROL Segment Builder]lo reciente y Frecuencia permiten segmento visitantes en función de las acciones que se producen o se repiten durante un intervalo diario establecido.

Audience Manager define [!DNL recency] y [!DNL frequency] como sigue:

* **[!UICONTROL Recency]: Cuán** recientemente una usuario visualizó o calificó para una (o más) [!UICONTROL traits].
* **[!UICONTROL Frequency]:** La tasa a la que un usuario visto o calificado para uno (o más) [!UICONTROL traits].

[!UICONTROL Recency] y [!UICONTROL Frequency] la configuración le ayuda a segmento los visitantes en función de su nivel de interés real (o percibido) en un sitio, sección o creativa en particular. Por ejemplo, los usuarios que califican para una segmento con altos requisitos de actualización / Frecuencia pueden estar más interesados en un sitio o producto que los usuarios que visita con menos frecuencia o con menos frecuencia.

## Ubicación de [!UICONTROL Recency and Frequency] Configuración {#location}

En [!UICONTROL Segment Builder], [!UICONTROL Recency] y [!UICONTROL Frequency] los [!UICONTROL Basic View] ajustes se encuentran en la [!UICONTROL Traits] sección del panel. Haga clic en el icono del reloj para exponer estos controles.

![](assets/recency_frequency.png)

## Limitaciones y reglas {#limitations-rules}

Revise y comprenda estos límites y reglas cuando desee aplicar lo último y Frecuencia a las características de los segmentos.

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
   <td colname="col1"> <p> <b>Mínimo Valor</b> </p> </td> 
   <td colname="col2"> <p>actualización debe ser mayor que 0. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Tipos de rasgos</b> </p> </td> 
   <td colname="col2"> <p>Solo puede aplicar controles de actualización a características basadas en regla y en carpetas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Características de terceros</b> </p> </td> 
   <td colname="col2"> <p>No se pueden establecer reglas de actualización en rasgos de terceros individuales o grupos de rasgos que contengan terceros rasgos. actualización y Frecuencia se aplica solo a sus propias características. </p> </td> 
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
   <td colname="col2"> <p>No se pueden establecer reglas de Frecuencia en terceros individuales ni en grupos de rasgos que contengan terceros rasgos. actualización y Frecuencia se aplica solo a sus propias características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tipos de rasgos</b> </p> </td> 
   <td colname="col2"> <p>Puede aplicar controles de Frecuencia solo a características basadas en regla y en carpeta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Requisitos actualización</b> </p> </td> 
   <td colname="col2"> <p>Puede configurar los requisitos <i>de Frecuencia sin necesidad</i> de configurar los requisitos de actualización. Solo tiene que establecer un valor Frecuencia y dejar el campo de actualidad en blanco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Reglas de combinación de perfiles</b> </p> </td> 
   <td colname="col2"> <p>Consulte <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Frecuencia de rasgos, Gráficos de dispositivos externos y Reglas de combinación de perfiles</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplos actualización {#recency-examples}

Aquí se muestran dos ejemplos de cómo funciona la actualidad, dependiendo de su selección en el IU:

### Con un operador menor o igual que (&lt;=)

![Menos que igual a](assets/less-than-equal-to.png)

En este ejemplo, se selecciona la variable &lt;= operator, as shown in the screenshot. Esto califica a su usuario para el [!UICONTROL segment] si califican para cualquiera de los tres [!UICONTROL traits] un mínimo de tres veces en los últimos cinco días. El cronología a continuación muestra la [!UICONTROL segment] calificación en el momento [!UICONTROL segment] en que se crea, el 1 de octubre y diez días después.

![Últimos cinco días](assets/last-5-days.png)

### Uso de un operador mayor o igual que (=>)

![Mayor que igual a](assets/greater-than-equal-to.png)

En este ejemplo, seleccione el operador =>, como se muestra en la captura de pantalla. Esto califica a su usuario para el [!UICONTROL segment] si califican para cualquiera de los tres [!UICONTROL traits] un mínimo de tres veces en cualquier momento entre su primera calificación en la plataforma Audience Manager y la hora límite hace cinco días. El cronología a continuación muestra la [!UICONTROL segment] calificación en el momento [!UICONTROL segment] en que se crea, el 1 de octubre y diez días después.

![Calificación previa](assets/earlier-qualification.png)


## Ejemplos de limitación de frecuencia {#frequency-capping}

Las expresiones de limitación de frecuencia incluyen a todos los usuarios cuyo número de [!UICONTROL trait] realizaciones es inferior a un valor deseado. Aquí hay algunos ejemplos correctos e incorrectos:

* Incorrecto - El expresión `frequency([1000T]) <= 5` incluye a todos los usuarios que han realizado el [!UICONTROL trait] con el ID &quot;1000&quot; un máximo de cinco veces, pero también incluye a los usuarios que no han realizado el [!UICONTROL trait]. Por lo tanto, Audience Manager no valida este expresión por motivos de rendimiento, ya que calificaría demasiados usuarios para el [!UICONTROL segment].

* Derecha - Si desea incluir a todos los usuarios que han realizado el [!UICONTROL trait] con el ID &quot;1000&quot; un máximo de cinco veces, agregue otra condición al expresión, para asegurarse de que los usuarios hayan calificado para al [!UICONTROL trait] menos una vez:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Correcto: cuando necesite que los requisitos de actualización / Frecuencia sean menores que un número específico de veces o días, únalos [!UICONTROL trait] a otro con un `AND` operador. Usando el ejemplo en el primer punto, este expresión se vuelve válido cuando se une con otro [!UICONTROL trait] como se muestra aquí: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Derecha: para los casos de uso de publicidad Frecuencia limitación de puntos, puede crear una [!UICONTROL segment] regla similar a esta: `(frequency([1000T] <= 2D) >= 5)`. Este expresión incluye a todos los usuarios que se han dado cuenta del [!UICONTROL trait] ID &quot;1000&quot; en los últimos 2 días al menos cinco veces. Establezca restricción de frecuencia enviando esto [!UICONTROL segment] a la servidor de anuncios con un `NOT` conjunto en [!UICONTROL segment] el servidor de anuncios. Este enfoque logra un mayor rendimiento sin [!DNL Audience Manager] dejar de cumplir el mismo propósito para restricción de frecuencia.

>[!MORELIKETHIS]
>
>* [Controles del Generador de segmentos: Sección de características](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintaxis del código utilizada en el Editor de Expresiones de segmentos](../../features/segments/segment-code-syntax.md)
