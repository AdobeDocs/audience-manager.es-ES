---
description: Información general y flujo de trabajo para compradores de datos que deseen comprar datos de terceros desde el Audience Manager
seo-description: Información general y flujo de trabajo para compradores de datos que deseen comprar datos de terceros desde el Audience Manager
seo-title: Audience Marketplace para compradores de datos
solution: Audience Manager
title: Audience Marketplace para compradores de datos
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 3%

---


# [!UICONTROL Audience Marketplace] para compradores de datos  {#audience-marketplace-for-data-buyers}

Información general y flujo de trabajo para compradores de datos que deseen comprar datos de terceros desde [!DNL Audience Manager].

>[!NOTE]
>[Los permisos basados en roles](../../../reporting/reports-dashboard.md) controlan el acceso a las funciones [!UICONTROL Audience Marketplace].
>
>* Los administradores pueden crear fuentes de datos, administrar suscriptores y suscribirse a fuentes de datos.
>* Los usuarios solo pueden buscar y vista de fuentes.


## El [!UICONTROL Marketplace]: Acerca de {#about-marketplace}

La [!UICONTROL Marketplace] es una función [!DNL Audience Manager] para compradores de datos que lista fuentes de datos a las que puede suscribirse. Lista fuentes de datos privadas, [!DNL CPM] y de tasa fija. Estas fuentes las proporcionan proveedores de terceros que utilizan [!DNL Audience Manager] para vender datos.

En [!UICONTROL Marketplace], las herramientas de sistema de informes permiten rastrear el uso de fuentes y la superposición entre su [!UICONTROL traits] y los de una fuente de datos suscrita. Finalmente, con [!UICONTROL Audience Marketplace], [!DNL Adobe] se encarga de las facturas y los pagos de honorarios (aunque tiene que informar automáticamente sobre el uso cuando está suscrito a una fuente [!DNL CPM]). Estas funciones le permiten encontrar fuentes de datos eficaces sin perder tiempo buscando un proveedor de datos.

