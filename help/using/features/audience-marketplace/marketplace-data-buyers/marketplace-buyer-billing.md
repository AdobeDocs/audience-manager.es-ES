---
description: Los compradores de datos de Audience Marketplace aceptan informar de todas las impresiones de publicidad servidas mediante características contenidas en la fuente de datos a un coste por mil impresiones de publicidad (CPM). El uso CPM se debe al quinto día de cada mes calendario e incluye datos del mes anterior. Los suscriptores de tarifas planas no necesitan informar sobre el uso.
seo-description: Los compradores de datos de Audience Marketplace aceptan informar de todas las impresiones de publicidad servidas mediante características contenidas en la fuente de datos a un coste por mil impresiones de publicidad (CPM). El uso CPM se debe al quinto día de cada mes calendario e incluye datos del mes anterior. Los suscriptores de tarifas planas no necesitan informar sobre el uso.
seo-title: Facturación de compradores de fuentes de datos
solution: Audience Manager
title: Facturación de compradores de fuentes de datos
keywords: Informes a nivel de segmento, nivel de segmento, nivel de segmento
uuid: d 7236667-282 b -4160-9909-579721 af 4016
translation-type: tm+mt
source-git-commit: dab5b255f966e63d51cc4d236d37bb0cb4eb960c

---


# Facturación de compradores de fuentes de datos {#billing-for-data-feed-buyers}

Los compradores de datos de Audience Marketplace aceptan informar de todas las impresiones de publicidad servidas mediante características contenidas en la fuente de datos a un costo por mil impresiones de publicidad ([!DNL CPM]). [!DNL CPM] el uso se debe al quinto día de cada mes calendario e incluye datos del mes anterior. Los suscriptores de tarifas planas no necesitan informar sobre el uso.

<br> 

## Uso del CPM de informes {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] los compradores de datos aceptan informar de todas las impresiones de publicidad servidas mediante características contenidas en la fuente de datos a un costo por mil impresiones de publicidad ([!DNL CPM]). [!DNL CPM] el uso debe realizarse el 5 día de cada mes calendario e incluye datos del mes anterior. Los suscriptores de tarifas planas no necesitan informar sobre el uso.

[!UICONTROL Audience Marketplace] ofrece dos maneras de informar [!DNL CPM] el uso:

