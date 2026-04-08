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
TQID: https://experienceleague.adobe.com/fFfEE048TORlBUDrVYjizvI31iBfJeNsBl99uZJNefA
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 533
ht-degree: 0%

---

# Acerca de los rasgos de carpeta {#folder-traits-about}

[!UICONTROL Folder traits] le permite agregar automáticamente rasgos que residen en la misma carpeta y todas las carpetas secundarias en un segmento de destino.

## Ventajas de utilizar las características de carpeta {#benefits}

Un [!UICONTROL folder trait] contiene todos los rasgos de una carpeta principal y sus carpetas secundarias asociadas. Esto permite segmentar y segmentar automáticamente a los usuarios en diferentes niveles de carpeta. Por ejemplo, supongamos que tiene una estructura de carpetas como esta:

`*` elementos electrónicos (principales)

    `*` portátiles (secundarios)

        `*` marcas (nieto)

[!UICONTROL Folder traits] califica a todos los usuarios de estas carpetas en un(a) [!DNL Electronics] [!UICONTROL Folder Trait] creado(a) automáticamente (según el nombre de la carpeta principal). Y, este proceso se repite a medida que se desplaza hacia abajo en la estructura de archivos. En este caso, las características de carpeta capturan a todos los usuarios de las carpetas Portátiles y Marcas en un Portátil [!UICONTROL Folder Trait] creado automáticamente.

[!UICONTROL Folder traits] se pueden seleccionar en expresiones de segmento. Seleccionar un(a) [!UICONTROL folder trait] equivale a seleccionar todos los rasgos de esa carpeta y sus subcarpetas con una agrupación [!UICONTROL OR].

![](assets/folder-traits-compare-border.jpg)

## Realización de rasgos de carpeta: actualización y frecuencia {#folder-traits-realization}

El recuento de frecuencia de una característica de carpeta es la suma de las realizaciones de las características en su carpeta y en sus carpetas secundarias. La siguiente ilustración muestra los rasgos A, B y C, que se encuentran en la carpeta Automóvil. Considere que cada uno de los rasgos tiene las siguientes realizaciones:

* Rasgo A: 5
* Rasgo B: 1
* Rasgo C: 1

En este caso, [!DNL Automobile Folder Trait] tiene 7 realizaciones.

![](assets/folder_traits_rollup_border.png)

## Informes de rasgos de carpeta {#folder-traits-reporting}

[!UICONTROL Folder traits] captura a todos los usuarios a partir de los rasgos de la estructura de carpetas debajo de ellos. Si mueve un rasgo de una carpeta a otra, el cambio se propaga a nuestros [servidores de recopilación de datos](../../reference/system-components/components-data-collection.md) igual que un cambio en la regla de rasgos. Los informes se actualizarán en la siguiente ejecución de informes para reflejar este cambio en los intervalos de fechas de los informes (1, 7, 14, 30, 60, 90). Los números anteriores de los informes de los días anteriores no cambiarán.

## Permisos de controles de acceso basados en roles (RBAC) {#role-based-access-controls}

Para las empresas que usan [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), los usuarios con los permisos adecuados de [!UICONTROL RBAC] pueden cambiar el origen de datos asociado a [!UICONTROL folder trait]. Un usuario debe pertenecer a un grupo con cualquiera de las siguientes características:

* Permisos de grupo de `READ` y `WRITE` para un origen de datos de rasgos.
* `VIEW_ALL_TRAITS` y `EDIT_ALL_TRAITS` permisos de comodines para orígenes de datos de rasgos.

Aprenda a asignar permisos de [!UICONTROL RBAC] en nuestra [documentación de administración](../../features/administration/administration-overview.md#create-group).

## Límites y otras consideraciones {#limits}

| Elemento | Descripción |
|---|---|
| Tipo de rasgo | [!UICONTROL Onboarded traits] y [!UICONTROL algorithmic traits] contribuyen como máximo 1 realización a la frecuencia de [!UICONTROL folder trait]. |
| Desplazamiento de rasgos entre carpetas | Si se mueve un rasgo de una carpeta a otra, se descalificará ese rasgo del primer rasgo de carpeta y se calificará para el segundo [!UICONTROL folder trait]. Esto significa que si elimina o mueve un rasgo de la carpeta, los usuarios de la población del rasgo se dessegmentarán de los segmentos utilizando el rasgo de carpeta como expresión de segmento. <br> Al asignar segmentos de Adobe Analytics o grupos de informes a su organización de Experience Cloud, Audience Manager crea automáticamente segmentos y rasgos nuevos y correspondientes de solo lectura. No se puede editar ni cambiar la ubicación de almacenamiento de estas características desde Audience Manager. Sin embargo, cualquier cambio que realice en los segmentos o grupos de informes asignados de Adobe Analytics se reflejará en Audience Manager. |
| Variables del sistema | [!UICONTROL Folder traits] no se puede realizar en llamadas de evento usando el parámetro `d_sid`. |
| Creación de informes | [!UICONTROL Folder traits] son rasgos calculados automáticamente y no aparecen en **[!UICONTROL Overlap Reports]**. |
