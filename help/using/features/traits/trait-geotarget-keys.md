---
description: Describe los pares de clave-valor comunes de nivel de plataforma que se pueden utilizar para destinatario de usuarios con variables geográficas en todas las propiedades de la cuenta del Administrador de Audiencias.
seo-description: Describe los pares de clave-valor comunes de nivel de plataforma que se pueden utilizar para destinatario de usuarios con variables geográficas en todas las propiedades de la cuenta del Administrador de Audiencias.
seo-title: Targeting geográfico con claves de nivel de plataforma
solution: Audience Manager
title: Targeting geográfico con claves de nivel de plataforma
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
translation-type: tm+mt
source-git-commit: 8959e0023f7663d7a20080aaf130d469ed8a4313
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 1%

---


# Geotargeting With Platform-level Keys {#geotargeting-with-platform-level-keys}

Describe los pares de clave-valor comunes de nivel de plataforma que se pueden utilizar para destinatario de usuarios con variables geográficas en todas las propiedades de la cuenta del Administrador de Audiencias.

<!-- c_tb_platform_vars.xml -->

## Objetivo de las variables de nivel de plataforma {#platform-variables}

Las variables de nivel de plataforma le permiten tomar datos pasados desde un sitio en particular y ponerlos a disposición para objetivos en todas las propiedades de su [!DNL Audience Manager] cuenta. Estas variables están formadas por pares [](../../reference/key-value-pairs-explained.md) clave-valor con la clave con el prefijo `d_` como se muestra a continuación.

## Añadir valores a claves de nivel de plataforma {#adding-values}

Para algunas claves de nivel de plataforma, puede especificar el valor usted mismo. Con otros, las claves se asocian con las [!DNL IP] direcciones correspondientes que se pasan en una llamada de evento. En cualquier caso, debe especificar el valor al generar características en [!UICONTROL Trait Builder].

## Teclas de nivel de plataforma definidas por el usuario {#user-defined-keys}

Especifique el valor al generar características con estos pares de clave-valor:

| Clave | Para objetivos |
|---|---|
| `d_zx` | Código postal (por ejemplo, `d_zx=10022`). |

## Claves de nivel de plataforma definidas por dirección IP {#keys-ip-address}

Trabajamos con [Digital Envoy](https://www.digitalenvoy.com/) para obtener y actualizar los datos demográficos y geográficos de las claves siguientes. Los valores de estas claves se determinan mediante la coincidencia de [!DNL IP] direcciones con los datos geográficos y demográficos correspondientes. Sin embargo, tendrá que introducir el parámetro value al crear el par clave-valor en [!UICONTROL Trait Builder].

| Clave | Para objetivos |
|--- |--- |
| d_area_code | [Códigos](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)de área de Norteamérica.  Por ejemplo: <ul><li>**Característica**:  d_area_code=801</li><li>**Nombre** de característica: Utah</li></ul> |
| d_city | Ciudades y pueblos. Descargue la lista [de](assets/d_city.txt)ciudades.  Por ejemplo: <ul><li>Característica:  d_city=bonn</li><li>Nombre de característica: Bonn</li></ul> **Sugerencia**: Puede usar `d_city` junto con `d_country` para asegurarse de no tener como objetivo dos ciudades con el mismo nombre en diferentes países. Puede ser aún más específico en la segmentación mediante `d_postal_code`. |
| d_country | Los valores corresponden a los códigos de país ISO. Para obtener una lista de códigos en la que se pueden realizar búsquedas, consulte la Plataforma [de exploración en línea](https://www.iso.org/obp/ui/#home)ISO. <br>  La determinación de objetivos para el Reino Unido es el único caso especial que no obedece la norma ISO 3166. Debería usar &quot;UK&quot; en lugar de &quot;GB&quot; para dirigir la campaña en el Reino Unido.  Para el destinatario de las Antillas Neerlandesas, el código &quot;AN&quot; ha quedado obsoleto desde 2010. La zona se ha disuelto en cinco unidades territoriales separadas. La implicancia es que para establecer objetivos en las Antillas Neerlandesas, no debe utilizar &quot;AN&quot;, sino una combinación de los códigos de país para &quot;CW&quot;, &quot;SX&quot; y &quot;BQ&quot;.  Por ejemplo:  <br>  Característica:  d_country=Nombre de característica de CZ <br>: Rasgo de la República Checa <br>:  d_country=Nombre de característica del Reino Unido <br>: Rasgo del Reino Unido <br>:  d_country=CW OR d_country=SX OR d_country=Nombre de característica de la <br>barbacoa: Antillas neerlandesas |
| d_dma_code | Códigos DMA del área metropolitana. Descargue la lista [de región](assets/DMAregions.csv) DMA (formato .csv).  Por ejemplo: <ul><li>Característica:  d_dma_code=807</li><li>Nombre de característica: San Francisco</li></ul> |
| d_lat | Latitud (p. ej. d_lat=40.75). Descargue la lista [de](assets/d_lat.txt)latitudes. |
| d_long | Longitud (p. ej. d_long=73.98). Descargue la lista [](assets/d_long.txt)longitudes. |
| d_postal_code | Códigos postales (excluye el código +4 ampliado). Descargue la lista [de códigos](assets/d_postal_code.txt)postales.  Por ejemplo: <ul><li>Característica:  d_postal_code=84004 </li><li>Nombre de característica: Alpino</li></ul> |
| d_state | Abreviación de 2 caracteres para un estado de EE.UU. Descargue la lista [de códigos de](assets/d_state.txt)estados.  Por ejemplo: <ul><li>Característica:  d_state=NY </li><li>Nombre de característica: Nueva York</li></ul>d_state contiene valores repetidos para diferentes estados en diferentes países. Por ejemplo, d_state == &quot;on&quot; coincide con varios estados: Ontario (en el Canadá), Ondo (en Nigeria), Oshana (en Namibia). Se recomienda asociar esta señal con otras, como d_country, para un objetivo geográfico más específico. |
| d_region | ID alfanuméricos regionales. Descargue la lista [de](assets/Country_RegionCodes_City.csv)región.  A continuación, puede utilizar esta lista para hacer coincidir los ID de región con los nombres de región. |
| d_isp | ISP/organización. Descargue la Lista [](assets/d_isp.txt)ISP. |

La lista de [todas las señales](assets/all.txt) basadas en la ubicación comprende todas las señales anteriores, en el orden siguiente: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Requisitos de prefijo para variables clave](../../features/traits/trait-variable-prefixes.md)

