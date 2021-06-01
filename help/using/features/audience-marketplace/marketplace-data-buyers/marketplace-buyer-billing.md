---
description: Los compradores de datos Audience Marketplace acuerdan informar de todas las impresiones de publicidad servidas utilizando los rasgos contenidos en la fuente de datos a precios de coste por cada mil impresiones de publicidad (CPM). El uso de CPM se debe realizar el quinto día de cada mes del calendario e incluye datos del mes anterior. Los suscriptores de tarifa plana no necesitan notificar el uso.
seo-description: Los compradores de datos Audience Marketplace acuerdan informar de todas las impresiones de publicidad servidas utilizando los rasgos contenidos en la fuente de datos a precios de coste por cada mil impresiones de publicidad (CPM). El uso de CPM se debe realizar el quinto día de cada mes del calendario e incluye datos del mes anterior. Los suscriptores de tarifa plana no necesitan notificar el uso.
seo-title: Facturación para compradores de fuentes de datos
solution: Audience Manager
title: Facturación para compradores de fuentes de datos
keywords: Informes a nivel de segmento, a nivel de segmento, a nivel de segmento
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2064'
ht-degree: 1%

---

# Facturación para compradores de fuentes de datos {#billing-for-data-feed-buyers}

Los compradores de datos Audience Marketplace aceptan informar de todas las impresiones de publicidad servidas utilizando los rasgos contenidos en la fuente de datos a precios de coste por cada mil impresiones de publicidad ([!DNL CPM]). [!DNL CPM] El uso de se debe realizar el quinto día de cada mes del calendario e incluye datos del mes anterior. Los suscriptores de tarifa plana no necesitan notificar el uso.

<br> 

## Cómo informar del uso de CPM {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] los compradores de datos acuerdan informar de todas las impresiones de publicidad servidas utilizando los rasgos contenidos en la fuente de datos con un precio de coste por cada mil impresiones de publicidad ([!DNL CPM]). [!DNL CPM] El uso de se debe realizar el día 5 de cada mes del calendario e incluye datos del mes anterior. Los suscriptores de tarifa plana no necesitan notificar el uso.

[!UICONTROL Audience Marketplace] ofrece dos formas de informar sobre el  [!DNL CPM] uso:

