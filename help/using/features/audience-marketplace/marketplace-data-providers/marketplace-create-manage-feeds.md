---
description: Una fuente de datos requiere un nombre, una descripción, una fuente de datos y un tipo de plan. Las fuentes se desactivan hasta que se guarda y activa. Configure fuentes de datos públicas o privadas en Audience Marketplace > Mis datos compartidos. Disponible solo para vendedores de datos.
seo-description: A data feed requires a name, description, data source, and a plan type. Feeds are disabled until you save and activate the feed. Set up public or private data feeds in Audience Marketplace > My Shared Data. Available to data sellers only.
seo-title: Create, Price, and Manage Data Feeds
solution: Audience Manager
title: Crear, cotizar y administrar fuentes de datos
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
exl-id: e8605e94-e62a-430c-9aef-875f995fb436
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1257'
ht-degree: 2%

---

# Crear, cotizar y administrar fuentes de datos {#create-price-and-manage-data-feeds}

## Crear una fuente de datos pública o privada {#create-public-private-data-feed}

Una fuente de datos requiere un nombre, una descripción, una fuente de datos y un tipo de plan. Las fuentes se desactivan hasta que se guarda y activa. Configuración de fuentes de datos públicas o privadas en **[!UICONTROL Audience Marketplace > My Shared Data]**. Disponible solo para vendedores de datos.

<!-- t_data_feed.xml -->

Debe tener derechos de administrador para crear una fuente de datos pública o privada.
Para crear una fuente de datos:

1. Haga clic **[!UICONTROL New Data Feed]**.
1. Asigne un nombre a la fuente de datos. Los compradores de datos pueden buscar tu fuente basándose en el nombre.
1. Proporcione una breve descripción (máximo de 255 caracteres).

   Una buena descripción debe describir su fuente con precisión. Por ejemplo, puede incluir texto para categorías de marketing, información demográfica y cobertura geográfica (por ejemplo, [!DNL US] o Norteamérica). El texto de descripción se puede buscar y ayuda a los compradores a encontrar o evaluar tu feed. Una buena descripción es una parte importante para atraer suscriptores a la fuente de datos.
1. Seleccione una fuente de datos de la **[!UICONTROL Data Source]** opciones. Las fuentes de datos están limitadas a una sola fuente de datos. No se pueden asignar varias fuentes de datos a la misma fuente de datos.

   >[!IMPORTANT]
   >
   >Cualquier característica actual o futura que pertenezca a esta fuente de datos se compartirá con los compradores de datos como parte de esta fuente.

