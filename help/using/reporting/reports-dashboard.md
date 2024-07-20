---
description: Utilice el panel para ver información sobre los recuentos de visitantes únicos de sus socios desglosados por tipos de rasgos y segmentos para un lapso de tiempo especificado.
seo-description: Use the Dashboard to view information about your partners' unique visitor counts broken down by trait types and segments for a specified time frame.
seo-title: Reports Dashboard
solution: Audience Manager
title: Panel de informes
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: Reporting Reference
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 0%

---

# Panel de informes {#reports-dashboard}

Utilice el panel para ver información sobre los recuentos de visitantes únicos desglosados por tipos de rasgos y segmentos para un lapso de tiempo específico.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] usa [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para extender permisos de grupos de usuarios a [!UICONTROL Dashboard]. Los usuarios solo pueden ver información en el panel para la que tienen permisos de visualización. La funcionalidad [!UICONTROL RBAC] permite controlar qué datos de informes pueden ver los equipos internos.

Por ejemplo, una agencia que administra diferentes cuentas de anunciante puede configurar permisos de grupos de usuarios para que un equipo que administra la cuenta del anunciante A no pueda ver los datos de informes del anunciante B. Este tablero se puede utilizar para solucionar problemas de entrega de datos.

Por ejemplo, si observa un descenso o un pico en el total de usuarios únicos con el desglose del tipo de usuario único (basado en reglas o integrado), tiene un mejor punto de partida para rastrear un posible problema de entrega de datos. Si observa un descenso en el total de usuarios únicos y en los usuarios únicos incorporados, puede ir al informe [!UICONTROL On-boarding Status] para ver si hubo un problema con un archivo entrante.

**Para tener acceso al panel:**

1. En el menú de navegación superior, haga clic en **[!UICONTROL Dashboard]**.
2. *Opcional* Seleccione el lapso de tiempo deseado en la última fecha de generación de informes de la lista desplegable (7 días, 14 días (valor predeterminado), 30 días o 60 días).

   Según el período seleccionado, el cambio delta en los paneles [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] y [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] muestra el cambio en los visitantes únicos en la audiencia durante el período que termina hoy en comparación con el período anterior de la misma duración. Por ejemplo, si selecciona 7 días, el delta compara los visitantes únicos de los siete días anteriores que finalizan hoy con los visitantes únicos de los siete días que finalizan hace siete días.

   >[!NOTE]
   >
   >Puede investigar un cambio delta que parezca fuera de lo normal ejecutando un informe [!UICONTROL Trend]. Por ejemplo, si observa un cambio delta inusualmente grande durante los últimos siete días, puede ejecutar un informe de [!UICONTROL Trend] durante los últimos 14 días (2 x 7) para comprender mejor las cifras.

   Según los permisos del usuario que ha iniciado sesión, se muestran los siguientes paneles:

   * [Exclusivos del socio](../reporting/reports-dashboard.md#partner-uniques)
   * [Características más grandes/Características más cambiadas](../reporting/reports-dashboard.md#largest-traits)
   * [Segmentos más grandes/Segmentos más cambiados](../reporting/reports-dashboard.md#most-changed-segments)

3. *Opcional* Haga clic en **[!UICONTROL Normalize]** sobre cualquier gráfico para mostrar todos los datos en la misma escala. También puede pasar el ratón sobre cualquier punto de datos para ver más información.

## Únicos de socio {#partner-uniques}

Permiso necesario para ver: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Este panel muestra la cantidad de visitantes únicos durante el lapso de tiempo especificado. Las líneas individuales con códigos de color representan la cantidad total de visitantes únicos y la cantidad de visitantes únicos capturados mediante rasgos algorítmicos, basados en reglas e incorporados.

>[!NOTE]
>
>El número total de visitantes únicos representa a los visitantes capturados mediante características basadas en reglas o integradas. Sin embargo, el número total de visitantes únicos no es igual a la suma de visitantes únicos capturados mediante los rasgos basados en reglas e incorporados. El mismo usuario único puede estar representado en cualquiera de estos dos tipos de rasgos.

## Características más grandes/características más cambiadas {#largest-traits}

Permiso necesario para ver: [!UICONTROL View Traits].

![](assets/largest_traits.png)

Este panel muestra el número de visitantes únicos capturados por varias características.

Utilice la lista desplegable **[!UICONTROL Show]** para mostrar información sobre distintos tipos de características: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded] o [!UICONTROL Rule-Based].

Este panel contiene las siguientes pestañas:

<table id="table_DA48BDEB4E0143BEA4EB85AC26FF6AE3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tabulación </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> rasgos más grandes</span> </p> </td> 
   <td colname="col2"> <p>Muestra información sobre la cantidad de visitantes únicos ordenados por número (de mayor a menor) y también enumera el cambio delta de visitantes únicos durante el lapso de tiempo especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> rasgos más cambiados</span> </p> </td> 
   <td colname="col2"> <p>Muestra información sobre el número de visitantes únicos ordenados por el cambio delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segmentos más grandes/Segmentos más cambiados {#most-changed-segments}

Permiso necesario para ver: [!UICONTROL View Segments].

![](assets/largest_segments.png)

Este panel muestra el número de visitantes únicos capturados por varios segmentos en tiempo real.

Este panel contiene las siguientes pestañas:

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tabulación </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmentos Más Grandes</span> </p> </td> 
   <td colname="col2"> <p>Muestra información sobre la cantidad de visitantes únicos y el cambio delta de visitantes únicos durante el lapso de tiempo especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> segmentos más cambiados</span> </p> </td> 
   <td colname="col2"> <p>Muestra información sobre el número de visitantes únicos ordenados por el cambio delta. </p> </td> 
  </tr> 
 </tbody> 
</table>
