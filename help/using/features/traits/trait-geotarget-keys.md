---
description: Describe los pares comunes de clave-valor de nivel de plataforma que puede utilizar para dirigirse a usuarios con variables geográficas en todas las propiedades de su cuenta de Audience Manager.
seo-description: Describe los pares comunes de clave-valor de nivel de plataforma que puede utilizar para dirigirse a usuarios con variables geográficas en todas las propiedades de su cuenta de Audience Manager.
seo-title: Targeting geográfico con claves a nivel de plataforma
solution: Audience Manager
title: Targeting geográfico con claves a nivel de plataforma
uuid: c 7 e 4 cbfe-e 564-404 e-a 565-bbe 5 fd 519 519
translation-type: tm+mt
source-git-commit: c5c57423bcba8d4b3974a04c46dc7c7afc7484a0

---


# Geotargeting With Platform-level Keys {#geotargeting-with-platform-level-keys}

Describe los pares comunes de clave-valor de nivel de plataforma que puede utilizar para dirigirse a usuarios con variables geográficas en todas las propiedades de su cuenta de Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Purpose of Platform-level Variables {#platform-variables}

Platform-level variables let you take data passed in from a particular site and make it available for targeting across all the properties in your [!DNL Audience Manager] account. These variables are formed by [key-value pairs](../../reference/key-value-pairs-explained.md) with the key prefixed by `d_` as shown below.

## Adding Values to Platform Level Keys {#adding-values}

Para algunas claves a nivel de plataforma, puede especificar el valor mismo. With others, the keys are associated with corresponding [!DNL IP] addresses passed in on an event call. In either case, you still need to specify the value when building traits in [!UICONTROL Trait Builder].

## User Defined Platform-Level Keys {#user-defined-keys}

Especifique el valor al crear características con estos pares clave-valor:

| Clave | Para objetivos |
|---|---|
| `d_zx` | ZIP code (e.g., `d_zx=10022`). |

## Platform Level Keys Defined by IP Address {#keys-ip-address}

We work with [Digital Envoy](https://www.digitalenvoy.com/) to obtain and update the demographic and geographic data for the keys below. The values for these keys are determined by matching [!DNL IP] addresses to corresponding geographic and demographic data. However, you&#39;ll still have to enter the value parameter when creating the key-value pair in [!UICONTROL Trait Builder].

| Clave | Para objetivos |
|--- |--- |
| d_ area_ code | [Códigos de área de Norteamérica](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes). Por ejemplo: <ul><li>**Característica**: d_ area_ code = 801</li><li>**Nombre de característica**: Utah</li></ul> |
| d_ city | Ciudades y ciudades. Download the [cities list](assets/d_city.txt).  Por ejemplo: <ul><li>Característica: d_ city = bonn</li><li>Nombre de característica: Bonn</li></ul> **Sugerencia**: Puede utilizar `d_city` la combinación para `d_country` asegurarse de que no está dirigiendo dos ciudades con el mismo nombre en diferentes países. You can be even more specific in your targeting by using `d_postal_code`. |
| d_ country | Los valores corresponden a códigos ISO de país. For a searchable list of codes, see the [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>La segmentación para el Reino Unido es el único caso especial que no obedece a ISO 3166. Debe utilizar &quot;Reino Unido&quot; en lugar de &quot;GB&quot; para segmentar en el Reino Unido. Para dirigir las Antillas Neerlandesas, el código &quot;AN&quot; dejó de utilizarse desde 2010. El área se ha disuelto en cinco unidades territoriales independientes. La consecuencia es que, para segmentar en las Antillas de Países Bajos, no debe utilizar &quot;AN&quot;, sino una combinación de los códigos de país para &quot;CW&quot;, &quot;SX&quot; y &quot;BQ&quot;. For example:  <br>  Trait:  d_country=CZ  <br>  Trait Name: Czech Republic <br>  Trait:  d_country=UK <br>  Trait Name: United Kingdom  <br>  Trait:  d_country=CW OR d_country=SX OR d_country=BQ  <br>  Trait Name: Netherlands Antilles |
| d_ dma_ code | Códigos de DMA de área metropolitana. Download the [DMA region list](assets/DMAregions.csv) (.csv format).  Por ejemplo: <ul><li>Característica: d_ dma_ code = 807</li><li>Nombre de característica: San Francisco</li></ul> |
| d_ lat | Latitud (p. ej. d_ lat = 40.75). Download the [latitudes list](assets/d_lat.txt). |
| d_ long | Longitud (p. ej. d_ long = 73.98). Download the [longitudes list](assets/d_long.txt). |
| d_ postal_ code | Códigos postales (excluir el código ampliado +4). Download the  [postal codes list](assets/d_postal_code.txt).  Por ejemplo: <ul><li>Característica: d_ postal_ code = 84004 </li><li>Nombre de característica: Alpine</li></ul> |
| d_ state | Abreviatura de 2 caracteres de estados Unidos. Download the [states codes list](assets/d_state.txt).  Por ejemplo: <ul><li>Característica: d_ state = NY </li><li>Nombre de característica: Nueva York</li></ul>d_ state contiene valores repetidos para distintos estados en diferentes países. Por ejemplo, d_ state = = &quot;on&quot; coincide con varios estados: Ontario (en Canadá), Ondo (en Nigeria), Oshana (en Namibia). Recomendamos que pares esta señal con otros como d_ country para un targeting geográfico más específico. |
| d_ region | ID alfanuméricos regionales. Download the [region list](assets/Country_RegionCodes_City.csv).  A continuación, puede utilizar esta lista para asignar ID de región a nombres de región. |
| d_ isp | ISP/organización. Download the [ISP List](assets/d_isp.txt). |

The list of [all location-based signals](assets/all.csv) comprises all the signals above, in the following order: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORE_ LIKE_ THIS]
>
>* [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md)

