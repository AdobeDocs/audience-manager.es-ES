---
description: Una fuente de datos requiere un nombre, una descripción, una fuente de datos y un tipo de plan. Las fuentes se desactivan hasta que guarde y activa la fuente. Configure fuentes de datos públicas o privadas en Audience Marketplace > Mis datos compartidos. Sólo está disponible para vendedores de datos.
seo-description: Una fuente de datos requiere un nombre, una descripción, una fuente de datos y un tipo de plan. Las fuentes se desactivan hasta que guarde y activa la fuente. Configure fuentes de datos públicas o privadas en Audience Marketplace > Mis datos compartidos. Sólo está disponible para vendedores de datos.
seo-title: Crear, cotizar y administrar fuentes de datos
solution: Audience Manager
title: Crear, cotizar y administrar fuentes de datos
topic: API DIL
uuid: e 28 c 20 b 3-33 fc -4485-8 ee 9-8530 d 126 f 741
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create, Price, and Manage Data Feeds {#create-price-and-manage-data-feeds}

Una fuente de datos requiere un nombre, una descripción, una fuente de datos y un tipo de plan. Las fuentes se desactivan hasta que guarde y activa la fuente. Set up public or private data feeds in [!UICONTROL Audience Marketplace] &gt; [!UICONTROL My Shared Data]. Sólo está disponible para vendedores de datos.

## Create a Public or Private Data Feed {#create-public-private-data-feed}

Una fuente de datos requiere un nombre, una descripción, una fuente de datos y un tipo de plan. Las fuentes se desactivan hasta que guarde y activa la fuente. Set up public or private data feeds in **[!UICONTROL Audience Marketplace > My Shared Data]**. Sólo está disponible para vendedores de datos.

<!-- t_data_feed.xml -->

Debe tener derechos de administrador para crear una fuente de datos pública o privada.
Para crear una fuente de datos:

1. Haga clic en **[!UICONTROL New Data Feed]**.
1. Asigne un nombre a la fuente de datos. Los compradores de datos pueden buscar su fuente en función del nombre.
1. Proporcione una breve descripción (máximo de 255 caracteres).

   Una buena descripción debería describir su fuente de forma precisa. For example, you could include text for marketing categories, demographics, and geographic coverage (e.g., [!DNL US] or North America). El texto de descripción es susceptible de búsqueda y ayuda a los compradores a encontrar o evaluar su fuente. Una buena descripción es una parte importante para atraer suscriptores a la fuente de datos.
1. Select a data source from the **[!UICONTROL Data Source]** options.

   >[!IMPORTANT]
   >
   >Cualquier característica actual y futura que pertenezca a esta fuente de datos se compartirá con los compradores de datos, como parte de esta fuente.

1. In [!UICONTROL Plan Types], select the options you want to use and click **[!UICONTROL Add Plan]**.

   Las fuentes pueden contener varios planes. Los planes pueden contener varios casos de uso. For details, see [Plan Types for Data Feeds](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Click **[!UICONTROL Save]** to save your data fee *without* activating it.
1. Para guardar y activar una fuente de datos:
   1. Move the **[!UICONTROL Availability]** slider to **[!UICONTROL Active]**.
   1. Haga clic en **[!UICONTROL Save]**.
   >[!NOTE]
   >
   >* Las fuentes de datos guardadas y activadas no se pueden eliminar.
   >* Los compradores ven solo fuentes activas.


### Opcional: Crear una fuente de datos privada

In the [!UICONTROL Settings] section, move the slider to:

* **[!UICONTROL Private]** y **[!UICONTROL Branded]**: [!UICONTROL Marketplace] La lista del comprador muestra el nombre del vendedor en la columna del proveedor y todos los demás datos están ocultos.

* **[!UICONTROL Private]** y **[!UICONTROL Unbranded]**: [!UICONTROL Marketplace] La lista del comprador muestra únicamente el nombre y la descripción de la fuente de datos. The data provider name appears as [!UICONTROL Private Seller].

To see what a private feed looks like to buyers, see the buyers section in [Private Data Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).

>[!MORE_ LIKE_ THIS]
>
>* [Fuentes de datos privadas](../../../features/audience-marketplace/marketplace-private-feeds.md)


## Desactivar una fuente de datos de un suscriptor {#deactivate-data-feed}

As an [!UICONTROL Audience Marketplace] data provider, you can revoke buyer access to a subscribed data feed. Es posible que desee eliminar a un comprador de una fuente por motivos tales como pago o no pago de tarifas, o si utiliza datos de características incorrectamente.

<!-- marketplace-deactiva4te-subscribers.xml -->

Para revocar un suscriptor:

1. In [!UICONTROL My Shared Data], find the feed the subscriber is using.

   >[!NOTE]
   >
   >Las fuentes de datos con cuentas vencidas están marcadas con un icono de signo de exclamación triángulo/exclamación.

1. In the [!UICONTROL Subscribers] column, click the blue number that counts subscribers for that feed. Se abre la página de detalles de la suscripción.
1. Move the **[!UICONTROL Subscription]** slider to **[!UICONTROL Off]**. Se abre una ventana de cuadro de diálogo de confirmación.
1. In the [!UICONTROL Confirmation] pop, click **[!UICONTROL Yes]** to deactivate a subscription or **[!UICONTROL Cancel]** to quit without making subscription changes.

### Qué sucede después de desactivar un suscriptor

Al anular el acceso a una fuente de datos, se envía un correo electrónico de notificación a todos los usuarios de administrador en la cuenta del comprador de datos. El correo electrónico incluye un archivo adjunto que enumera las características revocadas. Esta lista ayuda a los suscriptores a encontrar y eliminar características desactivadas de sus segmentos y modelos.

### Desactivación de facturación y fuente

Después de eliminar el acceso a una fuente de datos, los suscriptores son responsables de las tarifas del mes anterior o actual, según el momento en que se desactivó la fuente.

## Plan Types for Data Feeds {#plan-types}

[!DNL Plan types] son componentes esenciales en una fuente [!UICONTROL Audience Marketplace] de datos. Como proveedor de datos, le permiten crear varios casos de uso y opciones de precio para sus fuentes. Además, puede ser una buena estrategia crear algunos planes para cada fuente de datos. Esto proporciona a los compradores diferentes opciones para elegir cuándo buscan datos para modelar o enviar a un destino.

[Cree una fuente](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) de datos para seleccionar [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Plan Types and Use Case Options {#plan-types-use-cases}

<!-- c_feed_options.xml -->

[!UICONTROL Use Case] La configuración permite a los vendedores controlar cómo pueden utilizar los datos los compradores.

### Segmentos y superposición

A **[!UICONTROL Segments and Overlap]** use case creates a plan that lets buyers compare trait data in a [trait-to-trait overlap report](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Furthermore, buyers can add your data to segments and make comparisons with the [segment-to-trait](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) and [segment-to-segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) reports.

Each data feed must include at least one [!UICONTROL Segments and Overlap] use case. Buyers cannot subscribe to other plans in a data feed if the feed does not contain a [!UICONTROL Segments and Overlap] use case, either by itself or in combination with another use case.

Las comparaciones de superposiciones pueden ayudar a compradores:

* **Ampliar alcance de audiencia:** La superposición baja sugiere que sus características contienen usuarios que el comprador no ha visto antes. Como resultado, es posible que los compradores deseen que estas características agreguen nuevos usuarios a sus segmentos de audiencia.
* **Mejorar audiencias existentes:** La superposición alta sugiere que sus características contienen usuarios similares a los que ya conoce un comprador. Como resultado, es posible que los compradores deseen que estas características contribuyan a realizar mejoras de forma incremental y con objetivos a las audiencias desarrolladas.

Precio este caso de uso de la siguiente manera:

* Unidad de medida: Tarifa plana
* Precio: Gratis ($ 0,00)

### Modelado

A **[!UICONTROL Modeling]** use case creates a plan that lets buyers compare your traits to theirs with [algorithmic modeling](../../../features/algorithmic-models/understanding-models.md#understanding-models). Los compradores ven los resultados del modelo para encontrar nuevas audiencias en los datos que comparten atributos de conversión similares a los suyos propios. Precio este caso de uso de la siguiente manera:

* Unidad de medida: Tarifa plana
* Precio: Precio de la tasa de mercado o descuento

### Activation

An **[!UICONTROL Activation]** use case lets buyers send data to a [destination](../../../features/destinations/destinations.md). Con este caso de uso, los compradores no pueden comparar datos con un informe superpuesto o en un modelo algorítmico. Precio este caso de uso de la siguiente manera:

* Unit of Measure: [!DNL CPM]
* Price: [!DNL CPM] market rate

## Billing and Price Options {#billing}

Las opciones de facturación y cotización controlan el pago de los datos por parte de los compradores.

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción </th> 
   <th colname="col2" class="entry"> Descripción </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Ciclo de facturación</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> La opción mensual en mora</span></b> es la única opción. El ciclo de facturación termina el día 10 de cada mes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Unidad de medida</span></b> </td> 
   <td colname="col2">Cobrar compradores de datos en una tasa CPM o tarifa plana. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Con los precios CPM, los compradores de datos son necesarios para el uso de informes propios. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Al calcular precios por tarifa plana, los compradores de datos no registran el uso porque se les cobró una tasa fija. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Precio</span></b> </td>
   <td colname="col2"> Cantidad que un vendedor cobra al comprador como tasa CPM o precio de tarifa plana, en dólares. </td>
  </tr> 
 </tbody> 
</table>

## Plan Notes {#plan-notes}

In the **[!UICONTROL Additional Notes]** field, take some time to describe each data plan in a feed. Una descripción adecuada ayuda a los compradores a comprender el contenido o el propósito de cada plan en una fuente de datos. Los compradores pueden leer fuentes de datos y descripciones de planes a medida que buscan o evalúan nuevas fuentes de datos.

## Manage Private Data Feed Requests {#manage-private-requests}

Flujos de trabajo del proveedor para administrar solicitudes de fuente privada de compradores.

To review, approve, or reject buyer requests, go to [!UICONTROL My Shared Data] and:

<!-- t_private_feed_workflows.xml -->

1. Haga clic en el nombre de la fuente de datos privada.
2. Click **[!UICONTROL Access Requests]** to review all the buyers who want access to your data feed.
3. In the [!UICONTROL Allow Access] section of each request box, click the check mark to approve a request or the X to deny access.
4. Confirme o cancele la acción seleccionada en la ventana emergente de confirmación.

>[!MORE_ LIKE_ THIS]
>
>* [Fuentes de datos privadas](../../../features/audience-marketplace/marketplace-private-feeds.md)


## Discounts for Data Providers {#discounts}

In [!UICONTROL Audience Marketplace], discounts let you reduce the published price of a data feed for individual subscribers. Puede ofrecer descuentos a los suscriptores que han enviado una solicitud de suscripción o a suscriptores que han solicitado detalles sobre una fuente de datos. Discounts apply to [!DNL CPM] and flat rate feeds. Los descuentos pueden resultar útiles cuando se desea proporcionar incentivos de suscripción para nuevos clientes o para recompensar la lealtad del cliente.

## Apply Discounts to a Data Feed {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Para descuento en una fuente, agregue un descuento de descuento de % al campo de descuento y confirme los cambios. Data providers can discount a data feeds in [!UICONTROL Audience Marketplace] from either:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In these examples, the seller has added 10% discount to the [!UICONTROL Software Audience] data feed.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Review Discounted Feeds {#review-discounted-feeds}

Data providers can see all of their subscribers and discounted feeds in **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)