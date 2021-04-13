---
description: Este procedimiento requiere una lista de remarketing de AdWords, un código de píxel y un destino de URL de Audience Manager. También se conoce como lista de remarketing para la integración de anuncios de búsqueda (RLSA). Se aplica solo a la búsqueda de pago.
seo-description: Este procedimiento requiere una lista de remarketing de AdWords, un código de píxel y un destino de URL de Audience Manager. También se conoce como lista de remarketing para la integración de anuncios de búsqueda (RLSA). Se aplica solo a la búsqueda de pago.
seo-title: Envío de segmentos a una Lista de remarketing de Google AdWords
solution: Audience Manager
title: Envío de segmentos a una Lista de remarketing de Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Integración de terceros
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 5%

---

# Enviar segmentos a una lista de remarketing de Google Ads {#send-segments-to-a-google-adwords-remarketing-list}

Este procedimiento requiere una [!DNL Google Ads] lista de remarketing, un código de píxel y un Audience Manager [!DNL URL] [!DNL destination]. También se conoce como lista de remarketing para la integración de anuncios de búsqueda ([!DNL RLSA]). Se aplica solo a la búsqueda de pago.

>[!IMPORTANT]
>Tenga en cuenta que no se trata de una integración productiva de los dos sistemas.

Para configurar una lista de remarketing [!DNL Google Ads] como [!DNL Audience Manager] [!DNL URL destination]:

1. En su cuenta [!DNL Google Ads], [cree una lista de remarketing del sitio web](https://support.google.com/adwords/answer/2454064?hl=en) y anote su ID de conversión.
1. Utilice la siguiente URL como plantilla para la URL base y la URL segura. Sustituya la sección xxxxxxx por su ID de conversión.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. En el Audience Manager, [Cree un [!DNL URL destination]](../../features/destinations/create-url-destination.md) o edite un [!DNL destination] existente. Utilice la siguiente configuración al crear el [!DNL destination]:
   * Tipo: URL
   * Serializar: Habilitado
   * Delimitador: Punto y coma (;)

1. En la sección [!UICONTROL Segment Mappings] de su [!DNL URL] [!DNL destination], añada el código del paso 2 a los campos [!DNL URL] y [!DNL Secure URL]. Agregue el prefijo `http:` y `https:` en los campos [!DNL URL] y [!DNL Secure URL] respectivamente.

   >[!IMPORTANT]
   >
   >Reemplace los ampersands `&` codificados con los ampersands `&` no codificados

   Código [!DNL URL] no seguro:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Código seguro [!DNL URL]:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Haga clic **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Si está trabajando con varios segmentos, obtenga un píxel nuevo para cada segmento que desee asignar a [!DNL Google Ads] [!DNL destination]. Esto garantiza que los datos se apliquen a la lista de remarketing adecuada.

1. Al asignar un nuevo segmento a este [!DNL destination] en Audience Manager, defina la asignación como `aam=segmentID` y reemplace `segmentID` por el ID del segmento.
1. Al definir un bloque en [!DNL Google Ads], cree una regla que coincida con la asignación definida en el paso 6.

Una asignación completada podría tener un aspecto similar a este:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [Cree un [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [Acerca de las listas de remarketing de AdWords](https://support.google.com/adwords/answer/2472738)
>* [Cómo funciona el remarketing de AdWords](https://support.google.com/adwords/answer/2454000)

