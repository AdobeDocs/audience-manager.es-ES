---
description: Carpeta características le permiten agregado automáticamente las características que residen dentro de la misma carpeta y todas las carpetas secundarias en una segmento a la que se puede dirigir.
keywords: segmento estimador de tamaño; Sse
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Folder Traits  About
solution: Audience Manager
title: Carpeta Características sobre
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---

# Carpeta Rasgos: Acerca de {#folder-traits-about}

[!UICONTROL Folder traits] le permiten agregado automáticamente las características que residen en la misma carpeta y en todas las carpetas secundarias en un segmento de destino.

## Beneficios de usar Carpeta rasgos {#benefits}

A [!UICONTROL folder trait] contiene todas las características de una carpeta principal y sus carpetas secundarias asociadas. Esto le permite segmento y destino automáticamente a los usuarios en diferentes niveles de carpeta. Por ejemplo, supongamos que tiene una estructura de carpetas gustar esta:

`*` Electrónica (principal)

    `*` Portátiles (niños)

        `*` Marcas (nieto)

[!UICONTROL Folder traits] Califique a todos los usuarios de estas carpetas en una creada [!DNL Electronics] [!UICONTROL Folder Trait] automáticamente (según el nombre de la carpeta principal). Además, este proceso se repite a medida que avanza hacia abajo en la estructura de archivos. En este caso, los rasgos de carpeta capturan a todos los usuarios en las carpetas Portátiles y Marcas en un Equipo portátil [!UICONTROL Folder Trait]creado automáticamente.

[!UICONTROL Folder traits] se pueden seleccionar en expresiones segmento. Seleccionar una [!UICONTROL folder trait] es equivalente a seleccionar todas las características dentro de esa carpeta y sus subcarpetas con una [!UICONTROL OR] agrupación.

![](assets/folder-traits-compare-border.jpg)

## Carpeta Realización de rasgos - actualización y frecuencia {#folder-traits-realization}

El recuento Frecuencia de una característica de carpeta es la suma de las realizaciones de las características en su carpeta y sus carpetas secundarias. La siguiente ilustración muestra las características A, B y C, que residen en la carpeta Automóvil. Tenga en cuenta que cada uno de los rasgos tiene las siguientes realizaciones:

* Característica A: 5
* Característica B: 1
* Rasgo C: 1

En este caso, el [!DNL Automobile Folder Trait] tiene 7 realizaciones.

![](assets/folder_traits_rollup_border.png)

## Carpeta de informes de características {#folder-traits-reporting}

[!UICONTROL Folder traits] Capture a todos los usuarios desde las características de la estructura de carpetas debajo de ellos. Si mueve un rasgo de una carpeta a otra carpeta, el cambio se propaga a nuestros [servidores](../../reference/system-components/components-data-collection.md) de recopilación de datos solo gustar un rasgo regla cambio. La sistema de informes se actualizará en la ejecución del sistema de informes siguiente para reflejar este cambio en todos los intervalos de fechas del sistema de informes (1, 7, 14, 30, 60 y 90). Los números de sistema de informes antiguos de los días anteriores no cambiarán.

## Permisos de controles de acceso basados en roles (RBAC) {#role-based-access-controls}

Para las empresas que utilizan [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), los usuarios con los permisos adecuados [!UICONTROL RBAC] pueden cambiar las fuente de datos asociadas al [!UICONTROL folder trait]archivo . Un usuario debe pertenecer a una grupo con cualquiera de las siguientes opciones:

* `READ` y `WRITE` grupo permisos a un fuente de datos de rasgos.
* `VIEW_ALL_TRAITS` y `EDIT_ALL_TRAITS` permisos carácter comodín para fuentes de datos de características.

Aprenda a asignar [!UICONTROL RBAC] permisos en nuestra [documentación](../../features/administration/administration-overview.md#create-group) de administración.

## Límites y otras consideraciones {#limits}

| Elemento | Descripción |
|---|---|
| Tipo de rasgo | [!UICONTROL Onboarded traits] y [!UICONTROL algorithmic traits] contribuir como máximo 1 realización a la Frecuencia de A [!UICONTROL folder trait]. |
| Desplazamiento de características entre carpetas | Mover un rasgo de una carpeta a otra descalificará ese rasgo de la primera característica de carpeta y lo calificará para la segunda [!UICONTROL folder trait]. Esto significa que si elimina o mueve un rasgo de la carpeta, los usuarios de la población del rasgo no se segmentarán de los segmentos utilizando la característica de carpeta como segmento expresión. <br> Al asignar Adobe Analytics segmentos o grupos de informes a su organización Experience Cloud, Audience Manager crea automáticamente segmentos y características de solo lectura que corresponden. No se puede editar ni cambiar la ubicación almacenamiento de estas características desde Audience Manager. Sin embargo, cualquier cambio que realice en los segmentos de Adobe Analytics mapeados o en los grupos de informes se reflejará en Audience Manager. |
| Variables del sistema | [!UICONTROL Folder traits] no se puede realizar en llamadas evento utilizando el `d_sid` parámetro. |
| Creación de informes | [!UICONTROL Folder traits] son características calculadas automáticamente y no aparecen en **[!UICONTROL Overlap Reports]**. |
