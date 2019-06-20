---
description: Este procedimiento requiere una lista de remercadotecnia adwords, un código de píxeles y un destino de URL de Audience Manager. También se conoce como una lista de remercadotecnia para la integración de publicidades de búsqueda (RLSA). Se aplica únicamente a la búsqueda paga.
seo-description: Este procedimiento requiere una lista de remercadotecnia adwords, un código de píxeles y un destino de URL de Audience Manager. También se conoce como una lista de remercadotecnia para la integración de publicidades de búsqueda (RLSA). Se aplica únicamente a la búsqueda paga.
seo-title: Enviar segmentos a una lista de remercadotecnia de Google adwords
solution: Audience Manager
title: Enviar segmentos a una lista de remercadotecnia de Google adwords
uuid: 5 ad 821 c 6-48 b 4-42 c 0-b 912-1563331 e 93 a 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Send Segments to a Google Ads Remarketing List {#send-segments-to-a-google-adwords-remarketing-list}

This procedure requires a [!DNL Google Ads] remarketing list, pixel code, and an Audience Manager [!DNL URL] destination. It is also known as a remarketing list for search ads ([!DNL RLSA]) integration. Se aplica únicamente a la búsqueda paga.

>[!IMPORTANT]
>Tenga en cuenta que no se trata de una integración productable de ambos sistemas.

To set up a [!DNL Google Ads] remarketing list as an [!DNL Audience Manager] URL destination:

1. In your [!DNL Google Ads] account, [create a website re-marketing list](https://support.google.com/adwords/answer/2454064?hl=en) and write down your conversion ID.
1. Utilice la siguiente URL como plantilla para la URL base y la URL segura. Sustituya la sección xxxxxxxx por su ID de conversión.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager, [Create a URL destination](../../features/destinations/manage-destinations.md#configure-url-destination) or edit an existing destination. Utilice los siguientes ajustes al crear el destino:
   * Tipo: URL
   * Serializar: Habilitado
   * Delimitador: Punto y coma (;)

1. In the [!UICONTROL Segment Mappings] section of your [!DNL URL] destination, add the code from step 2 to the [!DNL URL] and [!DNL Secure URL] fields. Prefix the code with `http:` and `https:` in the [!DNL URL] and [!DNL Secure URL] fields, respectively.

   >[!IMPORTANT]
   >
   >Replace encoded ampersands `&` with un-encoded ampersands `&`

   Unsecure [!DNL URL] code:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Secure [!DNL URL] code:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Haga clic en **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Si está trabajando con varios segmentos, obtenga un nuevo píxel para cada segmento que desee asignar a un destino de Google Ads. Esto garantiza que los datos se apliquen a la lista de remercadotecnia adecuada.

1. When mapping a new segment to this destination in Audience Manager, define the mapping as `aam=segmentID` and replace `segmentID` with the ID of your segment.
1. When defining a bucket in [!DNL Google Ads], create a rule that matches the mapping defined at step 6.

Una asignación completada podría tener un aspecto similar al siguiente:

![](../assets/rlsa_mapping.png)

>[!MORE_ LIKE_ THIS]
>
>* [Destinos](../../features/destinations/destinations.md)
>* [Crear un destino de URL](../../features/destinations/manage-destinations.md#configure-url-destination)
>* [Acerca de las listas de remercadotecnia adwords](https://support.google.com/adwords/answer/2472738)
>* [Funcionamiento de adwords Remarketing](https://support.google.com/adwords/answer/2454000)