* **Informes a nivel de segmento**: es el método de informes [!DNL CPM] de uso recomendado. Al informar [!DNL CPM] el uso en nivel de segmento, la sección de informes a nivel de fuente de datos se rellena automáticamente con las cantidades de uso correspondientes, en función de los algoritmos descritos en [Atribución de costes para fuentes de datos CPM](#cost-attribution).
* **Informes de nivel de fuente de datos**: este método requiere que informe de forma individual el [!DNL CPM] uso de cada fuente de datos, según los algoritmos descritos en Atribución [de costes para fuentes de datos CPM](#cost-attribution). Sin embargo, este método es más tedioso y propenso a provocar errores que los informes a nivel de segmento.

<br> 

## Uso del CPM de informes en el nivel de segmento {#segment-level-report}

La [!UICONTROL Segment Usage] ficha permite informar el uso de nivel de segmento, al mismo tiempo que muestra los segmentos agrupados por los destinos a los que están asignados.

Después de informar [!DNL CPM] el uso en el nivel de segmento, [!UICONTROL Audience Marketplace] se asigna automáticamente la fuente de datos correspondiente, en función de la atribución [de costes para las fuentes de datos CPM](#cost-attribution).

Para informar [!DNL CPM] el uso en el nivel de segmento:

1. Vaya **[!UICONTROL Audience Marketplace > Payables]** a.
2. Seleccione **[!UICONTROL Segment Usage]** la ficha.
3. Complete el uso de sus segmentos. Puede utilizar [!UICONTROL Search] el cuadro para filtrar los segmentos si solo necesita informar para algunos de ellos.
4. Haga clic en **[!UICONTROL Edit Segments Usage]**.
5. Introduzca la cantidad [!DNL CPM] de uso en [!UICONTROL Usage] la columna.
6. Haga clic **[!UICONTROL Save]** en una vez que haya terminado y revise el cuadro de diálogo de confirmación.
   ![confirm-segment-usage](assets/confirm-segment-usage.png)
7. Haga clic en **[!UICONTROL Confirm]**.

<br> 

## Uso del CPM de informes en el nivel de fuente de datos {#feed-level-report}

Los informes de nivel de fuente de datos son un proceso más tedioso y propenso al proceso de error, ya que debe calcular individualmente [!DNL CPM] el uso de cada fuente de datos. Le recomendamos [que Informe el uso CPM en el nivel de segmento](#segment-level-report) en su lugar.

Para informar [!DNL CPM] el uso en el nivel de segmento:

1. Vaya **[!UICONTROL Audience Marketplace > Payables]** a.
2. Seleccione **[!UICONTROL Feed Usage]** la ficha.
3. Utilice [!UICONTROL Search] el cuadro para filtrar las fuentes de datos e identificar las a las que debe informar el uso.
4. Haga clic en **[!UICONTROL Edit Feeds Usage]**.
5. Calcule [!DNL CPM] el uso de cada fuente de datos en función de [la atribución de costes de las fuentes de datos CPM](#cost-attribution)e introdúzcala en [!UICONTROL Usage] la columna.
6. Haga clic **[!UICONTROL Save]** en una vez que haya terminado y revise el cuadro de diálogo de confirmación.

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. Haga clic en **[!UICONTROL Confirm]**.

<br> 

## Informes masivos

Para reducir los errores y sobrecargar al utilizar [!DNL CPM] el uso de informes, puede utilizar la opción de informes masivos para descargar [!DNL CSV] un archivo que contenga las fuentes de datos y los segmentos, rellenar el uso y volverlo [!DNL Audience Manager]a cargar. Puede utilizar informes masivos para informar tanto sobre la fuente como sobre el uso de segmentos.

Para actualizar [!DNL CPM] el uso de forma masiva:

1. Vaya **[!UICONTROL Audience Marketplace > Payables]** a.
1. Seleccione la **[!UICONTROL Feed Usage]** ficha o **[!UICONTROL Segment Usage]** la ficha, según el tipo de informe que desee actualizar.
1. Haga clic **[!UICONTROL Edit Feeds Usage]** o **[!UICONTROL Edit Segments Usage]**.
1. Haga clic para **[!UICONTROL download the current usage]** asegurarse de que utiliza un archivo CSV válido.
1. Abra el archivo en su equipo y rellene el informe de uso.
1. Haga clic en **[!UICONTROL Choose a CSV file]** para cargar el informe de uso actualizado.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] valida el archivo en cuanto lo carga y le solicita si detecta algún error en el archivo.

<br> 

### Errores de validación de informes masivos

| Mensaje de error | Descripción | Se corrigió un problema que hacía que se mostrara |
| ------------- | -------------| -----|
| Entrada no válida | [!DNL Audience Manager] detectó un cambio en el esquema [!DNL CSV] de archivos, como columnas que faltan o cambios en los títulos de columnas. | Evite cambiar la estructura de la tabla. |
| No encontrado | Para [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] no se pudo identificar la combinación [!UICONTROL Segment ID] y [!UICONTROL Destination ID] la combinación. Para [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] no se pudo identificar [!UICONTROL Data Provider Name]la combinación, [!UICONTROL Feed Name]ni la [!UICONTROL Use Case] combinación. | Para [!UICONTROL Segment Level Reporting], compruebe la validez de la combinación [!UICONTROL Segment ID] y [!UICONTROL Destination ID] la combinación. Para [!UICONTROL Feed Level Reporting], compruebe la validez del [!UICONTROL Data Provider Name], [!UICONTROL Feed Name]y [!UICONTROL Use Case] la combinación. |
| Se encontraron registros duplicados | [!DNL Audience Manager] detectados registros duplicados con diferentes valores de impresión. | Revise el informe y asegúrese de que no informa de distintos valores de uso para la misma fuente de datos o segmento. |
| Valores no admitidos | [!DNL Audience Manager] se han detectado valores no numéricos en [!DNL Audience Manager] la columna. | Revise el informe y asegúrese de introducir solo valores numéricos en [!DNL Audience Manager] la columna. |
| Faltan encabezados para campos obligatorios | [!DNL Audience Manager] detectaban encabezados de tabla que faltan para campos obligatorios. Para [!UICONTROL Segment Level Reporting], los campos obligatorios son: [!UICONTROL Segment ID][!UICONTROL Destination ID]. Para [!UICONTROL Feed Level Reporting], los campos obligatorios son: [!UICONTROL Data Provider Name][!UICONTROL Data Feed Name], [!UICONTROL Use Case] | Revise el informe y asegúrese de que los encabezados de tabla no se han manipulado con. |

>[!NOTE]
>La eliminación de filas del informe [!DNL CSV] de uso no afecta al informe de uso existente. [!DNL Audience Manager] procesa únicamente los campos incluidos en el informe.

<br> 

## [!DNL CPM] Optimizaciones para informes

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recomendaciones </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Informar siempre el número total de impresiones</b> </p> </td> 
   <td colname="col2"> <p>Para totales de impresión CPM: </p>
   <p> Informar el número total de impresiones, sin utilizar decimales. Audience Manager calcula automáticamente el CPM según el número total que informe.</p><p>Si necesita informar de 1234,567 impresiones, informe de la misma manera. No es necesario dividir el número total de impresiones en 1000 para calcular el CPM.</p><p>Las características utilizadas para optimizar el contenido de la aplicación o la aplicación (Optimización de contenido) con herramientas como Adobe Target o un destino de Analytics no contribuyen a los totales de uso de los planes CPM. Normalmente, los proveedores de datos se compensan con la optimización de contenido mediante planes de tarifas planos.</p><p>Consulte <a href="#cost-attribution">Atribución de costes para fuentes de datos CPM</a> para obtener más información. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Mantener pulsado el intervalo de informes mensual</b> </p> </td> 
   <td colname="col2"> <p>El sistema de informes se cierra después del 5 de cada mes. Si no puede informar el uso CPM para entonces, debe agregar esa cantidad al informe del mes siguiente. Por ejemplo: supongamos que utiliza 1000 impresiones en octubre, que no se ha superado el plazo de informes de octubre y que utilice 1000 impresiones en noviembre. En este caso, se informa el total de octubre y noviembre (2000) en diciembre, entre el primer y el quinto.</p><p><b>Sugerencia</b>: Siempre debe intentar informar el uso CPM para el mes anterior entre el primer día y el quinto día del siguiente mes.</p><p>Puede informar el uso CPM tan tarde como el quinto del nuevo mes calendario, pero esto no es recomendable. El uso del CPM de informes antes del quinto de cada mes proporciona a Audience Manager la hora de comprobar y procesar los datos.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Atribución de costes para fuentes de datos CPM {#cost-attribution}

En [!UICONTROL Audience Marketplace] usted debe generar un informe de las cantidades impresiones de autoinforme cada mes para cada uno de los segmentos. Recomendamos el [!DNL CPM] uso de informes en el nivel de segmento, de modo que la atribución de costes se realice automáticamente.

<!-- marketplace_cpm_billing.xml -->

### Resumen de facturación {#billing-summary}

Debe enviar [!DNL CPM] cantidades de impresión de fuente de datos entre el primer día y el quinto día de cada mes natural. Para hacerlo correctamente, le recomendamos [que Informe el uso CPM en el nivel de segmento](#segment-level-report).

>[!TIP]
>Al informar [!DNL CPM] el uso en nivel de segmento, la sección de informes a nivel de fuente de datos se rellena automáticamente con las cantidades de uso correspondientes.

Si lo necesita, [!UICONTROL Report CPM Usage at Data Feed Level]debe compilar de forma individual todas las impresiones entregadas para cada fuente en el mes natural anterior e informar de ellas según la asignación de facturación descrita en este artículo.

Después de registrar [!DNL CPM] el número del mes natural anterior, [!DNL Adobe] haga lo siguiente:

* Cree una factura y factura según [!DNL CPM] la tasa de cada fuente de datos suscrita.
* Pago de los proveedores de datos (vendedores) según [!DNL CPM] su uso informado.

>[!IMPORTANT]
>
>Como comprador, todos los totales de impresión informados deben ser verdaderos y precisos. Si no puede informar totales de impresión el quinto día de cada mes, debe incluir los totales del mes no informado en el mes siguiente.

<br> 

## Asignar impresiones en el nivel de fuente basadas en reglas de cualificación de características {#assign-impressions}

El caso [!UICONTROL Activation] de uso permite utilizar características en la fuente de datos correspondiente para crear segmentos en [el Generador](../../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74) de segmentos y asignar dichos segmentos a un destino. Los operadores [!UICONTROL AND]booleanos, [!UICONTROL OR]y [!UICONTROL NOT] permiten definir las condiciones para la calificación de segmentos y características.

Al [informar el uso CPM en el nivel de fuente de datos](#feed-level-report), debe asignar impresiones proporcionalmente para cada fuente de datos, según [!DNL Boolean] los operadores utilizados en las reglas de cualificación de características. La siguiente tabla muestra cómo asignar impresiones correctamente por tipo de regla booleana o tipo de característica.

>[!TIP]
>[Utilice el uso CPM de informes en Nivel](#segment-level-report) de segmento para que Audience Manager realice automáticamente los informes de nivel de fuente de datos.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Lógica o tipo de cualificación de regla </th> 
   <th colname="col2" class="entry"> Distribución de facturación </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> AND</span> </p> </td> 
   <td colname="col2"> <p>Aplique el 100% de los totales de impresión entregados a todas las características del proveedor en un segmento basado en reglas que utiliza una condición Booleana <span class="wintitle"> AND</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> O</span> </p> </td> 
   <td colname="col2"> <p>Aplique la asignación ponderada de los totales de impresión entregados a todas las características del proveedor en un segmento basado en reglas que utiliza una condición Booleana OR. La asignación ponderada se calcula con la fórmula siguiente:</p><p><code>(Característica Población/Segmento de segmento) * Número de impresiones * Costo del CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NO</span> </p> </td> 
   <td colname="col2"> <p>Aplique el 100% de los totales de impresión entregados a todas las características del proveedor en un segmento basado en reglas que utiliza una condición Booleana <span class="wintitle"> NOT</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segmentos algorítmicos </p> </td> 
   <td colname="col2"> <p>Aplique el 100% de los totales de impresión entregados a todas las fuentes de proveedores de un segmento que contenga características algorítmicas. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Ejemplos de facturación {#billing-examples}

Los ejemplos siguientes pretenden ilustrar cómo [!DNL CPM] se realiza la asignación de uso en el nivel de fuente de datos.

>[!IMPORTANT]
>Le recomendamos [que Informe el uso CPM en el nivel](#segment-level-report) de segmento, para que este proceso se realice de forma automática.

Veamos el siguiente escenario:

![ejemplos de facturación](assets/billing-examples.png)

<br> 

### Caso 1: Segmentos con reglas de cualificación Y

Este segmento contiene 3 características de proveedores de datos separados. Debido a que la cualificación de segmentos se basa en una [!UICONTROL AND] condición, los visitantes tienen que ver las características de las tres fuentes para cumplir los requisitos del segmento.

![](assets/billing-segment-and.png)

Con una [!UICONTROL AND] condición, debe asignar el 100% de las impresiones recibidas durante el mes a los tres proveedores de datos. En [!UICONTROL Audience Marketplace > Payables] la sección, usted crédito a cada proveedor con 1000 000 impresiones.

Este ejemplo se aplica a segmentos que utilizan [!DNL Boolean][!UICONTROL NOT] operadores o para segmentos que contienen características algorítmicas.

<br> 

### Caso 2: Segmentos con reglas de cualificación O

Este segmento contiene 3 características de proveedores de datos separados. Debido a que la cualificación de segmentos se basa en una [!UICONTROL OR] condición, los visitantes tienen que completar al menos una de las tres características para cumplir con el segmento.

No podemos saber cuál es el rasgo responsable de la impresión porque la cualificación se basa en [!UICONTROL OR] una condición. Como resultado, en [!UICONTROL Audience Marketplace > Payables] la sección debe acreditar a cada proveedor con una asignación ponderada de las impresiones totales, según la población de características.

![facturación-segmento-o](assets/billing-segment-or.png)

<br> 

### Caso 3: Segmentos con modelado y casos de uso de activación

Este ejemplo describe la atribución basada en dos casos de uso de Fuente de datos: Modelado y Activación. En el ejemplo, estamos viendo dos proveedores de datos con la siguiente información:

![fuente de datos](assets/feed-use-cases.png)

En la tabla siguiente, el Segmento X contiene dos características, T 1 y T 2, con la regla de segmento T 1 OR T 2, donde:

* T 1 es un rasgo de la fuente de datos A;
* T 2 es un modelo algorítmico modelado después de características de terceros de Fuente de datos A y Fuente de datos B.

El segmento se asigna a un destino y se introducen 1000 000 impresiones para este segmento en un mes usando los informes [de nivel de segmento](#segment-level-report).

De estas 1000 000 impresiones:

* T 1 constituye el 40% de la población de segmentos, que traduce 400 000 impresiones de Feed A.
* T 2 constituye el 60% de la población de segmentos, que traduce 600 000 impresiones de Fuente A y Fuente B.

En un nivel de fuente de datos, la manera de asignar las impresiones es:

* Fuente de datos A recibe 600 000 impresiones de la función T 2 (que se modelan en características de Fuente de datos A y Fuente de datos B, por lo tanto reciben las impresiones) y 400 000 impresiones de T 1 T 1 (que es un rasgo de la Fuente de datos A), con un total de 1000 000 impresiones. conversiones.
* La fuente de datos B recibe 600 000 impresiones de T 2 (véase la explicación anterior) e impresiones de características T 1.

El desglose general por fuente de datos y caso de uso es el siguiente:

![desglose de fuentes](assets/feed-breakdown-alt.png)

<br> 

## Asignación de impresiones e impresiones para fuentes de datos de tarifa plana {#billing-flat-fee}

Una fuente de datos de tarifa fija factura una cantidad fija cada mes, independientemente de cuándo empiece la suscripción o de cuántas impresiones utilice. Las tarifas no se prorratean para el uso o intervalos parciales de mes. Al igual que con la facturación CPM, Adobe generará una factura y le facturará a la tarifa mensual y plana de sus fuentes de datos suscritas.

Por ejemplo, supongamos que ha decidido activar ciertas características en una fuente en mitad del mes. Aún se facturará a la velocidad mensual completa, independientemente de cuándo haya iniciado la suscripción o de características específicas activadas.