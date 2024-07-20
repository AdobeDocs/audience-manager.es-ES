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
source-wordcount: '724'
ht-degree: 1%

---

# [!UICONTROL Audience Marketplace] para compradores de datos {#audience-marketplace-for-data-buyers}

Información general y flujo de trabajo para compradores de datos que desean comprar datos de terceros en [!DNL Audience Manager].

>[!NOTE]
>[Permisos basados en roles](../../../reporting/reports-dashboard.md) controlan el acceso a las características de [!UICONTROL Audience Marketplace].
>
>* Los administradores pueden crear fuentes de datos, administrar suscriptores y suscribirse a fuentes de datos.
>* Los usuarios solo pueden buscar y ver fuentes.

## El [!UICONTROL Marketplace]: Acerca de {#about-marketplace}

[!UICONTROL Marketplace] es una característica de [!DNL Audience Manager] para compradores de datos que enumera las fuentes de datos a las que puede suscribirse. Enumera fuentes de datos de tarifa plana, [!DNL CPM] y privadas. Estas fuentes las proporcionan proveedores de terceros que utilizan [!DNL Audience Manager] para vender datos.

En [!UICONTROL Marketplace], las herramientas de creación de informes le permiten hacer un seguimiento del uso de fuentes y de la superposición entre su [!UICONTROL traits] y los de una fuente de datos suscrita. Por último, con [!UICONTROL Audience Marketplace], [!DNL Adobe] se encarga de las facturas y los pagos de tarifas (aunque debe informar automáticamente sobre el uso cuando se suscriba a una fuente de [!DNL CPM]). Estas funciones le permiten encontrar fuentes de datos eficaces sin perder tiempo buscando un proveedor de datos.

>[!TIP]
>
>Use **[Buscador de audiencias de Adobe](https://www.adobe-audience-finder.com/)** para encontrar fuentes de datos de alta calidad a las que pueda suscribirse. A continuación, vuelve a la interfaz de usuario de [!DNL Audience Manager] o usa la [API de comprador Audience Marketplace](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) para suscribirte a las fuentes que hayas encontrado.

![reseña del mercado de compradores](assets/buyer-marketplace-overview.png)

La lista [!UICONTROL Marketplace] contiene información que puede ordenar y buscar para encontrar la fuente de datos adecuada para usted. Los artículos de la lista de compradores de [!UICONTROL Marketplace] incluyen:

* **[!UICONTROL Search]**: buscar fuentes de datos por nombre o descripción de texto.
* **[!UICONTROL Similar Traits]**: muestra el número de [!UICONTROL traits] similares de una fuente de datos. Esta columna se muestra después de escribir [!UICONTROL trait] o [!UICONTROL segment] para filtrar en la sección **[!UICONTROL Similarity To]**.
* **[!UICONTROL Name]**: nombre de la fuente de datos.
* **[!UICONTROL Description]**: información sobre el contenido de una fuente de datos.
* **[!UICONTROL Provider]**: nombre del proveedor de datos.
* **[!UICONTROL Traits]**: el número de [!UICONTROL traits] en una fuente de datos.
* **[!UICONTROL 30 Day Provider Unique Users]**: número de usuarios únicos vistos en los últimos 30 días.
* **[!UICONTROL 30 Day Overlapped Uniques]**: número de usuarios de su cuenta que se superponen con los usuarios de la cuenta del proveedor.
* **[!UICONTROL Feed Overlap]**: valor de valores exclusivos superpuestos de 30 días, mostrado en porcentajes, calculado como: comprador de datos (valores exclusivos superpuestos de 30 días / comprador de datos (valores exclusivos de 30 días) x 100.
* **[!UICONTROL Private Feeds]**: vea [Fuentes de datos privadas](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: el número de suscripciones que tiene con un proveedor de datos.

 

Para encontrar fácilmente las mejores fuentes de datos según sus necesidades, utilice los siguientes filtros disponibles a la izquierda de la página [!UICONTROL Marketplace]:

* **[!UICONTROL Similarity To]**: filtre las fuentes de datos en función de su similitud con [!UICONTROL trait] o [!UICONTROL segment] de su elección. Al escribir [!UICONTROL trait] o el segmento con el que comparar, puede usar el identificador [!UICONTROL trait] o [!UICONTROL segment], o sus nombres respectivos.
* **[!UICONTROL Similarity Cutoff]**: arrastre el control deslizante para filtrar las fuentes de datos en función de lo similares que sean sus [!UICONTROL traits] a los [!UICONTROL trait] o [!UICONTROL segment] seleccionados. Para obtener más información acerca de [!UICONTROL trait] puntuaciones de similitud, consulte [Puntuación de similitud de rasgos](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: filtre las fuentes de datos en función de su estado de suscripción.
* **[!UICONTROL Plan Use Case]**: filtre las fuentes de datos según los casos de uso admitidos: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** y **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: filtre las fuentes de datos según su tipo de precios.

## Buscando [!UICONTROL Traits] similares {#finding-similar-traits}

[!UICONTROL Audience Marketplace] le da la opción de encontrar [!UICONTROL traits] de varias fuentes de datos, según su similitud con sus [!UICONTROL traits] o segmentos existentes. A continuación se indica cómo hacerlo:

1. Ir a **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Utilice el selector **[!UICONTROL Similarity To]** para elegir entre filtrar según un [!UICONTROL trait] o [!UICONTROL segment]. Puede filtrar según el nombre o el ID [!UICONTROL trait]/[!UICONTROL segment]. El cuadro de búsqueda muestra automáticamente las sugerencias relevantes en función de sus entradas.
3. Una vez que haya identificado el rasgo o el segmento por el que desea filtrar, haga clic en él en la lista de sugerencias.
4. Para reducir los resultados, use el control deslizante **[!UICONTROL Similarity Cutoff]** para pasar de [!UICONTROL traits] menos similares a otros más similares.

Una vez completado el filtrado, verá una nueva columna en la página de resultados: **[!UICONTROL Similar Traits]**. Esta columna muestra el número de [!UICONTROL traits] similares al que filtró, de cada fuente de datos que cumple los criterios de filtrado.

Para ver la lista completa de características similares, haga clic en el número de la columna **[!UICONTROL Similar Traits]**.

>[!NOTE]
>
> El Audience Marketplace muestra los primeros 500 resultados similares de [!UICONTROL trait] en las fuentes de datos.

Vea el siguiente vídeo para obtener información general sobre cómo encontrar [!UICONTROL traits] similares.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Fuentes de datos privadas {#private-data-feeds}

En la lista [!UICONTROL Marketplace], a veces el nombre del proveedor y los datos de [!UICONTROL trait] se marcan como privados. Esto indica una [fuente de datos privada](../../../features/audience-marketplace/marketplace-private-feeds.md). Una fuente de datos privada permite a los vendedores limitar el acceso de los compradores a sus datos. Los vendedores pueden hacer que las fuentes sean privadas cuando ofrezcan ofertas especiales, descuentos o cuando la privacidad y el control de acceso sean importantes para ellos. Como comprador, debes enviar una solicitud de suscripción al vendedor si deseas acceder a una fuente privada. Consulte [Suscribirse a una fuente de datos privada](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) para obtener más información.

>[!MORELIKETHIS]
>
>* [La página de detalles del plan de Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Descuentos para compradores de datos](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)
