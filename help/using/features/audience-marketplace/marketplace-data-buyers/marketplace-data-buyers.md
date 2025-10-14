---
description: Información general y flujo de trabajo para compradores de datos que desean adquirir datos de terceros desde Audience Manager
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

Información general y flujo de trabajo para compradores de datos que deseen adquirir datos de terceros desde .[!DNL Audience Manager]

>[!NOTE]
>[Los permisos](../../../reporting/reports-dashboard.md) basados en roles controlan el acceso a las [!UICONTROL Audience Marketplace] características.
>
>* Los administradores pueden crear fuentes de datos, administrar suscriptores y suscribirse a fuentes de datos.
>* Los usuarios solo pueden búsqueda y vista fuentes.

## El [!UICONTROL Marketplace]: Acerca de {#about-marketplace}

La [!UICONTROL Marketplace] función para compradores de datos enumera [!DNL Audience Manager] las fuentes de datos a las que puede suscribirse. Enumera las fuentes de datos privadas y de tarifa plana. [!DNL CPM] Estas fuentes las proporcionan terceros proveedores que suelen [!DNL Audience Manager] vender datos.

En las herramientas , sistema de informes [!UICONTROL Marketplace]permiten realizar un seguimiento de fuente uso y la superposición entre su [!UICONTROL traits] y los de una fuente de datos a la que se ha suscrito. Finalmente, con [!UICONTROL Audience Marketplace], [!DNL Adobe] se encarga de las facturas y los pagos de tarifas (aunque tiene que autoinformar el uso cuando se suscribe a un [!DNL CPM] fuente). Estas características le permiten encontrar fuentes de datos eficaces sin perder tiempo buscando un proveedor de datos.

>[!TIP]
>
>Utilice el Buscador **[&#128279;](https://www.adobe-audience-finder.com/) de audiencia de Adobe Systems para encontrar fuentes de datos de alta calidad a las** que puede suscribirse. A continuación, vuelve a la interfaz de [!DNL Audience Manager] usuario o usa la API[&#x200B; de comprador de Audience Marketplace &#x200B;](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API)para suscribirte a las fuentes que encontraste.

![Descripción general de comprador-marketplace](assets/buyer-marketplace-overview.png)

El [!UICONTROL Marketplace] lista contiene información que puede ordenar y búsqueda para encontrar la fuente de datos adecuada para usted. Algunos de los [!UICONTROL Marketplace] elementos del lista del comprador son:

* **[!UICONTROL Search]**: busca fuentes de datos por nombre o por descripción de texto.
* **[!UICONTROL Similar Traits]**: Muestra el número de similares [!UICONTROL traits] de una fuente de datos. Esta columna se muestra después de introducir una [!UICONTROL trait] O [!UICONTROL segment] para filtrar por en la **[!UICONTROL Similarity To]** sección.
* **[!UICONTROL Name]**: Nombre del fuente de datos.
* **[!UICONTROL Description]**: información sobre el contenido de una fuente de datos.
* **[!UICONTROL Provider]**: Nombre del proveedor de datos.
* **[!UICONTROL Traits]**: El número de [!UICONTROL traits] en un fuente de datos.
* **[!UICONTROL 30 Day Provider Unique Users]**: El número de usuarios únicos vistos en los últimos 30 días.
* **[!UICONTROL 30 Day Overlapped Uniques]**: el número de usuarios del cuenta que se superponen con los usuarios del cuenta del proveedor.
* **[!UICONTROL Feed Overlap]**: El valor de los únicos solapados de 30 días, mostrado en porcentajes, calculado como: Datos comprador únicos solapados de 30 días/Datos comprador únicos de 30 días) x 100.
* **[!UICONTROL Private Feeds]**: Consulte [Fuentes](../../../features/audience-marketplace/marketplace-private-feeds.md) de datos privadas.
* **[!UICONTROL Currently Subscribed Plan Count]**: El número de suscripciones que tiene con un proveedor de datos.

 

Para encontrar fácilmente las fuentes de datos que mejor se adapten a sus necesidades, utilice las siguientes filtros disponibles en la [!UICONTROL Marketplace] parte izquierda del Página:

* **[!UICONTROL Similarity To]**: Filtrar las fuentes de datos en función de su similitud con una [!UICONTROL trait] o [!UICONTROL segment] de su elección. Al introducir la [!UICONTROL trait] segmento o con la que comparar, puede utilizar el ID de [!UICONTROL trait] o [!UICONTROL segment] sus respectivos nombres.
* **[!UICONTROL Similarity Cutoff]**: Arrastre la regulador para filtrar las fuentes de datos en función de su [!UICONTROL traits] similitud con la seleccionada [!UICONTROL trait] o [!UICONTROL segment]. Para obtener más información sobre [!UICONTROL trait] las puntuaciones de similitud, consulte [Puntuación de similitud de rasgos](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtrar las fuentes de datos en función del estado de su suscripción.
* **[!UICONTROL Plan Use Case]**: Filtrar las fuentes de datos en función de sus casos de uso admitidos: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]**, y **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtrar las fuentes de datos en función de su tipo de precio.

## Búsqueda de elementos similares [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] le da la opción de buscar [!UICONTROL traits] entre varias fuentes de datos, según su similitud con sus segmentos o segmentos existentes [!UICONTROL traits] . A continuación, le indicamos cómo hacerlo:

1. Vaya a **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Utilice el selector para elegir entre filtrar en función de **[!UICONTROL Similarity To]** un [!UICONTROL trait] o [!UICONTROL segment]. Puede filtrar en función de [!UICONTROL trait]/[!UICONTROL segment] ID o nombre. El cuadro búsqueda muestra automáticamente sugerencias relevantes en función de sus datos.
3. Una vez que haya identificado el rasgo o la segmento por la que desea filtrar, haga clic en él en el lista de sugerencias.
4. Para reducir los resultados, utilice el **[!UICONTROL Similarity Cutoff]** regulador para pasar de menos similares a más similares [!UICONTROL traits].

Una vez finalizado el filtrado, verás una nueva columna en el Página de resultados: **[!UICONTROL Similar Traits]**. Esta columna muestra el número de similar [!UICONTROL traits] al que filtró, de cada fuente de datos que cumple los criterios de filtrado.

Para ver la lista completa de características similares, haga clic en el número de la **[!UICONTROL Similar Traits]** columna.

>[!NOTE]
>
> Audience Marketplace muestra los primeros 500 resultados similares [!UICONTROL trait] de las fuentes de datos.

Mire el video a continuación para obtener una descripción general completa de cómo encontrar archivos .[!UICONTROL traits]

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Fuentes de datos privadas {#private-data-feeds}

En el [!UICONTROL Marketplace] lista, a veces el nombre y [!UICONTROL trait] los datos del proveedor se marcan como privados. Esto indica un [fuente de datos](../../../features/audience-marketplace/marketplace-private-feeds.md) privado. Una fuente de datos privada permite a los vendedores limitar el acceso comprador a sus datos. Los vendedores pueden hacer que los feeds sean privados cuando ofrecen ofertas especiales, descuentos o cuando la privacidad y la control de acceso son importantes para ellos. Como comprador, debe enviar una suscripción solicitud al vendedor si desea acceder a un fuente privado. Consulte [Suscribirse a una fuente](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) de datos privada para obtener más detalles.

>[!MORELIKETHIS]
>
>* [La página de detalles del plan de Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Descuentos para compradores de datos](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)
