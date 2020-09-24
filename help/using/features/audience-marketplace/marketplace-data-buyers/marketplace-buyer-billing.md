---
description: Los compradores de datos Audience Marketplace aceptan informar de todas las impresiones de publicidad servidas utilizando las características contenidas en la fuente de datos con el precio de costo por cada mil impresiones de publicidad (CPM). El uso de CPM vence el quinto día de cada mes natural e incluye datos del mes anterior. Los suscriptores de tarifa fija no necesitan notificar el uso.
seo-description: Los compradores de datos Audience Marketplace aceptan informar de todas las impresiones de publicidad servidas utilizando las características contenidas en la fuente de datos con el precio de costo por cada mil impresiones de publicidad (CPM). El uso de CPM vence el quinto día de cada mes natural e incluye datos del mes anterior. Los suscriptores de tarifa fija no necesitan notificar el uso.
seo-title: Facturación para compradores de fuentes de datos
solution: Audience Manager
title: Facturación para compradores de fuentes de datos
keywords: Segment-level Reporting, segment-level, segment level
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: dac08e9a31cb80b048013d95b7a617e4fb68e2fe
workflow-type: tm+mt
source-wordcount: '2027'
ht-degree: 1%

---


# Facturación para compradores de fuentes de datos {#billing-for-data-feed-buyers}

Los compradores de datos Audience Marketplace aceptan informar de todas las impresiones de publicidad servidas utilizando las características contenidas en la fuente de datos con el precio de costo por cada mil impresiones de publicidad ([!DNL CPM]). [!DNL CPM] el uso vence el quinto día de cada mes natural e incluye datos del mes anterior. Los suscriptores de tarifa fija no necesitan notificar el uso.

<br> 

## Cómo informar del uso de CPM {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] los compradores de datos aceptan informar de todas las impresiones de publicidad servidas utilizando las características contenidas en la fuente de datos con el precio de costo por cada mil impresiones de publicidad ([!DNL CPM]). [!DNL CPM] el uso vence el día 5 de cada mes natural e incluye los datos del mes anterior. Los suscriptores de tarifa fija no necesitan notificar el uso.

[!UICONTROL Audience Marketplace] ofertas dos formas de informar sobre el uso [!DNL CPM] :

