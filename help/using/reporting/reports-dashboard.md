---
description: Utilice el panel para ver información sobre los recuentos de visitantes únicos de los socios desglosados por tipos de características y segmentos para un intervalo de tiempo específico.
seo-description: Utilice el panel para ver información sobre los recuentos de visitantes únicos de los socios desglosados por tipos de características y segmentos para un intervalo de tiempo específico.
seo-title: Tablero de informes
solution: Audience Manager
title: Tablero de informes
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# Tablero de informes {#reports-dashboard}

Utilice el panel para ver información sobre los recuentos de visitantes únicos desglosados por tipos de características y segmentos, durante un período de tiempo específico.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] utiliza [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) para ampliar los permisos de grupo de usuarios al [!UICONTROL Dashboard]. Los usuarios solo pueden ver información en el tablero que tienen permisos para ver. [!UICONTROL RBAC] permite controlar los datos que pueden ver los equipos internos de informes.

Por ejemplo, una agencia que gestiona diferentes cuentas de anunciante puede configurar permisos de grupo de usuarios para que un equipo que administra la cuenta del anunciante A no pueda ver los datos de informes del anunciante B. Este tablero puede utilizarse para solucionar problemas de entrega de datos.

Por ejemplo: si observa una caída, o un pico, en el total de usuarios únicos con el desglose del tipo de usuario único (basado en reglas vs. integrado), tiene un mejor punto de partida para rastrear un posible problema de entrega de datos. Si observa una caída en el total de usuarios únicos y en los usuarios únicos integrados, puede ir al [!UICONTROL On-boarding Status] informe para ver si hubo algún problema con un archivo de entrada.

**Para acceder al tablero:**

1. En el menú de navegación superior, haga clic en **[!UICONTROL Dashboard]**.
2. *Opcional* Seleccione el intervalo de tiempo deseado desde la última fecha del informe en la lista desplegable (7 días, 14 días (el valor predeterminado), 30 días o 60 días).

   Según el período seleccionado, el cambio delta en los paneles [!UICONTROL Largest Traits] &gt; [!UICONTROL Most Changed Traits] y [!UICONTROL Largest Segments] &gt; [!UICONTROL Most Changed Segments] muestra el cambio en los visitantes únicos de la audiencia durante el período que termina hoy frente al período anterior de la misma duración. Por ejemplo: si selecciona 7 días, el delta compara a los visitantes únicos de los siete días anteriores que finalizaron hoy con los visitantes únicos de los siete días anteriores que finalizaron hace siete días.

   >[!NOTE]
   >
   >Puede investigar un cambio delta que parezca fuera de lo normal ejecutando un [!UICONTROL Trend] informe. Por ejemplo: si durante los últimos siete días ve un cambio de delta excepcionalmente grande, podría ejecutar un [!UICONTROL Trend] informe de los últimos 14 días (2 x 7) para comprender mejor los números.

   Según los permisos del usuario que ha iniciado sesión, se muestran los paneles siguientes:

   * [Únicos de socio](../reporting/reports-dashboard.md#partner-uniques)
   * [Características más grandes/Características más cambiadas](../reporting/reports-dashboard.md#largest-traits)
   * [Segmentos más grandes/Segmentos más cambiados](../reporting/reports-dashboard.md#most-changed-segments)

3. *Opcional* Haga clic **[!UICONTROL Normalize]** sobre cualquier gráfico para mostrar todos los datos en la misma escala. También puede pasar el ratón sobre cualquier punto de datos para ver más información.

## Únicos de socio {#partner-uniques}

Permiso necesario para ver: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Este panel muestra el número de visitantes únicos durante el intervalo de tiempo especificado. Las líneas individuales con códigos de color representan el número total de visitantes únicos y el número de visitantes únicos capturados con características algorítmicas, basadas en reglas y integradas.

>[!NOTE]
>
>El número total de visitantes únicos representa a los visitantes capturados mediante características basadas en reglas o integradas. Sin embargo, el número total de visitantes únicos no equivale a la suma de visitantes únicos capturados con las características basadas en reglas y integradas. El mismo usuario único puede estar representado en cualquiera de estos dos tipos de características.

## Características más grandes/Características más cambiadas {#largest-traits}

Permiso necesario para ver: [!UICONTROL View Traits].

![](assets/largest_traits.png)

Este panel muestra el número de visitantes únicos capturados por varias características.

Utilice la lista desplegable **[!UICONTROL Show]** para mostrar información sobre los distintos tipos de características: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded]o [!UICONTROL Rule-Based].

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
   <td colname="col2"> <p>Muestra información sobre el número de visitantes únicos ordenados por número (de mayor a menor) y también enumera el cambio delta de visitantes únicos durante el intervalo de tiempo especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Características más cambiadas</span> </p> </td> 
   <td colname="col2"> <p>Muestra información sobre el número de visitantes únicos ordenados por el cambio delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segmentos más grandes/Segmentos más cambiados {#most-changed-segments}

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
   <td colname="col2"> <p>Muestra información sobre el número de visitantes únicos y el cambio delta de visitantes únicos durante el intervalo de tiempo especificado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmentos más cambiados</span> </p> </td> 
   <td colname="col2"> <p>Muestra información sobre el número de visitantes únicos ordenados por el cambio delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

