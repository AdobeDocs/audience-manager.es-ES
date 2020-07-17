---
description: Qué hacer cuando las hojas de cálculo devuelven un error o la solicitud masiva falla.
seo-description: Qué hacer cuando las hojas de cálculo devuelven un error o la solicitud masiva falla.
seo-title: Consejos para la resolución de problemas de las herramientas de administración masiva
solution: Audience Manager
title: Consejos para la resolución de problemas de las herramientas de administración masiva
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 5%

---


# Consejos para la resolución de problemas de las herramientas de administración masiva{#troubleshooting-tips-for-bulk-management-tools}

Qué hacer cuando las hojas de cálculo devuelven un error o la solicitud masiva falla.



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[Los permisos](../../features/administration/administration-overview.md) de grupo RBAC asignados en la [!DNL Audience Manager] interfaz de usuario se respetan en la [!UICONTROL Bulk Management Tools].

Factores como el tráfico de red pesado, el uso del servidor y los grandes conjuntos de datos pueden hacer que una solicitud masiva falle o se agote el tiempo de espera. Si hay algún problema, la hoja de cálculo deja de escribir datos y muestra un mensaje de error. Cuando esto ocurra, debe:

* Lea el mensaje de error.
* Corrija el problema.
* Elimine todas las filas que ya se hayan actualizado.
* Intente la solicitud masiva de nuevo.

## Errores de autenticación, retrasos prolongados o comportamiento no interactivo {#delays-behavior}

La siguiente tabla lista algunos problemas comunes que puede encontrar al realizar solicitudes masivas con las hojas de cálculo. Intente solucionar estos problemas con las soluciones recomendadas. Si las soluciones recomendadas no resuelven el problema, debe guardar el trabajo, reiniciar el equipo e intentar la solicitud de nuevo sin iniciar ni trabajar con otras aplicaciones.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problema </th> 
   <th colname="col2" class="entry"> Solución </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Error de autenticación</b> </td> 
   <td colname="col2"> 
    <b>Actualización a la versión más reciente de Microsoft Excel</b>: Cuando se lanza una nueva versión de Microsoft Excel y se utiliza una versión anterior, es posible que se produzca un error de autenticación en la hoja de cálculo Administración masiva. Actualice a la versión más reciente de Microsoft Excel para resolver el error de autenticación.
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Largos retrasos</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Desactivar modo</b>de compatibilidad: Compruebe si hay otras hojas de cálculo abiertas en el modo de compatibilidad de Microsoft Excel. El modo de compatibilidad puede aumentar los tiempos de ejecución. Cierre las hojas de cálculo que pueda haber abierto en este modo e intente de nuevo la solicitud masiva. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Recursos</b>del sistema: La escasez de recursos del sistema contribuye a las demoras prolongadas. Intente cerrar todos los demás programas antes de realizar una solicitud masiva. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Sin respuesta</b> </td> 
   <td colname="col2">Si hace clic en un botón de acción y no sucede nada: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Asegúrese de que tiene el conjunto correcto de encabezados para la acción de selección. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Asegúrese de que está utilizando la hoja de cálculo correcta para los encabezados copiados. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Compruebe la posición de los datos que desea utilizar en una operación masiva. Todos los encabezados inicios en la columna A, fila 1. Todos los datos van en los encabezados correspondientes comenzando en la columna A, fila 2 (inmediatamente debajo de los encabezados). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Mensajes de error

A veces, puede recibir mensajes de error al realizar cambios masivos. Para interpretar el mensaje de error, consulte Códigos [de respuesta definidos](/help/using/api/rest-api-main/aam-api-getting-started.md) en nuestra documentación de API.

