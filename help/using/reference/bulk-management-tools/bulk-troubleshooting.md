---
description: Qué hacer cuando las hojas de cálculo devuelven un error o falla la solicitud masiva.
seo-description: What to do when the worksheets return an error or your bulk request fails.
seo-title: Troubleshooting Tips for Bulk Management Tools
solution: Audience Manager
title: Consejos para la resolución de problemas de las herramientas de administración masiva
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 4%

---

# Consejos para la resolución de problemas de las herramientas de administración masiva{#troubleshooting-tips-for-bulk-management-tools}

Qué hacer cuando las hojas de cálculo devuelven un error o falla la solicitud masiva.



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[Permisos de grupo de RBAC](../../features/administration/administration-overview.md) asignado en el [!DNL Audience Manager] Las IU se respetan en la [!UICONTROL Bulk Management Tools].

Factores como el tráfico de red intenso, el uso del servidor y los grandes conjuntos de datos pueden provocar errores en las solicitudes masivas o tiempos de espera. Si hay algún problema, la hoja de cálculo deja de escribir datos y muestra un mensaje de error. Cuando esto sucede, debe:

* Lea el mensaje de error.
* Solucione el problema.
* Elimine todas las filas que ya se hayan actualizado.
* Vuelva a intentar la solicitud masiva.

## Errores de autenticación, retrasos largos o comportamiento que no responde {#delays-behavior}

En la tabla siguiente se enumeran algunos problemas comunes que pueden producirse al realizar solicitudes masivas con las hojas de cálculo. Intente solucionar estos problemas con las soluciones recomendadas. Si las soluciones recomendadas no resuelven el problema, debe guardar el trabajo, reiniciar el equipo y volver a intentar la solicitud sin iniciar ni trabajar con otras aplicaciones.

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
    <b>Actualización a la última versión de Microsoft Excel</b>: Cuando se lanza una nueva versión de Microsoft Excel y se utiliza una versión anterior, puede encontrar un error de autenticación en la hoja de cálculo de Administración masiva. Actualice a la última versión de Microsoft Excel para resolver el error de autenticación.
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Largos retrasos</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Desactivar el modo de compatibilidad</b>: compruebe si tiene otras hojas de cálculo abiertas en el modo de compatibilidad de Microsoft Excel. El modo de compatibilidad puede aumentar los tiempos de ejecución. Cierre todas las hojas de cálculo que haya abierto en este modo y vuelva a intentar la solicitud masiva. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Recursos del sistema</b>: Los limitados recursos del sistema contribuyen a los largos retrasos. Cierre todos los demás programas antes de realizar una solicitud masiva. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Sin respuesta</b> </td> 
   <td colname="col2">Si hace clic en un botón de acción y no ocurre nada: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Asegúrese de que tiene el conjunto correcto de encabezados para la acción de selección. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Asegúrese de utilizar la hoja de cálculo correcta para los encabezados copiados. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Compruebe la posición de los datos que desea utilizar en una operación masiva. Todos los encabezados comienzan en la columna A, fila 1. Todos los datos se incluyen en los encabezados correspondientes a partir de la columna A, fila 2 (inmediatamente debajo de los encabezados). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Mensajes de error

A veces, puede recibir mensajes de error cuando realiza cambios masivos. Para interpretar el mensaje de error, consulte [Códigos de respuesta definidos](/help/using/api/rest-api-main/aam-api-getting-started.md) en nuestra documentación de API.
