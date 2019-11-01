---
description: En el Generador de segmentos, la actualización y la frecuencia permiten segmentar a los visitantes en función de las acciones que se producen o se repiten a lo largo de un intervalo diario establecido.
seo-description: En el Generador de segmentos, la actualización y la frecuencia permiten segmentar a los visitantes en función de las acciones que se producen o se repiten a lo largo de un intervalo diario establecido.
seo-title: Actualización y frecuencia
solution: Audience Manager
title: Actualización y frecuencia
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Recency and Frequency {#recency-and-frequency}

En [!UICONTROL Segment Builder], la actualización y la frecuencia permiten segmentar a los visitantes en función de las acciones que se producen o se repiten a lo largo de un intervalo diario establecido.

Audience Manager define [!DNL recency] y [!DNL frequency] :

* **[!UICONTROL Recency]** :: Última visualización o cualificación de un usuario para una (o más) característica.
* **[!UICONTROL Frequency]** :: Frecuencia con la que un usuario ha visualizado o calificado para una (o más) característica.

[!UICONTROL Recency] y [!UICONTROL Frequency] le ayudan a segmentar a los visitantes en función de su nivel de interés real (o percibido) en un sitio, sección o elemento creativo en particular. Por ejemplo: los usuarios que califican para un segmento con requisitos de alta frecuencia y actualización pueden estar más interesados en un sitio o producto que los usuarios que visitan con menos frecuencia o con menos frecuencia.

## Ubicación de la configuración de actualización y frecuencia {#location}

En [!UICONTROL Segment Builder], [!UICONTROL Recency] los ajustes y [!UICONTROL Frequency] se encuentran en la [!UICONTROL Basic View] sección del [!UICONTROL Traits] panel. Haga clic en el icono del reloj para mostrar estos controles.

![](assets/recency_frequency.png)

## Limitaciones y reglas {#limitations-rules}

Revise y comprenda estos límites y reglas cuando desee aplicar actualización y frecuencia a las características de los segmentos.

### Actualización

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
   <td colname="col2"> <p>La actualización debe ser mayor que 0. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Tipos de características</b> </p> </td> 
   <td colname="col2"> <p>Puede aplicar controles de actualización solo a características de carpetas y reglas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Características de terceros</b> </p> </td> 
   <td colname="col2"> <p>No se pueden establecer reglas de actualización en rasgos individuales de terceros ni en grupos de características que contengan características de terceros. La actualización y la frecuencia solo se aplican a sus propias características. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Frecuencia

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
   <td colname="col2"> <p>Puede configurar los requisitos de frecuencia <i>sin</i> configurar los requisitos de actualización. Simplemente configure un valor de frecuencia y deje el campo de actualización en blanco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Reglas de combinación de perfiles</b> </p> </td> 
   <td colname="col2"> <p>Consulte <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Frecuencia de características, Gráficos de dispositivos externos y Reglas</a>de combinación de perfiles. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplos de actualización {#recency-examples}

Estos son dos ejemplos de cómo funciona la actualización, según la selección realizada en la interfaz de usuario:

### Usar un operador menor o igual que (&lt;=)

![Menor que igual a](assets/less-than-equal-to.png)

En este ejemplo, se selecciona el operador &lt;=, como se muestra en la captura de pantalla. Esto califica al usuario para el segmento si cumple los requisitos para cualquiera de las tres características un mínimo de tres veces en los últimos cinco días. La línea de tiempo siguiente muestra la cualificación del segmento en el momento en que se crea, el 1 de octubre y diez días después.

![Últimos cinco días](assets/last-5-days.png)

### Usar un operador mayor o igual que (=&gt;)

![Mayor que igual a](assets/greater-than-equal-to.png)

En este ejemplo, se selecciona el operador =&gt;, como se muestra en la captura de pantalla. Esto califica al usuario para el segmento si cumple los requisitos para cualquiera de las tres características como mínimo tres veces en cualquier momento entre su primera calificación en la plataforma de Audience Manager y el tiempo de corte hace cinco días. La línea de tiempo siguiente muestra la cualificación del segmento en el momento en que se crea, el 1 de octubre y diez días después.

![Calificación previa](assets/earlier-qualification.png)


## Ejemplos de límite de frecuencia {#frequency-capping}

Las expresiones de límite de frecuencia incluyen todos los usuarios cuyo número de realizaciones de características está por debajo del valor deseado. Estos son algunos ejemplos de Right and Wrong:

* Incorrecto: la expresión `frequency([1000T]) <= 5` incluye a todos los usuarios que han realizado la característica con la ID "1000" un máximo de cinco veces, pero también a los usuarios que no han realizado la característica. Por lo tanto, Audience Manager no valida esta expresión por motivos de rendimiento, ya que calificaría a demasiados usuarios para el segmento.

* Derecha: Si desea incluir a todos los usuarios que han realizado la característica con el ID "1000" un máximo de cinco veces, agregue otra condición a la expresión para asegurarse de que los usuarios cumplen los requisitos para la característica al menos una vez:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Derecha: cuando necesite que los requisitos de actualización y frecuencia sean menores que un número específico de veces o días, una esa característica a otra con un `AND` operador. Con el ejemplo del primer punto de viñeta, esta expresión pasa a ser válida cuando se une con otra característica, como se muestra aquí: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Derecha: En los casos de uso de límite de frecuencia de publicidad, puede crear una regla de segmento similar a esta: `(frequency([1000T] <= 2D) >= 5)`. Esta expresión incluye todos los usuarios que han realizado la característica con el ID "1000" en los últimos 2 días al menos cinco veces. Establezca el límite de frecuencia enviando este segmento al servidor de publicidad con un `NOT` conjunto en el segmento en el servidor de publicidad. Este enfoque logra un mayor rendimiento en [!DNL Audience Manager] tanto que sigue cumpliendo el mismo propósito para limitar la frecuencia.

>[!MORELIKETHIS]
>
>* [Controles del Generador de segmentos: Sección de características](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintaxis del código utilizada en el Editor de expresiones de segmento](../../features/segments/segment-code-syntax.md)

