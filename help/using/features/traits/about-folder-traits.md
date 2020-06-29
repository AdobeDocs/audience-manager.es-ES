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
ht-degree: 0%

---


# Características de la carpeta: Acerca de {#folder-traits-about}

[!UICONTROL Folder traits] permite acumulado automáticamente en un segmento objetivo las características que residen en la misma carpeta y todas las carpetas secundarias.

## Ventajas del uso de características de carpeta {#benefits}

Un [!UICONTROL folder trait] contiene todas las características de una carpeta principal y sus carpetas secundarias asociadas. Esto le permite segmentar y destinatario automáticamente a los usuarios en diferentes niveles de carpeta. Por ejemplo, supongamos que tiene una estructura de carpetas como esta:

`*` Electrónica (principal)

    `*` Portátiles (niños)

        `*` Brands (grandchild)

[!UICONTROL Folder traits] califique a todos los usuarios de estas carpetas en una carpeta creada automáticamente [!DNL Electronics] [!UICONTROL Folder Trait] (en función del nombre de la carpeta principal). Y este proceso se repite a medida que se desplaza hacia abajo por la estructura de archivos. En este caso, las características de las carpetas capturan a todos los usuarios de las carpetas Portátiles y Marcas en un equipo portátil creado automáticamente [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] se pueden seleccionar en expresiones de segmentos. Seleccionar una carpeta [!UICONTROL folder trait] equivale a seleccionar todas las características de esa carpeta y sus subcarpetas con una [!UICONTROL OR] agrupación.

![](assets/folder-traits-compare-border.jpg)

## Realización de características de carpeta: actualización y frecuencia {#folder-traits-realization}

El recuento de frecuencia de una característica de carpeta es la suma de las realizaciones de las características de su carpeta y sus carpetas secundarias. The illustration below shows traits A, B and C, which live in the Automobile folder. Consider that each of the traits have the following realizations:

* Trait A: 5
* Trait B: 1
* Trait C: 1

In this case, the [!DNL Automobile Folder Trait] has 7 realizations.

![](assets/folder_traits_rollup_border.png)

## Folder Trait Reporting {#folder-traits-reporting}

[!UICONTROL Folder traits] capture a todos los usuarios de las características de la estructura de carpetas debajo de ellos. Si mueve una característica de una carpeta a otra, el cambio se propaga a nuestros servidores [de recopilación de](../../reference/system-components/components-data-collection.md) datos como un cambio de regla de rasgo. The reporting updates in the next reporting run to reflect this change across the reporting date ranges (1, 7, 14, 30, 60, 90). The old reporting numbers from the previous days will not change.

## Permisos de Controles de acceso basados en roles (RBAC) {#role-based-access-controls}

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), your users with the appropriate [!UICONTROL RBAC] permissions are able to change the data source associated to the [!UICONTROL folder trait]. Un usuario debe pertenecer a un grupo con cualquiera de los siguientes elementos:

* `READ` y `WRITE` agrupe permisos en un origen de datos de características.
* `VIEW_ALL_TRAITS` and `EDIT_ALL_TRAITS` wild card permissions for trait data sources.

Obtenga información sobre cómo asignar [!UICONTROL RBAC] permisos en la documentación [de](../../features/administration/administration-overview.md#create-group)administración.

## Limits and Other Considerations {#limits}

| Elemento | Descripción |
|---|---|
| Trait type | [!UICONTROL Onboarded traits] y [!UICONTROL algorithmic traits] contribuir como máximo 1 realización a la frecuencia [!UICONTROL folder trait]de un |
| Moving traits between folders | Si se mueve una característica de una carpeta a otra, se descalificará esa característica de la primera carpeta y se calificará para la segunda [!UICONTROL folder trait]. Esto significa que si elimina o mueve una característica de la carpeta, los usuarios de la población de características no se segmentarán de los segmentos mediante la característica de la carpeta como expresión de segmentos. <br> Al asignar segmentos o grupos de informes de Adobe Analytics a su organización Experience Cloud, Audience Manager crea automáticamente segmentos y características nuevos, correspondientes y de solo lectura. No se puede editar ni cambiar la ubicación de almacenamiento de estas características desde Audience Manager. Sin embargo, cualquier cambio que realice en los segmentos o grupos de informes asignados de Adobe Analytics se refleja en el Audience Manager. |
| Variables del sistema | [!UICONTROL Folder traits] no se puede realizar en llamadas de evento mediante el `d_sid` parámetro . |
| Informes | [!UICONTROL Folder traits] son características calculadas automáticamente y no aparecen en **[!UICONTROL Overlap Reports]**. |