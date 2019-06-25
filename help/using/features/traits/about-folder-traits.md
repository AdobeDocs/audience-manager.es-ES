---
description: Las características de carpeta permiten agregar automáticamente características que residen en la misma carpeta y en todas las carpetas secundarias en un segmento de tabla dinámica.
keywords: estimador de tamaño de segmento; sse
seo-description: Las características de carpeta permiten agregar automáticamente características que residen en la misma carpeta y en todas las carpetas secundarias en un segmento de tabla dinámica.
seo-title: Características de carpeta acerca de
solution: Audience Manager
title: Características de carpeta acerca de
uuid: e 561 ce 8 f -6 c 90-44 a 7-b 034-685533 f 29030
translation-type: tm+mt
source-git-commit: c229bf71da5b07277811219cbf2794c3ca7bc89d

---


# Folder Traits: About {#folder-traits-about}

[!UICONTROL Folder traits] permiten agregar características que residen en la misma carpeta y en todas las carpetas secundarias en un segmento de tabla dinámica.

## Benefits of Using Folder Traits {#benefits}

A [!UICONTROL folder trait] contains all the traits in a parent folder and its associated child folders. Esto permite segmentar y segmentar automáticamente a los usuarios en diferentes niveles de carpetas. Por ejemplo, supongamos que tiene una estructura de carpetas como ésta:

`*` Electrónica (principal)

`*` Portátiles (secundarios)

`*` Marcas (terciario)

[!UICONTROL Folder traits] calificar a todos los usuarios de estas carpetas de forma automática [!DNL Electronics][!UICONTROL Folder Trait] (según el nombre de la carpeta principal). Y este proceso se repite a medida que mueve la estructura de archivos. In this case, folder traits capture all of the users in the Laptops and Brands folders in an automatically created Laptops [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] se seleccionan en expresiones de segmento. Selecting a [!UICONTROL folder trait] is equivalent to selecting all the traits within that folder and its subfolders with an [!UICONTROL OR] grouping.

![](assets/folder-traits-compare-border.jpg)

## Folder Traits Realization - Recency and Frequency {#folder-traits-realization}

El recuento de frecuencia de un rasgo de carpeta es la suma de las características de las características en su carpeta y en sus carpetas secundarias. La siguiente ilustración muestra las características A, B y C, que viven en la carpeta Automobile. Considere que cada una de las características tiene las siguientes características:

* Característica A: 5
* Característica B: 1
* Característica C: 1

In this case, the [!DNL ]Automobile [!UICONTROL Folder Trait] has 7 realizations.

![](assets/folder_traits_rollup_border.png)

## Folder Trait Reporting {#folder-traits-reporting}

[!UICONTROL Folder traits] capturar todos los usuarios de las características de la estructura de carpetas debajo de ellas. If you move a trait from a folder to another folder, the change propagates to our [data collection servers](../../reference/system-components/components-data-collection.md) just like a trait rule change. Las actualizaciones de informes en los próximos informes se ejecutan para reflejar este cambio en los intervalos de fechas de informes (1, 7, 14, 30, 60, 90, duración). Los números anteriores de informes de los días anteriores no cambiarán.

## Role-Based Access Controls (RBAC) Permissions {#role-based-access-controls}

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), your users with the appropriate [!UICONTROL RBAC] permissions are able to change the data source associated to the [!UICONTROL folder trait]. Un usuario debe pertenecer a un grupo con cualquiera de las siguientes opciones:

* `READ` y `WRITE` permisos de grupo a una fuente de datos de rasgos.
* `VIEW_ALL_TRAITS` y `EDIT_ALL_TRAITS` permisos comodín para fuentes de datos de características.

Learn how to assign [!UICONTROL RBAC] permissions in our [administration documentation](../../features/administration/administration-overview.md#create-group).

## Limits and Other Considerations {#limits}

| Elemento | Descripción |
|---|---|
| Tipo de característica | [!UICONTROL Onboarded traits] y [!UICONTROL algorithmic traits] contribuye en mayor medida 1 a la frecuencia de una [!UICONTROL folder trait]. |
| Desplazamiento de características entre carpetas | Moving a trait from a folder to another will disqualify that trait from the first folder trait and qualify it for the second [!UICONTROL folder trait]. Esto significa que, si elimina o mueve un rasgo de la carpeta, los usuarios de la población de características no se segmentarán de los segmentos utilizando el rasgo de carpeta como expresión de segmento. <br> Al asignar segmentos o grupos de informes de Adobe Analytics a su organización de Experience Cloud, Audience Manager crea automáticamente nuevos segmentos y características de solo lectura. No se puede editar ni modificar la ubicación de almacenamiento de estas características de Audience Manager. Sin embargo, cualquier cambio que realice en los segmentos o grupos de informes de Adobe Analytics asignados reflejará en Audience Manager. |
| Variables del sistema | [!UICONTROL Folder traits] no se puede activar en las llamadas de evento mediante `d_sid` el parámetro. |
| Creación de informes | [!UICONTROL Folder traits] son características autocalculadas y no aparecen en **[!UICONTROL Overlap Reports]**. |