---
description: Información general y flujo de trabajo para compradores de datos que desean adquirir datos de terceros desde el Audience Manager
seo-description: Información general y flujo de trabajo para compradores de datos que desean adquirir datos de terceros desde el Audience Manager
seo-title: Audience Marketplace para compradores de datos
solution: Audience Manager
title: Audience Marketplace para compradores de datos
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 3%

---

# [!UICONTROL Audience Marketplace] para compradores de datos  {#audience-marketplace-for-data-buyers}

Información general y flujo de trabajo para compradores de datos que desean adquirir datos de terceros desde [!DNL Audience Manager].

>[!NOTE]
>[Los permisos basados en roles](../../../reporting/reports-dashboard.md) controlan el acceso a las funciones [!UICONTROL Audience Marketplace].
>
>* Los administradores pueden crear fuentes de datos, administrar suscriptores y suscribirse a fuentes de datos.
>* Los usuarios solo pueden buscar y ver fuentes.


## El [!UICONTROL Marketplace]: Acerca de {#about-marketplace}

La [!UICONTROL Marketplace] es una función [!DNL Audience Manager] para compradores de datos que enumera las fuentes de datos a las que puede suscribirse. Enumera las fuentes de datos privadas, [!DNL CPM] y de tasa plana. Estas fuentes las proporcionan proveedores externos que utilizan [!DNL Audience Manager] para vender datos.

En [!UICONTROL Marketplace], las herramientas de informes permiten rastrear el uso de fuentes y la superposición entre [!UICONTROL traits] y las de una fuente de datos suscrita. Por último, con [!UICONTROL Audience Marketplace], [!DNL Adobe] se encarga de las facturas y los pagos de tasas (aunque tiene que informar sobre el uso cuando está suscrito a una fuente [!DNL CPM]). Estas funciones permiten encontrar fuentes de datos eficaces sin perder tiempo buscando un proveedor de datos.

>[!TIP]
>
>Utilice el **[Buscador de audiencias de Adobe](https://www.adobe-audience-finder.com/)** para encontrar fuentes de datos de alta calidad a las que puede suscribirse. A continuación, vuelva a la interfaz de usuario [!DNL Audience Manager] o utilice la [API del comprador Audience Marketplace](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) para suscribirse a las fuentes que ha encontrado.

![purcher-marketplace-overview](assets/buyer-marketplace-overview.png)

La lista [!UICONTROL Marketplace] contiene información que puede ordenar y buscar para encontrar la fuente de datos que sea adecuada para usted. Los elementos de la lista de [!UICONTROL Marketplace] compradores incluyen:

* **[!UICONTROL Search]**: Busque fuentes de datos por nombre o descripción de texto.
* **[!UICONTROL Similar Traits]**: Muestra el número de elementos similares  [!UICONTROL traits] de una fuente de datos. Esta columna se muestra después de introducir [!UICONTROL trait] o [!UICONTROL segment] para filtrar por en la sección **[!UICONTROL Similarity To]**.
* **[!UICONTROL Name]**: Nombre de la fuente de datos.
* **[!UICONTROL Description]**: Información sobre el contenido de una fuente de datos.
* **[!UICONTROL Provider]**: Nombre del proveedor de datos.
* **[!UICONTROL Traits]**: El número de  [!UICONTROL traits] en una fuente de datos.
* **[!UICONTROL 30 Day Provider Unique Users]**: Número de usuarios únicos vistos en los últimos 30 días.
* **[!UICONTROL 30 Day Overlapped Uniques]**: El número de usuarios de la cuenta que se superponen con los usuarios de la cuenta del proveedor.
* **[!UICONTROL Feed Overlap]**: El valor único superpuesto de 30 días, mostrado en porcentajes, calculado como: Comprador de datos 30 días únicos superpuestos / Comprador de datos 30 días únicos) x 100.
* **[!UICONTROL Private Feeds]**: Consulte Fuentes de datos  [privadas](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Número de suscripciones que tiene con un proveedor de datos.

 

Para encontrar fácilmente las mejores fuentes de datos para sus necesidades, utilice los siguientes filtros disponibles en la parte izquierda de la página [!UICONTROL Marketplace]:

* **[!UICONTROL Similarity To]**: Filtre las fuentes de datos en función de su similitud con  [!UICONTROL trait] o  [!UICONTROL segment] de su elección. Al introducir el [!UICONTROL trait] o segmento con el que comparar, puede utilizar el [!UICONTROL trait] o el [!UICONTROL segment] ID, o sus nombres respectivos.
* **[!UICONTROL Similarity Cutoff]**: Arrastre el control deslizante para filtrar las fuentes de datos en función de lo similares que  [!UICONTROL traits] sean a las fuentes seleccionadas  [!UICONTROL trait] o  [!UICONTROL segment]. Para obtener más información sobre las [!UICONTROL trait] puntuaciones de similitud, consulte [Puntuación de similitud de rasgos](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtre las fuentes de datos en función de su estado de suscripción.
* **[!UICONTROL Plan Use Case]**: Filtre las fuentes de datos en función de sus casos de uso admitidos:  **[!UICONTROL Activation]**,  **[!UICONTROL Segments and Overlap]**, y  **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtre las fuentes de datos en función de su tipo de precio.

## Búsqueda de similar [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] le da la opción de buscar  [!UICONTROL traits] desde varias fuentes de datos, en función de su similitud con los segmentos  [!UICONTROL traits] o existentes. A continuación se muestra cómo hacerlo:

1. Vaya a **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Utilice el selector **[!UICONTROL Similarity To]** para elegir entre filtrar según [!UICONTROL trait] o [!UICONTROL segment]. Puede filtrar por ID o nombre [!UICONTROL trait]/[!UICONTROL segment] . El cuadro de búsqueda muestra automáticamente las sugerencias relevantes en función de sus datos introducidos.
3. Una vez identificado el rasgo o segmento por el que desea filtrar, haga clic en él en la lista de sugerencias.
4. Para reducir los resultados, utilice el control deslizante **[!UICONTROL Similarity Cutoff]** para pasar de [!UICONTROL traits] menos similar a otros más similares.

Una vez completado el filtrado, verá una nueva columna en la página de resultados: **[!UICONTROL Similar Traits]**. Esta columna muestra el número de fuentes de datos similares [!UICONTROL traits] al que filtró, de cada fuente de datos que cumple los criterios de filtrado.

Para ver la lista completa de características similares, haga clic en el número en la columna **[!UICONTROL Similar Traits]**.

>[!NOTE]
>
> Audience Marketplace muestra los 500 resultados similares [!UICONTROL trait] principales de las fuentes de datos.

Vea el siguiente vídeo para obtener una descripción general completa de cómo encontrar [!UICONTROL traits] similares.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Fuentes de datos privadas {#private-data-feeds}

En la lista [!UICONTROL Marketplace], a veces el nombre del proveedor y los datos [!UICONTROL trait] se marcan como privados. Esto indica una [fuente de datos privada](../../../features/audience-marketplace/marketplace-private-feeds.md). Una fuente de datos privada permite a los vendedores limitar el acceso de los compradores a sus datos. Los vendedores pueden convertir las fuentes en privadas cuando ofrecen ofertas especiales, descuentos o cuando la privacidad y el control de acceso son importantes para ellos. Como comprador, debe enviar una solicitud de suscripción al vendedor si desea acceder a una fuente privada. Consulte [Suscribirse a una fuente de datos privada](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) para obtener más información.

>[!MORELIKETHIS]
>
>* [La página de detalles del plan de Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Descuentos para compradores de datos](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

