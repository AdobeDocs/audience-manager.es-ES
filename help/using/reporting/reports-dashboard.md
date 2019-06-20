---
description: Utilice el panel para ver información sobre los recuentos de visitantes únicos de los socios desglosados por tipos de características y segmentos durante un intervalo de tiempo especificado.
seo-description: Utilice el panel para ver información sobre los recuentos de visitantes únicos de los socios desglosados por tipos de características y segmentos durante un intervalo de tiempo especificado.
seo-title: Panel de informes
solution: Audience Manager
title: Panel de informes
uuid: 350 eee 2 d -72 f 7-42 a 7-916 b -60 f 9 a 362 c 5 cf
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# Reports Dashboard {#reports-dashboard}

Utilice el panel para ver información sobre los recuentos de visitantes únicos desglosados por tipos de características y segmentos, durante un intervalo de tiempo específico.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] utiliza [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para ampliar los permisos de grupos de usuarios al [!UICONTROL Dashboard]. Los usuarios solo pueden ver información en el tablero que tienen permisos para ver. [!UICONTROL RBAC] permite controlar qué datos de informes pueden ver los equipos internos.

Por ejemplo, una agencia que administra diferentes cuentas de anunciante puede configurar permisos de grupos de usuarios para que un equipo que administra la cuenta de Anunciante A pueda ver los datos de informes del Anunciante B. Este tablero puede utilizarse para solucionar problemas de entrega de datos.

Por ejemplo, si observa una caída o un pico en total de usuarios únicos con el desglose del tipo de usuario único (basado en reglas vs. conectado), tiene un mejor punto de partida para rastrear un posible problema de entrega de datos. If you notice a dip in total unique users and in on-boarded unique users, you can go to the [!UICONTROL On-boarding Status] report to see if there was an issue with an inbound file.

**Para acceder al panel:**

1. In the top navigation menu, click **[!UICONTROL Dashboard]**.
2. *Opcional* Seleccione el intervalo de tiempo deseado desde la última fecha de informe de la lista desplegable (7 días, 14 días (opción predeterminada), 30 días o 60 días).

   Depending on the period selected, the delta change in the [!UICONTROL Largest Traits] &gt; [!UICONTROL Most Changed Traits] and [!UICONTROL Largest Segments] &gt; [!UICONTROL Most Changed Segments] panels displays the change in unique visitors in the audience over the period ending today vs. the prior period of the same length. Por ejemplo: si selecciona 7 días, el delta compara los visitantes únicos de los siete días anteriores que finalizan hoy con los visitantes únicos de los siete días que finalizan siete días atrás.

   >[!NOTE]
   >
   >You can investigate a delta change that seems out of the ordinary by running a [!UICONTROL Trend] report. For example, if you see an unusually large delta change during the last seven days, you could run a [!UICONTROL Trend] report for the last 14 days (2 x 7) to better understand the numbers.

   Según los permisos del usuario registrado, se muestran los paneles siguientes:

   * [Únicos de socios](../reporting/reports-dashboard.md#partner-uniques)
   * [Características más grandes/Características cambiadas más](../reporting/reports-dashboard.md#largest-traits)
   * [Segmentos más grandes/Segmentos más modificados](../reporting/reports-dashboard.md#most-changed-segments)

3. *Haga clic sobre* **[!UICONTROL Normalize]** cualquier gráfico para mostrar todos los datos de la misma escala. También puede pasar el ratón sobre cualquier punto de datos para obtener más información.

## Partner Uniques {#partner-uniques}

Permission Required to View: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Este panel muestra el número de visitantes únicos durante el intervalo de tiempo especificado. Las líneas individuales con códigos de colores representan el número total de visitantes únicos y la cantidad de visitantes únicos capturados mediante características algorítmicas, basadas en reglas y en valores integrados.

>[!NOTE]
>
>El número total de visitantes únicos representa a los visitantes capturados mediante características basadas en reglas o en puntos. Sin embargo, el número total de visitantes únicos no es igual a la suma de visitantes únicos capturados mediante las características basadas en reglas y en las características integradas. El mismo usuario único puede representarse en cualquiera de estos dos tipos de características.

## Largest Traits/Most Changed Traits {#largest-traits}

Permission Required to View: [!UICONTROL View Traits].

![](assets/largest_traits.png)

Este panel muestra la cantidad de visitantes únicos capturados por distintas características.

Use the **[!UICONTROL Show]** drop-down list to display information about different types of traits: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded], or [!UICONTROL Rule-Based].

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
   <td colname="col2"> <p>Muestra información sobre el número de visitantes únicos ordenados por número (el más alto al más bajo) y también muestra el cambio delta de visitantes únicos durante el intervalo de tiempo especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Características más cambiadas</span> </p> </td> 
   <td colname="col2"> <p>Muestra información sobre el número de visitantes únicos ordenados por el cambio delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Largest Segments/Most Changed Segments {#most-changed-segments}

Permission Required to View: [!UICONTROL View Segments].

![](assets/largest_segments.png)

Este panel muestra la cantidad de visitantes únicos capturados por varios segmentos en tiempo real.

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
   <td colname="col1"> <p><span class="wintitle"> Segmentos más modificados</span> </p> </td> 
   <td colname="col2"> <p>Muestra información sobre el número de visitantes únicos ordenados por el cambio delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

