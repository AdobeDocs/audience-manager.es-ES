---
description: En el Generador de segmentos, la actualización y la frecuencia le permiten segmentar a los visitantes en función de las acciones que se producen o se repiten a lo largo de un intervalo diario determinado.
seo-description: En el Generador de segmentos, la actualización y la frecuencia le permiten segmentar a los visitantes en función de las acciones que se producen o se repiten a lo largo de un intervalo diario determinado.
seo-title: Fecha de adquisición más frecuente y frecuencia.
solution: Audience Manager
title: Fecha de adquisición más frecuente y frecuencia.
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: 'Segmentos '
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 3%

---

# Fecha de adquisición más frecuente y frecuencia.{#recency-and-frequency}

En [!UICONTROL Segment Builder], la actualización y la frecuencia le permiten segmentar a los visitantes en función de las acciones que se producen o se repiten a lo largo de un intervalo diario determinado.

El Audience Manager define [!DNL recency] y [!DNL frequency] de la siguiente manera:

* **[!UICONTROL Recency]:** La fecha en la que un usuario ha visto o cumplido los requisitos para una (o más)  [!UICONTROL traits].
* **[!UICONTROL Frequency]:** Frecuencia a la que un usuario ha visto o calificado para uno o más  [!UICONTROL traits].

[!UICONTROL Recency] La  [!UICONTROL Frequency] configuración de y le ayuda a segmentar a los visitantes en función de su nivel de interés real (o percibido) en un sitio, una sección o un creativo determinado. Por ejemplo, los usuarios que cumplen los requisitos para un segmento con requisitos de alta actualización y frecuencia pueden estar más interesados en un sitio o producto que los usuarios que visitan con menos frecuencia o con menos frecuencia.

## Ubicación de la configuración [!UICONTROL Recency and Frequency] {#location}

En [!UICONTROL Segment Builder], las configuraciones [!UICONTROL Recency] y [!UICONTROL Frequency] se encuentran en la sección [!UICONTROL Basic View] del panel [!UICONTROL Traits]. Haga clic en el icono del reloj para mostrar estos controles.

![](assets/recency_frequency.png)

## Limitaciones y reglas {#limitations-rules}

Revise y comprenda estos límites y reglas cuando quiera aplicar actualización y frecuencia a características en sus segmentos.

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
   <td colname="col1"> <p> <b>Tipos de rasgos</b> </p> </td> 
   <td colname="col2"> <p>Puede aplicar controles de actualización solo a características basadas en reglas y de carpeta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Rasgos de terceros</b> </p> </td> 
   <td colname="col2"> <p>No puede establecer reglas de actualización en rasgos individuales de terceros o grupos de rasgos que contengan rasgos de terceros. La actualización y la frecuencia solo se aplican a sus propios rasgos. </p> </td> 
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
   <td colname="col1"> <p> <b>Rasgos de terceros</b> </p> </td> 
   <td colname="col2"> <p>No puede establecer reglas de frecuencia en rasgos individuales de terceros o grupos de rasgos que contengan rasgos de terceros. La actualización y la frecuencia solo se aplican a sus propios rasgos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tipos de rasgos</b> </p> </td> 
   <td colname="col2"> <p>Puede aplicar controles de frecuencia solo a características de carpeta y basadas en reglas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Requisitos de actualización</b> </p> </td> 
   <td colname="col2"> <p>Puede configurar los requisitos de frecuencia <i>sin</i> configurar los requisitos de actualización. Establezca un valor de frecuencia y deje el campo actualización en blanco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Reglas de combinación de perfiles</b> </p> </td> 
   <td colname="col2"> <p>Consulte <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Frecuencia de rasgos, gráficos de dispositivos externos y reglas de combinación de perfiles</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplos de actualización {#recency-examples}

A continuación se muestran dos ejemplos de cómo funciona la actualización, en función de la selección que realice en la interfaz de usuario:

### Uso de un operador menor o igual que (&lt;=)

![Less than-equal-to](assets/less-than-equal-to.png)

En este ejemplo, se selecciona el operador &lt;=, como se muestra en la captura de pantalla. Esto califica al usuario para [!UICONTROL segment] si cumple los requisitos para cualquiera de los tres [!UICONTROL traits] como mínimo tres veces en los últimos cinco días. La línea de tiempo siguiente muestra la calificación [!UICONTROL segment] en el momento en que se crea la [!UICONTROL segment], el 1 de octubre y diez días después.

![Últimos cinco días](assets/last-5-days.png)

### Uso de un operador bueno o igual que (=>)

![Bueno-than-equal-to](assets/greater-than-equal-to.png)

En este ejemplo, se selecciona el operador => , como se muestra en la captura de pantalla. Esto califica al usuario para el [!UICONTROL segment] si cumple los requisitos para cualquiera de los tres [!UICONTROL traits] un mínimo de tres veces en cualquier momento entre su primera calificación en la plataforma del Audience Manager y el tiempo de corte hace cinco días. La línea de tiempo siguiente muestra la calificación [!UICONTROL segment] en el momento en que se crea la [!UICONTROL segment], el 1 de octubre y diez días después.

![Clasificación anterior](assets/earlier-qualification.png)


## Ejemplos de restricción de frecuencia {#frequency-capping}

Las expresiones de límite de frecuencia incluyen todos los usuarios cuyo número de [!UICONTROL trait] realizaciones es inferior al valor deseado. Estos son algunos ejemplos de Right y Wrong :

* Incorrecto: la expresión `frequency([1000T]) <= 5` incluye a todos los usuarios que han realizado el [!UICONTROL trait] con el ID &quot;1000&quot; un máximo de cinco veces, pero también incluye a los usuarios que no han realizado el [!UICONTROL trait]. Por lo tanto, Audience Manager no valida esta expresión por motivos de rendimiento, ya que calificaría a demasiados usuarios para el [!UICONTROL segment].

* Derecha: Si desea incluir a todos los usuarios que han realizado el [!UICONTROL trait] con el ID &quot;1000&quot; un máximo de cinco veces, agregue otra condición a la expresión para asegurarse de que los usuarios hayan cumplido los requisitos para el [!UICONTROL trait] al menos una vez:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Derecha: cuando necesite que los requisitos de actualización y frecuencia sean inferiores a un número específico de veces o días, una esa [!UICONTROL trait] a otra con un operador `AND`. Con el ejemplo del primer punto de viñeta, esta expresión es válida cuando se une con otro [!UICONTROL trait] como se muestra aquí: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Derecha: En los casos de uso de restricción de frecuencia de publicidad, puede crear una regla [!UICONTROL segment] similar a esta: `(frequency([1000T] <= 2D) >= 5)`. Esta expresión incluye todos los usuarios que han realizado el [!UICONTROL trait] con el ID &quot;1000&quot; en los últimos 2 días al menos cinco veces. Establezca el límite de frecuencia enviando este [!UICONTROL segment] al servidor de publicidad con un `NOT` configurado en el [!UICONTROL segment] en el servidor de publicidad. Este enfoque logra un rendimiento bueno en [!DNL Audience Manager] mientras sigue cumpliendo el mismo propósito para limitar la frecuencia.

>[!MORELIKETHIS]
>
>* [Controles del Generador de segmentos: Sección Características](../../features/segments/segment-builder.md#segment-builder-controls-traits)
* [Sintaxis del código utilizada en el Editor de Expresiones de segmentos](../../features/segments/segment-code-syntax.md)

