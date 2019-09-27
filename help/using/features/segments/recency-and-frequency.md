---
description: En el Generador de segmentos, la actualización y la frecuencia permiten segmentar a los visitantes en función de las acciones que se producen o se repiten a lo largo de un intervalo diario establecido.
seo-description: En el Generador de segmentos, la actualización y la frecuencia permiten segmentar a los visitantes en función de las acciones que se producen o se repiten a lo largo de un intervalo diario establecido.
seo-title: Recency and Frequency
solution: Audience Manager
title: Actualización y frecuencia
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: c7e8b67ccad4479487b471668462937c5be6be34

---


# Recency and Frequency {#recency-and-frequency}

En [!UICONTROL Segment Builder], la actualización y la frecuencia permiten segmentar a los visitantes en función de las acciones que se producen o se repiten a lo largo de un intervalo diario establecido.

Audience Manager defines [!DNL recency] and [!DNL frequency] as follows:

* **[!UICONTROL Recency]:** How recently a user viewed or qualified for one (or more) traits.
* **[!UICONTROL Frequency]:** The rate at which a user viewed or qualified for one (or more) traits.

[!UICONTROL Recency] and  settings help you segment visitors based on their real (or perceived) level of interest in a site, section, or particular creative. [!UICONTROL Frequency] For example, users who qualify for a segment with high recency/frequency requirements may be more interested in a site or product than users who visit less often or less frequently.

## Location of Recency and Frequency Settings {#location}

In ,  and  settings are located in the  section of the  panel. [!UICONTROL Segment Builder][!UICONTROL Recency][!UICONTROL Frequency][!UICONTROL Basic View][!UICONTROL Traits] Click the clock icon to expose these controls.

![](assets/recency_frequency.png)

## Limitations and Rules {#limitations-rules}

Review and understand these limits and rules when you want to apply recency and frequency to traits in your segments.

### Actualización

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limit or Rule </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Valor mínimo</b> </p> </td> 
   <td colname="col2"> <p>Recency must be greater than 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Third-Party Traits</b> </p> </td> 
   <td colname="col2"> <p>You cannot set recency rules on individual third-party traits or trait groups that contain third-party traits. Recency and frequency applies to your own traits only. </p> </td> 
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

Las expresiones de límite de frecuencia incluyen todos los usuarios cuyo número de realizaciones de características está por debajo del valor deseado. Estos son algunos ejemplos:

* La expresión `frequency([1000T]) <= 5` incluye a todos los usuarios que hayan realizado la característica con el ID "1000" un máximo de cinco veces, incluidos los usuarios que no hayan realizado la característica.
* Cuando necesite que los requisitos de actualización y frecuencia sean inferiores a un número específico de veces o días, una esa característica a otra con un `AND` operador. Con el ejemplo anterior, esta expresión pasa a ser válida cuando se une con otra característica, como se muestra aquí: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* En los casos de uso de límite de frecuencia de publicidad, puede crear una regla de segmento similar a esta: `(frequency([1000T] <= 2D) >= 5)`. This expression includes all users that have realized the trait with the ID "1000" in the past 2 days at least five times. Set frequency capping by sending this segment to the ad server with a  set on the segment in the ad server. `NOT` This approach achieves greater performance in  while still serving the same purpose for frequency capping.[!DNL Audience Manager]

>[!MORE_LIKE_THIS]
>
>* [Segment Builder Controls: Traits Section](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Code Syntax Used in the Segment Expression Editor](../../features/segments/segment-code-syntax.md)

