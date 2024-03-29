---
description: Describe los pares clave-valor comunes a nivel de plataforma que puede utilizar para dirigirse a usuarios con variables geográficas en todas las propiedades de la cuenta de Audience Manager.
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

Describe los pares clave-valor comunes a nivel de plataforma que puede utilizar para dirigirse a usuarios con variables geográficas en todas las propiedades de la cuenta de Audience Manager.

<!-- c_tb_platform_vars.xml -->

## Propósito de las variables de nivel de plataforma {#platform-variables}

Las variables de nivel de plataforma permiten tomar datos pasados desde un sitio en particular y hacer que estén disponibles para la segmentación en todas las propiedades de [!DNL Audience Manager] cuenta. Estas variables están formadas por [pares clave-valor](../../reference/key-value-pairs-explained.md) con la clave precedida por `d_` como se muestra a continuación.

## Adición de valores a claves de nivel de plataforma {#adding-values}

Para algunas claves a nivel de plataforma, puede especificar el valor usted mismo. Con otras, las claves se asocian con las correspondientes [!DNL IP] direcciones transferidas en una llamada de evento. En cualquier caso, sigue siendo necesario especificar el valor al crear rasgos en [!UICONTROL Trait Builder].

## Claves de nivel de plataforma definidas por el usuario {#user-defined-keys}

Si ya tiene o está estableciendo un proceso para definir y recopilar pares clave-valor, utilice esta opción. Si desea utilizar claves predefinidas por dirección IP, continúe a la siguiente sección. En el caso de las claves definidas por el usuario, se especifica el valor al crear rasgos con estos pares clave-valor:

| Clave | Para Targeting |
|---|---|
| `d_zx` | Código postal (por ejemplo, `d_zx=10022`). |

## Claves de nivel de plataforma definidas por dirección IP {#keys-ip-address}

Trabajamos con [Enviado digital](https://www.digitalenvoy.com/) para obtener y actualizar los datos demográficos y geográficos de las siguientes claves. Los valores de estas claves se determinan mediante la coincidencia [!DNL IP] direcciones a los datos geográficos y demográficos correspondientes. Sin embargo, aún tendrá que introducir el parámetro valor al crear el par clave-valor en [!UICONTROL Trait Builder].

| Clave | Para Targeting |
|--- |--- |
| d_area_code | [Códigos de área de Norteamérica](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  Por ejemplo: <ul><li>**Rasgo**: d_area_code=801</li><li>**Nombre del rasgo**: Utah</li></ul> |
| d_city | Ciudades y pueblos. Descargue la [lista de ciudades](assets/d_city.txt).  Por ejemplo: <ul><li>Característica: d_city=bonn</li><li>Nombre del rasgo: Bonn</li></ul> **Sugerencia**: Puede utilizar `d_city` junto con `d_country` para asegurarse de que no está dirigiendo dos ciudades con el mismo nombre en diferentes países. Puede ser aún más específico en su segmentación utilizando `d_postal_code`. |
| d_country | Los valores corresponden a los códigos de país ISO. Para obtener una lista de códigos en los que realizar búsquedas, consulte la [Plataforma de navegación en línea ISO](https://www.iso.org/obp/ui/#home). <br>  La segmentación para el Reino Unido es el único caso especial que no obedece la norma ISO 3166. Debe usar &quot;UK&quot; en lugar de &quot;GB&quot; para segmentar en el Reino Unido.  Para dirigirse a las Antillas Neerlandesas, el código &quot;AN&quot; ha quedado obsoleto desde 2010. La zona se ha disuelto en cinco unidades territoriales distintas. Esto implica que, para realizar la segmentación en las Antillas Neerlandesas, no se debe utilizar &quot;AN&quot;, sino una combinación de los códigos de país para &quot;CW&quot;, &quot;SX&quot; y &quot;BQ&quot;.  Por ejemplo:  <br>  Característica: d_country=CZ  <br>  Nombre del rasgo: República Checa <br>  Característica: d_country=UK <br>  Nombre del rasgo: Reino Unido  <br>  Rasgo: d_country=CW O d_country=SX O d_country=BQ  <br>  Nombre del rasgo: Antillas Neerlandesas |
| d_dma_code | Códigos DMA del área metropolitana. Descargue la [Lista de región DMA](assets/DMAregions.csv) (formato .csv).  Por ejemplo: <ul><li>Característica: d_dma_code=807</li><li>Nombre del rasgo: San Francisco</li></ul> |
| d_lat | Latitud (p. ej. d_lat=40,75). Descargue la [lista de latitudes](assets/d_lat.txt). |
| d_long | Longitud (p. ej. d_long=73.98). Descargue la [lista de longitudes](assets/d_long.txt). |
| d_postal_code | Códigos postales (excluido el código extendido +4). Descargue la  [lista de códigos postales](assets/d_postal_code.txt).  Por ejemplo: <ul><li>Característica: d_postal_code=84004 </li><li>Nombre del rasgo: Alpine</li></ul> |
| d_state | Abreviatura de 2 caracteres para un estado de EE. UU. Descargue la [lista de códigos de estados](assets/d_state.txt).  Por ejemplo: <ul><li>Característica: d_state=NY </li><li>Nombre del rasgo: Nueva York</li></ul>d_state contiene valores repetidos para diferentes estados en diferentes países. Por ejemplo, d_state == &quot;on&quot; coincide con varios estados: Ontario (en Canadá), Ondo (en Nigeria) y Oshana (en Namibia). Se recomienda emparejar esta señal con otras como d_country para un targeting geográfico más específico. |
| d_region | ID alfanuméricos regionales. Descargue la [lista de regiones](assets/Country_RegionCodes_City.csv).  A continuación, puede utilizar esta lista para hacer coincidir los ID de región con los nombres de región. |
| d_isp | ISP/organización. Descargue la [Lista de ISP](assets/d_isp.txt). |

La lista de [todas las señales basadas en la ubicación](assets/all.txt) incluye todas las señales anteriores en el siguiente orden: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md)

