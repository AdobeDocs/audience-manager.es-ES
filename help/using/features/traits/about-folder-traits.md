---
description: Las características de carpeta permiten acumular automáticamente características que residen dentro de la misma carpeta y todas las carpetas secundarias en un segmento objetivo.
keywords: estimador de tamaño de segmento;sse
seo-description: Las características de carpeta permiten acumular automáticamente características que residen dentro de la misma carpeta y todas las carpetas secundarias en un segmento objetivo.
seo-title: Acerca de los rasgos de carpeta
solution: Audience Manager
title: Acerca de los rasgos de carpeta
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: 'Rasgos '
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 1%

---

# Acerca de los rasgos de carpetas {#folder-traits-about}

[!UICONTROL Folder traits] permite agregar automáticamente características que residen dentro de la misma carpeta y todas las carpetas secundarias a un segmento objetivo.

## Ventajas del uso de características de carpeta {#benefits}

Un [!UICONTROL folder trait] contiene todos los rasgos de una carpeta principal y sus carpetas secundarias asociadas. Esto le permite segmentar y dirigirse automáticamente a sus usuarios en diferentes niveles de carpeta. Por ejemplo, supongamos que tiene una estructura de carpetas como esta:

`*` Electrónica (principal)

    `*` Portátiles (secundario)

        `*` Marcas (nieto)

[!UICONTROL Folder traits] califique a todos los usuarios de estas carpetas en una carpeta creada automáticamente  [!DNL Electronics] [!UICONTROL Folder Trait] (en función del nombre de la carpeta principal). Y, este proceso se repite a medida que baja por la estructura de archivos. En este caso, los rasgos de carpeta capturan a todos los usuarios de las carpetas Portátiles y Marcas en un equipo portátil creado automáticamente [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] se pueden seleccionar en expresiones de segmento. Seleccionar un [!UICONTROL folder trait] equivale a seleccionar todos los rasgos de esa carpeta y sus subcarpetas con una agrupación [!UICONTROL OR].

![](assets/folder-traits-compare-border.jpg)

## Realización de características de carpeta: actualización y frecuencia {#folder-traits-realization}

El recuento de frecuencia de un rasgo de carpeta es la suma de las realizaciones de los rasgos de su carpeta y sus carpetas secundarias. La siguiente ilustración muestra los rasgos A, B y C, que residen en la carpeta Automóvil. Tenga en cuenta que cada una de las características tiene las siguientes realizaciones:

* Rasgo A: 5
* Rasgo B: 1
* Rasgo C: 1

En este caso, el [!DNL Automobile Folder Trait] tiene 7 realizaciones.

![](assets/folder_traits_rollup_border.png)

## Informes de características de carpeta {#folder-traits-reporting}

[!UICONTROL Folder traits] capture todos los usuarios de los rasgos en la estructura de carpetas debajo de ellos. Si mueve un rasgo de una carpeta a otra carpeta, el cambio se propaga a nuestros [servidores de recopilación de datos](../../reference/system-components/components-data-collection.md) como un cambio en la regla de rasgos. Las actualizaciones de informes de los próximos informes se ejecutan para reflejar este cambio en los intervalos de fechas de los informes (1, 7, 14, 30, 60, 90). Los números de informes antiguos de los días anteriores no cambiarán.

## Permisos {#role-based-access-controls} de controles de acceso basados en roles (RBAC)

Para las empresas que usan [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), los usuarios con los permisos [!UICONTROL RBAC] adecuados pueden cambiar la fuente de datos asociada al [!UICONTROL folder trait]. Un usuario debe pertenecer a un grupo con cualquiera de las siguientes opciones:

* `READ` y permisos de  `WRITE` grupo a una fuente de datos de características.
* `VIEW_ALL_TRAITS` y permisos de  `EDIT_ALL_TRAITS` comodines para fuentes de datos de características.

Aprenda a asignar [!UICONTROL RBAC] permisos en nuestra [documentación de administración](../../features/administration/administration-overview.md#create-group).

## Límites y otras consideraciones {#limits}

| Elemento | Descripción |
|---|---|
| Tipo de rasgo | [!UICONTROL Onboarded traits] y  [!UICONTROL algorithmic traits] contribuir como máximo a una realización a  [!UICONTROL folder trait]la frecuencia de un |
| Desplazamiento de características entre carpetas | Mover un rasgo de una carpeta a otra descalificará ese rasgo de la primera carpeta y lo calificará para la segunda [!UICONTROL folder trait]. Esto significa que si elimina o mueve un rasgo de la carpeta, los usuarios de la población del rasgo no se segmentarán de los segmentos usando el rasgo de la carpeta como una expresión de segmento. <br> Al asignar segmentos o grupos de informes de Adobe Analytics a su organización Experience Cloud, el Audience Manager crea automáticamente segmentos y rasgos nuevos, correspondientes y de solo lectura. No se puede editar ni cambiar la ubicación de almacenamiento de estas características desde el Audience Manager . Sin embargo, cualquier cambio que realice en los segmentos o grupos de informes de Adobe Analytics asignados se reflejará en el Audience Manager. |
| Variables del sistema | [!UICONTROL Folder traits] no se puede realizar en llamadas de evento usando el  `d_sid` parámetro . |
| Informes | [!UICONTROL Folder traits] son características calculadas automáticamente y no aparecen en  **[!UICONTROL Overlap Reports]**. |
