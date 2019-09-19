---
description: Las características de carpeta permiten agregar automáticamente características que residen en la misma carpeta y en todas las carpetas secundarias en un segmento objetivo.
keywords: estimador de tamaño de segmento;sse
seo-description: Las características de carpeta permiten agregar automáticamente características que residen en la misma carpeta y en todas las carpetas secundarias en un segmento objetivo.
seo-title: Características de la carpeta acerca de
solution: Audience Manager
title: Características de la carpeta acerca de
uuid: e561ce8f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: 263c55e6bd2c9ad7159306fc889b048d800c59da

---


# Características de la carpeta: Acerca de {#folder-traits-about}

[!UICONTROL Folder traits] permite agregar automáticamente características que residen en la misma carpeta y en todas las carpetas secundarias en un segmento objetivo.

## Ventajas del uso de características de carpeta {#benefits}

Un [!UICONTROL folder trait] contiene todas las características de una carpeta principal y sus carpetas secundarias asociadas. Esto le permite segmentar automáticamente y dirigirse a los usuarios en diferentes niveles de carpeta. Por ejemplo, supongamos que tiene una estructura de carpetas como esta:

`*` Electrónica (principal)

    `*` Portátiles (niños)

        `*` Marcas (nieto)

[!UICONTROL Folder traits] califique a todos los usuarios de estas carpetas en una carpeta creada automáticamente [!DNL Electronics] [!UICONTROL Folder Trait] (en función del nombre de la carpeta principal). Y este proceso se repite a medida que se mueve hacia abajo en la estructura de archivos. En este caso, las características de las carpetas capturan a todos los usuarios de las carpetas Portátiles y Marcas en un equipo portátil creado automáticamente [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] se pueden seleccionar en expresiones de segmento. Seleccionar una carpeta [!UICONTROL folder trait] equivale a seleccionar todas las características de esa carpeta y sus subcarpetas con una [!UICONTROL OR] agrupación.

![](assets/folder-traits-compare-border.jpg)

## Realización de características de carpeta: actualización y frecuencia {#folder-traits-realization}

El recuento de frecuencia de una característica de carpeta es la suma de las realizaciones de las características de su carpeta y sus carpetas secundarias. La siguiente ilustración muestra las características A, B y C, que residen en la carpeta Automóvil. Considere que cada una de las características tiene las siguientes realizaciones:

* Característica A: 5
* Rasgo B: 1
* Característica C: 1

En este caso, el [!DNL ]Automóvil [!UICONTROL Folder Trait] tiene 7 realizaciones.

![](assets/folder_traits_rollup_border.png)

## Informes de características de la carpeta {#folder-traits-reporting}

[!UICONTROL Folder traits] capture a todos los usuarios de las características de la estructura de carpetas debajo de ellos. Si mueve una característica de una carpeta a otra, el cambio se propaga a nuestros servidores [de recopilación de](../../reference/system-components/components-data-collection.md) datos como un cambio de regla de rasgo. Las actualizaciones de informes de los próximos informes se ejecutan para reflejar este cambio en los intervalos de fechas de los informes (1, 7, 14, 30, 60, 90). Los números de informes antiguos de los días anteriores no cambiarán.

## Permisos de controles de acceso basados en roles (RBAC) {#role-based-access-controls}

Para las empresas que utilizan [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), los usuarios con los [!UICONTROL RBAC] permisos adecuados pueden cambiar la fuente de datos asociada al [!UICONTROL folder trait]. Un usuario debe pertenecer a un grupo con cualquiera de los siguientes elementos:

* `READ` y `WRITE` agrupe permisos en un origen de datos de características.
* `VIEW_ALL_TRAITS` y `EDIT_ALL_TRAITS` comodines para fuentes de datos de características.

Obtenga información sobre cómo asignar [!UICONTROL RBAC] permisos en la documentación [de](../../features/administration/administration-overview.md#create-group)administración.

## Límites y otras consideraciones {#limits}

| Elemento | Descripción |
|---|---|
| Tipo de característica | [!UICONTROL Onboarded traits] y [!UICONTROL algorithmic traits] contribuir como máximo 1 realización a la frecuencia [!UICONTROL folder trait]de un |
| Desplazamiento de características entre carpetas | Si se mueve una característica de una carpeta a otra, se descalificará esa característica de la primera carpeta y se calificará para la segunda [!UICONTROL folder trait]. Esto significa que si elimina o mueve una característica de la carpeta, los usuarios de la población de características no se segmentarán de los segmentos mediante la característica de carpeta como expresión de segmento. <br> Al asignar segmentos o grupos de informes de Adobe Analytics a su organización de Experience Cloud, Audience Manager crea automáticamente segmentos y características nuevos, correspondientes y de solo lectura. No puede editar ni cambiar la ubicación de almacenamiento de estas características desde Audience Manager. Sin embargo, cualquier cambio que realice en los segmentos o grupos de informes de Adobe Analytics asignados se reflejará en Audience Manager. |
| Variables del sistema | [!UICONTROL Folder traits] no se puede realizar en llamadas de evento mediante el `d_sid` parámetro . |
| Creación de informes | [!UICONTROL Folder traits] son características calculadas automáticamente y no aparecen en **[!UICONTROL Overlap Reports]**. |