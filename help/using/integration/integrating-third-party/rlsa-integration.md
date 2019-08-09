---
description: Este procedimiento requiere una lista de remercadotecnia adwords, un código de píxeles y un destino de URL de Audience Manager. También se conoce como una lista de remercadotecnia para la integración de publicidades de búsqueda (RLSA). Se aplica únicamente a la búsqueda paga.
seo-description: Este procedimiento requiere una lista de remercadotecnia adwords, un código de píxeles y un destino de URL de Audience Manager. También se conoce como una lista de remercadotecnia para la integración de publicidades de búsqueda (RLSA). Se aplica únicamente a la búsqueda paga.
seo-title: Enviar segmentos a una lista de remercadotecnia de Google adwords
solution: Audience Manager
title: Enviar segmentos a una lista de remercadotecnia de Google adwords
uuid: 5 ad 821 c 6-48 b 4-42 c 0-b 912-1563331 e 93 a 2
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Enviar segmentos a una lista de remercadotecnia de Google Ads {#send-segments-to-a-google-adwords-remarketing-list}

Este procedimiento requiere una [!DNL Google Ads] lista de remarketing, un código de píxeles y [!DNL URL] un destino de Audience Manager. También se conoce como una lista de remercadotecnia para la integración de anuncios de búsqueda ([!DNL RLSA]). Se aplica únicamente a la búsqueda paga.

>[!IMPORTANT]
>Tenga en cuenta que no se trata de una integración productable de ambos sistemas.

Para configurar una [!DNL Google Ads] lista de remercadotecnia como destino [!DNL Audience Manager] de URL:

1. En [!DNL Google Ads] su cuenta [, cree una lista de remarketing del sitio web](https://support.google.com/adwords/answer/2454064?hl=en) y anote el ID de conversión.
1. Utilice la siguiente URL como plantilla para la URL base y la URL segura. Sustituya la sección xxxxxxxx por su ID de conversión.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. En Audience Manager, [cree un destino de URL](../../features/destinations/create-url-destination.md) o edite un destino existente. Utilice los siguientes ajustes al crear el destino:
   * Tipo: URL
   * Serializar: Habilitado
   * Delimitador: Punto y coma (;)

1. En [!UICONTROL Segment Mappings] la sección [!DNL URL] del destino, agregue el código del paso 2 a los campos [!DNL URL] y a los [!DNL Secure URL] campos. Prefiera el código con `http:` y `https:` en los [!DNL URL][!DNL Secure URL] campos, respectivamente.

   >[!IMPORTANT]
   >
   >Reemplazar ampersands codificados `&` con ampersands no codificados `&`

   Código no seguro [!DNL URL] :

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Código seguro [!DNL URL] :

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Haga clic en **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Si está trabajando con varios segmentos, obtenga un nuevo píxel para cada segmento que desee asignar a un destino de Google Ads. Esto garantiza que los datos se apliquen a la lista de remercadotecnia adecuada.

1. Cuando asigne un nuevo segmento a este destino en Audience Manager, defina la asignación como `aam=segmentID` y sustituya `segmentID` por la ID del segmento.
1. Al definir un bloque en [!DNL Google Ads], cree una regla que coincida con la asignación definida en el paso 6.

Una asignación completada podría tener un aspecto similar al siguiente:

![](../assets/rlsa_mapping.png)

>[!MORE_ LIKE_ THIS]
>
>* [Destinos](../../features/destinations/destinations.md)
>* [Crear un destino de URL](../../features/destinations/create-url-destination.md)
>* [Acerca de las listas de remercadotecnia adwords](https://support.google.com/adwords/answer/2472738)
>* [Funcionamiento de adwords Remarketing](https://support.google.com/adwords/answer/2454000)

