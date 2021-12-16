---
description: Describe los pares clave-valor comunes de nivel de plataforma que puede utilizar para dirigirse a usuarios con variables geográficas en todas las propiedades de la cuenta de Audience Manager.
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: Segmentación geográfica con claves a nivel de plataforma
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 366589d51601f438999bfdc6a10c306eb1186742
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 3%

---

# Segmentación geográfica con claves a nivel de plataforma {#geotargeting-with-platform-level-keys}

Describe los pares clave-valor comunes de nivel de plataforma que puede utilizar para dirigirse a usuarios con variables geográficas en todas las propiedades de la cuenta de Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Objetivo de las variables a nivel de plataforma {#platform-variables}

Las variables de nivel de plataforma le permiten tomar datos pasados desde un sitio en particular y hacer que estén disponibles para la segmentación en todas las propiedades del [!DNL Audience Manager] cuenta. Estas variables están formadas por [pares clave-valor](../../reference/key-value-pairs-explained.md) con la clave con el prefijo `d_` como se muestra a continuación.

## Adición de valores a claves de nivel de plataforma {#adding-values}

Para algunas claves de nivel de plataforma, puede especificar el valor usted mismo. Con otros, las claves se asocian con las correspondientes [!DNL IP] direcciones transferidas en una llamada de evento. En cualquier caso, al crear características en , aún debe especificar el valor [!UICONTROL Trait Builder].

## Claves a nivel de plataforma definidas por el usuario {#user-defined-keys}

Si ya tiene o está estableciendo un proceso para definir y recopilar pares de clave-valor, utilice esta opción. Si desea utilizar claves predefinidas por la dirección IP, continúe con la siguiente sección. En el caso de las claves definidas por el usuario, se especifica el valor al crear características con estos pares clave-valor:

| Clave | Para objetivos |
|---|---|
| `d_zx` | Código postal (p. ej., `d_zx=10022`). |

## Claves a nivel de plataforma definidas por dirección IP {#keys-ip-address}

Trabajamos con [Digital Envoy](https://www.digitalenvoy.com/) para obtener y actualizar los datos demográficos y geográficos de las claves siguientes. Los valores de estas claves se determinan mediante la coincidencia [!DNL IP] direcciones a los datos geográficos y demográficos correspondientes. Sin embargo, tendrá que introducir el parámetro value al crear el par clave-valor en [!UICONTROL Trait Builder].

| Clave | Para objetivos |
|--- |--- |
| d_area_code | [Códigos de área de Norteamérica](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  Por ejemplo: <ul><li>**Característica**: d_area_code=801</li><li>**Nombre del rasgo**: Utah</li></ul> |
| d_city | Ciudades y ciudades. Descargue el [lista de ciudades](assets/d_city.txt).  Por ejemplo: <ul><li>Característica: d_city=bonn</li><li>Nombre del rasgo: Bonn</li></ul> **Sugerencia**: Puede usar `d_city` acoplado con `d_country` para estar seguro de que no se están dirigiendo a dos ciudades con el mismo nombre en diferentes países. Puede ser aún más específico en la segmentación utilizando `d_postal_code`. |
| d_country | Los valores corresponden a los códigos ISO de país. Para obtener una lista de códigos que se pueden buscar, consulte la [Plataforma de navegación en línea ISO](https://www.iso.org/obp/ui/#home). <br>  Dirigirse al Reino Unido es el único caso especial que no cumple la norma ISO 3166. Debería usar &quot;UK&quot; en lugar de &quot;GB&quot; para la segmentación en el Reino Unido.  Para dirigirse a las Antillas Neerlandesas, el código &quot;AN&quot; ha quedado obsoleto desde 2010. La zona se ha disuelto en cinco unidades territoriales separadas. La implicancia es que para la segmentación en las Antillas Neerlandesas, no se debe usar &quot;AN&quot;, sino una combinación de los códigos de país para &quot;CW&quot;, &quot;SX&quot; y &quot;BQ&quot;.  Por ejemplo:  <br>  Característica: d_country=CZ  <br>  Nombre del rasgo: República Checa <br>  Característica: d_country=UK <br>  Nombre del rasgo: Reino Unido  <br>  Característica: d_country=CW OR d_country=SX OR d_country=BQ  <br>  Nombre del rasgo: Antillas Neerlandesas |
| d_dma_code | Códigos DMA de área metropolitana. Descargue el [Lista de regiones DMA](assets/DMAregions.csv) (formato .csv ).  Por ejemplo: <ul><li>Característica: d_dma_code=807</li><li>Nombre del rasgo: San Francisco</li></ul> |
| d_lat | Latitud (por ejemplo, d_lat=40.75). Descargue el [lista de latitudes](assets/d_lat.txt). |
| d_long | Longitud (por ejemplo, d_long=73.98). Descargue el [lista longitudes](assets/d_long.txt). |
| d_postal_code | Códigos postales (excepto el código +4 ampliado). Descargue el  [lista de códigos postales](assets/d_postal_code.txt).  Por ejemplo: <ul><li>Característica: d_postal_code=84004 </li><li>Nombre del rasgo: Alpino</li></ul> |
| d_state | Abreviación de 2 caracteres para un estado de EE. UU. Descargue el [lista de códigos de estados](assets/d_state.txt).  Por ejemplo: <ul><li>Característica: d_state=NY </li><li>Nombre del rasgo: Nueva York</li></ul>d_state contiene valores repetidos para diferentes estados en diferentes países. Por ejemplo, d_state == &quot;on&quot; coincide con varios estados: Ontario (Canadá), Ondo (Nigeria), Oshana (Namibia). Se recomienda combinar esta señal con otras como d_country para una segmentación geográfica más específica. |
| d_region | ID alfanuméricos regionales. Descargue el [lista de regiones](assets/Country_RegionCodes_City.csv).  A continuación, puede utilizar esta lista para hacer coincidir los ID de región con los nombres de región. |
| d_isp | ISP/organización. Descargue el [Lista ISP](assets/d_isp.txt). |

La lista de [todas las señales basadas en ubicaciones](assets/all.txt) comprende todas las señales anteriores, en el siguiente orden: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md)