* **Informes** a nivel de segmento: este es el método recomendado de generación de informes de  [!DNL CPM] uso. Al informar sobre el uso de [!DNL CPM] a nivel de segmento, la sección de informes a nivel de fuente de datos se rellena automáticamente con las cantidades de uso correspondientes, según los algoritmos descritos en [Atribución de costo para fuentes de datos CPM](#cost-attribution).
* **Informes** de nivel de fuente de datos: este método requiere que informe individualmente del  [!DNL CPM] uso de cada fuente de datos, en función de los algoritmos descritos en Atribución de  [coste para fuentes de datos CPM](#cost-attribution). Sin embargo, este método es más tedioso y propenso a errores que los informes a nivel de segmento.

<br> 

## Informe del uso del CPM en el nivel de segmento {#segment-level-report}

La pestaña [!UICONTROL Segment Usage] le permite informar sobre el uso en el nivel de segmento, al mismo tiempo que muestra los segmentos agrupados por los destinos a los que están asignados.

Después de informar sobre el uso de [!DNL CPM] a nivel de segmento, [!UICONTROL Audience Marketplace] asigna automáticamente las fuentes de datos correspondientes al uso correcto, en función de la [Atribución de costes para fuentes de datos CPM](#cost-attribution).

Para informar sobre el uso de [!DNL CPM] a nivel de segmento:

1. Vaya a **[!UICONTROL Audience Marketplace > Payables]**.
1. Seleccione la pestaña **[!UICONTROL Segment Usage]**.
1. Complete el uso de los segmentos. Puede utilizar el cuadro [!UICONTROL Search] para filtrar los segmentos si solo necesita informar del uso de algunos de ellos.
1. Haga clic **[!UICONTROL Edit Segments Usage]**.
1. Introduzca la cantidad de uso [!DNL CPM] en la columna [!UICONTROL Usage].
1. Haga clic en **[!UICONTROL Save]** cuando haya terminado y revise el cuadro de diálogo de confirmación.

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. Haga clic **[!UICONTROL Confirm]**.

Consulte también nuestra demostración en vídeo de cómo puede informar sobre el uso a nivel de segmento:

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## Informe del uso del CPM en el nivel de fuente de datos {#feed-level-report}

El sistema de informes de nivel de fuente de datos es más tedioso y propenso a errores, ya que debe calcular individualmente el uso de [!DNL CPM] para cada fuente de datos. Le recomendamos que [Informe del uso del CPM en el nivel de segmento](#segment-level-report) en su lugar.

Para informar sobre el uso de [!DNL CPM] a nivel de segmento:

1. Vaya a **[!UICONTROL Audience Marketplace > Payables]**.
2. Seleccione la pestaña **[!UICONTROL Feed Usage]**.
3. Utilice el cuadro [!UICONTROL Search] para filtrar las fuentes de datos e identificar las que necesita para informar del uso.
4. Haga clic **[!UICONTROL Edit Feeds Usage]**.
5. Calcule el uso de [!DNL CPM] para cada fuente de datos en función de la [Atribución de coste para fuentes de datos CPM](#cost-attribution) e introdúzcala en la columna [!UICONTROL Usage].
6. Haga clic en **[!UICONTROL Save]** cuando haya terminado y revise el cuadro de diálogo de confirmación.

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. Haga clic **[!UICONTROL Confirm]**.

<br> 

## Informes masivos

Para reducir los errores y la sobrecarga durante el uso de los informes [!DNL CPM], puede utilizar la opción de informes masivos para descargar un archivo [!DNL CSV] que contenga las fuentes de datos y los segmentos, rellenar el uso y volver a cargarlo en [!DNL Audience Manager]. Puede utilizar los informes masivos para informar sobre el uso de fuentes y segmentos.

Para actualizar el uso de [!DNL CPM] de forma masiva:

1. Vaya a **[!UICONTROL Audience Marketplace > Payables]**.
1. Seleccione la pestaña **[!UICONTROL Feed Usage]** o **[!UICONTROL Segment Usage]** , según el tipo de informe que desee actualizar.
1. Haga clic en **[!UICONTROL Edit Feeds Usage]** o **[!UICONTROL Edit Segments Usage]**.
1. Haga clic en **[!UICONTROL download the current usage]** para asegurarse de utilizar un archivo CSV válido.
1. Abra el archivo en el equipo y rellene el informe de uso.
1. Haga clic en **[!UICONTROL Choose a CSV file]** para cargar el informe de uso actualizado.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] valida el archivo en cuanto lo carga y le pregunta si detecta errores en el archivo.

<br> 

### Errores de validación de informes masivos

| Mensaje de error | Descripción | Se corrigió un problema que hacía que se mostrara |
| ------------- | -------------| -----|
| Entrada no válida | [!DNL Audience Manager] se ha detectado un cambio en el esquema de  [!DNL CSV] archivo, como columnas que faltaban o cambios en los títulos de las columnas. | Evite cambiar la estructura de la tabla. |
| No encontrado | Para [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] no pudo identificar la combinación [!UICONTROL Segment ID] y [!UICONTROL Destination ID]. Para [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] no pudo identificar la combinación [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] y [!UICONTROL Use Case]. | Para [!UICONTROL Segment Level Reporting], compruebe la validez de la combinación [!UICONTROL Segment ID] y [!UICONTROL Destination ID] . Para [!UICONTROL Feed Level Reporting], compruebe la validez de la combinación [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] y [!UICONTROL Use Case]. |
| Se encontraron registros duplicados | [!DNL Audience Manager] se han detectado registros duplicados con valores de impresión diferentes. | Revise el informe y asegúrese de que no informa de valores de uso diferentes para la misma fuente de datos o segmento. |
| Valores no admitidos | [!DNL Audience Manager] se han detectado valores no numéricos en la  [!DNL Audience Manager] columna . | Revise el informe y asegúrese de introducir solo valores numéricos en la columna [!DNL Audience Manager]. |
| Faltan encabezados para campos obligatorios | [!DNL Audience Manager] se han detectado encabezados de tabla faltantes para campos obligatorios. Para [!UICONTROL Segment Level Reporting], los campos obligatorios son: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. Para [!UICONTROL Feed Level Reporting], los campos obligatorios son: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name], [!UICONTROL Use Case] | Revise el informe y asegúrese de que los encabezados de tabla no estén alterados. |

>[!NOTE]
>La eliminación de filas del informe de uso [!DNL CSV] no tiene ningún efecto en el informe de uso existente. [!DNL Audience Manager] solo procesa los campos incluidos en el informe.

<br> 

## [!DNL CPM] Prácticas recomendadas de creación de informes

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
   <p> Informar del número total de impresiones, sin usar decimales. El Audience Manager calcula automáticamente el CPM en función del número total que informe.</p><p>Si necesita informar de 1.234.567 impresiones, infórmelas exactamente así. No es necesario dividir el número total de impresiones en 1000 para calcular el CPM.</p><p>Las características utilizadas para optimizar el contenido de su aplicación o web (optimización del contenido) mediante herramientas como Adobe Target o un destino de Analytics no contribuyen a los totales de uso de los planes de CPM. Los proveedores de datos generalmente reciben una compensación por la optimización del contenido mediante planes de tarifa plana.</p><p>Consulte <a href="#cost-attribution">Atribución de costes para fuentes de datos CPM</a> para obtener más información. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Se ajusta al intervalo mensual de informes</b> </p> </td> 
   <td colname="col2"> <p>El sistema de informes se cierra después del quinto día de cada mes. Si no puede informar sobre el uso de CPM antes de ese momento, debe agregar esa cantidad al informe para el mes siguiente. Por ejemplo, supongamos que utiliza 1000 impresiones en octubre, que no cumple el plazo de presentación de informes de octubre y que utiliza 1000 impresiones en noviembre. En este caso, se informa del total de octubre y noviembre (2000) en diciembre, entre el 1 y el 5.</p><p><b>Sugerencia</b>: Siempre debe intentar informar del uso de CPM del mes anterior entre el primer y el quinto día del mes siguiente.</p><p>Puede notificar el uso de CPM hasta el quinto día del nuevo mes del calendario, pero esto no es recomendable. El informe del uso de CPM antes del 5 de cada mes da al Audience Manager tiempo para comprobar y procesar los datos.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Atribución de costes para fuentes de datos CPM {#cost-attribution}

En [!UICONTROL Audience Marketplace] debe informar automáticamente sobre las cantidades de impresión cada mes, para cada uno de sus segmentos. Se recomienda el uso de informes [!DNL CPM] en el nivel de segmento, de modo que la atribución de costes se realice automáticamente.

<!-- marketplace_cpm_billing.xml -->

### Resumen de facturación {#billing-summary}

Debe enviar [!DNL CPM] cantidades de impresión de fuentes de datos entre el primer y el quinto día de cada mes del calendario. Para hacerlo correctamente, le recomendamos que [Informe del uso del CPM en el nivel de segmento](#segment-level-report).

>[!TIP]
>Al informar sobre el uso de [!DNL CPM] a nivel de segmento, la sección de informes a nivel de fuente de datos se rellena automáticamente con las cantidades de uso correspondientes.

Si necesita [!UICONTROL Report CPM Usage at Data Feed Level], debe compilar individualmente todas las impresiones entregadas para cada fuente en el mes del calendario anterior e informarlas según la asignación de facturación descrita en este artículo.

Después de informar del número [!DNL CPM] del mes del calendario anterior, [!DNL Adobe] hará lo siguiente:

* Cree una factura y una factura basadas en la tasa [!DNL CPM] de cada fuente de datos suscrita.
* Pagar las tarifas que deben pagar los proveedores de datos (vendedores) en función de su [!DNL CPM] uso registrado.

>[!IMPORTANT]
>
>Como comprador, todos los totales de impresiones notificadas deben ser verdaderos y exactos. Si no informa de los totales de impresiones antes del quinto día de cada mes, debe incluir los totales del mes sin registrar en el mes siguiente.

<br> 

## Asignar impresiones en el nivel de fuente según las reglas de calificación de rasgos {#assign-impressions}

El caso de uso [!UICONTROL Activation] permite utilizar características en la fuente de datos correspondiente para crear segmentos en el [Generador de segmentos](../../../features/segments/segment-builder.md) y asignar esos segmentos a un destino. Los operadores booleanos [!UICONTROL AND], [!UICONTROL OR] y [!UICONTROL NOT] permiten establecer las condiciones para la clasificación de rasgos y segmentos.

Cuando [Informe del uso de CPM en el nivel de fuente de datos](#feed-level-report), debe asignar las impresiones proporcionalmente para cada fuente de datos, según los operadores [!DNL Boolean] utilizados en las reglas de clasificación de características. En la tabla siguiente se muestra cómo asignar correctamente impresiones por regla booleana o tipo de rasgo.

>[!TIP]
>[Informe del uso del CPM en el nivel de segmento](#segment-level-report) para que el Audience Manager realice automáticamente los informes de nivel de fuente de datos.

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
   <td colname="col2"> <p>Aplique el 100% de los totales de impresiones entregadas a todas las características del proveedor en un segmento basado en reglas que utilice una condición booleana <span class="wintitle"> AND</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> O</span> </p> </td> 
   <td colname="col2"> <p>Aplique una asignación ponderada de los totales de impresiones entregadas a todas las características del proveedor en un segmento basado en reglas que utilice una condición booleana OR. La asignación ponderada se calcula mediante la fórmula siguiente:</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NO</span> </p> </td> 
   <td colname="col2"> <p>Aplique el 100% de los totales de impresiones entregadas a todas las características del proveedor en un segmento basado en reglas que utilice una condición booleana <span class="wintitle"> NOT</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segmentos algorítmicos </p> </td> 
   <td colname="col2"> <p>Aplique el 100% de los totales de impresiones entregadas a todas las fuentes de proveedor en un segmento que contenga características algorítmicas. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Ejemplos de facturación {#billing-examples}

Los ejemplos siguientes ilustran cómo se realiza la asignación de uso de [!DNL CPM] en el nivel de fuente de datos.

>[!IMPORTANT]
>Le recomendamos que [Informe del uso del CPM en el nivel de segmento](#segment-level-report) en su lugar, para que este proceso se realice automáticamente.

Consideremos el siguiente escenario:

![facturación-ejemplos](assets/billing-examples.png)

<br> 

### Caso 1: Segmentos con reglas de clasificación AND

Este segmento contiene 3 características de proveedores de datos independientes. Dado que la calificación de segmentos se basa en una condición [!UICONTROL AND] , los visitantes deben realizar las características de las tres fuentes para poder optar al segmento.

![](assets/billing-segment-and.png)

Con una condición [!UICONTROL AND], debe asignar el 100% de las impresiones recibidas durante el mes a los tres proveedores de datos. En la sección [!UICONTROL Audience Marketplace > Payables], se acredita a cada proveedor con 1000 000 impresiones.

Este ejemplo se aplica a segmentos que utilizan operadores [!DNL Boolean] [!UICONTROL NOT] o a segmentos que contienen características algorítmicas.

<br> 

### Caso 2: Segmentos con reglas de calificación O

Este segmento contiene 3 características de proveedores de datos independientes. Dado que la calificación de segmentos se basa en una condición [!UICONTROL OR] , los visitantes deben realizar al menos una de las tres características para calificar para el segmento.

No podemos saber qué rasgo es responsable de una impresión porque la calificación se basa en una condición [!UICONTROL OR]. Como resultado, en la sección [!UICONTROL Audience Marketplace > Payables] se da crédito a cada proveedor con una asignación ponderada de las impresiones totales, en función de la población de rasgos.

![billing-segment-or](assets/billing-segment-or.png)

<br> 

### Caso 3: Segmentos con casos de uso de modelado y activación

En este ejemplo se describe la atribución en función de dos casos de uso de Fuente de datos: Modelado y Activación. En el ejemplo, se busca dos proveedores de datos, con la siguiente información:

![fuente de datos](assets/feed-use-cases.png)

En la siguiente tabla, el segmento X contiene dos características, T1 y T2, con la regla de segmento T1 O T2, donde:

* T1 es un rasgo de la fuente de datos A;
* T2 es un rasgo algorítmico modelado a partir de características de terceros de la fuente de datos A y la fuente de datos B.

El segmento se asigna a un destino y se introducen 1000 000 impresiones para este segmento en un mes, mediante [Informes de nivel de segmento](#segment-level-report).

De estas 1,000,000 impresiones:

* T1 representa el 40% de la población del segmento, lo que supone 400.000 impresiones para la fuente A.
* T2 representa el 60% de la población del segmento, lo que equivale a 600.000 impresiones para la fuente A y la fuente B.

A nivel de fuente de datos, la manera en que se asignan las impresiones es:

* La fuente de datos A recibe 600 000 impresiones del rasgo T2 (que se basa en los rasgos de la fuente de datos A y de la fuente de datos B, por lo que ambas reciben las impresiones) y 400 000 impresiones del rasgo T1 (que es un rasgo de la fuente de datos A), que totalizan 1 000 00 impresiones.
* La fuente de datos B recibe 600 000 impresiones del rasgo T2 (ver la explicación anterior) y 0 impresiones del rasgo T1.

El desglose general por fuente de datos y caso de uso es el siguiente:

![desglose de fuentes](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>Para el caso de uso de modelado, solo debe informar del uso de CPM tras la activación. Si solo ejecuta un modelo, pero no lo activa, no se requiere ningún informe de uso.

<br> 

## Asignación de facturación e impresión para fuentes de datos de tarifa plana {#billing-flat-fee}

Una fuente de datos de tarifa fija le factura una cantidad fija cada mes, independientemente de cuándo se inicie la suscripción o de cuántas impresiones utilice. Las tarifas no se prorratean para el uso parcial de mes o intervalos. Al igual que con la facturación de CPM, los Adobes generarán una factura y le facturarán a la tarifa mensual fija de sus fuentes de datos suscritas.

Por ejemplo, supongamos que ha decidido activar ciertos rasgos en una fuente a mediados del mes. Se le facturará a la tarifa completa mensual independientemente del momento en que haya iniciado la suscripción o activado características específicas.
