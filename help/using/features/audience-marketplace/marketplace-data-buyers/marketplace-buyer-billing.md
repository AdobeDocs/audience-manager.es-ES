---
description: Audience Marketplace los compradores de datos acuerdan informar de todas las impresiones anuncios servidas utilizando características contenidas en el fuente de datos con un precio basado en un costo por cada mil impresiones de anuncios (CPM). CPM uso vence el día 5 de cada mes calendario e incluye los datos del mes anterior. Los suscriptores de tarifa plana no necesitan informar el uso.
seo-description: Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions (CPM) basis. CPM usage is due on the 5th day of each calendar month and includes data for previous month. Flat fee subscribers do not need to report usage.
seo-title: Billing for Data Feed Buyers
solution: Audience Manager
title: Facturación para compradores de fuentes de datos
keywords: Informes de nivel de segmento, nivel segmento nivel segmento
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2029'
ht-degree: 0%

---

# Facturación para compradores de fuentes de datos {#billing-for-data-feed-buyers}

Audience Marketplace los compradores de datos acuerdan informar de todas las impresiones anuncios servidas utilizando características contenidas en el fuente de datos con un precio basado en un costo por cada mil impresiones de anuncios ([!DNL CPM]). [!DNL CPM] El uso vence el día 5 de cada mes calendario e incluye los datos del mes anterior. Los suscriptores de tarifa plana no necesitan informar el uso.

<br> 

## Cómo informar sobre el uso de CPM {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] Los compradores de datos acuerdan informar todas las impresiones anuncios servidas utilizando características contenidas en el fuente de datos con un precio basado en un costo por cada mil impresiones de anuncios ([!DNL CPM]). [!DNL CPM] El uso vence el día 5 de cada mes calendario e incluye los datos del mes anterior. Los suscriptores de tarifa plana no necesitan informar el uso.

[!UICONTROL Audience Marketplace] ofrece dos maneras de informar sobre [!DNL CPM] el uso:

