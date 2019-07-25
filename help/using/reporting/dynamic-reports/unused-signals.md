---
description: Este informe devuelve un recuento de frecuencia de toda la información no utilizada recopilada en el inventario y se envía a Audience Manager.
seo-description: Este informe devuelve un recuento de frecuencia de toda la información no utilizada recopilada en el inventario y se envía a Audience Manager.
seo-title: Informe Señales no utilizadas
solution: Audience Manager
title: Informe Señales no utilizadas
uuid: 04334 a 5 c -3 e 21-44 db-b 971-0 b 4457685 e 9 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Unused Signals Report{#unused-signals-report}

Este informe devuelve un recuento de frecuencia de toda la información no utilizada recopilada en el inventario y se envía a Audience Manager.

<!-- 

c_unused_signals.xml

 -->

## Informe Señales no utilizadas

A signal is information from your website passed in to [!DNL Audience Manager] in the form of [key-value pairs](../../reference/key-value-pairs-explained.md) (e.g., `color=blue, price>100, gender=female`, etc.).

Las señales no utilizadas consisten en datos recopilados pero que no se han asignado a un rasgo. The [!UICONTROL Unused Signals] report shows data in a table by date, key, value, and frequency count. Any unmapped signal passed in to [!DNL Audience Manager] at least 100 times in a day qualifies for the [!UICONTROL Unused Signals] report.

Revise este informe para ayudar a identificar señales huérfanas que pueden asignarse a características nuevas o existentes.

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
   <td colname="col1"> <p><b>Asegurar uniformidad de características o Agregar valores relacionados a una única clave</b> </p> </td> 
   <td colname="col2"> <p>Revise el informe para tener en cuenta diferentes variaciones de valores para una señal en particular. </p> <p>For example, say you have a trait for the state "North Carolina" defined in a key-value pair as <code> c_state = North Carolina</code>. The report can help you find name variants and add those to the trait (e.g., <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Como alternativa, puede asignar nombres a las variantes de nombres con el informe y sustituirlos por un valor uniforme en todos los sitios. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Crear nuevas características</b> </p> </td> 
   <td colname="col2"> <p>Revise el informe para ver qué valores nuevos pasan en una clave en particular. Es posible que desee crear nuevos pares clave-valor basados en estos nuevos valores. </p> <p> <p>Nota: Verifique el informe trimestral de los valores que cambian con frecuencia (por ejemplo: muestra, campañas, celebridades, etc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Buscar valores sin asignar</b> </p> </td> 
   <td colname="col2"> <p>Revise el informe del número 1. The number 1 in an <span class="wintitle"> Unused Signals</span> report represents a null value. Esto no es necesariamente malo. Simplemente significa que una clave en particular no tiene una asignación de valor asociada. Cuando vea muchos valores de 1 para una variable importante, consulte con el equipo del sitio para asegurarse de que todas las páginas estén etiquetadas correctamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Prácticas recomendadas

Run and check the [!UICONTROL Unused Signals] report:

* Después de crear un rasgo o de actualizar las reglas. Esto ayuda a garantizar que las características y las reglas estén configuradas correctamente. El número 1 en resultados indica que es posible que un nuevo rasgo no esté configurado correctamente.
* Semanal o mensual. Las revisiones programadas ayudan a garantizar que las asignaciones de características estén actualizadas.

>[!NOTE]
>
>Al buscar valores no utilizados en el informe, considere la siguiente particularidad. Hay una diferencia entre los dos ejemplos siguientes:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Both examples show a trait which contains two key-value pairs v and a. The first expression translates into: the trait contains key v with the value 1 [!UICONTROL AND NOT] the key a with the value 23. The second expression contains key v with the value 1 [!UICONTROL AND] the key a with the value [!UICONTROL NOT EQUAL] 23.
* Considering the two different expressions above, let's say you search in the [!UICONTROL Unused Signals Report] for the values that get passed on key a with any value different than 23, you'll only obtain results in the first case because values for key were not sent AT ALL. En el segundo caso, se enviaban valores diferentes a 23, por lo que la clave no se utilizaba.

## Creación de rasgos masivos

Contact your Partner Solutions representative if you need to bulk create a lot of traits based on data obtained from the [!UICONTROL Unused Signals] report.