1. Entrada [!UICONTROL Plan Types], seleccione las opciones que desee utilizar y haga clic en **[!UICONTROL Add Plan]**.

   Las fuentes pueden contener varios planes. Los planes pueden contener varios casos de uso. Para obtener más información, consulte [Tipos de plan para fuentes de datos](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Clic **[!UICONTROL Save]** para guardar la fuente de datos *sin* activándolo.
1. Para guardar y activar una fuente de datos:
   1. Mover el **[!UICONTROL Availability]** deslizador a **[!UICONTROL Active]**.
   1. Haga clic **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* Las fuentes de datos guardadas y activadas no se pueden eliminar.
   >* Los compradores solo ven las fuentes activas.


### Opcional: Crear una fuente de datos privada

En el [!UICONTROL Settings] , mueva el control deslizante a:

* **[!UICONTROL Private]** y **[!UICONTROL Branded]**: el del comprador [!UICONTROL Marketplace] La lista muestra el nombre del vendedor en la columna proveedor y el resto de los datos están ocultos.

* **[!UICONTROL Private]** y **[!UICONTROL Unbranded]**: el del comprador [!UICONTROL Marketplace] La lista muestra solo el nombre y la descripción de la fuente de datos. El nombre del proveedor de datos aparece como [!UICONTROL Private Seller].

Para ver el aspecto que tiene una fuente privada para los compradores, consulte la sección compradores en [Fuentes de datos privadas](../../../features/audience-marketplace/marketplace-private-feeds.md).

## Desactivar una fuente de datos de un suscriptor {#deactivate-data-feed}

Como un [!UICONTROL Audience Marketplace] del proveedor de datos, puede anular el acceso del comprador a una fuente de datos suscrita. Es posible que desees eliminar a un comprador de una fuente por motivos como pago tardío/impago de comisiones o si utiliza incorrectamente los datos de rasgos.

<!-- marketplace-deactiva4te-subscribers.xml -->

Para revocar un suscriptor:

1. Entrada [!UICONTROL My Shared Data], busque la fuente que utiliza el suscriptor.

   >[!NOTE]
   >
   >Las fuentes de datos con cuentas vencidas se marcan con un icono de triángulo/signo de exclamación.

1. En el [!UICONTROL Subscribers] , haga clic en el número azul que cuenta los suscriptores de esa fuente. Se abrirá la página de detalles de la suscripción.
1. Mover el **[!UICONTROL Subscription]** deslizador a **[!UICONTROL Off]**. Se abrirá una ventana de diálogo de confirmación.
1. En el [!UICONTROL Confirmation] haga clic en **[!UICONTROL Yes]** para desactivar una suscripción o **[!UICONTROL Cancel]** para salir sin realizar cambios de suscripción.

### Qué Sucede Después de Desactivar un Suscriptor

Si se deniega el acceso a una fuente de datos, se enviará un correo electrónico de notificación a todos los usuarios administradores de la cuenta del comprador de datos. El correo electrónico incluye un archivo adjunto que enumera los rasgos revocados. Esta lista ayuda a los suscriptores a encontrar y eliminar rasgos desactivados de sus segmentos y modelos.

### Facturación y desactivación de fuente

Después de eliminar el acceso a una fuente de datos, los suscriptores son responsables de las tarifas del mes anterior o actual, según el momento en el que desactivó la fuente.

## Tipos de plan para fuentes de datos {#plan-types}

[!DNL Plan types] son componentes esenciales en una [!UICONTROL Audience Marketplace] fuente de datos. Como proveedor de datos, le permiten crear varios casos de uso y opciones de precios para sus fuentes. Además, puede ser una buena estrategia crear algunos planes para cada fuente de datos. Esto ofrece a los compradores diferentes opciones para elegir cuando buscan datos para modelar o enviar a un destino.

[Crear una fuente de datos](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) para seleccionar [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Tipos de planes y opciones de casos de uso {#plan-types-use-cases}

<!-- c_feed_options.xml -->

El [!UICONTROL Use Case] La configuración de permite a los vendedores controlar cómo los compradores pueden usar tus datos.

### Segmentos y superposición

A **[!UICONTROL Segments and Overlap]** caso de uso crea un plan que permite a los compradores comparar los datos de rasgos en una [informe de superposición de rasgos](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Además, los compradores pueden añadir tus datos a los segmentos y hacer comparaciones con el [segmento a característica](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) y [segmento a segmento](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) informes.

Cada fuente de datos debe incluir al menos una [!UICONTROL Segments and Overlap] caso de uso. Los compradores no pueden suscribirse a otros planes en una fuente de datos si esta no contiene [!UICONTROL Segments and Overlap] Caso de uso, ya sea por sí solo o en combinación con otro caso de uso.

Las comparaciones superpuestas pueden ayudar a los compradores a:

* **Ampliar alcance de audiencia:** La superposición baja sugiere que tus rasgos contienen usuarios que el comprador no ha visto antes. Como resultado, es posible que los compradores quieran que estos rasgos añadan nuevos usuarios a sus segmentos de audiencia.
* **Mejore las audiencias existentes:** La superposición alta sugiere que tus rasgos contienen usuarios similares a los que un comprador ya conoce. Como resultado, es posible que los compradores deseen que estos rasgos ayuden a realizar mejoras direccionadas e incrementales en las audiencias desarrolladas.

Valore este caso de uso de la siguiente manera:

* Unidad de medida: tarifa plana
* Precio: Gratis ($0.00)

### Modelado

A **[!UICONTROL Modeling]** caso de uso crea un plan que permite a los compradores comparar tus rasgos con los de ellos [modelado algorítmico](../../../features/algorithmic-models/understanding-models.md#understanding-models). Los compradores ven los resultados del modelo para encontrar nuevas audiencias en sus datos que compartan atributos de conversión similares a los suyos propios. Valore este caso de uso de la siguiente manera:

* Unidad de medida: tarifa plana
* Precio: Precio con descuento o a tipo de mercado

### Activación

Un **[!UICONTROL Activation]** caso de uso permite a los compradores enviar datos a un [destino](../../../features/destinations/destinations.md). Con este caso de uso, los compradores no pueden comparar los datos con un informe de superposición o un modelo algorítmico. Valore este caso de uso de la siguiente manera:

* Unidad de medida: [!DNL CPM]
* Precio: [!DNL CPM] tipo de mercado

## Opciones de facturación y precio {#billing}

Las opciones de facturación y precio controlan el modo en que los compradores pagan por tus datos.

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
   <td colname="col2"> <b><span class="uicontrol"> Mensual en atrasos</span></b> es la única opción. El ciclo de facturación finaliza el día 10 de cada mes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Unidad de medida</span></b> </td> 
   <td colname="col2">Cobra a los compradores de datos una tarifa CPM o una tarifa plana. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Con los precios de CPM, los compradores de datos deben informar sobre el uso de forma automática. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Con un precio fijo, los compradores de datos no informan del uso porque se les cobra una tarifa fija. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Precio</span></b> </td>
   <td colname="col2"> El importe que un vendedor cobra al comprador como tarifa CPM o precio fijo de la tarifa, en dólares. </td>
  </tr> 
 </tbody> 
</table>

## Notas del plan {#plan-notes}

En el **[!UICONTROL Additional Notes]** , dedique un poco de tiempo a describir cada plan de datos en una fuente. Una descripción breve y correcta ayuda a los compradores a comprender el contenido o el propósito de cada plan de una fuente de datos. Los compradores pueden leer las descripciones de las fuentes de datos y los planes a medida que buscan o evalúan nuevas fuentes de datos.

## Administrar solicitudes de fuentes de datos privadas {#manage-private-requests}

Flujos de trabajo del proveedor para gestionar solicitudes de fuentes privadas de compradores.

Para revisar, aprobar o rechazar solicitudes de compradores, ve a [!UICONTROL My Shared Data] y:

<!-- t_private_feed_workflows.xml -->

1. Haga clic en el nombre de la fuente de datos privada.
2. Clic **[!UICONTROL Access Requests]** para revisar todos los compradores que quieran acceder a tu fuente de datos.
3. En el [!UICONTROL Allow Access] de cada cuadro de solicitud, haga clic en la marca de verificación para aprobar una solicitud o en la X para denegar el acceso.
4. Confirme o cancele la acción seleccionada en el elemento emergente de confirmación.

## Descuentos para proveedores de datos {#discounts}

Entrada [!UICONTROL Audience Marketplace], los descuentos le permiten reducir el precio publicado de una fuente de datos para suscriptores individuales. Puede ofrecer descuentos a los suscriptores que hayan enviado una solicitud de suscripción o a los suscriptores que hayan solicitado detalles sobre una fuente de datos. Se aplican descuentos a [!DNL CPM] y fuentes de tarifa plana. Los descuentos pueden ser útiles cuando desea ofrecer incentivos de suscripción para nuevos clientes o para recompensar la lealtad del cliente.

## Aplicar descuentos a una fuente de datos {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Para aplicar un descuento a una fuente, añada un importe de descuento como % al campo de descuento y confirme los cambios. Los proveedores de datos pueden descontar las fuentes de datos en [!UICONTROL Audience Marketplace] de:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

En estos ejemplos, el vendedor ha agregado un 10% de descuento a la [!UICONTROL Software Audience] fuente de datos.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Revisar fuentes con descuento {#review-discounted-feeds}

Los proveedores de datos pueden ver todos sus suscriptores y fuentes con descuento en **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [Fuentes de datos privadas](../../../features/audience-marketplace/marketplace-private-feeds.md)