* **Sistema de informes** de nivel de segmento: es el método de sistema de informes de [!DNL CPM] uso recomendado. Cuando se informa sobre [!DNL CPM] el uso en el nivel de segmento, la sección de sistemas de informes en el nivel de fuente de datos se rellena automáticamente con las cantidades de uso correspondientes, en función de los algoritmos descritos en Atribución de [costos para fuentes](#cost-attribution)de datos CPM.
* **Sistema de informes** de nivel de fuente de datos: este método requiere que informe de forma individual el uso [!DNL CPM] de cada fuente de datos, en función de los algoritmos descritos en Atribución de [costos para fuentes](#cost-attribution)de datos CPM. Sin embargo, este método es más tedioso y propenso a errores que el sistema de informes a nivel de segmento.

<br> 

## Informe del uso de CPM en el nivel de segmento {#segment-level-report}

La [!UICONTROL Segment Usage] ficha le permite informar sobre el uso de nivel de segmento, al tiempo que muestra los segmentos agrupados por los destinos a los que están asignados.

Después del uso del sistema de informes [!DNL CPM] en el nivel de segmento, [!UICONTROL Audience Marketplace] asigna automáticamente el uso correcto a las fuentes de datos correspondientes, según la atribución de [costo para las fuentes](#cost-attribution)de datos CPM.

Para informar [!DNL CPM] sobre el uso en el nivel de segmento:

1. Vaya a **[!UICONTROL Audience Marketplace > Payables]**.
1. Seleccione la **[!UICONTROL Segment Usage]** ficha.
1. Complete el uso de los segmentos. Puede utilizar el [!UICONTROL Search] cuadro para filtrar los segmentos si sólo necesita informar sobre el uso de algunos de ellos.
1. Haga clic **[!UICONTROL Edit Segments Usage]**.
1. Introduzca la cantidad de uso [!DNL CPM] en la [!UICONTROL Usage] columna.
1. Haga clic **[!UICONTROL Save]** cuando haya terminado y revise el cuadro de diálogo de confirmación.

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. Haga clic **[!UICONTROL Confirm]**.

Consulte también nuestra demostración en vídeo de cómo puede informar sobre el uso de nivel de segmento:

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## Informe del uso de CPM en el nivel de fuente de datos {#feed-level-report}

El sistema de informes del nivel de fuente de datos es más tedioso y propenso a errores, ya que debe calcular [!DNL CPM] el uso de cada fuente de datos de forma individual. Le recomendamos que [informe del uso de CPM en el nivel](#segment-level-report) de segmento.

Para informar [!DNL CPM] sobre el uso en el nivel de segmento:

1. Vaya a **[!UICONTROL Audience Marketplace > Payables]**.
2. Seleccione la **[!UICONTROL Feed Usage]** ficha.
3. Utilice el [!UICONTROL Search] cuadro para filtrar las fuentes de datos e identificar las que necesita para las que debe informar el uso.
4. Haga clic **[!UICONTROL Edit Feeds Usage]**.
5. Calcule el uso [!DNL CPM] de cada fuente de datos en función de la atribución de [costo de las fuentes](#cost-attribution)de datos de CPM e introdúzcala en la [!UICONTROL Usage] columna.
6. Haga clic **[!UICONTROL Save]** cuando haya terminado y revise el cuadro de diálogo de confirmación.

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. Haga clic **[!UICONTROL Confirm]**.

<br> 

## Sistema de informes masivo

Para reducir los errores y la sobrecarga durante el uso del sistema de informes [!DNL CPM] , puede utilizar la opción de sistema de informes masivo para descargar un [!DNL CSV] archivo que contenga las fuentes de datos y los segmentos, completar el uso y volver a cargarlo a [!DNL Audience Manager]. Puede utilizar el sistema de informes masivo para informar sobre el uso de fuentes y segmentos.

Para actualizar [!DNL CPM] el uso de forma masiva:

1. Vaya a **[!UICONTROL Audience Marketplace > Payables]**.
1. Seleccione la ficha **[!UICONTROL Feed Usage]** o **[!UICONTROL Segment Usage]** , según el tipo de sistema de informes que desee actualizar.
1. Haga clic en **[!UICONTROL Edit Feeds Usage]** o **[!UICONTROL Edit Segments Usage]**.
1. Haga clic **[!UICONTROL download the current usage]** para asegurarse de que utiliza un archivo CSV válido.
1. Abra el archivo en el equipo y rellene el informe de uso.
1. Haga clic en **[!UICONTROL Choose a CSV file]** para cargar el informe de uso actualizado.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] valida el archivo en cuanto lo cargue y le preguntará si detecta algún error en el archivo.

<br> 

### Errores de validación de Sistema de informes masivo

| Mensaje de error | Descripción | Se corrigió un problema que hacía que se mostrara |
| ------------- | -------------| -----|
| Entrada no válida | [!DNL Audience Manager] se ha detectado un cambio en el esquema del [!DNL CSV] archivo, como la falta de columnas o cambios en los títulos de columna. | Evite cambiar la estructura de la tabla. |
| No encontrado | Por [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] no pudo identificar la [!UICONTROL Segment ID] combinación y [!UICONTROL Destination ID] . Por [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] no pudo identificar la combinación [!UICONTROL Data Provider Name], [!UICONTROL Feed Name]y [!UICONTROL Use Case] . | Para [!UICONTROL Segment Level Reporting]comprobar la validez de la combinación [!UICONTROL Segment ID] y [!UICONTROL Destination ID] . Para [!UICONTROL Feed Level Reporting]comprobar la validez de la combinación [!UICONTROL Data Provider Name], [!UICONTROL Feed Name]y [!UICONTROL Use Case] . |
| Registros de duplicado encontrados | [!DNL Audience Manager] registros de duplicado detectados con valores de impresión diferentes. | Revise el informe y asegúrese de que no informa de diferentes valores de uso para la misma fuente de datos o segmento. |
| Valores no admitidos | [!DNL Audience Manager] valores no numéricos detectados en la [!DNL Audience Manager] columna. | Revise el informe y asegúrese de introducir solamente valores numéricos en la [!DNL Audience Manager] columna. |
| Faltan encabezados para campos obligatorios | [!DNL Audience Manager] se detectaron encabezados de tabla que faltaban en los campos obligatorios. Por [!UICONTROL Segment Level Reporting], los campos obligatorios son: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. Por [!UICONTROL Feed Level Reporting], los campos obligatorios son: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name],  [!UICONTROL Use Case] | Revise el informe y asegúrese de que los encabezados de tabla no se hayan alterado. |

>[!NOTE]
>La eliminación de filas del [!DNL CSV] informe de uso no tiene ningún efecto en el informe de uso existente. [!DNL Audience Manager] solo procesa los campos incluidos en el informe.

<br> 

## [!DNL CPM] Prácticas recomendadas de sistema de informes

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recomendaciones </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Informar siempre del número total de impresiones</b> </p> </td> 
   <td colname="col2"> <p>Para totales de impresión CPM: </p>
   <p> Informar el número total de impresiones, sin usar decimales. El Audience Manager calcula automáticamente el CPM en función del número total de informes.</p><p>Si necesita informar 1.234.567 impresiones, informe exactamente así. No es necesario dividir el número total de impresiones en 1000 para calcular el CPM.</p><p>Las características utilizadas para optimizar el contenido web o de la aplicación (Optimización de contenido) mediante herramientas como Adobe Target o un destino de Analytics no contribuyen a los totales de uso de los planes de CPM. Los proveedores de datos generalmente reciben una compensación por la optimización del contenido mediante planes de tarifa fija.</p><p>Consulte Atribución <a href="#cost-attribution">de costos para fuentes</a> de datos CPM para obtener más información. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Mantener el intervalo de sistema de informes mensual</b> </p> </td> 
   <td colname="col2"> <p>El sistema de informes se cierra después del 5 de cada mes. Si no puede informar sobre el uso de CPM para entonces, debe agregar esa cantidad al informe para el mes siguiente. Por ejemplo: supongamos que utiliza 1000 impresiones en octubre, que no cumple el plazo de sistema de informes de octubre y que utiliza 1000 impresiones en noviembre. En este caso, se informa del total de octubre y noviembre (2000) en diciembre, entre el 1 y el 5.</p><p><b>Sugerencia</b>: Siempre debe intentar informar del uso de CPM del mes anterior entre el primer y el quinto día del mes siguiente.</p><p>Puede informar sobre el uso de CPM hasta el quinto del nuevo mes calendario, pero no se recomienda. El uso de CPM de sistema de informes antes del 5 de cada mes proporciona al Audience Manager tiempo para comprobar y procesar los datos.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Atribución de costos para fuentes de datos CPM {#cost-attribution}

En [!UICONTROL Audience Marketplace] debe informar automáticamente las cantidades de impresiones cada mes, para cada uno de los segmentos. Se recomienda el uso de sistemas de informes [!DNL CPM] en el nivel de segmento, de modo que la atribución de costes se realice automáticamente.

<!-- marketplace_cpm_billing.xml -->

### Resumen de facturación {#billing-summary}

Debe enviar las cantidades de impresiones [!DNL CPM] de fuentes de datos entre el primer y el quinto día de cada mes natural. Para hacerlo correctamente, le recomendamos que [informe del uso de CPM en el nivel](#segment-level-report)de segmento.

>[!TIP]
>Cuando se informa [!DNL CPM] del uso a nivel de segmento, la sección de sistemas de informes a nivel de fuente de datos se rellena automáticamente con las cantidades de uso correspondientes.

Si es necesario, [!UICONTROL Report CPM Usage at Data Feed Level]debe compilar individualmente todas las impresiones entregadas para cada fuente en el mes natural anterior y registrarlas según la asignación de facturación descrita en este artículo.

Después de informar [!DNL CPM] el número del mes natural anterior, [!DNL Adobe] realizará lo siguiente:

* Cree una factura y una factura según la [!DNL CPM] tasa de cada fuente de datos suscrita.
* Las tarifas que deben pagar los proveedores de datos (vendedores) en función del uso [!DNL CPM] que haya informado.

>[!IMPORTANT]
>
>Como comprador, todos los totales de impresión comunicados deben ser verdaderos y exactos. Si no informa de los totales de impresión antes del quinto día de cada mes, debe incluir los totales del mes no informado en el mes siguiente.

<br> 

## Asignar impresiones a nivel de fuente en función de las reglas de cualificación de características {#assign-impressions}

El caso de [!UICONTROL Activation] uso le permite utilizar características en la fuente de datos correspondiente para crear segmentos en el Generador [de](../../../features/segments/segment-builder.md) segmentos y asignar dichos segmentos a un destino. Los operadores booleanos [!UICONTROL AND][!UICONTROL OR]y [!UICONTROL NOT] permiten definir las condiciones para la calificación de rasgos y segmentos.

Al [informar del uso de CPM en el nivel](#feed-level-report)de fuente de datos, debe asignar las impresiones proporcionalmente para cada fuente de datos, según los [!DNL Boolean] operadores utilizados en las reglas de calificación de rasgos. La siguiente tabla lista cómo asignar correctamente impresiones según la regla booleana o el tipo de característica.

>[!TIP]
>
> [Informar sobre el uso de CPM en el nivel](#segment-level-report) de segmento para que el sistema de informes del nivel de fuente de datos lo realice automáticamente el Audience Manager.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo o lógica de calificación de regla </th> 
   <th colname="col2" class="entry"> Distribución de facturación </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Y</span> </p> </td> 
   <td colname="col2"> <p>Aplique el 100 % de los totales de impresión entregados a todas las características del proveedor en un segmento basado en reglas que utilice una condición booleana <span class="wintitle"> AND</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> O</span> </p> </td> 
   <td colname="col2"> <p>Aplique una asignación ponderada de los totales de impresión entregados a todas las características del proveedor en un segmento basado en reglas que utilice una condición booleana OR. La asignación ponderada se calcula mediante la fórmula siguiente:</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NO</span> </p> </td> 
   <td colname="col2"> <p>Aplique el 100 % de los totales de impresión entregados a todas las características del proveedor en un segmento basado en reglas que utilice una condición booleana <span class="wintitle"> NOT</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segmentos algorítmicos </p> </td> 
   <td colname="col2"> <p>Aplique el 100 % de los totales de impresión entregados a todas las fuentes del proveedor en un segmento que contenga características algorítmicas. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Ejemplos de facturación {#billing-examples}

Los ejemplos siguientes pretenden ilustrar cómo se realiza la asignación de [!DNL CPM] uso en el nivel de fuente de datos.

>[!IMPORTANT]
>Le recomendamos que [informe del uso de CPM en el nivel](#segment-level-report) de segmento para que este proceso se realice automáticamente.

Consideremos el siguiente escenario:

![facturación-ejemplos](assets/billing-examples.png)

<br> 

### Caso 1: Segmentos con reglas de cualificación AND

Este segmento contiene 3 características de proveedores de datos independientes. Dado que la calificación de segmentos se basa en una [!UICONTROL AND] condición, los visitantes deben realizar las características de las tres fuentes para poder optar al segmento.

![](assets/billing-segment-and.png)

Con una [!UICONTROL AND] condición, debe asignar el 100 % de las impresiones recibidas durante el mes a los tres proveedores de datos. En la [!UICONTROL Audience Marketplace > Payables] sección, usted atribuye a cada proveedor 1.000.000 impresiones.

Este ejemplo se aplica a segmentos que utilizan [!DNL Boolean] operadores [!UICONTROL NOT] o a segmentos que contienen características algorítmicas.

<br> 

### Caso 2: Segmentos con reglas de calificación O

Este segmento contiene 3 características de proveedores de datos independientes. Dado que la calificación de segmentos se basa en una [!UICONTROL OR] condición, los visitantes deben realizar al menos una de las tres características para poder optar al segmento.

No podemos saber qué rasgo es responsable de una impresión porque la calificación se basa en una [!UICONTROL OR] condición. Como resultado, en la [!UICONTROL Audience Marketplace > Payables] sección se atribuye a cada proveedor una asignación ponderada de las impresiones totales, en función de la población de características.

![facturar-segmento-o](assets/billing-segment-or.png)

<br> 

### Caso 3: Segmentos con casos de uso de modelado y Activación

En este ejemplo se describe la atribución en función de dos casos de uso de fuente de datos: modelado y Activación. En el ejemplo, estamos viendo dos proveedores de datos, con la siguiente información:

![fuente de datos](assets/feed-use-cases.png)

En la tabla siguiente, el segmento X contiene dos características, T1 y T2, con la regla de segmento T1 O T2, donde:

* T1 es una característica de la fuente de datos A;
* T2 es una característica algorítmica modelada según características de terceros de Fuente de datos A y Fuente de datos B.

El segmento se asigna a un destino y se introducen 1.000.000 impresiones para este segmento en un mes, mediante el Sistema de informes [de nivel de](#segment-level-report)segmento.

De estas 1,000,000 impresiones:

* T1 representa el 40% de la población de segmentos, lo que se traduce en 400.000 impresiones para la fuente A.
* T2 representa el 60% de la población de segmentos, lo que se traduce en 600.000 impresiones para las fuentes A y B.

A nivel de fuente de datos, la manera en que se asignan las impresiones es:

* Fuente de datos A recibe 600.000 impresiones de la característica T2 (que se modela en características de Fuente de datos A y Fuente de datos B, por lo que ambas reciben las impresiones) y 400.000 impresiones de la característica T1 (que es una característica de Fuente de datos A), que ascienden a un total de 1.000.000 impresiones.
* La fuente de datos B recibe 600.000 impresiones de la característica T2 (ver la explicación más arriba) y 0 impresiones de la característica T1.

El desglose por fuente de datos y caso de uso es el siguiente:

![feed-break](assets/feed-breakdown-alt.png)

<br> 

## Asignación de facturación e impresión para fuentes de datos de tarifa fija {#billing-flat-fee}

Una fuente de datos de tarifa fija le factura una cantidad fija cada mes, independientemente del momento en que la suscripción inicio o del número de impresiones que utilice. Las tarifas no se prorratean para el uso parcial del mes o los intervalos. Al igual que con la facturación de CPM, los Adobes generarán una factura y le facturarán a la tarifa mensual fija de sus fuentes de datos suscritas.

Por ejemplo, supongamos que decidió activar ciertas características en una fuente a mediados del mes. Se le facturará a la tarifa mensual completa independientemente de cuándo inició la suscripción o activó características específicas.