---
description: Información general y flujo de trabajo para compradores de datos que desean comprar datos de terceros desde Audience Manager
seo-description: Información general y flujo de trabajo para compradores de datos que desean comprar datos de terceros desde Audience Manager
seo-title: Mercado de audiencias para compradores de datos
solution: Audience Manager
title: Mercado de audiencias para compradores de datos
topic: API DIL
uuid: f 505 b 5 f 4-4231-4 e 84-993 a-cd 64128 b 540 f
translation-type: tm+mt
source-git-commit: 12cc02103902a77b8b5967c319f4ac18746a700e

---


# Audience Marketplace for Data Buyers {#audience-marketplace-for-data-buyers}

Overview and workflow for data buyers who want to purchase third-party data from within [!DNL Audience Manager].

>[!NOTE]
>[Los permisos basados en roles](../../../reporting/reports-dashboard.md) controlan el acceso [!UICONTROL Audience Marketplace] a las funciones.
>
>* Los administradores pueden crear fuentes de datos, administrar suscriptores y suscribirse a fuentes de datos.
>* Los usuarios pueden buscar y ver solo fuentes.


## The Marketplace: About {#about-marketplace}

<!-- c_marketplace_about.xml -->

The [!UICONTROL Marketplace] is an [!DNL Audience Manager] feature for data buyers that lists data feeds you can subscribe to. It lists flat rate, [!DNL CPM], or private data feeds. These feeds are provided by third-party vendors that use [!DNL Audience Manager] to sell data. In the [!UICONTROL Marketplace], reporting tools let you track feed usage and the overlap between your traits and those in a subscribed data feed. Finally, with [!UICONTROL Audience Marketplace], [!DNL Adobe] takes care of invoices and fee payments (though you do have to self-report usage when subscribed to a [!DNL CPM] feed). Estas funciones permiten encontrar fuentes de datos eficaces sin perder tiempo buscando un proveedor de datos.

>[!TIP]
> 
>Use the **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** to find high quality data feeds that you can subscribe to. Then, go back into the Audience Manager UI or use the [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) to subscribe to the feeds you found.

![](assets/buyer_marketplace.png)

The [!UICONTROL Marketplace] list contains information that you can sort and search to find the data feed that's right for you. Items in the [!UICONTROL Marketplace] buyer's list include:

* **[!UICONTROL Search]:** Buscar fuentes de datos por nombre o descripción del texto.
* **[!UICONTROL Name]:** Nombre de la fuente de datos.
* **[!UICONTROL Description]:** Información sobre el contenido de una fuente de datos.
* **[!UICONTROL Provider]:** Nombre del proveedor de datos.
* **[!UICONTROL Traits]:** Número de características en una fuente de datos.
* **[!UICONTROL 30 Day Provider Unique Users]:** Número de usuarios únicos que se vieron en los últimos 30 días.
* **[!UICONTROL 30 Day Overlapped Uniques]:** El número de usuarios de la cuenta que se superponen con los usuarios de la cuenta del proveedor.
* **[!UICONTROL Feed Overlap]:** El valor únicos de 30 días superpuesto, mostrado en porcentajes, calculado como: Comprador de datos 30 días superpuestos únicos/Compradores de datos 30 días únicos) x 100.
* **[!UICONTROL Private Feeds]:** Consulte [Fuentes de datos privadas](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]:** Número de suscripciones que tiene con un proveedor de datos.

## Fuentes de datos privadas {#private-data-feeds}

In the [!UICONTROL Marketplace] list, sometimes the provider's name and trait data are marked as private. This indicates a [private data feed](../../../features/audience-marketplace/marketplace-private-feeds.md). Una fuente de datos privada permite a los vendedores limitar el acceso de los compradores a sus datos. Los vendedores pueden convertir las fuentes en privadas cuando ofrecen ofertas especiales, descuentos o cuando son importantes para ellos. Como comprador, debe enviar una solicitud de suscripción al vendedor si desea acceder a una fuente privada. See [Subscribe to a Private Data Feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) for details.

>[!MORE_ LIKE_ THIS]
>
>* [La página de detalles del plan de Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Descuentos para compradores de datos](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

