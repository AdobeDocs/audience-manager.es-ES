---
description: Este informe devuelve un recuento de frecuencia de toda la información no utilizada recopilada en el inventario y enviada al Audience Manager.
seo-description: Este informe devuelve un recuento de frecuencia de toda la información no utilizada recopilada en el inventario y enviada al Audience Manager.
seo-title: Informe de señales no utilizadas
solution: Audience Manager
title: Informe de señales no utilizadas
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 2%

---


# Informe de señales no utilizadas{#unused-signals-report}

Este informe devuelve un recuento de frecuencia de toda la información no utilizada recopilada en el inventario y enviada al Audience Manager. Para acceder a este informe, vaya a **Análisis > Informes de Audiencia > Otros informes > Señales no utilizadas**.

>[!NOTE]
>
>Si aparece el mensaje &quot;No tiene acceso a los informes de Audiencia&quot;, póngase en contacto con el consultor de Audience Manager o con el Servicio de atención al cliente para que le proporcione el informe.

![Captura de pantalla del informe Señales no utilizadas](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Información general

Una señal es la información de su sitio Web que se pasa a [!DNL Audience Manager] en forma de [pares clave-valor](../../reference/key-value-pairs-explained.md) (por ejemplo, `color=blue, price>100, gender=female`, etc.).

Las señales no utilizadas consisten en datos que se recopilan pero que no se han asignado a una característica. El informe [!UICONTROL Unused Signals] muestra los datos de una tabla por fecha, clave, valor y recuento de frecuencia. Cualquier señal sin asignar que se pase a [!DNL Audience Manager] al menos 100 veces en un día califica para el informe [!UICONTROL Unused Signals].

Revise este informe para identificar las señales huérfanas que se pueden asignar a características nuevas o existentes.

>[!NOTE]
>
>Especifique una clave o un nombre de valor en los campos de búsqueda para limitar los resultados a registros específicos.

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
   <td colname="col1"> <p><b>Garantizar la uniformidad de características o Añadir los valores relacionados a una sola clave</b> </p> </td> 
   <td colname="col2"> <p>Revise el informe para tener en cuenta las diferentes variaciones de valor de una señal en particular. </p> <p>Por ejemplo, supongamos que tiene una característica para el estado "Carolina del Norte" definida en un par clave-valor como <code> c_state = North Carolina</code>. El informe puede ayudarle a encontrar las variantes de nombre y agregarlas a la característica (por ejemplo: <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Otra opción es colocar las variantes de nombre en el informe y reemplazarlas por un valor uniforme en todos los sitios. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Crear nuevas características</b> </p> </td> 
   <td colname="col2"> <p>Revise el informe para ver qué valores nuevos se pasan en una clave en particular. Es posible que desee crear nuevos pares clave-valor basados en estos nuevos valores. </p> <p> <p>Nota:  Verifique el informe dos veces por semana para ver los valores que cambian con frecuencia (por ejemplo: programas, campañas, celebridades, etc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Buscar valores no asignados</b> </p> </td> 
   <td colname="col2"> <p>Revise el informe del número 1. El número 1 de un informe <span class="wintitle"> Señales no utilizadas</span> representa un valor nulo. Esto no es necesariamente malo. Simplemente significa que una clave en particular no tiene una asignación de valores asociada. Cuando vea muchos valores de 1 para una variable importante, consulte con el equipo del sitio para asegurarse de que todas las páginas estén etiquetadas correctamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Prácticas recomendadas

Ejecute y verifique el informe [!UICONTROL Unused Signals]:

* Después de crear una característica o actualizar las reglas de características. Esto ayuda a garantizar que las características y las reglas estén configuradas correctamente. El número 1 en los resultados indica que una nueva característica puede no estar correctamente configurada.
* Bi-semanal o mensual. Las revisiones programadas ayudan a garantizar que las asignaciones de características estén actualizadas.

>[!NOTE]
>
>Al buscar valores no utilizados en el informe, tenga en cuenta las siguientes particularidades. Hay una diferencia en la expresión entre los dos ejemplos siguientes:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Ambos ejemplos muestran una característica que contiene dos pares de clave-valor v y a. La primera expresión se traduce en: la característica contiene la clave v con el valor 1 [!UICONTROL AND NOT] la clave a con el valor 23. La segunda expresión contiene la clave v con el valor 1 [!UICONTROL AND] la clave a con el valor [!UICONTROL NOT EQUAL] 23.
* Teniendo en cuenta las dos expresiones anteriores, supongamos que busca en la [!UICONTROL Unused Signals Report] los valores que se pasan en la clave a con cualquier valor diferente a 23, solo obtendrá resultados en el primer caso porque los valores de la clave no se enviaron EN ABSOLUTO. En el segundo caso, se enviaron valores diferentes a 23, por lo que la clave a no se utiliza.

## Creación de rasgos masivos

Póngase en contacto con el representante de soluciones de socio si necesita crear masivamente muchas características en base a los datos obtenidos del informe [!UICONTROL Unused Signals].
