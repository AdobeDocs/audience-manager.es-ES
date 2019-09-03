---
description: Las características de carpeta permiten agregar automáticamente características que residen en la misma carpeta y en todas las carpetas secundarias en un segmento de tabla dinámica.
keywords: estimador de tamaño de segmento; sse
seo-description: Las características de carpeta permiten agregar automáticamente características que residen en la misma carpeta y en todas las carpetas secundarias en un segmento de tabla dinámica.
seo-title: Características de carpeta acerca de
solution: Audience Manager
title: Características de carpeta acerca de
uuid: e 561 ce 8 f -6 c 90-44 a 7-b 034-685533 f 29030
translation-type: tm+mt
source-git-commit: 263c55e6bd2c9ad7159306fc889b048d800c59da

---


# Características de carpeta: Acerca de {#folder-traits-about}

[!UICONTROL Folder traits] permiten agregar características que residen en la misma carpeta y en todas las carpetas secundarias en un segmento de tabla dinámica.

## Beneficios del uso de características de carpeta {#benefits}

A [!UICONTROL folder trait] contiene todas las características de una carpeta principal y las carpetas secundarias asociadas. Esto permite segmentar y segmentar automáticamente a los usuarios en diferentes niveles de carpetas. Por ejemplo, supongamos que tiene una estructura de carpetas como ésta:

`*` Electrónica (principal)

`*` Portátiles (secundarios)

`*` Marcas (terciario)

[!UICONTROL Folder traits] calificar a todos los usuarios de estas carpetas de forma automática [!DNL Electronics][!UICONTROL Folder Trait] (según el nombre de la carpeta principal). Y este proceso se repite a medida que mueve la estructura de archivos. En este caso, las características de carpeta capturan todos los usuarios de las carpetas portátiles y marcas de un equipo portátil [!UICONTROL Folder Trait]creado automáticamente.

[!UICONTROL Folder traits] se seleccionan en expresiones de segmento. Seleccionar a [!UICONTROL folder trait] equivale a seleccionar todas las características de esa carpeta y sus subcarpetas con una [!UICONTROL OR] agrupación.

![](assets/folder-traits-compare-border.jpg)

## Realización de características de carpeta: Actualización y frecuencia {#folder-traits-realization}

El recuento de frecuencia de un rasgo de carpeta es la suma de las características de las características en su carpeta y en sus carpetas secundarias. La siguiente ilustración muestra las características A, B y C, que viven en la carpeta Automobile. Considere que cada una de las características tiene las siguientes características:

* Característica A: 5
* Característica B: 1
* Característica C: 1

En este caso [!DNL ], Automobile [!UICONTROL Folder Trait] tiene 7 realizaciones.

![](assets/folder_traits_rollup_border.png)

## Informes de características de carpeta {#folder-traits-reporting}

[!UICONTROL Folder traits] capturar todos los usuarios de las características de la estructura de carpetas debajo de ellas. Si mueve un rasgo de una carpeta a otra, el cambio se propaga a nuestros [servidores](../../reference/system-components/components-data-collection.md) de recopilación de datos como un cambio de regla de características. Las actualizaciones de informes en la próxima ejecución de informes para reflejar este cambio en los intervalos de fechas de informes (1, 7, 14, 30, 60, 90). Los números anteriores de informes de los días anteriores no cambiarán.

## Permisos de controles de acceso basados en roles (RBAC) {#role-based-access-controls}

Para las empresas que utilizan [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), los usuarios con [!UICONTROL RBAC] los permisos adecuados pueden cambiar la fuente de datos asociada a [!UICONTROL folder trait]la. Un usuario debe pertenecer a un grupo con cualquiera de las siguientes opciones:

* `READ` y `WRITE` permisos de grupo a una fuente de datos de rasgos.
* `VIEW_ALL_TRAITS` y `EDIT_ALL_TRAITS` permisos comodín para fuentes de datos de características.

Descubra cómo asignar [!UICONTROL RBAC] permisos en nuestra documentación [de administración](../../features/administration/administration-overview.md#create-group).

## Límites y otras consideraciones {#limits}

| Elemento | Descripción |
|---|---|
| Tipo de característica | [!UICONTROL Onboarded traits] y [!UICONTROL algorithmic traits] contribuye en mayor medida 1 a la frecuencia de una [!UICONTROL folder trait]. |
| Desplazamiento de características entre carpetas | Si se mueve un rasgo de una carpeta a otra, se descalifica el rasgo de la primera carpeta y se clasificará para el segundo [!UICONTROL folder trait]. Esto significa que, si elimina o mueve un rasgo de la carpeta, los usuarios de la población de características no se segmentarán de los segmentos utilizando el rasgo de carpeta como expresión de segmento. <br> Al asignar segmentos o grupos de informes de Adobe Analytics a su organización de Experience Cloud, Audience Manager crea automáticamente nuevos segmentos y características de solo lectura. No se puede editar ni modificar la ubicación de almacenamiento de estas características de Audience Manager. Sin embargo, cualquier cambio que realice en los segmentos o grupos de informes de Adobe Analytics asignados reflejará en Audience Manager. |
| Variables del sistema | [!UICONTROL Folder traits] no se puede activar en las llamadas de evento mediante `d_sid` el parámetro. |
| Creación de informes | [!UICONTROL Folder traits] son características autocalculadas y no aparecen en **[!UICONTROL Overlap Reports]**. |