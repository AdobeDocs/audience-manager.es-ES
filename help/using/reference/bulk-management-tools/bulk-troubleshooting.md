---
description: Qué hacer cuando las hojas de cálculo devuelven un error o si falla la solicitud masiva.
seo-description: Qué hacer cuando las hojas de cálculo devuelven un error o si falla la solicitud masiva.
seo-title: Sugerencias para la solución de problemas de las herramientas de administración masiva
solution: Audience Manager
title: Sugerencias para la solución de problemas de las herramientas de administración masiva
uuid: 550908 a 1-e 24 e -4 f 31-954 b -7132 c 0 c 8 dc 3 e
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Troubleshooting Tips for Bulk Management Tools{#troubleshooting-tips-for-bulk-management-tools}

Qué hacer cuando las hojas de cálculo devuelven un error o si falla la solicitud masiva.



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]*No* se admite [!DNL Audience Manager]en. Esta herramienta se proporciona para su comodidad y solo como cortesía. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Los permisos de grupo RBAC](../../features/administration/administration-overview.md) asignados en [!DNL Audience Manager] la interfaz de usuario se aceptan en [!UICONTROL Bulk Management Tools]la.

Los factores como el tráfico de red pesado, el uso del servidor y los conjuntos de datos grandes pueden provocar errores o tiempo de espera en una solicitud masiva. Si hay un problema, la hoja de cálculo deja de escribir datos y muestra un mensaje de error. Cuando esto ocurra, debe:

* Lea el mensaje de error.
* Soluciona el problema.
* Elimine todas las filas que ya se hayan actualizado.
* Intente de nuevo la solicitud masiva.

## Long delays or unresponsive behavior {#delays-behavior}

La siguiente tabla enumera algunos problemas comunes que puede encontrar al realizar solicitudes masivas con las hojas de cálculo. Intente solucionar estos problemas con las soluciones recomendadas. Si las soluciones recomendadas no resuelven el problema, debe guardar su trabajo, reiniciar el equipo e intentar de nuevo la solicitud sin iniciar ni trabajar con otras aplicaciones.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problema </th> 
   <th colname="col2" class="entry"> Solución </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Retrasos largos</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Desactivar el modo de compatibilidad</b>: Compruebe si hay otras hojas de cálculo abiertas en el modo de compatibilidad de Microsoft Excel. El modo de compatibilidad puede aumentar los tiempos de ejecución. Cierre todas las hojas de cálculo que haya abierto en este modo e intente de nuevo la solicitud masiva. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Recursos del sistema</b>: Los recursos limitados del sistema contribuyen a retrasos prolongados. Intente cerrar todos los demás programas antes de realizar una solicitud masiva. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Sin respuesta</b> </td> 
   <td colname="col2">Si hace clic en un botón de acción y no sucede nada: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Asegúrese de que tiene el conjunto correcto de encabezados para la acción de selección. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Asegúrese de que está utilizando la hoja de cálculo correcta para los encabezados copiados. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Compruebe la posición de los datos que desee utilizar en una operación masiva. Todos los encabezados empiezan en la columna A, fila 1. Todos los datos van en los encabezados correspondientes empezando en la columna A, fila 2 (inmediatamente debajo de los encabezados). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

