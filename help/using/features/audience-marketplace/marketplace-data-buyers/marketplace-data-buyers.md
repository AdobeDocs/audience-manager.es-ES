---
description: Información general y flujo de trabajo para compradores de datos que desean comprar datos de terceros desde Audience Manager
seo-description: Overview and workflow for data buyers who want to purchase third-party data from within Audience Manager
seo-title: Audience Marketplace for Data Buyers
solution: Audience Manager
title: Audience Marketplace para compradores de datos
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 2%

---

# [!UICONTROL Audience Marketplace] para compradores de datos {#audience-marketplace-for-data-buyers}

Información general y flujo de trabajo para compradores de datos que desean comprar datos de terceros desde [!DNL Audience Manager].

>[!NOTE]
>[Permisos basados en funciones](../../../reporting/reports-dashboard.md) control del acceso a [!UICONTROL Audience Marketplace] funciones.
>
>* Los administradores pueden crear fuentes de datos, administrar suscriptores y suscribirse a fuentes de datos.
>* Los usuarios solo pueden buscar y ver fuentes.


## El [!UICONTROL Marketplace]: Acerca de {#about-marketplace}

El [!UICONTROL Marketplace] es un [!DNL Audience Manager] función para compradores de datos que enumera las fuentes de datos a las que puedes suscribirte. Enumera la tarifa plana, [!DNL CPM]y fuentes de datos privadas. Estas fuentes las proporcionan proveedores externos que utilizan [!DNL Audience Manager] para vender datos.

En el [!UICONTROL Marketplace], las herramientas de creación de informes permiten realizar un seguimiento del uso de las fuentes y de la superposición entre las [!UICONTROL traits] y los de una fuente de datos suscrita. Finalmente, con [!UICONTROL Audience Marketplace], [!DNL Adobe] se encarga de las facturas y los pagos de tarifas (aunque debe informar sobre el uso automáticamente cuando se suscriba a un [!DNL CPM] fuente). Estas funciones le permiten encontrar fuentes de datos eficaces sin perder tiempo buscando un proveedor de datos.

>[!TIP]
>
>Utilice el **[Adobe de Audience Finder](https://www.adobe-audience-finder.com/)** para buscar fuentes de datos de alta calidad a las que pueda suscribirse. A continuación, vuelva al [!DNL Audience Manager] interfaz de usuario o utilice [API de comprador Audience Marketplace](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) para suscribirse a las fuentes que ha encontrado.

![purchator-marketplace-overview](assets/buyer-marketplace-overview.png)

El [!UICONTROL Marketplace] Esta lista contiene información que puede ordenar y buscar para encontrar la fuente de datos que más le convenga. Elementos en la [!UICONTROL Marketplace] la lista del comprador incluye:

* **[!UICONTROL Search]**: busque fuentes de datos por nombre o descripción de texto.
* **[!UICONTROL Similar Traits]**: Muestra el número de [!UICONTROL traits] desde una fuente de datos. Esta columna se muestra después de introducir una [!UICONTROL trait] o [!UICONTROL segment] para filtrar por en **[!UICONTROL Similarity To]** sección.
* **[!UICONTROL Name]**: Nombre de la fuente de datos.
* **[!UICONTROL Description]**: información sobre el contenido de una fuente de datos.
* **[!UICONTROL Provider]**: Nombre del proveedor de datos.
* **[!UICONTROL Traits]**: el número de [!UICONTROL traits] en una fuente de datos.
* **[!UICONTROL 30 Day Provider Unique Users]**: el número de usuarios únicos vistos en los últimos 30 días.
* **[!UICONTROL 30 Day Overlapped Uniques]**: el número de usuarios de la cuenta que se superponen con los usuarios de la cuenta del proveedor.
* **[!UICONTROL Feed Overlap]**: Valor de valores exclusivos superpuestos de 30 días, mostrado en porcentajes, calculado como: Comprador de datos (valores exclusivos superpuestos de 30 días / Comprador de datos (valores exclusivos de 30 días) x 100.
* **[!UICONTROL Private Feeds]**: consulte [Fuentes de datos privadas](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: El número de suscripciones que tiene con un proveedor de datos.

 

Para encontrar fácilmente las mejores fuentes de datos para sus necesidades, utilice los siguientes filtros disponibles a la izquierda del [!UICONTROL Marketplace] página:

* **[!UICONTROL Similarity To]**: filtre las fuentes de datos en función de su similitud con un [!UICONTROL trait] o [!UICONTROL segment] de su elección. Al introducir el [!UICONTROL trait] o segmento con el que comparar, puede utilizar el [!UICONTROL trait] o [!UICONTROL segment] ID de o sus respectivos nombres.
* **[!UICONTROL Similarity Cutoff]**: arrastre el control deslizante para filtrar las fuentes de datos en función de la similitud de su [!UICONTROL traits] son para el seleccionado [!UICONTROL trait] o [!UICONTROL segment]. Para obtener más información acerca de [!UICONTROL trait] puntuaciones de similitud, consulte [Puntuación de similitud de rasgos](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: filtre las fuentes de datos en función del estado de suscripción.
* **[!UICONTROL Plan Use Case]**: filtre las fuentes de datos en función de los casos de uso admitidos: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]**, y **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: filtre las fuentes de datos según su tipo de precios.

## Búsqueda de elementos similares [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] le da la opción de buscar [!UICONTROL traits] de varias fuentes de datos, en función de su similitud con las [!UICONTROL traits] o segmentos. A continuación se indica cómo hacerlo:

1. Ir a **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Utilice el **[!UICONTROL Similarity To]** selector para elegir entre filtrar según una [!UICONTROL trait] o [!UICONTROL segment]. Puede filtrar según [!UICONTROL trait]/[!UICONTROL segment] ID o nombre. El cuadro de búsqueda muestra automáticamente las sugerencias relevantes en función de sus entradas.
3. Una vez que haya identificado el rasgo o el segmento por el que desea filtrar, haga clic en él en la lista de sugerencias.
4. Para reducir los resultados, utilice el **[!UICONTROL Similarity Cutoff]** deslizador para moverse de menos similar [!UICONTROL traits], a otros más similares.

Una vez completado el filtrado, verá una nueva columna en la página de resultados: **[!UICONTROL Similar Traits]**. Esta columna muestra el número de [!UICONTROL traits] al que ha filtrado, de cada fuente de datos que cumpla los criterios de filtrado.

Para ver la lista completa de características similares, haga clic en el número en la **[!UICONTROL Similar Traits]** columna.

>[!NOTE]
>
> El Audience Marketplace muestra los 500 más similares [!UICONTROL trait] resultados de en las fuentes de datos.

Vea el siguiente vídeo para obtener una descripción general completa de cómo encontrar recursos similares [!UICONTROL traits].

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Fuentes de datos privadas {#private-data-feeds}

En el [!UICONTROL Marketplace] , a veces el nombre del proveedor y [!UICONTROL trait] los datos se marcan como privados. Esto indica un [fuente de datos privada](../../../features/audience-marketplace/marketplace-private-feeds.md). Una fuente de datos privada permite a los vendedores limitar el acceso de los compradores a sus datos. Los vendedores pueden hacer que las fuentes sean privadas cuando ofrezcan ofertas especiales, descuentos o cuando la privacidad y el control de acceso sean importantes para ellos. Como comprador, debes enviar una solicitud de suscripción al vendedor si deseas acceder a una fuente privada. Consulte [Suscripción a una fuente de datos privada](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) para obtener más información.

>[!MORELIKETHIS]
>
>* [La página de detalles del plan de Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Descuentos para compradores de datos](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

