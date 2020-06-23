---
description: Información general y flujo de trabajo para compradores de datos que deseen comprar datos de terceros desde el Audience Manager
seo-description: Información general y flujo de trabajo para compradores de datos que deseen comprar datos de terceros desde el Audience Manager
seo-title: Audience Marketplace para compradores de datos
solution: Audience Manager
title: Audience Marketplace para compradores de datos
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 1%

---


# [!UICONTROL Audience Marketplace] para compradores de datos {#audience-marketplace-for-data-buyers}

Información general y flujo de trabajo para compradores de datos que deseen comprar datos de terceros desde dentro [!DNL Audience Manager].

>[!NOTE]
>[Los permisos](../../../reporting/reports-dashboard.md) basados en roles controlan el acceso a [!UICONTROL Audience Marketplace] las funciones.
>
>* Los administradores pueden crear fuentes de datos, administrar suscriptores y suscribirse a fuentes de datos.
>* Los usuarios solo pueden buscar y vista de fuentes.


## El [!UICONTROL Marketplace]: Acerca de {#about-marketplace}

La [!UICONTROL Marketplace] es una [!DNL Audience Manager] función para compradores de datos que lista fuentes de datos a las que puede suscribirse. lista fuentes de datos privadas [!DNL CPM]y de tasa fija. Estas fuentes las proporcionan proveedores externos que las utilizan [!DNL Audience Manager] para vender datos.

En el [!UICONTROL Marketplace], las herramientas de sistema de informes permiten realizar un seguimiento del uso de las fuentes y de la superposición entre el usuario [!UICONTROL traits] y los usuarios de una fuente de datos suscrita. Por último, con [!UICONTROL Audience Marketplace], [!DNL Adobe] se encarga de las facturas y los pagos de honorarios (aunque es necesario informar sobre el uso cuando se suscribe a una [!DNL CPM] fuente). Estas funciones le permiten encontrar fuentes de datos eficaces sin perder tiempo buscando un proveedor de datos.

>[!TIP]
>
>Utilice el buscador **[de Audiencias de](https://www.adobe-audience-finder.com/)**Adobe para encontrar fuentes de datos de alta calidad a las que puede suscribirse. A continuación, vuelva a la interfaz de usuario o utilice la API[!DNL Audience Manager]de[](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API)Audience Marketplace Buyer para suscribirse a las fuentes que haya encontrado.

![comprador-mercado-información general](assets/buyer-marketplace-overview.png)

La [!UICONTROL Marketplace] lista contiene información que puede ordenar y buscar para encontrar la fuente de datos que sea adecuada para usted. Los artículos de la lista del [!UICONTROL Marketplace] comprador incluyen:

* **[!UICONTROL Search]**:: Busque fuentes de datos por nombre o descripción de texto.
* **[!UICONTROL Similar Traits]**:: Muestra el número de elementos similares [!UICONTROL traits] de una fuente de datos. Esta columna se muestra después de introducir un [!UICONTROL trait] o [!UICONTROL segment] para filtrar por en la **[!UICONTROL Similarity To]** sección.
* **[!UICONTROL Name]**:: Nombre de la fuente de datos.
* **[!UICONTROL Description]**:: Información sobre el contenido de una fuente de datos.
* **[!UICONTROL Provider]**:: Nombre del proveedor de datos.
* **[!UICONTROL Traits]**:: El número de [!UICONTROL traits] una fuente de datos.
* **[!UICONTROL 30 Day Provider Unique Users]**:: Número de usuarios únicos vistos en los últimos 30 días.
* **[!UICONTROL 30 Day Overlapped Uniques]**:: El número de usuarios de su cuenta que se superponen con los usuarios de la cuenta del proveedor.
* **[!UICONTROL Feed Overlap]**:: El valor de valores únicos superpuestos de 30 días, mostrado en porcentajes, calculado como: Comprador de datos 30 días superpuestos únicos / Comprador de datos 30 días únicos) x 100.
* **[!UICONTROL Private Feeds]**:: Consulte Fuentes de datos [privadas](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**:: Número de suscripciones que tiene con un proveedor de datos.

 

Para encontrar fácilmente las mejores fuentes de datos según sus necesidades, utilice los siguientes filtros disponibles en la parte izquierda de la [!UICONTROL Marketplace] página:

* **[!UICONTROL Similarity To]**:: Filtre las fuentes de datos en función de su similitud con una [!UICONTROL trait] o [!UICONTROL segment] una de sus opciones. Al introducir el segmento [!UICONTROL trait] o con el que comparar, puede utilizar el [!UICONTROL trait] ID o [!UICONTROL segment] , o sus respectivos nombres.
* **[!UICONTROL Similarity Cutoff]**:: Arrastre el control deslizante para filtrar las fuentes de datos en función de su parecido [!UICONTROL traits] a la seleccionada [!UICONTROL trait] o [!UICONTROL segment]. Para obtener más información sobre las puntuaciones [!UICONTROL trait] de similitud, consulte Puntuación de similitud [de rasgos](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**:: Filtre las fuentes de datos en función del estado de la suscripción.
* **[!UICONTROL Plan Use Case]**:: Filtre las fuentes de datos en función de los casos de uso admitidos: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]**, y **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**:: Filtre las fuentes de datos en función de su tipo de precio.

## Búsqueda similar [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] le ofrece la opción de buscar [!UICONTROL traits] desde varias fuentes de datos, en función de su similitud con los segmentos [!UICONTROL traits] o existentes. A continuación se muestra cómo hacerlo:

1. Vaya a **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Utilice el **[!UICONTROL Similarity To]** selector para elegir entre filtrar según [!UICONTROL trait] o [!UICONTROL segment]. Puede filtrar según [!UICONTROL trait]/[!UICONTROL segment] ID o nombre. El cuadro de búsqueda muestra automáticamente las sugerencias relevantes en función de los datos introducidos.
3. Una vez que haya identificado la característica o el segmento por el que desea filtrar, haga clic en él en la lista de sugerencias.
4. Para reducir los resultados, utilice el **[!UICONTROL Similarity Cutoff]** control deslizante para pasar de menos similar [!UICONTROL traits], a más similares.

Una vez finalizado el filtrado, verá una nueva columna en la página de resultados: **[!UICONTROL Similar Traits]**. Esta columna muestra el número de fuentes de datos similares [!UICONTROL traits] al que ha filtrado, de cada fuente de datos que cumple los criterios de filtrado.

Para ver la lista completa de características similares, haga clic en el número de la **[!UICONTROL Similar Traits]** columna.

>[!NOTE]
>
> Audience Marketplace muestra los 500 resultados más similares [!UICONTROL trait] de las fuentes de datos.

Vea el siguiente vídeo para obtener una descripción general completa de cómo encontrar algo similar [!UICONTROL traits].

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Fuentes de datos privadas {#private-data-feeds}

En la [!UICONTROL Marketplace] lista, a veces el nombre y los datos del proveedor [!UICONTROL trait] se marcan como privados. Esto indica una fuente [de datos](../../../features/audience-marketplace/marketplace-private-feeds.md)privada. Una fuente de datos privada permite a los vendedores limitar el acceso del comprador a sus datos. Los vendedores pueden convertir las fuentes en privadas cuando ofrecen ofertas especiales, descuentos o cuando la privacidad y el control de acceso son importantes para ellos. Como comprador, tienes que enviar una solicitud de suscripción al vendedor si quieres acceder a una fuente privada. Consulte [Suscripción a una fuente](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) de datos privada para obtener más información.

>[!MORELIKETHIS]
>
>* [La página de detalles del plan de Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Descuentos para compradores de datos](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

