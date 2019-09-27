---
description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Actualización y frecuencia
solution: Audience Manager
title: Actualización y frecuencia
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: 1cbff10b9e978755e139e7d5b996249de5ebb5bd

---


# Recency and Frequency {#recency-and-frequency}

En [!UICONTROL Segment Builder], la actualización y la frecuencia permiten segmentar a los visitantes en función de las acciones que se producen o se repiten a lo largo de un intervalo diario establecido.

Audience Manager defines  and  as follows:[!DNL recency][!DNL frequency]

* **[!UICONTROL Recency]** :: How recently a user viewed or qualified for one (or more) traits.
* **[!UICONTROL Frequency]** :: The rate at which a user viewed or qualified for one (or more) traits.

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

![Less-than-equal-to](assets/less-than-equal-to.png)

En este ejemplo, se selecciona el operador &lt;=, como se muestra en la captura de pantalla. This qualifies your user for the segment if they qualify for any of the three traits a minimum of three times within the last five days. La línea de tiempo siguiente muestra la cualificación del segmento en el momento en que se crea, el 1 de octubre y diez días después.

![Last-five-days](assets/last-5-days.png)

### Usar un operador mayor o igual que (=&gt;)

![Mayor que igual a](assets/greater-than-equal-to.png)

En este ejemplo, se selecciona el operador =&gt;, como se muestra en la captura de pantalla. Esto califica al usuario para el segmento si cumple los requisitos para cualquiera de las tres características como mínimo tres veces en cualquier momento entre su primera calificación en la plataforma de Audience Manager y el tiempo de corte hace cinco días. La línea de tiempo siguiente muestra la cualificación del segmento en el momento en que se crea, el 1 de octubre y diez días después.

![Earlier-qualification](assets/earlier-qualification.png)


## Ejemplos de límite de frecuencia {#frequency-capping}

Frequency-capping expressions include all the users whose number of trait realizations is below a desired value. Estos son algunos ejemplos de Right and Wrong:

* Wrong - The expression  includes all users that have realized the trait with the ID "1000" a maximum of five times but also includes users who have not realized the trait. `frequency([1000T]) <= 5` Therefore, Audience Manager does not validate this expression for performance reasons, as it would qualify too many users for the segment.

* Right - If you want to include all users that have realized the trait with the ID "1000" a maximum of five times, add another condition to the expression, to make sure the users have qualified for the trait at least once:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Right- When you need recency/frequency requirements to be less than a specific number of times or days, join that trait to another with an  operator. `AND` Con el ejemplo del primer punto de viñeta, esta expresión pasa a ser válida cuando se une con otra característica, como se muestra aquí: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Right - For advertising frequency-capping use cases, you could create a segment rule similar to this: . `(frequency([1000T] <= 2D) >= 5)` Esta expresión incluye todos los usuarios que han realizado la característica con el ID "1000" en los últimos 2 días al menos cinco veces. Establezca el límite de frecuencia enviando este segmento al servidor de publicidad con un `NOT` conjunto en el segmento en el servidor de publicidad. Este enfoque logra un mayor rendimiento en [!DNL Audience Manager] tanto que sigue cumpliendo el mismo propósito para limitar la frecuencia.

>[!MORE_LIKE_THIS]
>
>* [Controles del Generador de segmentos: Sección de características](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Sintaxis del código utilizada en el Editor de expresiones de segmento](../../features/segments/segment-code-syntax.md)

