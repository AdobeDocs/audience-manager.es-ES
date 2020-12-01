---
description: Las características de carpeta le permiten acumulado automáticamente en un segmento objetivo las características que residen dentro de la misma carpeta y todas las carpetas secundarias.
keywords: segment size estimator;sse
seo-description: Las características de carpeta le permiten acumulado automáticamente en un segmento objetivo las características que residen dentro de la misma carpeta y todas las carpetas secundarias.
seo-title: Características de la carpeta acerca de
solution: Audience Manager
title: Características de la carpeta acerca de
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 1%

---


# Acerca de los rasgos de carpetas {#folder-traits-about}

[!UICONTROL Folder traits] permite acumulado automáticamente en un segmento objetivo las características que residen en la misma carpeta y todas las carpetas secundarias.

## Ventajas del uso de características de carpeta {#benefits}

Un [!UICONTROL folder trait] contiene todas las características de una carpeta principal y sus carpetas secundarias asociadas. Esto le permite segmentar y destinatario automáticamente a los usuarios en diferentes niveles de carpeta. Por ejemplo, supongamos que tiene una estructura de carpetas como esta:

`*` Electrónica (principal)

    `*` Portátiles (secundarios)

        `*` Marcas (nieto)

[!UICONTROL Folder traits] califique a todos los usuarios de estas carpetas en una carpeta creada automáticamente  [!DNL Electronics] [!UICONTROL Folder Trait] (en función del nombre de la carpeta principal). Y este proceso se repite a medida que se desplaza hacia abajo por la estructura de archivos. En este caso, las características de las carpetas capturan a todos los usuarios de las carpetas Portátiles y Marcas en un equipo portátil creado automáticamente [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] se pueden seleccionar en expresiones de segmentos. Seleccionar un [!UICONTROL folder trait] equivale a seleccionar todos los rasgos dentro de esa carpeta y sus subcarpetas con una agrupación [!UICONTROL OR].

![](assets/folder-traits-compare-border.jpg)

## Realización de características de carpeta: actualización y frecuencia {#folder-traits-realization}

El recuento de frecuencia de una característica de carpeta es la suma de las realizaciones de las características de su carpeta y sus carpetas secundarias. La siguiente ilustración muestra las características A, B y C, que residen en la carpeta Automóvil. Considere que cada una de las características tiene las siguientes realizaciones:

* Característica A: 5
* Rasgo B: 1
* Característica C: 1

En este caso, el [!DNL Automobile Folder Trait] tiene 7 realizaciones.

![](assets/folder_traits_rollup_border.png)

## Sistema de informes de características de la carpeta {#folder-traits-reporting}

[!UICONTROL Folder traits] capture a todos los usuarios de las características de la estructura de carpetas debajo de ellos. Si mueve una característica de una carpeta a otra, el cambio se propaga a nuestros [servidores de recopilación de datos](../../reference/system-components/components-data-collection.md) como un cambio de regla de rasgo. El sistema de informes se actualiza en la siguiente ejecución del sistema de informes para reflejar este cambio en los intervalos de fechas del sistema de informes (1, 7, 14, 30, 60, 90). Los números de sistemas de informes antiguos de los días anteriores no cambiarán.

## Permisos de Controles de acceso basados en roles (RBAC) {#role-based-access-controls}

Para compañías que utilizan [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), los usuarios con los permisos [!UICONTROL RBAC] adecuados pueden cambiar la fuente de datos asociada a [!UICONTROL folder trait]. Un usuario debe pertenecer a un grupo con cualquiera de los siguientes elementos:

* `READ` y  `WRITE` agrupe permisos en un origen de datos de características.
* `VIEW_ALL_TRAITS` y permisos de  `EDIT_ALL_TRAITS` comodines para fuentes de datos de características.

Descubra cómo asignar [!UICONTROL RBAC] permisos en nuestra [documentación de administración](../../features/administration/administration-overview.md#create-group).

## Límites y otras consideraciones {#limits}

| Elemento | Descripción |
|---|---|
| Tipo de característica | [!UICONTROL Onboarded traits] y  [!UICONTROL algorithmic traits] contribuir como máximo 1 realización a la frecuencia  [!UICONTROL folder trait]de un |
| Desplazamiento de características entre carpetas | Si se mueve una característica de una carpeta a otra, se descalificará esa característica de la primera carpeta y se calificará para la segunda [!UICONTROL folder trait]. Esto significa que si elimina o mueve una característica de la carpeta, los usuarios de la población de características no se segmentarán de los segmentos mediante la característica de la carpeta como expresión de segmentos. <br> Al asignar segmentos o grupos de informes de Adobe Analytics a su organización Experience Cloud, Audience Manager crea automáticamente segmentos y características nuevos, correspondientes y de sólo lectura. No se puede editar ni cambiar la ubicación de almacenamiento de estas características desde Audience Manager. Sin embargo, cualquier cambio que realice en los segmentos o grupos de informes asignados de Adobe Analytics se refleja en el Audience Manager. |
| Variables del sistema | [!UICONTROL Folder traits] no se puede realizar en llamadas de evento mediante el  `d_sid` parámetro . |
| Informes | [!UICONTROL Folder traits] son características calculadas automáticamente y no aparecen en  **[!UICONTROL Overlap Reports]**. |