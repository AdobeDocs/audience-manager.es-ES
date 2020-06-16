---
description: Este procedimiento requiere una lista de remercadotecnia de AdWords, un código de píxeles y un destino de URL de Audience Manager. También se conoce como lista de remercadotecnia para la integración de publicidades de búsqueda (RLSA). Se aplica solo a la búsqueda paga.
seo-description: Este procedimiento requiere una lista de remercadotecnia de AdWords, un código de píxeles y un destino de URL de Audience Manager. También se conoce como lista de remercadotecnia para la integración de publicidades de búsqueda (RLSA). Se aplica solo a la búsqueda paga.
seo-title: Envío de segmentos a una Lista de remercadotecnia de Google AdWords
solution: Audience Manager
title: Envío de segmentos a una Lista de remercadotecnia de Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
translation-type: tm+mt
source-git-commit: c70d02637615848a86fc980a70868a6b0f7bda00
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---


# Envío de segmentos a una Lista de remercadotecnia de anuncios de Google {#send-segments-to-a-google-adwords-remarketing-list}

Este procedimiento requiere una lista de [!DNL Google Ads] remercadotecnia, un código de píxel y un Audience Manager [!DNL URL][!DNL destination]. También se denomina lista de remercadotecnia para la integración de publicidades de búsqueda ([!DNL RLSA]). Se aplica solo a la búsqueda paga.

>[!IMPORTANT]
>Tenga en cuenta que no se trata de una integración productiva de los dos sistemas.

Para configurar una lista [!DNL Google Ads] de remercadotecnia como una [!DNL Audience Manager][!DNL URL destination]:

1. En su [!DNL Google Ads] cuenta, [cree una lista](https://support.google.com/adwords/answer/2454064?hl=en) de remercadotecnia de sitio web y anote su ID de conversión.
1. Utilice la siguiente URL como plantilla para la URL base y la URL segura. Reemplace la sección xxxxxxxx con su ID de conversión.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. En Audience Manager, [cree un [!Destino URL de DNL]](../../features/destinations/create-url-destination.md) o edite uno existente [!DNL destination]. Utilice los siguientes ajustes al crear el [!DNL destination]:
   * Tipo: URL
   * Serializar: Habilitado
   * Delimitador: Punto y coma (;)

1. En la [!UICONTROL Segment Mappings] sección del [!DNL URL] , agregue el código del paso 2 a los campos [!DNL destination]y [!DNL URL] [!DNL Secure URL] . Agregue un prefijo al código con `http:` y `https:` en los [!DNL URL] campos y [!DNL Secure URL] , respectivamente.

   >[!IMPORTANT]
   >
   >Reemplazar ampersands codificados `&` con ampersands no codificados `&`

   Código no seguro [!DNL URL] :

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Código [!DNL URL] seguro:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Haga clic **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Si está trabajando con varios segmentos, obtenga un píxel nuevo para cada segmento que desee asignar a un [!DNL Google Ads][!DNL destination]. Esto garantiza que los datos se apliquen a la lista de remercadotecnia adecuada.

1. Al asignar un nuevo segmento a este [!DNL destination] en Audience Manager, defina la asignación como `aam=segmentID` y reemplace `segmentID` por el ID del segmento.
1. Al definir un bloque en [!DNL Google Ads], cree una regla que coincida con la asignación definida en el paso 6.

Una asignación completada podría tener un aspecto similar a este:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!Destinos DNL]](../../features/destinations/destinations.md)
>* [Crear un destino de URL [!DNL]](../../features/destinations/create-url-destination.md)
>* [Acerca de las Listas de remercadotecnia de AdWords](https://support.google.com/adwords/answer/2472738)
>* [Cómo funciona la remercadotecnia de AdWords](https://support.google.com/adwords/answer/2454000)

