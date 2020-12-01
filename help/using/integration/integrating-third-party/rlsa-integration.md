---
description: Este procedimiento requiere una lista de remercadotecnia de AdWords, un código de píxeles y un destino de URL de Audience Manager. También se conoce como lista de remercadotecnia para la integración de publicidades de búsqueda (RLSA). Se aplica solo a la búsqueda paga.
seo-description: Este procedimiento requiere una lista de remercadotecnia de AdWords, un código de píxeles y un destino de URL de Audience Manager. También se conoce como lista de remercadotecnia para la integración de publicidades de búsqueda (RLSA). Se aplica solo a la búsqueda paga.
seo-title: Envío de segmentos a una Lista de remarketing de Google AdWords
solution: Audience Manager
title: Envío de segmentos a una Lista de remarketing de Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 5%

---


# Enviar segmentos a una Lista de remercadotecnia de Google Ads {#send-segments-to-a-google-adwords-remarketing-list}

Este procedimiento requiere una [!DNL Google Ads] lista de remercadotecnia, código de píxel y un Audience Manager [!DNL URL] [!DNL destination]. También se conoce como lista de remercadotecnia para la integración de publicidades de búsqueda ([!DNL RLSA]). Se aplica solo a la búsqueda paga.

>[!IMPORTANT]
>Tenga en cuenta que no se trata de una integración productiva de los dos sistemas.

Para configurar una lista de remercadotecnia [!DNL Google Ads] como [!DNL Audience Manager] [!DNL URL destination]:

1. En su cuenta [!DNL Google Ads], [cree una lista de remercadotecnia de sitio Web](https://support.google.com/adwords/answer/2454064?hl=en) y anote su ID de conversión.
1. Utilice la siguiente URL como plantilla para la URL base y la URL segura. Reemplace la sección xxxxxxxx con su ID de conversión.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. En Audience Manager, [Cree una [!DNL URL destination]](../../features/destinations/create-url-destination.md) o edite una [!DNL destination] existente. Utilice la siguiente configuración al crear el [!DNL destination]:
   * Tipo: URL
   * Serializar: Habilitado
   * Delimitador: Punto y coma (;)

1. En la sección [!UICONTROL Segment Mappings] de su [!DNL URL] [!DNL destination], agregue el código del paso 2 a los campos [!DNL URL] y [!DNL Secure URL]. Agregue el prefijo `http:` y `https:` en los campos [!DNL URL] y [!DNL Secure URL], respectivamente.

   >[!IMPORTANT]
   >
   >Reemplazar los ampersands codificados `&` con los ampersands `&` no codificados

   Código [!DNL URL] no seguro:

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
   >Si está trabajando con varios segmentos, obtenga un píxel nuevo para cada segmento que desee asignar a un [!DNL Google Ads] [!DNL destination]. Esto garantiza que los datos se apliquen a la lista de remercadotecnia adecuada.

1. Al asignar un nuevo segmento a este [!DNL destination] Audience Manager, defina la asignación como `aam=segmentID` y reemplace `segmentID` por el ID del segmento.
1. Al definir un bloque en [!DNL Google Ads], cree una regla que coincida con la asignación definida en el paso 6.

Una asignación completada podría tener un aspecto similar a este:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [Cree un [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [Acerca de las Listas de remercadotecnia de AdWords](https://support.google.com/adwords/answer/2472738)
>* [Cómo funciona la remercadotecnia de AdWords](https://support.google.com/adwords/answer/2454000)