>[!TIP]
>
>Utilice el **[Buscador de Audiencias de Adobe](https://www.adobe-audience-finder.com/)** para encontrar fuentes de datos de alta calidad a las que puede suscribirse. A continuación, vuelva a la interfaz de usuario [!DNL Audience Manager] o utilice la [API del comprador Audience Marketplace](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) para suscribirse a las fuentes que ha encontrado.

![comprador-mercado-información general](assets/buyer-marketplace-overview.png)

La lista [!UICONTROL Marketplace] contiene información que puede ordenar y buscar para encontrar la fuente de datos que sea adecuada para usted. Los elementos de la lista del comprador [!UICONTROL Marketplace] incluyen:

* **[!UICONTROL Search]**:: Busque fuentes de datos por nombre o descripción de texto.
* **[!UICONTROL Similar Traits]**:: Muestra el número de elementos similares  [!UICONTROL traits] de una fuente de datos. Esta columna se muestra después de ingresar un [!UICONTROL trait] o [!UICONTROL segment] para filtrar por en la sección **[!UICONTROL Similarity To]**.
* **[!UICONTROL Name]**:: Nombre de la fuente de datos.
* **[!UICONTROL Description]**:: Información sobre el contenido de una fuente de datos.
* **[!UICONTROL Provider]**:: Nombre del proveedor de datos.
* **[!UICONTROL Traits]**:: Número de  [!UICONTROL traits] en una fuente de datos.
* **[!UICONTROL 30 Day Provider Unique Users]**:: Número de usuarios únicos vistos en los últimos 30 días.
* **[!UICONTROL 30 Day Overlapped Uniques]**:: El número de usuarios de su cuenta que se superponen con los usuarios de la cuenta del proveedor.
* **[!UICONTROL Feed Overlap]**:: El valor de valores únicos superpuestos de 30 días, mostrado en porcentajes, calculado como: Comprador de datos 30 días superpuestos únicos / Comprador de datos 30 días únicos) x 100.
* **[!UICONTROL Private Feeds]**:: Consulte Fuentes de datos  [privadas](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**:: Número de suscripciones que tiene con un proveedor de datos.

 

Para encontrar fácilmente las mejores fuentes de datos según sus necesidades, utilice los siguientes filtros disponibles en la parte izquierda de la página [!UICONTROL Marketplace]:

* **[!UICONTROL Similarity To]**:: Filtre las fuentes de datos en función de su similitud con  [!UICONTROL trait] o  [!UICONTROL segment] de su elección. Al introducir el [!UICONTROL trait] o segmento con el que comparar, puede utilizar el [!UICONTROL trait] o el [!UICONTROL segment] ID, o sus respectivos nombres.
* **[!UICONTROL Similarity Cutoff]**:: Arrastre el control deslizante para filtrar las fuentes de datos en función de su parecido  [!UICONTROL traits] a la seleccionada  [!UICONTROL trait] o  [!UICONTROL segment]. Para obtener más información sobre las [!UICONTROL trait] puntuaciones de similitud, consulte [Puntuación de similitud de características](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**:: Filtre las fuentes de datos en función del estado de la suscripción.
* **[!UICONTROL Plan Use Case]**:: Filtre las fuentes de datos en función de los casos de uso admitidos:  **[!UICONTROL Activation]**,  **[!UICONTROL Segments and Overlap]**, y  **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**:: Filtre las fuentes de datos en función de su tipo de precio.

## Búsqueda de similar [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] le ofrece la opción  [!UICONTROL traits] de buscar desde varias fuentes de datos, en función de su similitud con los segmentos  [!UICONTROL traits] o existentes. A continuación se muestra cómo hacerlo:

1. Vaya a **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Utilice el selector **[!UICONTROL Similarity To]** para elegir entre filtrar según [!UICONTROL trait] o [!UICONTROL segment]. Puede filtrar por [!UICONTROL trait]/[!UICONTROL segment] ID o nombre. El cuadro de búsqueda muestra automáticamente las sugerencias relevantes en función de los datos introducidos.
3. Una vez que haya identificado la característica o el segmento por el que desea filtrar, haga clic en él en la lista de sugerencias.
4. Para reducir los resultados, utilice el deslizador **[!UICONTROL Similarity Cutoff]** para pasar de menos similar [!UICONTROL traits] a más similares.

Una vez finalizado el filtrado, verá una nueva columna en la página de resultados: **[!UICONTROL Similar Traits]**. Esta columna muestra el número de fuentes de datos similares [!UICONTROL traits] a la filtrada por cada fuente de datos que cumple los criterios de filtrado.

Para ver la lista completa de características similares, haga clic en el número en la columna **[!UICONTROL Similar Traits]**.

>[!NOTE]
>
> Audience Marketplace muestra los 500 resultados más parecidos de las fuentes de datos.[!UICONTROL trait]

Vea el siguiente video para obtener una visión general completa de cómo encontrar un [!UICONTROL traits] similar.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Fuentes de datos privadas {#private-data-feeds}

En la lista [!UICONTROL Marketplace], a veces el nombre del proveedor y los datos [!UICONTROL trait] se marcan como privados. Esto indica una [fuente de datos privada](../../../features/audience-marketplace/marketplace-private-feeds.md). Una fuente de datos privada permite a los vendedores limitar el acceso del comprador a sus datos. Los vendedores pueden convertir las fuentes en privadas cuando ofrecen ofertas especiales, descuentos o cuando la privacidad y el control de acceso son importantes para ellos. Como comprador, tienes que enviar una solicitud de suscripción al vendedor si quieres acceder a una fuente privada. Consulte [Suscribirse a una fuente de datos privada](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) para obtener más información.

>[!MORELIKETHIS]
>
>* [La página de detalles del plan de Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Descuentos para compradores de datos](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

