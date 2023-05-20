---
description: Las características de carpeta permiten agregar automáticamente características que residen en la misma carpeta y en todas las carpetas secundarias a un segmento objetivo.
keywords: estimador de tamaño de segmento;sse
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Folder Traits  About
solution: Audience Manager
title: Acerca de los rasgos de carpeta
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 1%

---

# Acerca de los rasgos de carpetas {#folder-traits-about}

[!UICONTROL Folder traits] permite agregar automáticamente rasgos que residen en la misma carpeta y todas las carpetas secundarias a un segmento destino.

## Ventajas de utilizar las características de carpeta {#benefits}

A [!UICONTROL folder trait] contiene todos los rasgos de una carpeta principal y sus carpetas secundarias asociadas. Esto permite segmentar y segmentar automáticamente a los usuarios en diferentes niveles de carpeta. Por ejemplo, supongamos que tiene una estructura de carpetas como esta:

`*` Electrónica (principal)

    `*` Portátiles (secundarios)

        `*` Marcas (nieto)

[!UICONTROL Folder traits] calificar a todos los usuarios de estas carpetas en un creado automáticamente [!DNL Electronics] [!UICONTROL Folder Trait] (basado en el nombre de la carpeta principal). Y, este proceso se repite a medida que se desplaza hacia abajo en la estructura de archivos. En este caso, las características de carpeta capturan a todos los usuarios de las carpetas Portátiles y Marcas en un Portátil creado automáticamente [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] se pueden seleccionar en expresiones de segmento. Selección de una [!UICONTROL folder trait] equivale a seleccionar todos los rasgos de esa carpeta y sus subcarpetas con un [!UICONTROL OR] agrupación.

![](assets/folder-traits-compare-border.jpg)

## Realización de rasgos de carpeta: actualización y frecuencia {#folder-traits-realization}

El recuento de frecuencia de una característica de carpeta es la suma de las realizaciones de las características en su carpeta y en sus carpetas secundarias. La siguiente ilustración muestra los rasgos A, B y C, que se encuentran en la carpeta Automóvil. Considere que cada uno de los rasgos tiene las siguientes realizaciones:

* Rasgo A: 5
* Rasgo B: 1
* Rasgo C: 1

En este caso, la variable [!DNL Automobile Folder Trait] tiene 7 realizaciones.

![](assets/folder_traits_rollup_border.png)

## Informes de rasgos de carpeta {#folder-traits-reporting}

[!UICONTROL Folder traits] capture todos los usuarios de los rasgos en la estructura de carpetas debajo de ellos. Si mueve un rasgo de una carpeta a otra, el cambio se propaga a su [servidores de recopilación de datos](../../reference/system-components/components-data-collection.md) igual que un cambio en las reglas de rasgos. Los informes se actualizarán en la siguiente ejecución de informes para reflejar este cambio en los intervalos de fechas de los informes (1, 7, 14, 30, 60, 90). Los números anteriores de los informes de los días anteriores no cambiarán.

## Permisos de controles de acceso basados en roles (RBAC) {#role-based-access-controls}

Para empresas que utilizan [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), los usuarios con el correspondiente [!UICONTROL RBAC] Los permisos de pueden cambiar la fuente de datos asociada al [!UICONTROL folder trait]. Un usuario debe pertenecer a un grupo con cualquiera de las siguientes características:

* `READ` y `WRITE` permisos de grupo para una fuente de datos de rasgos.
* `VIEW_ALL_TRAITS` y `EDIT_ALL_TRAITS` permisos de comodines para fuentes de datos de rasgos.

Obtenga información sobre cómo asignar [!UICONTROL RBAC] permisos en nuestra [documentación de administración](../../features/administration/administration-overview.md#create-group).

## Límites y otras consideraciones {#limits}

| Elemento | Descripción |
|---|---|
| Tipo de rasgo | [!UICONTROL Onboarded traits] y [!UICONTROL algorithmic traits] aportar como máximo 1 realización a una [!UICONTROL folder trait]Es la frecuencia. |
| Desplazamiento de rasgos entre carpetas | Si se mueve un rasgo de una carpeta a otra, se descalificará ese rasgo del primer rasgo de carpeta y se clasificará para el segundo [!UICONTROL folder trait]. Esto significa que si elimina o mueve un rasgo de la carpeta, los usuarios de la población del rasgo se dessegmentarán de los segmentos utilizando el rasgo de carpeta como expresión de segmento. <br> Al asignar segmentos de Adobe Analytics o grupos de informes a su organización de Experience Cloud, Audience Manager crea automáticamente segmentos y rasgos nuevos y correspondientes de solo lectura. No se puede editar ni cambiar la ubicación de almacenamiento de estos rasgos desde el Audience Manager. Sin embargo, cualquier cambio que realice en los segmentos de Adobe Analytics o grupos de informes asignados se reflejará en Audience Manager. |
| Variables del sistema | [!UICONTROL Folder traits] no se puede realizar en llamadas de evento usando `d_sid` parámetro. |
| Informes | [!UICONTROL Folder traits] son rasgos calculados automáticamente y no aparecen en **[!UICONTROL Overlap Reports]**. |
