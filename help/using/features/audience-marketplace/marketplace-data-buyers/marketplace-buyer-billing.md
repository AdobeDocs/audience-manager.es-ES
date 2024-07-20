---
description: Los compradores de datos de Audience Marketplace aceptan informar de todas las impresiones de publicidad servidas mediante las características incluidas en la fuente de datos con un precio de coste por cada mil impresiones de publicidad (CPM). El uso de CPM vence el quinto día de cada mes calendario e incluye datos del mes anterior. Los suscriptores de tarifa plana no necesitan informar sobre el uso.
seo-description: Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions (CPM) basis. CPM usage is due on the 5th day of each calendar month and includes data for previous month. Flat fee subscribers do not need to report usage.
seo-title: Billing for Data Feed Buyers
solution: Audience Manager
title: Facturación para compradores de fuentes de datos
keywords: Informes de nivel de segmento, nivel de segmento, nivel de segmento
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2029'
ht-degree: 0%

---

# Facturación para compradores de fuentes de datos {#billing-for-data-feed-buyers}

Los compradores de datos del Audience Marketplace aceptan informar de todas las impresiones de publicidad servidas mediante las características incluidas en la fuente de datos con un precio de coste por cada mil impresiones de publicidad ([!DNL CPM]). El uso de [!DNL CPM] vence el quinto día de cada mes calendario e incluye datos del mes anterior. Los suscriptores de tarifa plana no necesitan informar sobre el uso.

<br> 

## Cómo informar sobre el uso de CPM {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] compradores de datos aceptan informar de todas las impresiones de publicidad servidas mediante los rasgos contenidos en la fuente de datos con un precio de coste por cada mil impresiones de publicidad ([!DNL CPM]). El uso de [!DNL CPM] vence el día 5 de cada mes calendario e incluye datos del mes anterior. Los suscriptores de tarifa plana no necesitan informar sobre el uso.

[!UICONTROL Audience Marketplace] ofrece dos maneras de informar sobre el uso de [!DNL CPM]:

* **Informes de nivel de segmento**: este es el método de informes de uso recomendado de [!DNL CPM]. Cuando se informa del uso de [!DNL CPM] en el nivel de segmento, la sección de informes en el nivel de fuente de datos se completa automáticamente con las cantidades de uso correspondientes, según los algoritmos descritos en [Atribución de costos para fuentes de datos de CPM](#cost-attribution).
* **Informes a nivel de fuente de datos**: este método requiere que informe individualmente del uso de [!DNL CPM] para cada fuente de datos, en función de los algoritmos descritos en [Atribución de costos para fuentes de datos CPM](#cost-attribution). Sin embargo, este método es más tedioso y propenso a errores que los informes de nivel de segmento.

<br> 

## Informe de uso de CPM en el nivel de segmento {#segment-level-report}

La pestaña [!UICONTROL Segment Usage] le permite informar sobre el uso a nivel de segmento, mientras muestra los segmentos agrupados por los destinos a los que están asignados.

Después de informar sobre el uso de [!DNL CPM] en el nivel de segmento, [!UICONTROL Audience Marketplace] asigna automáticamente el uso correcto a las fuentes de datos correspondientes, según la [Atribución de costos para las fuentes de datos de CPM](#cost-attribution).

Para informar sobre el uso de [!DNL CPM] en el nivel de segmento:

1. Ir a **[!UICONTROL Audience Marketplace > Payables]**.
1. Seleccione la ficha **[!UICONTROL Segment Usage]**.
1. Complete el uso de los segmentos. Puede usar el cuadro [!UICONTROL Search] para filtrar los segmentos si solo necesita informar del uso de algunos de ellos.
1. Haga clic en **[!UICONTROL Edit Segments Usage]**.
1. Escriba la cantidad de uso [!DNL CPM] en la columna [!UICONTROL Usage].
1. Haga clic en **[!UICONTROL Save]** cuando haya terminado y revise el cuadro de diálogo de confirmación.

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. Haga clic en **[!UICONTROL Confirm]**.

Consulte también nuestro vídeo de demostración sobre cómo informar del uso a nivel de segmento:

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## Uso de Report CPM en el nivel de fuente de datos {#feed-level-report}

Los informes de nivel de fuente de datos son un proceso más tedioso y propenso a errores, ya que debe calcular individualmente el uso de [!DNL CPM] para cada fuente de datos. Le recomendamos que [Informe de uso de CPM en el nivel de segmento](#segment-level-report).

Para informar sobre el uso de [!DNL CPM] en el nivel de segmento:

1. Ir a **[!UICONTROL Audience Marketplace > Payables]**.
2. Seleccione la ficha **[!UICONTROL Feed Usage]**.
3. Utilice la casilla [!UICONTROL Search] para filtrar las fuentes de datos e identificar las que necesita utilizar en los informes.
4. Haga clic en **[!UICONTROL Edit Feeds Usage]**.
5. Calcule el uso de [!DNL CPM] para cada fuente de datos en función de [Atribución de costos para fuentes de datos de CPM](#cost-attribution) e ingrésela en la columna [!UICONTROL Usage].
6. Haga clic en **[!UICONTROL Save]** cuando haya terminado y revise el cuadro de diálogo de confirmación.

   ![confirmar-uso-de-fuentes](assets/confirm-feed-usage.png)

7. Haga clic en **[!UICONTROL Confirm]**.

<br> 

## Informes en lote

Para reducir los errores y la sobrecarga al informar sobre el uso de [!DNL CPM], puede usar la opción de informes masivos para descargar un archivo de [!DNL CSV] que contenga las fuentes de datos y los segmentos, rellenar el uso y cargarlo de nuevo en [!DNL Audience Manager]. Puede utilizar los informes masivos para informar sobre el uso de fuentes y segmentos.

Para actualizar el uso de [!DNL CPM] de forma masiva:

1. Ir a **[!UICONTROL Audience Marketplace > Payables]**.
1. Seleccione la ficha **[!UICONTROL Feed Usage]** o **[!UICONTROL Segment Usage]**, según el tipo de informe que desee actualizar.
1. Haga clic en **[!UICONTROL Edit Feeds Usage]** o **[!UICONTROL Edit Segments Usage]**.
1. Haga clic en **[!UICONTROL download the current usage]** para asegurarse de que utiliza un archivo CSV válido.
1. Abra el archivo en el equipo y rellene el informe de uso.
1. Haga clic en **[!UICONTROL Choose a CSV file]** para cargar el informe de uso actualizado.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] valida el archivo en cuanto lo sube y le pregunta si detecta errores en el archivo.

<br> 

### Notificación masiva de errores de validación

| Mensaje de error | Descripción | Se corrigió un problema que hacía que se mostrara |
| ------------- | -------------| -----|
| Entrada no válida | [!DNL Audience Manager] detectó un cambio en el esquema de archivo [!DNL CSV], como la falta de columnas o cambios en los títulos de las columnas. | Evite cambiar la estructura de la tabla. |
| No encontrado | Para [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] no pudo identificar la combinación de [!UICONTROL Segment ID] y [!UICONTROL Destination ID]. Para [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] no pudo identificar la combinación de [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] y [!UICONTROL Use Case]. | Para [!UICONTROL Segment Level Reporting], compruebe la validez de la combinación [!UICONTROL Segment ID] y [!UICONTROL Destination ID]. Para [!UICONTROL Feed Level Reporting], compruebe la validez de las combinaciones [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] y [!UICONTROL Use Case]. |
| Registros duplicados encontrados | [!DNL Audience Manager] detectó registros duplicados con valores de impresión diferentes. | Revise el informe y asegúrese de que no informa de valores de uso diferentes para la misma fuente de datos o segmento. |
| Valores no admitidos | [!DNL Audience Manager] detectó valores no numéricos en la columna [!DNL Audience Manager]. | Revise el informe y asegúrese de que sólo especifica valores numéricos en la columna [!DNL Audience Manager]. |
| Faltan encabezados para los campos obligatorios | [!DNL Audience Manager] ha detectado que faltan encabezados de tabla para los campos obligatorios. Para [!UICONTROL Segment Level Reporting], los campos obligatorios son: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. Para [!UICONTROL Feed Level Reporting], los campos obligatorios son: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name], [!UICONTROL Use Case] | Revise el informe y asegúrese de que los encabezados de tabla no se han manipulado. |

>[!NOTE]
>La eliminación de filas del informe de uso [!DNL CSV] no afecta al informe de uso existente. [!DNL Audience Manager] solo procesa los campos incluidos en el informe.

<br> 

## [!DNL CPM]: prácticas recomendadas de informes

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recomendaciones </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Informar siempre sobre el número total de impresiones</b> </p> </td> 
   <td colname="col2"> <p>Para los totales de impresiones de CPM: </p>
   <p> Notificar el número total de impresiones, sin utilizar decimales. Audience Manager calcula automáticamente el CPM en función del número total del informe.</p><p>Si necesita informar de 1.234.567 impresiones, informe exactamente de esa manera. No es necesario dividir el número total de impresiones entre 1000 para calcular el CPM.</p><p>Las características utilizadas para optimizar el contenido de su aplicación o web (optimización de contenido) mediante herramientas como Adobe Target o un destino de Analytics no contribuyen a los totales de uso de los planes de CPM. Los proveedores de datos suelen recibir una compensación por la optimización de contenido mediante planes de tarifas fijas.</p><p>Consulte <a href="#cost-attribution">Atribución de costes para fuentes de datos de CPM</a> para obtener más información. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Respetar el intervalo de informe mensual</b> </p> </td> 
   <td colname="col2"> <p>El sistema de informes se cierra a partir del 5 de cada mes. Si no informa del uso de CPM para entonces, debe agregar esa cantidad al informe del mes siguiente. Por ejemplo, supongamos que utiliza 1000 impresiones en octubre, que se pierde la fecha límite de informes de octubre y que utiliza 1000 impresiones en noviembre. En este caso, se informa del total de octubre y noviembre (2000) en diciembre, entre el 1 y el 5.</p><p><b>Sugerencia</b>: Siempre debe intentar informar sobre el uso de CPM del mes anterior entre el primer y el quinto día del mes siguiente.</p><p>Puede realizar informes de uso de CPM hasta el día 5 del nuevo mes natural, pero no es recomendable. Informar sobre el uso de CPM antes del 5 de cada mes da al Audience Manager tiempo para comprobar y procesar los datos.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Atribución de costes para fuentes de datos de CPM {#cost-attribution}

En [!UICONTROL Audience Marketplace], debe informar automáticamente de las cantidades imprimidas cada mes, para cada uno de sus segmentos. Se recomienda informar sobre el uso de [!DNL CPM] en el nivel de segmento para que la atribución de costos se realice automáticamente.

<!-- marketplace_cpm_billing.xml -->

### Resumen de facturación {#billing-summary}

Debe enviar [!DNL CPM] cantidades de impresiones de fuentes de datos entre el primer y el quinto día de cada mes calendario. Para hacerlo correctamente, le recomendamos que [Informe de uso de CPM en el nivel de segmento](#segment-level-report).

>[!TIP]
>Cuando se informa del uso de [!DNL CPM] en el nivel de segmento, la sección de informes en el nivel de fuente de datos se completa automáticamente con las cantidades de uso correspondientes.

Si necesita [!UICONTROL Report CPM Usage at Data Feed Level], debe compilar individualmente todas las impresiones entregadas para cada fuente en el mes calendario anterior e informarlas de acuerdo con la asignación de facturación descrita en este artículo.

Después de informar sobre el número [!DNL CPM] del mes anterior, [!DNL Adobe] hará lo siguiente:

* Crea una factura y te factura según la tarifa de [!DNL CPM] para cada fuente de datos suscrita.
* Paga a los proveedores de datos (vendedores) las tarifas que se deben según el uso informado de [!DNL CPM].

>[!IMPORTANT]
>
>Como comprador, todos los totales de impresiones notificadas deben ser verdaderos y exactos. Si no comunica los totales de impresiones antes del quinto día de cada mes, debe incluir los totales del mes no informado del mes siguiente.

<br> 

## Asignar impresiones a nivel de fuente según las reglas de calificación de rasgos {#assign-impressions}

El caso de uso [!UICONTROL Activation] le permite usar características en la fuente de datos correspondiente para crear segmentos en [Generador de segmentos](../../../features/segments/segment-builder.md) y asignar esos segmentos a un destino. Los operadores booleanos [!UICONTROL AND], [!UICONTROL OR] y [!UICONTROL NOT] le permiten establecer las condiciones para la clasificación de rasgos y segmentos.

Al [Informar sobre el uso de CPM en el nivel de fuente de datos](#feed-level-report), debe asignar las impresiones proporcionalmente para cada fuente de datos, según los operadores [!DNL Boolean] utilizados en las reglas de clasificación de rasgos. En la tabla siguiente se muestra cómo asignar correctamente las impresiones por regla booleana o tipo de rasgo.

>[!TIP]
>[Informe de uso de CPM en el nivel de segmento](#segment-level-report) para que el Audience Manager realice automáticamente los informes de nivel de fuente de datos.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo o lógica de calificación de reglas </th> 
   <th colname="col2" class="entry"> Distribución de facturación </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Y </span> </p> </td> 
   <td colname="col2"> <p>Aplique el 100% de los totales de impresiones enviadas a todos los rasgos del proveedor en un segmento basado en reglas que utilice una condición booleana <span class="wintitle"> AND</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> O </span> </p> </td> 
   <td colname="col2"> <p>Aplique la asignación ponderada de los totales de impresiones enviadas a todos los rasgos del proveedor en un segmento basado en reglas que utilice una condición booleana OR. La asignación ponderada se calcula mediante la fórmula siguiente:</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NO </span> </p> </td> 
   <td colname="col2"> <p>Aplique el 100% de los totales de impresiones enviadas a todos los rasgos del proveedor en un segmento basado en reglas que utilice una condición <span class="wintitle"> NOT</span> booleana. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segmentos algorítmicos </p> </td> 
   <td colname="col2"> <p>Aplique el 100% de los totales de impresiones enviadas a todas las fuentes de proveedor en un segmento que contenga rasgos algorítmicos. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Ejemplos de facturación {#billing-examples}

Los ejemplos siguientes tienen por objeto ilustrar cómo se realiza la asignación de uso de [!DNL CPM] en el nivel de fuente de datos.

>[!IMPORTANT]
>En su lugar, le recomendamos que [Informe del uso de CPM en el nivel de segmento](#segment-level-report), para que este proceso se realice automáticamente.

Consideremos el siguiente escenario:

![ejemplos de facturación](assets/billing-examples.png)

<br> 

### Caso 1: Segmentos con reglas de calificación AND

Este segmento contiene 3 características de proveedores de datos independientes. Dado que la calificación de segmentos se basa en una condición [!UICONTROL AND], los visitantes deben conocer los rasgos de las tres fuentes para poder pertenecer al segmento.

![](assets/billing-segment-and.png)

Con una condición [!UICONTROL AND], debe asignar el 100% de las impresiones recibidas durante el mes a los tres proveedores de datos. En la sección [!UICONTROL Audience Marketplace > Payables], debe acreditar a cada proveedor 1.000.000 de impresiones.

Este ejemplo se aplica a segmentos que utilizan operadores [!DNL Boolean] [!UICONTROL NOT] o a segmentos que contienen características algorítmicas.

<br> 

### Caso 2: Segmentos con reglas de calificación OR

Este segmento contiene 3 características de proveedores de datos independientes. Dado que la calificación de segmentos se basa en una condición [!UICONTROL OR], los visitantes deben realizar al menos uno de los tres rasgos para calificar para el segmento.

No podemos saber qué característica es responsable de una impresión porque la calificación se basa en una condición [!UICONTROL OR]. Como resultado, en la sección [!UICONTROL Audience Marketplace > Payables] debe acreditar a cada proveedor con una asignación ponderada del total de impresiones, según la población de rasgos.

![billing-segment-or](assets/billing-segment-or.png)

<br> 

### Caso 3: Segmentos con casos de uso de modelado y activación

En este ejemplo se describe la atribución en función de dos casos de uso de fuentes de datos: Modelado y Activación. En el ejemplo, se busca dos proveedores de datos con la siguiente información:

![fuente de datos](assets/feed-use-cases.png)

En la tabla siguiente, el segmento X contiene dos rasgos, T1 y T2, con la regla de segmento T1 O T2, donde:

* T1 es un rasgo de la fuente de datos A;
* T2 es un rasgo algorítmico modelado a partir de rasgos de terceros de la fuente de datos A y la fuente de datos B.

El segmento se asigna a un destino y se escriben 1.000.000 de impresiones para este segmento en un mes, utilizando [informes de nivel de segmento](#segment-level-report).

De estas 1.000.000 impresiones:

* T1 representa el 40 % de la población del segmento, lo que significa 400 000 impresiones para la fuente A.
* T2 representa el 60 % de la población del segmento, lo que significa 600 000 impresiones para la fuente A y la fuente B.

A nivel de fuente de datos, la forma de asignar las impresiones es la siguiente:

* La fuente de datos A recibe 600 000 impresiones del rasgo T2 (que se modela en rasgos de la fuente de datos A y la fuente de datos B, por lo que ambas reciben las impresiones) y 400 000 impresiones del rasgo T1 (que es un rasgo de la fuente de datos A), por un total de 1 000 000 de impresiones.
* La fuente de datos B recibe 600 000 impresiones del rasgo T2 (consulte la explicación anterior) y 0 impresiones del rasgo T1.

El desglose de un vistazo por fuente de datos y caso de uso es el siguiente:

![desglose de fuentes](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>En el caso de uso de modelado, solo debe informar del uso de CPM tras la activación. Si solo ejecuta un modelo pero no lo activa, no se requiere ningún informe de uso.

<br> 

## Asignación de facturación e impresión para fuentes de datos con tarifa plana {#billing-flat-fee}

Una fuente de datos de tarifa plana le factura una cantidad fija cada mes, independientemente de cuándo comience la suscripción o de cuántas impresiones utilice. Las tarifas no se prorratean para el uso parcial del mes o los intervalos. Al igual que con la facturación de CPM, los Adobes generarán una factura y le facturarán a la tarifa mensual fija de las fuentes de datos suscritas.

Por ejemplo, supongamos que ha decidido activar ciertos rasgos en una fuente a mediados de mes. Se le cobrará la tarifa mensual completa, independientemente del momento en que inició la suscripción o activó características específicas.
