---
description: Genere un informe de facturación de Audience Marketplace para ver el uso de fuentes de datos del mes anterior para cada uno de sus suscriptores. Puede crear un informe para el mes anterior en cualquier momento. Sin embargo, el informe es más preciso cuando se genera el día 10 del mes actual o después del mismo.
seo-description: Genere un informe de facturación de Audience Marketplace para ver el uso de fuentes de datos del mes anterior para cada uno de sus suscriptores. Puede crear un informe para el mes anterior en cualquier momento. Sin embargo, el informe es más preciso cuando se genera el día 10 del mes actual o después del mismo.
seo-title: Facturación de proveedores de fuentes de datos
solution: Audience Manager
title: Facturación de proveedores de fuentes de datos
topic: API DIL
uuid: 4 e 11 dbd 2-91 fd -4 b 59-a 66 d -86 a 92 e 0 de 655
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Billing for Data Feed Providers {#billing-for-data-feed-providers}

Generate an [!DNL Audience Marketplace] billing report to view data feed usage for the previous month for each of your subscribers. Puede crear un informe para el mes anterior en cualquier momento. Sin embargo, el informe es más preciso cuando se genera el día 10 del mes actual o después del mismo.

## Download a Billing Report {#download-billing-report}

Para descargar un informe:

1. Go to **[!UICONTROL Audience Marketplace > Receivables]**.
1. Haga clic en **[!UICONTROL Generate Billing Report]**.

## Report Fields Defined {#report-fields-defined}

Un informe de facturación contiene la información siguiente.

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo de informe </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID del proveedor de datos</span></b> </p> </td> 
   <td colname="col2"> <p>Your <span class="keyword"> Audience Manager</span> data provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nombre del proveedor de datos</span></b> </p> </td> 
   <td colname="col2"> <p>Nombre de empresa o organización. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Comprador PID</span></b> </p> </td> 
   <td colname="col2"> <p>ID del comprador (suscriptor). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nombre del comprador</span></b> </p> </td> 
   <td colname="col2"> <p>Nombre de empresa o organización del comprador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> ID de fuente</span></b> </p> </td> 
   <td colname="col2"> <p>El ID de la fuente de datos </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nombre de la fuente</span></b> </p> </td> 
   <td colname="col2"> <p>El nombre de la fuente de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Casos de uso del plan</span></b> </p> </td> 
   <td colname="col2"> <p>Los casos de uso permiten a los vendedores controlar cómo utilizan los datos los compradores. Las opciones incluyen: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segmentos y superposición </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modelado </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Activation </li> 
    </ul> <p>See <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> Plan Types for Data Feeds</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unidad de medida</span></b> </p> </td> 
   <td colname="col2"> <p>Indica la facturación por CPM o por tarifa fija. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Precio de lista</span></b> </p> </td> 
   <td colname="col2"> <p>Tarifa de suscripción por cada fuente de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Precio de descuento</span></b> </p> </td> 
   <td colname="col2"> <p>Tarifa de suscripción de una fuente de datos con descuentos. See <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> Discounts for Data Providers</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unidades</span></b> </p> </td> 
   <td colname="col2"> <p>Varía según el tipo de precio de la fuente: </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Fuentes de datos de tarifa plana: Solo devuelve 1. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">Fuentes de datos CPM: Devuelve la cantidad de uso real para fuentes de datos CPM. Si un suscriptor no ha proporcionado datos de impresión para una fuente CPM, la celda Unidades está vacía y la celda Indicador se establece en 1. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Costo total</span></b> </p> </td> 
   <td colname="col2"> <p>The amount <span class="keyword"> Audience Manager</span> bills a buyer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Período de facturación</span></b> </p> </td> 
   <td colname="col2"> <p> En el informe, es el último día del mes anterior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Fecha de entrada</span></b> </p> </td> 
   <td colname="col2"> <p>Fecha en la que un comprador ingresó información de suscripción/uso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Fecha inicial de suscripción</span></b> </p> </td> 
   <td colname="col2"> <p>Fecha en la que un comprador inició la suscripción de fuente de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Fecha final de suscripción</span></b> </p> </td> 
   <td colname="col2"> <p>La fecha en la que un comprador finalizó su suscripción de fuente de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Indicador</span></b> </p> </td> 
   <td colname="col2"> <p> <i>Solo para fuentes CPM</i>. Las opciones de indicador incluyen: </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: Indicates a subscriber has reported usage information to <span class="keyword"> Audience Manager</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: Indicates a subscriber has not reported usage information to <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Asignación de impresiones e impresiones para fuentes de datos CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Asignación de impresiones e impresiones para fuentes de datos de tarifa plana](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Uso del CPM de informes](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

