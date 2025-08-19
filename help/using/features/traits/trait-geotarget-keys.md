---
description: Describe los pares comunes de clave-valor de nivel de plataforma que puede utilizar para destino a los usuarios variables geográficas en todas las propiedades del Audience Manager cuenta.
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: Geotargeting con claves de Platform nivel
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 2de7aba53e3c88d31270f2acb4fa29389f940312
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 2%

---

# Geotargeting con claves de Platform nivel {#geotargeting-with-platform-level-keys}

Describe los pares comunes de clave-valor de nivel de plataforma que puede utilizar para destino a los usuarios variables geográficas en todas las propiedades del Audience Manager cuenta.

<!-- c_tb_platform_vars.xml -->

## Propósito de las variables de Platform nivel {#platform-variables}

Platform variables de nivel le permiten tomar los datos pasados de un sitio en particular y ponerlos a disposición de direccionamiento en todas las propiedades de su [!DNL Audience Manager] cuenta. Estas variables están formadas por [pares clave-valor](../../reference/key-value-pairs-explained.md) con la clave prefijada por `d_` como se muestra a continuación.

## Adición de valores a claves de Platform nivel {#adding-values}

Para algunas claves de nivel de plataforma, puede especificar el valor usted mismo. Con otros, las claves se asocian con las direcciones correspondientes [!DNL IP] pasadas en una llamada evento. En cualquier caso, aún tiene que especificar el valor al crear características en [!UICONTROL Trait Builder].

## Claves de nivel de Platform definidas por el usuario {#user-defined-keys}

Si ya tiene, o está estableciendo, un proceso para definir y recopilar pares clave-valor, utilice esta opción. Si desea utilizar claves predefinidas por dirección IP, continúe con la siguiente sección. En el caso de claves definidas por usuario, especifique el valor al crear características con estos pares clave-valor:

| Clave | Para la segmentación |
|---|---|
| `d_zx` | Código postal (por ejemplo, `d_zx=10022`). |

## Claves de nivel Platform definidas por una dirección IP {#keys-ip-address}

Trabajamos con [Digital Envoy](https://www.digitalenvoy.com/) para obtener y actualizar los datos demográficos y geográficos para las claves a continuación. Los valores de estas claves se determinan haciendo coincidir [!DNL IP] las direcciones con los datos geográficos y demográficos correspondientes. Sin embargo, aún tendrá que introducir el parámetro value al crear el par clave-valor en [!UICONTROL Trait Builder].

| Clave | Para la segmentación |
|--- |--- |
| d_area_code | [Códigos](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes) de área de Norteamérica.  Por ejemplo: <ul><li>**** Rasgo: d_area_code=801</li><li>**Nombre** del rasgo: Utah</li></ul> |
| d_city | Ciudades y pueblos. Descargue el lista[ de ciudades](assets/d_city.txt).  Por ejemplo: <ul><li>Rasgo: d_city=bonn</li><li>Nombre del rasgo: Bonn</li></ul> **Sugerencia**: Puede usar `d_city` junto con `d_country` para asegurarse de que no está direccionamiento dos ciudades con el mismo nombre en diferentes países. Puede ser igualado más específico en su direccionamiento utilizando `d_postal_code`. |
| d_country | Los valores corresponden a los códigos ISO de país. Para obtener una lista de códigos con capacidad de búsqueda, consulte el [Platform](https://www.iso.org/obp/ui/#home) de exploración en línea ISO. <br>La segmentación para el Reino Unido es el único caso especial que no obedece a la norma ISO 3166. Debe usar &quot;UK&quot; en lugar de &quot;GB&quot; para direccionamiento en el Reino Unido.  Para destino las Antillas Neerlandesas, el código &quot;AN&quot; ha quedado obsoleto desde 2010. El área se ha disuelto en cinco unidades territoriales separadas. La implicación es que para direccionamiento en las Antillas Neerlandesas, no debe usar &quot;AN&quot;, sino una combinación de los códigos de país para &quot;CW&quot;, &quot;SX&quot; y &quot;BQ&quot;.  Por ejemplo:  <br> Rasgo: d_country=CZ  <br> Nombre de rasgo: Checo Republic <br> Rasgo: d_country=UK <br> Nombre de rasgo: Reino Unido  <br> Rasgo: d_country=CW O d_country=SX OR d_country=BQ  <br> Nombre de rasgo: Antillas Neerlandesas |
| d_dma_code | Códigos de DMA del área metropolitana. Descargue el [DMA área geográfica lista](assets/DMAregions.csv) (.csv formato).  Por ejemplo: <ul><li>Rasgo: d_dma_code=807</li><li>Nombre del rasgo: San Francisco</li></ul> |
| d_lat | Latitud (p. ej.  d_lat=40,75). Descargue las [latitudes lista](assets/d_lat.txt). |
| d_long | Longitud (p. ej.  d_long=73,98). Descargue el lista[ de ](assets/d_long.txt)longitudes. |
| d_postal_code | Códigos postales (excluya el código +4 extendido). Descargue los  [códigos postales lista](assets/d_postal_code.txt).  Por ejemplo: <ul><li>Rasgo: d_postal_code=84004 </li><li>Nombre del rasgo: alpino</li></ul> |
| d_state | Abreviatura de 2 caracteres de un estado de EE. UU. Descargue los códigos de [estado lista](assets/d_state.txt).  Por ejemplo: <ul><li>Rasgo: d_state=NY </li><li>Nombre del rasgo: Nuevo York</li></ul>d_state contiene valores repetidos para diferentes estados en diferentes países. Por ejemplo, d_state == &quot;on&quot; coincide con varios estados: Ontario (en Canadá), Ondo (en Nigeria), Oshana (en Namibia). Recomendamos asociar esta señal con otras, como d_country para un targeting geográfico más específico. |
| d_área geográfica | ID alfanuméricos regionales. Descargue el [área geográfica lista](assets/Country_RegionCodes_City.csv).  A continuación, puede utilizar este lista para hacer coincidir área geográfica ID con área geográfica nombres. |
| d_isp | ISP/organización. Descargue la lista[ de ](assets/d_isp.txt)ISP. |

El lista de [todas las señales](assets/all.txt) basadas en la localización comprende todas las señales anteriores, en el siguiente orden: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md)

