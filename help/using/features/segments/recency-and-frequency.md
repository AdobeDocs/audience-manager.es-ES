---
description: En el Generador de segmentos, la actualización y la frecuencia permiten segmentar a los visitantes en función de las acciones que se produzcan o repitan durante un intervalo diario establecido.
seo-description: En el Generador de segmentos, la actualización y la frecuencia permiten segmentar a los visitantes en función de las acciones que se produzcan o repitan durante un intervalo diario establecido.
seo-title: Actualización y frecuencia
solution: Audience Manager
title: Actualización y frecuencia
uuid: faadd 18 a-bf 27-4 b 73-995 e -9809 f 52 f 5350
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Recency and Frequency {#recency-and-frequency}

In [!UICONTROL Segment Builder], recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.

Audience Manager defines [!DNL recency] and [!DNL frequency] as follows:

* **[!UICONTROL Recency]:** Cantidad de días durante los cuales un usuario ha visto o calificado para una (o más) características.
* **[!UICONTROL Frequency]:** La velocidad a la que un usuario ha visto o calificado para una (o más) características.

[!UICONTROL Recency] y [!UICONTROL Frequency] la configuración le ayudan a segmentar a los visitantes según su nivel de interés real (o percibido) en un sitio, una sección o un elemento creativo concreto. Por ejemplo, es posible que los usuarios que cumplen los requisitos de un segmento con requisitos de alta frecuencia y frecuencia estén más interesados en un sitio o producto que los usuarios que visitan con menor frecuencia o menos frecuencia.

## Location of Recency and Frequency Settings {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency] and [!UICONTROL Frequency] settings are located in the [!UICONTROL Basic View] section of the [!UICONTROL Traits] panel. Haga clic en el icono del reloj para exponer estos controles.

![](assets/recency_frequency.png)

## Limitations and Rules {#limitations-rules}

Revise y comprenda estos límites y reglas cuando desee aplicar la actualización y la frecuencia a características de sus segmentos.

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
   <td colname="col1"> <p> <b>Características de terceros</b> </p> </td> 
   <td colname="col2"> <p>No puede definir reglas de actualización en características individuales de terceros o grupos de rasgos que contengan características de terceros. La actualización y la frecuencia solo se aplican a sus características. </p> </td> 
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
   <td colname="col2"> <p>No se pueden definir reglas de frecuencia en características individuales de terceros o grupos de rasgos que contengan características de terceros. La actualización y la frecuencia solo se aplican a sus características. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Requisitos de actualización</b> </p> </td> 
   <td colname="col2"> <p>You can configure frequency requirements <i>without</i> configuring recency requirements. Solo tiene que definir un valor de frecuencia y dejar el campo de actualización en blanco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Reglas de combinación de perfiles</b> </p> </td> 
   <td colname="col2"> <p>See <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Trait Frequency, External Device Graphs, and Profile Merge Rules</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Frequency Capping Examples {#frequency-capping}

Las expresiones de restricción de frecuencia incluyen todos los usuarios cuyo número de características de características está por debajo del valor deseado. Algunos ejemplos son:

* The expression `frequency([1000T]) <= 5` includes all users that have realized the trait with the ID "1000" a maximum of five times, including users who have not realized the trait.
* When you need recency/frequency requirements to be less than a specific number of times or days, join that trait to another with an `AND` operator. Using the example above, this expression becomes valid when joined with another trait as shown here: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* For advertising frequency-capping use cases, you could create a segment rule similar to this: `(frequency([1000T] <= 2D) >= 5)`. Esta expresión incluye todos los usuarios que han observado la característica con el ID "1000" en los últimos 2 días, al menos cinco veces. Set frequency capping by sending this segment to the ad server with a `NOT` set on the segment in the ad server. This approach achieves greater performance in [!DNL Audience Manager] while still serving the same purpose for frequency capping.

>[!MORE_ LIKE_ THIS]
>
>* [Controles del Generador de segmentos: Sección Características](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintaxis de código utilizada en el Editor de expresiones de segmentos](../../features/segments/segment-code-syntax.md)

