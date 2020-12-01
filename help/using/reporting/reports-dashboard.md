---
description: Use el Panel para vista información sobre los recuentos de visitantes únicos de sus socios desglosados por tipos de características y segmentos para un intervalo de tiempo específico.
seo-description: Use el Panel para vista información sobre los recuentos de visitantes únicos de sus socios desglosados por tipos de características y segmentos para un intervalo de tiempo específico.
seo-title: Panel de informes
solution: Audience Manager
title: Panel de informes
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 1%

---


# Panel de informes {#reports-dashboard}

Utilice el Panel para vista información sobre los recuentos de visitantes únicos desglosados por tipos de características y segmentos, durante un período de tiempo específico.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] utiliza  [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para ampliar los permisos de grupo de usuarios al  [!UICONTROL Dashboard]. Los usuarios solo pueden ver información en el panel de que tienen permisos para la vista. [!UICONTROL RBAC] le permite controlar qué datos de sistema de informes pueden realizar la vista los equipos internos.

Por ejemplo, una agencia que gestione diferentes cuentas de anunciante puede configurar permisos de grupo de usuarios para que un equipo que administre la cuenta del Anunciante A no pueda ver los datos de sistema de informes del Anunciante B. Este panel se puede utilizar para solucionar problemas de envío de datos.

Por ejemplo: si observa una caída, o un pico, en el total de usuarios únicos con el desglose del tipo de usuario único (basado en reglas vs. integrado), tiene un mejor punto de partida para rastrear un posible problema de envío de datos. Si observa una caída en el total de usuarios únicos y en los usuarios únicos integrados, puede ir al informe [!UICONTROL On-boarding Status] para ver si hubo algún problema con un archivo de entrada.

**Para acceder al Panel:**

1. En el menú de navegación superior, haga clic en **[!UICONTROL Dashboard]**.
2. ** OpcionalSeleccione el intervalo de tiempo deseado desde la última fecha de sistema de informes en la lista desplegable (7 días, 14 días (el valor predeterminado), 30 días o 60 días).

   Según el período seleccionado, el cambio delta en los paneles [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] y [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] muestra el cambio en visitantes únicos en la audiencia durante el período que termina hoy frente al período anterior de la misma duración. Por ejemplo, si selecciona 7 días, el delta compara los visitantes únicos de los siete días anteriores que finalizan hoy con los visitantes únicos de los siete días anteriores que finalizan hace siete días.

   >[!NOTE]
   >
   >Puede investigar un cambio delta que parezca fuera de lo normal ejecutando un informe [!UICONTROL Trend]. Por ejemplo: si ve un cambio delta inusualmente grande durante los últimos siete días, puede ejecutar un informe [!UICONTROL Trend] para los últimos 14 días (2 x 7) para comprender mejor los números.

   Según los permisos del usuario que ha iniciado sesión, se muestran los paneles siguientes:

   * [Únicos de socio](../reporting/reports-dashboard.md#partner-uniques)
   * [Características más grandes/Características más cambiadas](../reporting/reports-dashboard.md#largest-traits)
   * [Segmentos más grandes/Segmentos más cambiados](../reporting/reports-dashboard.md#most-changed-segments)

3. ** OpcionalHaga clic  **[!UICONTROL Normalize]** encima de cualquier gráfico para mostrar todos los datos en la misma escala. También puede pasar el ratón sobre cualquier punto de datos para ver más información.

## Únicos de socio {#partner-uniques}

Permiso necesario para la Vista: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Este panel muestra el número de visitantes únicos durante el intervalo de tiempo especificado. Las líneas individuales con códigos de color representan el número total de visitantes únicos y el número de visitantes únicos capturados con características algorítmicas, basadas en reglas y integradas.

>[!NOTE]
>
>El número total de visitantes únicos representa los visitantes capturados mediante características basadas en reglas o integradas. Sin embargo, el número total de visitantes únicos no es igual a la suma de visitantes únicos capturados con las características basadas en reglas y integradas. El mismo usuario único puede estar representado en cualquiera de estos dos tipos de características.

## Características más grandes/Características más cambiadas {#largest-traits}

Permiso necesario para la Vista: [!UICONTROL View Traits].

![](assets/largest_traits.png)

Este panel muestra el número de visitantes únicos capturados por varias características.

Utilice la lista desplegable **[!UICONTROL Show]** para mostrar información sobre los diferentes tipos de características: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded] o [!UICONTROL Rule-Based].

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
   <td colname="col1"> <p><span class="wintitle"> Características más grandes</span> </p> </td> 
   <td colname="col2"> <p>Muestra información sobre el número de visitantes únicos ordenados por número (de mayor a menor) y también lista el cambio delta de visitantes únicos durante el intervalo de tiempo especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Características más cambiadas</span> </p> </td> 
   <td colname="col2"> <p>Muestra información sobre el número de visitantes únicos ordenados por el cambio delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segmentos más grandes/Segmentos más cambiados {#most-changed-segments}

Permiso necesario para la Vista: [!UICONTROL View Segments].

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
   <td colname="col2"> <p>Muestra información sobre el número de visitantes únicos y el cambio delta de visitantes únicos durante el intervalo de tiempo especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmentos más cambiados</span> </p> </td> 
   <td colname="col2"> <p>Muestra información sobre el número de visitantes únicos ordenados por el cambio delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

