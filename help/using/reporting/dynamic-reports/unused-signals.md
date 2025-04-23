---
description: Este informe devuelve un recuento de frecuencia de toda la información no utilizada recopilada en el inventario y enviada a Audience Manager.
seo-description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-title: Unused Signals Report
solution: Audience Manager
title: Informe de señales no utilizadas
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Overlap Reports
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: 9c980b8fd5c3cb6ba7b3031726da726ee5caeec6
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 1%

---

# Informe de señales no utilizadas{#unused-signals-report}

Este informe devuelve un recuento de frecuencia de toda la información no utilizada recopilada en el inventario y enviada a Audience Manager. Para acceder a este informe, vaya a **Analytics > Informes de audiencia > Otros informes > Señales no utilizadas**.

>[!NOTE]
>
>Si ve el mensaje &quot;No tiene acceso a los informes de audiencia&quot;, póngase en contacto con su asesor de Audience Manager o con el servicio de atención al cliente para que le faciliten el informe.

![Captura de pantalla del informe de señales no utilizadas](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Información general

Una señal es información del sitio web que se pasó a [!DNL Audience Manager] en forma de [pares clave-valor](../../reference/key-value-pairs-explained.md) (por ejemplo, `color=blue, price>100, gender=female`, etc.).

Las señales no utilizadas consisten en datos que recopila, pero que no se han asignado a una característica. El informe [!UICONTROL Unused Signals] muestra los datos de una tabla por fecha, clave, valor y recuento de frecuencia. Cualquier señal sin asignar que se pase a [!DNL Audience Manager] al menos 100 veces en un día califica para el informe [!UICONTROL Unused Signals].

Las señales que no se utilicen se almacenan durante 45 días y luego se descartan. El informe de señales no utilizadas muestra datos de los últimos 10 días.

Revise este informe para identificar las señales huérfanas que pueden asignarse a rasgos nuevos o existentes.

>[!NOTE]
>
>Especifique un nombre de clave o valor en los campos de búsqueda para limitar los resultados a registros específicos.

## Casos de uso

<table id="table_E5EE0EC078E14EF4B197243488517A2D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ejemplos </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Garantizar la uniformidad de rasgos o agregar valores relacionados a una sola clave</b> </p> </td> 
   <td colname="col2"> <p>Revise el informe para tener en cuenta las diferentes variaciones de valor de una señal en particular. </p> <p>Por ejemplo, supongamos que tiene un rasgo para el estado "Carolina del Norte" definido en un par clave-valor como <code> c_state = North Carolina</code>. El informe puede ayudarle a encontrar variantes de nombre y agregarlas al rasgo (por ejemplo, <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Alternativamente, puede identificar variantes de nombre con el informe y reemplazarlas con un valor uniforme en todos los sitios. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Crear nuevas características</b> </p> </td> 
   <td colname="col2"> <p>Revise el informe para ver qué nuevos valores se pasan en una clave determinada. Es posible que desee crear nuevos pares de clave-valor basados en estos nuevos valores. </p> <p> <p>Nota: Compruebe el informe cada dos semanas para ver si hay valores que cambien con frecuencia (por ejemplo, programas, campañas, famosos, etc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Buscar valores sin asignar</b> </p> </td> 
   <td colname="col2"> <p>Revise el informe para el número 1. El número 1 en un informe <span class="wintitle"> señales sin usar</span> representa un valor nulo. Esto no es necesariamente malo. Simplemente significa que una clave en particular no tiene una asignación de valor asociada. Cuando vea muchos valores de uno para una variable importante, póngase en contacto con el equipo del sitio para asegurarse de que todas las páginas estén etiquetadas correctamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Prácticas recomendadas

Ejecute y compruebe el informe [!UICONTROL Unused Signals]:

* Después de crear un rasgo o actualizar las reglas de rasgos. Esto ayuda a garantizar que los rasgos y las reglas se hayan configurado correctamente. El número 1 en los resultados indica que es posible que un nuevo rasgo no se haya configurado correctamente.
* Cada dos semanas o cada mes. Las revisiones programadas ayudan a garantizar que las asignaciones de características estén actualizadas.

>[!NOTE]
>
>Cuando busque valores no utilizados en el informe, tenga en cuenta la siguiente particularidad. Hay una diferencia en la expresión entre los dos ejemplos siguientes:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23)
* Ambos ejemplos muestran un rasgo que contiene dos pares clave-valor v y a. La primera expresión se traduce como: el rasgo contiene la clave v con el valor 1 [!UICONTROL AND NOT] y la clave a con el valor 23. La segunda expresión contiene la clave v con el valor 1 [!UICONTROL AND] la clave a con el valor [!UICONTROL NOT EQUAL] 23.
* Teniendo en cuenta las dos expresiones diferentes anteriores, supongamos que busca en [!UICONTROL Unused Signals Report] los valores que se pasan en la clave a con cualquier valor distinto de 23, solo obtendrá resultados en el primer caso, ya que los valores de la clave no se enviaron en absoluto. En el segundo caso, se han enviado valores diferentes de 23, por lo que la clave a no se utiliza.

## Creación de rasgos en lote

Póngase en contacto con su representante de Soluciones para socios si necesita crear de forma masiva muchas características basadas en los datos obtenidos del informe [!UICONTROL Unused Signals].
