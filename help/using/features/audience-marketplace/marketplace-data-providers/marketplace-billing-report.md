---
description: Genere un informe de facturación del Audience Marketplace para ver el uso de las fuentes de datos del mes anterior para cada uno de sus suscriptores. Puede crear un informe del mes anterior en cualquier momento. Sin embargo, el informe es más preciso cuando se genera el décimo día del mes actual o después de este.
seo-description: Generate an Audience Marketplace billing report to view data feed usage for the previous month for each of your subscribers. You can create a report for the previous month at any time. However, the report is more accurate when you generate it on or after the 10th day of the current month.
seo-title: Billing for Data Feed Providers
solution: Audience Manager
title: Facturación para proveedores de fuentes de datos
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
exl-id: aca2cec1-d3a0-421c-83ca-1c11e9e7d4c7
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 1%

---

# Facturación para proveedores de fuentes de datos {#billing-for-data-feed-providers}

Genere un informe de facturación [!DNL Audience Marketplace] para ver el uso de fuentes de datos del mes anterior para cada uno de sus suscriptores. Puede crear un informe del mes anterior en cualquier momento. Sin embargo, el informe es más preciso cuando se genera el décimo día del mes actual o después de este.

## Descargar un informe de facturación {#download-billing-report}

Para descargar un informe:

1. Ir a **[!UICONTROL Audience Marketplace > Receivables]**.
1. Haga clic en **[!UICONTROL Generate Billing Report]**.

## Campos de informe definidos {#report-fields-defined}

Un informe de facturación contiene la siguiente información.

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo de informe </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID de proveedor de datos</span></b> </p> </td> 
   <td colname="col2"> <p>Su ID de proveedor de datos <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nombre de proveedor de datos</span></b> </p> </td> 
   <td colname="col2"> <p>Nombre de su empresa u organización. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID de comprador</span></b> </p> </td> 
   <td colname="col2"> <p>ID del comprador (suscriptor). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nombre de comprador</span></b> </p> </td> 
   <td colname="col2"> <p>El nombre de la empresa u organización del comprador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> ID de fuente </span></b> </p> </td> 
   <td colname="col2"> <p>El ID de la fuente de datos </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nombre de fuente</span></b> </p> </td> 
   <td colname="col2"> <p>Nombre de la fuente de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> casos de uso del plan</span></b> </p> </td> 
   <td colname="col2"> <p>Los casos de uso permiten a los vendedores controlar el uso que hacen los compradores de los datos. Las opciones incluyen: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segmentos y superposición </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modelado </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Activación </li> 
    </ul> <p>Ver <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> tipos de plan para fuentes de datos</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> unidad de medida</span></b> </p> </td> 
   <td colname="col2"> <p>Indica facturación de CPM o tarifa plana. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> precio de lista</span></b> </p> </td> 
   <td colname="col2"> <p>La tarifa de suscripción para cada fuente de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> precio con descuento</span></b> </p> </td> 
   <td colname="col2"> <p>La tarifa de suscripción para una fuente de datos con descuento. Ver <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> descuentos para proveedores de datos</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> unidades</span></b> </p> </td> 
   <td colname="col2"> <p>Varía por tipo de precio de fuente: </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Fuentes de datos de tarifa plana: solo devuelve 1. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">Fuentes de datos de CPM: Devuelve la cantidad de uso real de las fuentes de datos de CPM. Si un suscriptor no ha proporcionado datos de impresión para una fuente CPM, la celda Units está vacía y la celda Flag se establece en 1. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Costo total</span></b> </p> </td> 
   <td colname="col2"> <p>La cantidad <span class="keyword"> Audience Manager</span> factura a un comprador. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> período de facturación</span></b> </p> </td> 
   <td colname="col2"> <p> En el informe, este es el último día del mes anterior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> fecha de entrada</span></b> </p> </td> 
   <td colname="col2"> <p>La fecha en la que el comprador introdujo la información de uso/suscripción. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> fecha de inicio de suscripción</span></b> </p> </td> 
   <td colname="col2"> <p>La fecha en la que un comprador inició su suscripción a la fuente de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> fecha de finalización de suscripción</span></b> </p> </td> 
   <td colname="col2"> <p>La fecha en la que un comprador finalizó su suscripción a la fuente de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Indicador</span></b> </p> </td> 
   <td colname="col2"> <p> <i>Solo para fuentes CPM</i>. Las opciones de indicador incluyen: </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: Indica que un suscriptor ha informado sobre la información de uso al Audience Manager <span class="keyword"></span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: Indica que un suscriptor no ha informado sobre la información de uso al Audience Manager <span class="keyword"></span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Asignación de facturación e impresión para fuentes de datos de CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Asignación de facturación e impresión para fuentes de datos con tarifa plana](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Cómo informar sobre el uso de CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)
