---
description: Qué hacer cuando las hojas de cálculo devuelven un error o se produce un error en la solicitud masiva.
seo-description: What to do when the worksheets return an error or your bulk request fails.
seo-title: Troubleshooting Tips for Bulk Management Tools
solution: Audience Manager
title: Consejos para la resolución de problemas de Herramientas de gestión masiva
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# Consejos para la resolución de problemas de Herramientas de gestión masiva{#troubleshooting-tips-for-bulk-management-tools}

Qué hacer cuando las hojas de cálculo devuelven un error o se produce un error en la solicitud masiva.

>[!IMPORTANT]
>
>Los Herramientas de administración masiva no son una oferta Adobe Systems que se admita oficialmente. La solución de problemas y el soporte a través del Servicio de atención al cliente se manejarán caso por caso.

<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[Los permisos](../../features/administration/administration-overview.md) RBAC grupo asignados en el [!DNL Audience Manager] IU se respetan en el [!UICONTROL Bulk Management Tools].

Factores gustar la tráfico de red pesada, el uso del servidor y los grandes conjuntos de datos pueden causar que un solicitud masivo falle o se agote el tiempo de espera. Si hay un problema, la hoja de cálculo deja de escribir datos y muestra un mensaje de error. Cuando esto sucede, usted debe:

* Lea el mensaje de error.
* Arregle el problema.
* Eliminar todas las filas que ya se han actualizado.
* Vuelva a probar la solicitud masiva.

## Authentication errores, retrasos prolongados o comportamiento que no responde {#delays-behavior}

En la tabla siguiente se enumeran algunos problemas comunes que pueden surgir al realizar solicitudes masivas con las hojas de cálculo. Intente solucionar estos problemas con las soluciones recomendadas. Si las soluciones recomendadas no resuelven el problema, debe guardar el trabajo, reiniciar el equipo e intentar el solicitud de nuevo sin iniciar ni trabajar con otras aplicaciones.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problema </th> 
   <th colname="col2" class="entry"> Solución </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Error Authentication</b> </td> 
   <td colname="col2"> 
    <b>Actualizar a la versión más reciente de Microsoft Excel: Cuando se publica una nueva versión de Microsoft Excel</b> y está utilizando una versión anterior, es posible que encuentre un error de autenticación en la hoja de cálculo de administración masiva. Actualice a la versión más reciente de Microsoft Excel para resolver el error de autenticación.
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Largos retrasos</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Desactivar el modo</b> de compatibilidad: compruebe si tiene otras hojas de cálculo abiertas en el modo de compatibilidad de Microsoft Excel. Compatibilidad modo puede aumentar los tiempos de ejecución. Cerrar cualquier hoja de cálculo que pueda tener abierta en este modo y pruebe de nuevo su solicitud masiva. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Recursos del sistema: Los</b> recursos limitados del sistema contribuyen a los largos retrasos. Intente cerrar todos sus otros programas antes de hacer una solicitud masiva. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Sin respuesta</b> </td> 
   <td colname="col2">Si hace clic en un botón de acción y no sucede nada: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Asegúrese de que dispone del conjunto correcto de encabezados para la acción de selección. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Asegúrese de usar la hoja de cálculo correcta para los encabezados copiados. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Compruebe la posición de los datos que desea utilizar en una operación de forma masiva. Todos los encabezados inicio en la columna A, fila 1. Todos los datos van en los encabezados correspondientes a partir de la columna A, fila 2 (inmediatamente debajo de los encabezados). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Mensajes de error

A veces, puede recibir mensajes de error al realizar cambios masivos. Para interpretar el mensaje de error, consulte [Códigos de respuesta definidos](/help/using/api/rest-api-main/aam-api-getting-started.md) en nuestra documentación de API.
