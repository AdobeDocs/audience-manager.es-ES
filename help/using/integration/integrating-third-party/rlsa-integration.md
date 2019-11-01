---
description: Este procedimiento requiere una lista de remercadotecnia de AdWords, un código de píxeles y un destino de URL de Audience Manager. También se denomina lista de remercadotecnia para la integración de publicidades de búsqueda (RLSA). Se aplica solo a la búsqueda paga.
seo-description: Este procedimiento requiere una lista de remercadotecnia de AdWords, un código de píxeles y un destino de URL de Audience Manager. También se denomina lista de remercadotecnia para la integración de publicidades de búsqueda (RLSA). Se aplica solo a la búsqueda paga.
seo-title: Envío de segmentos a una lista de remercadotecnia de Google AdWords
solution: Audience Manager
title: Envío de segmentos a una lista de remercadotecnia de Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Envío de segmentos a una lista de remercadotecnia de anuncios de Google {#send-segments-to-a-google-adwords-remarketing-list}

Este procedimiento requiere una lista [!DNL Google Ads] de remercadotecnia, un código de píxeles y un destino de Audience Manager [!DNL URL] . También se conoce como lista de remercadotecnia para la integración de publicidades de búsqueda ([!DNL RLSA]). Se aplica solo a la búsqueda paga.

>[!IMPORTANT]
>Tenga en cuenta que no se trata de una integración productiva de los dos sistemas.

Para configurar una lista [!DNL Google Ads] de remercadotecnia como destino de [!DNL Audience Manager] URL:

1. En su [!DNL Google Ads] cuenta, [cree una lista](https://support.google.com/adwords/answer/2454064?hl=en) de remercadotecnia de sitio web y anote su ID de conversión.
1. Utilice la siguiente URL como plantilla para la URL base y la URL segura. Reemplace la sección xxxxxxxx con su ID de conversión.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. En Audience Manager, [cree un destino](../../features/destinations/create-url-destination.md) URL o edite un destino existente. Utilice los siguientes ajustes al crear el destino:
   * Tipo:URL
   * Serializar: Habilitado
   * Delimitador: Punto y coma (;)

1. En la [!UICONTROL Segment Mappings] sección de su [!DNL URL] destino, agregue el código del paso 2 a los campos [!DNL URL] y [!DNL Secure URL] . Agregue un prefijo al código con `http:` y `https:` en los [!DNL URL] campos y [!DNL Secure URL] , respectivamente.

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

1. Haga clic en **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Si está trabajando con varios segmentos, obtenga un píxel nuevo para cada segmento que desee asignar a un destino de Google Ads. Esto garantiza que los datos se apliquen a la lista de remercadotecnia correspondiente.

1. Al asignar un nuevo segmento a este destino en Audience Manager, defina la asignación como `aam=segmentID` y reemplace `segmentID` por el ID del segmento.
1. Al definir un bloque en [!DNL Google Ads], cree una regla que coincida con la asignación definida en el paso 6.

Una asignación completada podría tener un aspecto similar a este:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [Destinos](../../features/destinations/destinations.md)
>* [Crear un destino de dirección URL](../../features/destinations/create-url-destination.md)
>* [Acerca de las listas de remercadotecnia de AdWords](https://support.google.com/adwords/answer/2472738)
>* [Cómo funciona la remercadotecnia de AdWords](https://support.google.com/adwords/answer/2454000)