* **sistema de informes** a nivel de segmento: es el método de sistema de informes de uso recomendado [!DNL CPM] . Cuando se informa [!DNL CPM] de un uso en segmento nivel, la sección de sistema de informes de nivel fuente de datos se rellena automáticamente con las cantidades de uso correspondientes, en función de los algoritmos descritos en [Atribución de costes para fuentes de datos](#cost-attribution) de CPM.
* **sistema de informes de nivel de fuente** de datos: este método requiere que informe individualmente el uso de [!DNL CPM] cada fuente de datos, en función de los algoritmos descritos en [Atribución de costos para fuentes de datos](#cost-attribution) de CPM. Sin embargo, este método es más tedioso y propenso a errores que el sistema de informes de nivel segmento.

<br> 

## Informe CPM uso a nivel de segmento {#segment-level-report}

La [!UICONTROL Segment Usage] pestaña permite crear informes sobre el uso de nivel segmento, a la vez que muestra los segmentos agrupados por los destinos a los que están asignados.

Después de sistema de informes [!DNL CPM] uso en segmento nivel, [!UICONTROL Audience Marketplace] asigna automáticamente a las fuentes de datos correspondientes el uso correcto, en función de la [atribución de costos para CPM fuentes](#cost-attribution) de datos.

Para informar sobre [!DNL CPM] el uso en segmento nivel:

1. Vaya a **[!UICONTROL Audience Marketplace > Payables]**.
1. Seleccione el **[!UICONTROL Segment Usage]** pestaña.
1. Complete el uso de los segmentos. Puede usar el [!UICONTROL Search] cuadro para filtrar los segmentos si solo necesita informar del uso de algunos de ellos.
1. Haga clic en **[!UICONTROL Edit Segments Usage]**.
1. Introduzca la cantidad de [!DNL CPM] uso en la [!UICONTROL Usage] columna.
1. Haga clic **[!UICONTROL Save]** cuando haya terminado y revise el cuadro de diálogo de confirmación.

   ![confirm-segmento-uso](assets/confirm-segment-usage.png)

1. Haga clic en **[!UICONTROL Confirm]**.

Consulte también nuestra demostración en vídeo de cómo puede informar sobre el uso a nivel segmento:

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## Uso de CPM de informes en el nivel de fuente de datos {#feed-level-report}

La sistema de informes a nivel de fuente de datos es un proceso más tedioso y propenso a errores, ya que debe calcular [!DNL CPM] individualmente el uso para cada fuente de datos. Le recomendamos que [informe CPM uso a nivel](#segment-level-report) de segmento.

Para informar sobre [!DNL CPM] el uso en segmento nivel:

1. Vaya a **[!UICONTROL Audience Marketplace > Payables]**.
2. Seleccione el **[!UICONTROL Feed Usage]** pestaña.
3. Use el [!UICONTROL Search] cuadro para filtrar las fuentes de datos e identificar aquellas para las que necesita informar del uso.
4. Haga clic en **[!UICONTROL Edit Feeds Usage]**.
5. Calcule el uso de [!DNL CPM] cada fuente de datos en función de la atribución de [costo para CPM fuentes](#cost-attribution) de datos e ingréselo en la [!UICONTROL Usage] columna.
6. Haga clic **[!UICONTROL Save]** cuando haya terminado y revise el cuadro de diálogo de confirmación.

   ![confirm-fuente-uso](assets/confirm-feed-usage.png)

7. Haga clic en **[!UICONTROL Confirm]**.

<br> 

## Informes masivos

Para reducir los errores y los gastos generales durante el uso sistema de informes [!DNL CPM] , puede utilizar la opción de sistema de informes masiva para descargar un [!DNL CSV] archivo que contenga las fuentes de datos y los segmentos, rellenar el uso y volver a cargar a [!DNL Audience Manager]. Puede utilizar la sistema de informes masiva para informar tanto del uso fuente como del segmento.

Para actualizar [!DNL CPM] el uso de forma masiva:

1. Vaya a **[!UICONTROL Audience Marketplace > Payables]**.
1. Seleccione el o **[!UICONTROL Feed Usage]** pestaña **[!UICONTROL Segment Usage]**, según el tipo de sistema de informes que desee actualizar.
1. Haga clic **[!UICONTROL Edit Feeds Usage]** o **[!UICONTROL Edit Segments Usage]** seleccione .
1. Haga clic **[!UICONTROL download the current usage]** para asegurarse de que utiliza un archivo CSV válido.
1. Abra el archivo en su computadora y complete el informe de uso.
1. Haga clic para **[!UICONTROL Choose a CSV file]** cargar el informe de uso actualizado.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] valida el archivo tan pronto como lo cargar y le pregunta si detecta algún error en el archivo.

<br> 

### Errores de validación de informes masivos

| Mensaje de error | Descripción | Se corrigió un problema que hacía que se mostrara |
| ------------- | -------------| -----|
| Entrada no válida | [!DNL Audience Manager] Se ha detectado un cambio en el esquema de archivo, como la falta de columnas o cambios en los [!DNL CSV] títulos de columnas. | Evite cambiar la estructura de la tabla. |
| No encontrado | Para [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] no se pudo identificar la combinación y [!UICONTROL Segment ID] [!UICONTROL Destination ID] . Para [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] no se pudo identificar la combinación , [!UICONTROL Data Provider Name], y [!UICONTROL Feed Name] .[!UICONTROL Use Case] | Para [!UICONTROL Segment Level Reporting], compruebe la validez de la [!UICONTROL Segment ID] combinación y [!UICONTROL Destination ID] . Para [!UICONTROL Feed Level Reporting], compruebe la validez de la [!UICONTROL Data Provider Name]combinación [!UICONTROL Feed Name], , y [!UICONTROL Use Case] . |
| Se han encontrado registros duplicados | [!DNL Audience Manager] se han detectado registros duplicado con valores de impresión diferentes. | Revise el informe y asegúrese de no informar sobre valores de uso diferentes para el mismo fuente de datos o segmento. |
| Valores no admitidos | [!DNL Audience Manager] Se han detectado valores no numéricos en la [!DNL Audience Manager] columna. | Revise el informe y asegúrese de introducir sólo valores numéricos en la [!DNL Audience Manager] columna. |
| Faltan encabezados para campos obligatorios | [!DNL Audience Manager] Se han detectado encabezados de tabla que faltaban para los campos obligatorios. Para [!UICONTROL Segment Level Reporting], los campos obligatorios son: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. Para [!UICONTROL Feed Level Reporting], los campos obligatorios son: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name], ,  [!UICONTROL Use Case] | Revise el informe y asegúrese de que los encabezados de tabla no han sido manipulados. |

>[!NOTE]
>La eliminación de filas del informe de uso no afecta al informe de [!DNL CSV] uso existente. [!DNL Audience Manager] únicamente procesa los campos incluidos en el informe.

<br> 

## [!DNL CPM] Informar sobre las prácticas recomendadas

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recomendaciones </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Informe siempre del número total de impresiones</b> </p> </td> 
   <td colname="col2"> <p>Para obtener CPM impresión totales: </p>
   <p> Informe del número total de impresiones, sin utilizar decimales. Audience Manager calcula automáticamente el CPM en función del número total que informe.</p><p>Si necesita informar de 1.234.567 impresiones, infórmelo exactamente gustar eso. No es necesario dividir el número total de impresiones entre 1000 para calcular el CPM.</p><p>Las características utilizadas para optimizar su contenido web o de aplicación (Optimización de contenido) mediante herramientas como Adobe Target o un destino Analytics no contribuyen a los totales de uso para CPM planes. Los proveedores de datos suelen recibir una compensación por la optimización del contenido mediante planes de tarifa plana.</p><p>Consulte <a href="#cost-attribution">Atribución de costos para CPM fuentes de</a> datos para obtener más información. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Apéguese al intervalo de sistema de informes mensual</b> </p> </td> 
   <td colname="col2"> <p>El sistema de informes se cierra después del día 5 de cada mes. Si no informa CPM uso para entonces, debe agregar esa cantidad al informe para el mes siguiente. Por ejemplo, supongamos que usa 1000 impresiones en octubre, no cumple con la fecha límite del sistema de informes de octubre y usa 1000 impresiones en noviembre. En este caso, informa del total de octubre y noviembre (2000) en diciembre, entre el 1 y el 5.</p><p><b>Sugerencia</b>: Siempre debe intentar informar CPM el uso del mes anterior entre el día 1 y el 5 del mes siguiente.</p><p>Puede informar CPM uso hasta el día 5 del nuevo mes calendario, pero esto no se recomienda. Informar CPM uso antes del día 5 de cada mes Audience Manager da tiempo para comprobar y procesar los datos.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Atribución de costos para fuentes de datos de CPM {#cost-attribution}

En [!UICONTROL Audience Marketplace] usted debe autoinformar impresión importes mensuales, para cada uno de sus segmentos. Se recomienda sistema de informes [!DNL CPM] uso a nivel segmento, de modo que la atribución de costes se realice automáticamente.

<!-- marketplace_cpm_billing.xml -->

### Resumen de facturación {#billing-summary}

Debe enviar [!DNL CPM] fuente de datos impresión importes entre el día 1 y el 5 de cada mes calendario. Para hacerlo correctamente, le recomendamos que [informe CPM uso a nivel](#segment-level-report) de segmento.

>[!TIP]
>Cuando se informa [!DNL CPM] de un uso en segmento nivel, la sección de sistema de informes de nivel fuente de datos se rellena automáticamente con las cantidades de uso correspondientes.

Si es necesario [!UICONTROL Report CPM Usage at Data Feed Level], debe compilar individualmente todas las impresiones entregadas para cada fuente en el mes calendario anterior e informarlas de acuerdo con el facturación Asignación descrito en este artículo.

Después de reportar [!DNL CPM] el número del mes calendario anterior, [!DNL Adobe] hará lo siguiente:

* Crear una factura y una factura en función de la [!DNL CPM] tarifa de cada fuente de datos suscrito.
* Pagar a los proveedores de datos (vendedores) las tarifas adeudadas en función del uso informado [!DNL CPM] .

>[!IMPORTANT]
>
>Como comprador, todos los totales de impresión reportados deben ser verdaderos y precisos. Si no informa los totales de impresión antes del día 5 de cada mes, debe incluir los totales del mes no informado del mes siguiente.

<br> 

## Asignar impresiones en el nivel de fuente según las reglas de calificación de características {#assign-impressions}

El [!UICONTROL Activation] caso de uso le permite utilizar características en la fuente de datos correspondiente para crear segmentos en [el Generador](../../../features/segments/segment-builder.md) de segmentos y asignar esos segmentos a un destino. Los operadores [!UICONTROL AND]booleanos , [!UICONTROL OR]y [!UICONTROL NOT] permiten establecer las condiciones para el rasgo y la calificación segmento.

Cuando informe [CPM uso a nivel](#feed-level-report) de fuente de datos, debe asignar impresiones proporcionalmente para cada fuente de datos, de acuerdo con los [!DNL Boolean] operadores utilizados en las reglas de calificación de rasgos. En la tabla siguiente se explica cómo asignar correctamente las impresiones por regla booleano o tipo de rasgo.

>[!TIP]
>[Informe CPM uso a nivel](#segment-level-report) de segmento para que el nivel de fuente de datos sistema de informes realice automáticamente por Audience Manager.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Lógica o tipo de calificación de regla </th> 
   <th colname="col2" class="entry"> Distribución de facturación </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Y</span> </p> </td> 
   <td colname="col2"> <p>Aplicar el 100 % de los totales de impresión entregados a todos los rasgos del proveedor en un segmento basado en reglas que usa una condición Y booleana<span class="wintitle"></span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> O</span> </p> </td> 
   <td colname="col2"> <p>Aplicar Asignación ponderada de los totales de impresión entregados a todos los rasgos del proveedor en un segmento basado en reglas que usa una condición OR booleana. El Asignación ponderado se calcula mediante la siguiente fórmula:</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NO</span> </p> </td> 
   <td colname="col2"> <p>Aplicar el 100 % de los totales de impresión entregados a todos los rasgos del proveedor en un segmento basado en reglas que usa una condición NOT<span class="wintitle"> booleana</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segmentos algorítmicos </p> </td> 
   <td colname="col2"> <p>Aplicar el 100 % de los totales de impresión entregados a todas las fuentes del proveedor en una segmento que contiene rasgos algorítmicos. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Ejemplos de facturación {#billing-examples}

Los ejemplos siguientes pretenden ilustrar cómo [!DNL CPM] se realiza la Asignación de uso a nivel fuente de datos.

>[!IMPORTANT]
>Le recomendamos que [informe CPM uso a nivel](#segment-level-report) de segmento para que este proceso se realice automáticamente.

Veamos el siguiente escenario:

![facturación ejemplos](assets/billing-examples.png)

<br> 

### Caso 1: Segmentos con reglas de calificación Y

Este segmento contiene 3 características de proveedores de datos independientes. Dado que segmento calificación se basa en una [!UICONTROL AND] condición, los visitantes deben darse cuenta de las características de las tres fuentes para calificar para el segmento.

![](assets/billing-segment-and.png)

Con una [!UICONTROL AND] condición, debe asignar el 100 % de las impresiones recibidas durante el mes a los tres proveedores de datos. En la [!UICONTROL Audience Marketplace > Payables] sección, acredita a cada proveedor con 1,000,000 impresiones.

Este ejemplo se aplica a segmentos que utilizan [!DNL Boolean] [!UICONTROL NOT] operadores o para segmentos que contienen rasgos algorítmicos.

<br> 

### Caso 2: Segmentos con reglas de calificación OR

Este segmento contiene 3 características de proveedores de datos independientes. Dado que segmento calificación se basa en una [!UICONTROL OR] condición, los visitantes deben realizar al menos uno de los tres rasgos para calificar para el segmento.

No podemos decir qué rasgo es responsable de un impresión porque la calificación se basa en una [!UICONTROL OR] condición. Como resultado, en la [!UICONTROL Audience Marketplace > Payables] sección acredita a cada proveedor con un Asignación ponderado de las impresiones totales, basado en la población de rasgos.

![facturación-segmento-o](assets/billing-segment-or.png)

<br> 

### Caso 3: Segmentos con casos de uso de modelado y Activation

En este ejemplo se describen atribución que se basan en dos casos de uso de fuentes de datos: modelado y Activation. En el ejemplo, estamos viendo dos proveedores de datos, con la siguiente información:

![fuente datos](assets/feed-use-cases.png)

En la tabla más abajo, el segmento X contiene dos características, T1 y T2, con el segmento regla T1 O T2, donde:

* T1 es un rasgo de la fuente de datos A;
* T2 es un rasgo algorítmico inspirado en terceros características de la fuente de datos A y la fuente de datos B.

El segmento se asigna a un destino y se introducen 1.000.000 de impresiones para este segmento en un mes, mediante [los informes](#segment-level-report) de nivel de segmento.

De estas 1.000.000 de impresiones:

* T1 representa el 40% de la población segmento, lo que se traduce en 400.000 impresiones para Feed A.
* T2 representa el 60% de la población segmento, lo que se traduce en 600.000 impresiones para Feed A y Feed B.

En un nivel fuente de datos, la forma en que se asignan las impresiones es:

* La fuente de datos A recibe 600 000 impresiones del rasgo T2 (que se basa en los rasgos de la fuente de datos A y la fuente de datos B, por lo que ambos reciben las impresiones) y 400 000 impresiones del rasgo T1 (que es un rasgo de la fuente de datos A), con un total de 1 000 000 de impresiones.
* La fuente de datos B recibe 600 000 impresiones del rasgo T2 (consulte la explicación anterior) y 0 impresiones del rasgo T1.

Las desglose rápidas por fuente de datos y caso de uso son las siguientes:

![fuente-desglose](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>Para el caso de uso de modelado, solo debe informar CPM uso después de activación. Si sólo ejecuta un modelo, pero no lo activa, no se requiere ninguna sistema de informes de uso.

<br> 

## Facturación y asignación de impresiones para fuentes de datos de tarifa plana {#billing-flat-fee}

Una tarifa plana fuente de datos le factura una cantidad fija cada mes, independientemente de cuándo comience la suscripción o cuántas impresiones use. Las tarifas no se prorratean por el uso parcial de meses o intervalos. Al igual que con CPM facturación, Adobe Systems generará una factura y le facturará a la tarifa plana mensual por sus fuentes de datos suscritas.

Por ejemplo, supongamos que decidiste activar ciertas características de una fuente a mediados de mes. Aún se le facturará a la tarifa mensual completa, independientemente de cuándo comenzó la suscripción o activó características específicas.
