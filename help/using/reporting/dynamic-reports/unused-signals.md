---
description: Este informe devuelve un recuento Frecuencia de toda la información no utilizada recopilada en su inventario y enviada a Audience Manager.
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

Este informe devuelve un recuento Frecuencia de toda la información no utilizada recopilada en su inventario y enviada a Audience Manager. Para acceder a este informe, navegue hasta **Analytics > Informes de audiencia > Otros informes > Señales no utilizadas**.

>[!NOTE]
>
>Si ve el mensaje &quot;No tiene acceso a los informes de audiencia&quot;, póngase en contacto con su asesor de Audience Manager o con el Servicio de atención al cliente para aprovisionar el informe por usted.

![Captura de pantalla del informe de señales no utilizadas](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Información general

Una señal es la información de su sitio web que [!DNL Audience Manager] se transmite en forma de pares[&#x200B; clave-valor &#x200B;](../../reference/key-value-pairs-explained.md)(por ejemplo, `color=blue, price>100, gender=female`, etc.).

Las señales no utilizadas consisten en datos que usted recopila pero que no se han asignado a un rasgo. El [!UICONTROL Unused Signals] informe muestra los datos en una tabla por fecha, clave, valor y recuento Frecuencia. Cualquier señal no asignada que se pase al [!DNL Audience Manager] menos 100 veces en un día califica para el [!UICONTROL Unused Signals] informe.

Las señales no utilizadas se almacenan durante 45 días y luego se descartan. El informe de señales no utilizadas muestra datos de los últimos 10 días.

Revise este informe para ayudar a identificar las señales huérfanas que se pueden asignar a rasgos nuevos o existentes.

>[!NOTE]
>
>Especifique un nombre de clave o valor en los campos búsqueda para limitar los resultados a registros específicos.

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
   <td colname="col1"> <p><b>Garantizar la uniformidad de los rasgos o añadir valores relacionados con una sola clave</b> </p> </td> 
   <td colname="col2"> <p>Revise el informe para cuenta las diferentes variaciones de valores para una señal en particular. </p> <p>Por ejemplo, supongamos que tiene un rasgo para el estado "Carolina del Norte" definido en un par clave-valor como <code> c_state = North Carolina</code>. El informe puede ayudarle a encontrar variantes de nombres y agregarlas al rasgo (por ejemplo, <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Alternativamente, podría detectar variantes de nombres con el informe y reemplazar aquellas con un valor uniforme en todos los sitios. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Crear Nuevo Características</b> </p> </td> 
   <td colname="col2"> <p>Revise el informe para ver qué nuevos valores se transfieren en una clave determinada. Puede que desee crear nuevos pares de clave-valor basados en estos nuevos valores. </p> <p> <p>Nota: Consulte el informe quincenalmente para ver los valores que cambian con frecuencia (por ejemplo, programas, campañas, celebridades, etc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Buscar valores no asignados</b> </p> </td> 
   <td colname="col2"> <p>Revise el informe para el número 1. El número 1 en un <span class="wintitle"> informe de señales</span> no utilizadas representa un valor nulo. Esto no es necesariamente malo. Simplemente significa que una clave en particular no tiene una asignación de valor asociada. Cuando vea muchos valores 1 para un variable importante, consulte con su sitio equipo para asegurarse de que todas sus páginas estén etiquetado correctamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Prácticas recomendadas

Ejecute y compruebe el [!UICONTROL Unused Signals] informe:

* Después de crear un rasgo o actualizar las reglas de características. Esto ayuda a garantizar que sus rasgos y reglas estén configurados correctamente. El número 1 en los resultados indica que una nueva característica podría no estar configurada correctamente.
* Quincenal o mensual. Las revisiones programadas ayudan a garantizar que las asignaciones de características estén actualizadas.

>[!NOTE]
>
>Cuando busque valores no utilizados en el informe, tenga en cuenta la siguiente particularidad. Hay una diferencia en expresión entre los dos ejemplos siguientes:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Ambos ejemplos muestran un rasgo que contiene dos pares clave-valor v y a. La primera expresión se traduce en: el rasgo contiene la clave v con el valor 1 [!UICONTROL AND NOT] , la clave a con el valor 23. El segundo expresión contiene la clave v con el valor 1 [!UICONTROL AND] , la clave a con el valor [!UICONTROL NOT EQUAL] 23.
* Teniendo en cuenta las dos expresiones diferentes anteriores, supongamos que búsqueda en el Para los valores que se pasan en la [!UICONTROL Unused Signals Report] clave a con cualquier valor diferente de 23, solo obtendrá resultados en el primer caso porque los valores de la clave no se enviaron EN ABSOLUTO. En el segundo caso, se enviaron valores diferentes a 23, por lo que la clave a no está sin usar.

## Creación masiva de rasgos

Póngase en contacto con su representante de Partner Solutions si necesita crear muchas características de forma masiva basándose en los [!UICONTROL Unused Signals] datos obtenidos del informe.
