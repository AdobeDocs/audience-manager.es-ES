---
description: Este procedimiento requiere una lista de remarketing de AdWords, un código de píxel y un destino de URL de Audience Manager. También se conoce como lista de remarketing para la integración de anuncios de búsqueda (RLSA). Se aplica solo a la búsqueda de pago.
seo-description: This procedure requires an AdWords remarketing list, pixel code, and an Audience Manager URL destination. It is also known as a remarketing list for search ads (RLSA) integration. Applies to paid search only.
seo-title: Send Segments to a Google AdWords Remarketing List
solution: Audience Manager
title: Envío de segmentos a una Lista de remarketing de Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third-party Integration
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
source-git-commit: b8d65ef8c27100d174a997eb24a75f37b4e75d40
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 3%

---

# Envío de segmentos a una lista de remarketing de Google Ads {#send-segments-to-a-google-adwords-remarketing-list}

Este procedimiento requiere una [!DNL Google Ads] lista de remarketing, código de píxeles y Audience Manager [!DNL URL] [!DNL destination]. También se conoce como lista de remarketing para los anuncios de búsqueda ([!DNL RLSA]). Se aplica solo a la búsqueda de pago.

>[!IMPORTANT]
>Tenga en cuenta que no se trata de una integración productiva de los dos sistemas.

Para configurar un [!DNL Google Ads] lista de remarketing como [!DNL Audience Manager] [!DNL URL destination]:

1. En [!DNL Google Ads] cuenta, [crear una lista de remarketing de sitio web](https://support.google.com/tagmanager/answer/6106960?hl=en) y anote su ID de conversión.
1. Utilice la siguiente URL como plantilla para la URL base y la URL segura. Sustituya la sección xxxxxxx por su ID de conversión.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. En Audience Manager, [Cree un [!DNL URL destination]](../../features/destinations/create-url-destination.md) o editar una [!DNL destination]. Utilice la siguiente configuración al crear la variable [!DNL destination]:
   * Tipo: URL
   * Serializar: Habilitado
   * Delimitador: Punto y coma ( &amp;semi) )

1. En el [!UICONTROL Segment Mappings] del [!DNL URL] [!DNL destination], añada el código del paso 2 al [!DNL URL] y [!DNL Secure URL] campos. Agregue a prefijo el código con `http:` y `https:` en el [!DNL URL] y [!DNL Secure URL] , respectivamente.

   >[!IMPORTANT]
   >
   >Reemplazar ampersands codificados `&` con el símbolo &amp; `&`

   Inseguro [!DNL URL] código:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Secure [!DNL URL] código:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Haga clic **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Si trabaja con varios segmentos, obtenga un píxel nuevo para cada segmento que desee asignar a un [!DNL Google Ads] [!DNL destination]. Esto garantiza que los datos se apliquen a la lista de remarketing adecuada.

1. Al asignar un nuevo segmento a esta [!DNL destination] en el Audience Manager, defina la asignación como `aam=segmentID` y reemplace `segmentID` con el ID de su segmento.
1. Al definir un bloque en [!DNL Google Ads], cree una regla que coincida con la asignación definida en el paso 6.

Una asignación completada podría tener un aspecto similar a este:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [Cree un [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [Acerca de las listas de remarketing de AdWords](https://support.google.com/adwords/answer/2472738)
>* [Cómo funciona el remarketing de AdWords](https://support.google.com/adwords/answer/2454000)

