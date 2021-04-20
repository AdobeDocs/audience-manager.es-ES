---
description: Utilice el tablero para ver información sobre los recuentos de visitantes únicos de sus socios desglosados por tipos de rasgos y segmentos durante un período de tiempo especificado.
seo-description: Utilice el tablero para ver información sobre los recuentos de visitantes únicos de sus socios desglosados por tipos de rasgos y segmentos durante un período de tiempo especificado.
seo-title: Panel de informes
solution: Audience Manager
title: Panel de informes
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: Reporting Reference
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 1%

---

# Panel de informes {#reports-dashboard}

Utilice el tablero para ver información sobre los recuentos de visitantes únicos desglosados por tipos de rasgos y segmentos durante un período de tiempo especificado.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] utiliza  [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para ampliar los permisos de grupo de usuarios a  [!UICONTROL Dashboard]. Los usuarios solo pueden ver información en el tablero que tienen permisos para ver. [!UICONTROL RBAC] permite controlar los datos que pueden ver los equipos internos de informes.

Por ejemplo, una agencia que administre diferentes cuentas de anunciante puede configurar permisos de grupo de usuarios para que un equipo que administre la cuenta del Anunciante A no pueda ver los datos de informes del Anunciante B. Este tablero se puede utilizar para solucionar problemas de envío de datos.

Por ejemplo, si observa un descenso o un pico en el total de usuarios únicos con el desglose del tipo de usuario único (basado en reglas vs. integrado), tiene un mejor punto de partida para rastrear un posible problema de envío de datos. Si observa una caída en el total de usuarios únicos y en los usuarios únicos incorporados, puede ir al informe [!UICONTROL On-boarding Status] para ver si hubo algún problema con un archivo entrante.

**Para acceder al tablero:**

1. En el menú de navegación superior, haga clic en **[!UICONTROL Dashboard]**.
2. ** OpcionalSeleccione el lapso de tiempo que desee en la última fecha del informe en la lista desplegable (7 días, 14 días (el valor predeterminado), 30 días o 60 días).

   Según el periodo seleccionado, el cambio delta en los paneles [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] y [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] muestra el cambio en visitantes únicos en la audiencia durante el periodo que termina hoy frente al periodo anterior de la misma duración. Por ejemplo, si selecciona 7 días, el delta compara a los visitantes únicos durante los siete días anteriores que terminan hoy con los visitantes únicos durante los siete días anteriores que terminan hace siete días.

   >[!NOTE]
   >
   >Puede investigar un cambio delta que parezca fuera de lo normal ejecutando un informe [!UICONTROL Trend]. Por ejemplo, si observa un cambio delta inusualmente grande durante los últimos siete días, puede ejecutar un informe [!UICONTROL Trend] para los últimos 14 días (2 x 7) para comprender mejor los números.

   En función de los permisos del usuario que ha iniciado sesión, se muestran los paneles siguientes:

   * [Únicos del socio](../reporting/reports-dashboard.md#partner-uniques)
   * [Rasgos más grandes/Rasgos más modificados](../reporting/reports-dashboard.md#largest-traits)
   * [Segmentos más grandes/segmentos más modificados](../reporting/reports-dashboard.md#most-changed-segments)

3. ** OpcionalHaga clic  **[!UICONTROL Normalize]** encima de cualquier gráfico para mostrar todos los datos en la misma escala. También puede pasar el ratón sobre cualquier punto de datos para ver más información.

## Únicos del socio {#partner-uniques}

Permiso necesario para ver: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Este panel muestra el número de visitantes únicos durante el lapso de tiempo especificado. Las líneas individuales con códigos de color representan el número total de visitantes únicos y el número de visitantes únicos capturados mediante características algorítmicas, basadas en reglas y integradas.

>[!NOTE]
>
>El número total de visitantes únicos representa a los visitantes capturados mediante características basadas en reglas o integradas. Sin embargo, el número total de visitantes únicos no es igual a la suma de visitantes únicos capturados usando los rasgos basados en reglas e incorporados. El mismo usuario único puede estar representado en cualquiera de estos dos tipos de rasgos.

## Rasgos más grandes/rasgos más modificados {#largest-traits}

Permiso necesario para ver: [!UICONTROL View Traits].

![](assets/largest_traits.png)

Este panel muestra el número de visitantes únicos capturados por varias características.

Utilice la lista desplegable **[!UICONTROL Show]** para mostrar información sobre diferentes tipos de características: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded] o [!UICONTROL Rule-Based].

Este panel contiene las fichas siguientes:

<table id="table_DA48BDEB4E0143BEA4EB85AC26FF6AE3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tabulación </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Rasgos más grandes</span> </p> </td> 
   <td colname="col2"> <p>Muestra información sobre el número de visitantes únicos clasificados por número (de mayor a menor) y también enumera el cambio delta de visitantes únicos durante el lapso de tiempo especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Características más modificadas</span> </p> </td> 
   <td colname="col2"> <p>Muestra información sobre la cantidad de visitantes únicos ordenados por el cambio delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segmentos más grandes/Segmentos más modificados {#most-changed-segments}

Permiso necesario para ver: [!UICONTROL View Segments].

![](assets/largest_segments.png)

Este panel muestra el número de visitantes únicos capturados por varios segmentos en tiempo real.

Este panel contiene las fichas siguientes:

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tabulación </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmentos más grandes</span> </p> </td> 
   <td colname="col2"> <p>Muestra información sobre el número de visitantes únicos y el cambio delta de visitantes únicos durante el lapso de tiempo especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmentos más modificados</span> </p> </td> 
   <td colname="col2"> <p>Muestra información sobre la cantidad de visitantes únicos ordenados por el cambio delta. </p> </td> 
  </tr> 
 </tbody> 
</table>
