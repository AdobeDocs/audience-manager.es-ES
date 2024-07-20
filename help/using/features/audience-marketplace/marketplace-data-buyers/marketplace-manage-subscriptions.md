---
description: En Marketplace, los compradores de datos acceden a la investigación y se suscriben a fuentes de datos públicas y privadas. Siga estos pasos para suscribirse a una fuente de datos pública.
seo-description: The Marketplace is where data buyers go to research and subscribe to public and private data feeds. Follow these steps to subscribe to a public data feed.
seo-title: Manage Data Feed Subscriptions
solution: Audience Manager
title: Administrar suscripciones a fuentes de datos
uuid: 7305adb6-cbb8-4430-8204-2243095c0ba5
feature: Audience Marketplace
exl-id: 171acbbc-88ab-496f-93ea-48956325d8fd
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '2159'
ht-degree: 0%

---

# Administrar suscripciones a fuentes de datos {#manage-data-feed-subscriptions}

En [!UICONTROL Marketplace] es donde los compradores de datos van a buscar y suscribirse a fuentes de datos públicas y privadas. Siga estos pasos para suscribirse a una fuente de datos pública.

## Suscripción a una fuente de datos pública {#subscript-public-data-feed}

En [!UICONTROL Marketplace] es donde los compradores de datos van a buscar y suscribirse a fuentes de datos públicas y privadas. Siga estos pasos para suscribirse a una fuente de datos pública.

<!-- t_subscribe_feed.xml -->

Para suscribirse a una fuente de datos pública:

1. Ir a **[!UICONTROL Audience Marketplace > Marketplace]**. Utilice la función de búsqueda o examine la lista para encontrar una fuente de datos.

   ![suscribirse](assets/subscribe1.png)

1. Haga clic en el nombre de la fuente de datos que desee utilizar. Se abre la [página de detalles del plan](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details) de la fuente seleccionada.

   ![detalles del plan](assets/plan-details.png)

1. Elija un caso de uso de la tabla de suscripciones y:
   * Mover el control deslizante **[!UICONTROL Subscription]** a **[!UICONTROL On]**.
   * Haga clic en **[!UICONTROL Review & Subscribe]**. Se abrirá la ventana [!UICONTROL Terms and Conditions].

   ![suscribirse](assets/subscribe3.png)

1. En la ventana [!UICONTROL Terms and Conditions]:

   * **Importante:** Deje activada la casilla de verificación **[!UICONTROL ID sync]**. Esta configuración ayuda a mejorar las tasas de coincidencia con su proveedor de datos.
   * Marque la casilla de verificación Términos y condiciones y haga clic en **[!UICONTROL Accept]** para completar el proceso de suscripción.

   ![suscribirse](assets/subscribe4.png)

### Pasos siguientes

Después de suscribirse a una fuente de datos:

* Compruebe la suscripción comprobando su carpeta [!UICONTROL Traits]. Ver [Almacenamiento de fuentes de datos suscritas](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee).

* Revise la documentación de facturación y pago. Consulte los vínculos relacionados a continuación.

### Prácticas recomendadas {#best-practices}

Este es un conjunto de prácticas recomendadas que le recomendamos que siga al trabajar con [!UICONTROL Audience Marketplace]:

Al explorar nuevos conjuntos de datos de terceros y de segundo nivel a través de [!UICONTROL Audience Marketplace], el primer paso que recomendamos es habilitar las fuentes de datos para [!UICONTROL Segments & Overlap]. Esto permite a los usuarios explorar datos mediante la creación de segmentos para evaluar el tamaño de la audiencia y la ejecución de informes de superposición para obtener perspectivas de audiencia iniciales. La mayoría de los proveedores de datos ofrecen este caso de uso de forma gratuita, por lo que puede realizar este análisis sin coste adicional.

Cuando ejecute informes de superposición, siga estas prácticas recomendadas para asegurarse de que obtiene resultados útiles.

1. Asegúrese de que los conjuntos de datos superpuestos sean similares en términos de tipo de datos y metodologías de recopilación, como:
   * Geografía del visitante
   * Cookie e ID de móviles
   * Ventana retroactiva
   * Actividad sin conexión frente a en línea
   * Frecuencia con la que el proveedor de datos actualiza los datos

1. La superposición puede crecer ligeramente con el tiempo, por lo que debe asegurarse de dejar que transcurran hasta 30 días antes de ejecutar los informes de superposición para que se puedan sincronizar los datos.
1. La superposición puede aumentar si utiliza datos de un proveedor de datos en varias campañas de marketing.
e iniciativas. Esto ofrece más oportunidades para que los usuarios de los dos conjuntos de datos se sincronicen.
1. No hay garantías de que haya una superposición entre los conjuntos de datos. Para que una superposición sea válida, un usuario del conjunto de datos del cliente debe estar asociado a los datos
conjunto de datos del proveedor durante el lapso de tiempo del sistema de informes. Si los datos de medios del cliente no se entregaron a los usuarios en el conjunto de datos del proveedor de datos, nunca habrá una superposición.
1. No piense en la superposición baja como algo malo. Aproveche una baja superposición para atraer a nuevos usuarios.

## Suscripción a una fuente de datos privada {#subscript-private-data-feed}

Los compradores se suscriben a fuentes de datos y planes privados en **[!UICONTROL Audience Marketplace > Marketplace]**.

<!-- t_private_feed.xml -->

>[!TIP]
>
>A veces, los proveedores de datos pueden ofrecer un descuento en una fuente de datos privada. Es posible que quiera preguntar sobre un posible descuento al enviar su solicitud de suscripción.

Para suscribirse a una fuente de datos privada:

1. Haga clic en el nombre de la fuente de datos en [!UICONTROL Marketplace].
1. Haga clic en **[!UICONTROL Request Access]**. Se abrirá el cuadro de diálogo de la solicitud.
1. En el cuadro de diálogo de solicitud, escriba al proveedor una nota en la que exprese su interés en la fuente de datos y haga clic en **[!UICONTROL Send]**. El vendedor revisará tu mensaje y aprobará o rechazará tu solicitud. Mientras se espera la aprobación, aparece &quot;Solicitado&quot; en la lista [!UICONTROL Marketplace] de esa fuente de datos.

   * **[!UICONTROL Request approved]**: el estado de la lista [!UICONTROL Marketplace] cambia a &quot;Acceso concedido&quot; y recibirá una notificación automatizada. En este punto, puede suscribirse a la fuente. Consulte [Suscribirse a una fuente de datos pública](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-public-data-feed) para obtener instrucciones.
   * **[!UICONTROL Request denied]**: el texto &quot;Solicitado&quot; se quita de la lista [!UICONTROL Marketplace] de la fuente. Puede intentar suscribirse de nuevo o elegir una fuente diferente.

## Descuentos de fuentes de datos para compradores {#buyer-discount}

En [!UICONTROL Audience Marketplace], los proveedores pueden ofrecer a los compradores un descuento en el precio publicado de una fuente de datos de [!DNL CPM] o de tarifa plana. Sin embargo, los compradores de la lista de fuentes de [!DNL Marketplace] no pueden ver los importes de descuento. Sin embargo, también puede solicitar un descuento al suscribirse a una fuente de datos privada o al solicitar más información sobre una fuente en particular.

## Solicitar un descuento {#request-discount}

<!-- marketplace-buyer-discounts.xml -->

<table id="table_3C6E58F593BA48EC89ACBD9A26E4E74F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Estado del comprador </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Suscriptores actuales</b> </p> </td> 
   <td colname="col2"> <p>Si ya está suscrito a una fuente de datos privada y desea solicitar un descuento: </p> 
    <ol id="ol_A58D419EBB9349E9B1225202535130F6"> 
     <li id="li_D0DDC8AC6E9C4675AA4630D63FE8F071"> <a href="../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#unsubscribe"> canceló la suscripción de </a> a la fuente de datos. </li> 
     <li id="li_05A5379F2A944FB28AB39C196DDE3A1D">Póngase en contacto con el proveedor de datos y solicite un precio con descuento. </li> 
     <li id="li_B1B5AA6F6CC64512A02D5E8861A5F266">Si el proveedor le ofrece un descuento, vuelva a suscribirse a la fuente el día 1<sup>st</sup> del mes siguiente. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Nuevos suscriptores de fuentes de datos privadas</b> </p> </td> 
   <td colname="col2"> <p>Pida un descuento en su solicitud de suscripción. Ver <a href="../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed"> suscribirse a una fuente de datos privada</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Suscriptores potenciales</b> </p> </td> 
   <td colname="col2"> <p>Un <a href="../../../features/audience-marketplace/marketplace-private-feeds.md"> posible suscriptor</a> es un comprador de datos que ha solicitado acceso a una fuente de datos privada, que recibió la aprobación del vendedor, pero que no se ha suscrito a la fuente. Para solicitar un descuento como suscriptor potencial: </p> 
    <ol id="ol_9CECDA92E7894B20AC8A777D78962188"> 
     <li id="li_618B64160CF24549AFCA73E006DCA35A">Vaya a <b><span class="uicontrol"> Audience Marketplace &gt; Marketplace</span></b>. </li> 
     <li id="li_FE52A06B30FC4858B48AF81954365FE9">Haga clic en el nombre de la fuente para la que se le ha aprobado. </li> 
     <li id="li_763C050AC9464BE380D00F6085B6E540">Haga clic en <b><span class="uicontrol"> para solicitar más detalles</span></b>. Solicita un descuento en tu solicitud de datos al vendedor. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

## Revisar fuentes con descuento {#review-discounted-feeds}

Para revisar las fuentes con descuento:

1. Ir a **[!UICONTROL Audience Marketplace > Marketplace]**.
1. Haga clic en el nombre de una fuente a la que ya esté suscrito.
1. Observe las columnas [!UICONTROL Price] y [!UICONTROL Your Price] de la tabla [!UICONTROL Plan Details]. Si se descuenta la fuente:

   * El precio original está marcado con una línea roja.
   * La tarifa de la columna [!UICONTROL Your Price] será inferior a la tarifa de la columna [!UICONTROL Price].

En el ejemplo, el comprador obtiene un descuento del 10% en el plan [!UICONTROL Segments and Overlap] del **[!UICONTROL Software Audience Feed]**.

![](assets/buyer-discount.png)

## Búsqueda de datos de fuentes suscritas {#find-subscribed-data-fee}

Los datos (características) de las fuentes de datos aparecen en sus propias carpetas de almacenamiento de características. Vaya a **[!UICONTROL Audience Data > Traits]** y expanda la carpeta **[!UICONTROL 3rd-Party Data]** para ver y trabajar con las características de las fuentes suscritas. Busque la subcarpeta con el nombre de su proveedor de datos. Contienen carpetas con nombres basados en las características de lista y fuente de datos individuales que proporciona la fuente.

<!-- marketplace-feed-storage.xml -->

![](assets/subscribe5.png)

## Cancelar la suscripción a una fuente de datos {#unsubscribe}

Los compradores de datos cancelan la suscripción a fuentes de datos y planes en **[!UICONTROL Audience Marketplace > Marketplace]**.

<!-- t_unsubscribe_feed.xml -->

Para cancelar la suscripción a una fuente de datos:

1. Haga clic en el nombre de la fuente de datos en [!UICONTROL Marketplace].
1. En la sección [!UICONTROL Use Case], busque el plan que desea usar y mueva el control deslizante **[!UICONTROL Subscription]** a **[!UICONTROL Off]**.

## Desactivación de fuentes de datos: por qué ocurre y cómo responder {#data-feed-deactivation-reasons}

En [!UICONTROL Audience Marketplace], los proveedores de datos pueden revocar el acceso a las fuentes de datos suscritas. No te alarmes si esto te pasa a ti. Te tenemos a cubierto. Lea esta sección para ver los procesos y procedimientos relacionados con las desactivaciones de fuentes de datos.

## Razones comunes para la desactivación de fuentes de datos {#reasons-for-deactivation}

<!-- marketplace-subscriber-deactivated.xml -->

Puede resultar confuso o incluso molesto si una fuente a la que se suscribe se desactiva. Sin embargo, los proveedores de datos pueden desactivar una fuente de datos por varios motivos. Algunas razones comunes incluyen:

* **Facturación:** Los proveedores de datos desactivarán una fuente si el cliente se retrasa constantemente en el pago de las tarifas o si no paga las tarifas.
* **Actualizaciones de fuentes:** Los proveedores de datos deben desactivar las fuentes cuando actualicen su taxonomía de fuentes o las estructuras de costos.
* **Compradores inactivos:** Los proveedores de datos se reservan el derecho de desactivar las fuentes si los suscriptores no gastan durante un período de tiempo prolongado.
* **Vendedores inactivos:** Los proveedores de datos que dejen [!UICONTROL Audience Marketplace] desactivarán y eliminarán todas sus fuentes de datos.

>[!TIP]
>
>Póngase en contacto directamente con el proveedor de datos si cree que una fuente de datos se desactivó por error. Su asesor de [!DNL Adobe] puede ayudarle con información de contacto o soporte técnico adicional.

## Correo electrónico de desactivación {#deactivation-email}

Cuando un proveedor de datos desactiva una de las fuentes de datos, [!DNL Audience Manager] envía un correo electrónico a los usuarios de la empresa que tienen permisos para [!UICONTROL Administrator]. A veces, los filtros de correo electrónico clasifican este mensaje como correo no deseado. Como resultado, es posible que se pierda esta notificación importante. Para ayudarle a identificar el mensaje de desactivación, este correo electrónico contiene los siguientes elementos:

* **De:** El correo electrónico de desactivación procede de `aam-noreply@adobe.com`. Consejo: No responda a este correo electrónico.

* **Línea de asunto:** La suscripción a *nombre de la fuente de datos aquí* está cancelada.

* **Archivos adjuntos:** El correo electrónico incluye un archivo adjunto con el título &quot;`list-of-affected-entities-by-feed-revocation.csv`&quot;. Es una forma enrevesada de decir que el archivo adjunto enumera todos los rasgos incluidos en la fuente cancelada. Como comprador de datos, debes revisar este archivo adjunto. Le ayudará a encontrar y eliminar características desactivadas de sus segmentos y [modelos algorítmicos](../../../features/algorithmic-models/understanding-models.md).

## Lista de rasgos desactivada {#deactivation-trait-list}

La lista que acompaña al correo electrónico de desactivación contiene los campos como se muestra a continuación.

<table id="table_5C3800F9D8AA43EFAB4690959A721F63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> ID de fuente de datos</span></b> </p> </td> 
   <td colname="col2"> <p>ID de la fuente de datos desactivada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nombre de fuente de datos</span></b> </p> </td> 
   <td colname="col2"> <p>Nombre de la fuente de datos desactivada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> SID de rasgo</span></b> </p> </td> 
   <td colname="col2"> <p>ID de rasgos desactivados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nombre de característica</span></b> </p> </td> 
   <td colname="col2"> <p>Nombres de rasgos desactivados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> SID de segmento</span></b> </p> </td> 
   <td colname="col2"> <p>ID del segmento que contiene características desactivadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nombre de segmento</span></b> </p> </td> 
   <td colname="col2"> <p>Nombre del segmento que contiene características desactivadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> ID. de modelo de algoritmo </span></b> </p> </td> 
   <td colname="col2"> <p>El ID del modelo algorítmico que contiene rasgos desactivados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> nombre de modelo de algoritmo</span></b> </p> </td> 
   <td colname="col2"> <p>Nombres de modelos algorítmicos que contienen características desactivadas. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Eliminar rasgos desactivados {#remove-deactivated-traits}

Como comprador de datos, eres responsable de eliminar los rasgos de una fuente cancelada de todos tus segmentos activos, en uso o inactivos. Las opciones de eliminación incluyen:

* Eliminación en lotes con [las API de REST](../../../api/rest-api-main/rest-api-main.md) o [las herramientas de administración en lotes](../../../reference/bulk-management-tools/bulk-management-intro.md).

* Busque manualmente los segmentos afectados y elimine los rasgos desactivados usando [!UICONTROL Segment Builder]. Consulte [Quitar características de un segmento](../../../features/segments/segment-builder.md#segment-builder-controls-traits).

>[!NOTE]
>
>La eliminación de rasgos de los modelos algorítmicos activos o los destinos afecta a la precisión de escala y segmentación. Intente reemplazar los rasgos revocados por nuevos rasgos activos, si es posible.

[Cancele la suscripción a la fuente de datos desactivada](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#unsubscribe) después de eliminar todos los rasgos revocados de su cuenta. Si se trata de una desactivación temporal, puede volver a suscribirse una vez que el proveedor de datos termine de realizar los cambios necesarios y reactive la fuente. Al igual que con la mayoría de las cosas, una buena comunicación con sus socios (el proveedor de datos y [!DNL Adobe]) puede ayudarle a llevar a cabo este proceso.

## Explicación de la página Detalles del Plan en Audience Marketplace {#marketplace-buyer-details}

Al hacer clic en el nombre de un plan de datos en [!UICONTROL Marketplace], [!DNL Audience Manager] proporciona información que puede ayudarle a tomar decisiones informadas sobre la suscripción a una fuente de datos.

<!-- marketplace-buyer-details.xml -->

![](assets/plan-details-numbered.png)

Esta página le proporciona la siguiente información:

1. **Información básica del plan**. Esto incluye información de fuentes como:
   * Nombre de fuente de datos. Por ejemplo, como se muestra más arriba, el nombre de esta fuente es Fuente de datos de ejemplo.
   * El nombre del proveedor de datos;
   * ID de fuente de datos;
   * Descripción;
   * Número de rasgos de la fuente;

1. Botones de información del plan.
   * Haga clic en **[!UICONTROL Explore All Traits]** para ver los detalles de todas las características de la fuente de datos seleccionada.
   * Haga clic en **[!UICONTROL Request More Details]** para hacer preguntas al proveedor de datos acerca de la fuente de datos seleccionada o para solicitar un descuento. Esta función envía sus comentarios y preguntas directamente al proveedor de datos.

1. Métricas del informe de fuentes de datos. El diagrama de Venn (y las métricas relacionadas) muestran los datos de superposición de características de los últimos 30 días. Consulte [La tienda: Acerca de](marketplace-data-buyers.md#about-marketplace) para obtener más información.
   * **[!UICONTROL 30 Day Overlapped Uniques]**: número de usuarios únicos en su cuenta que se superponen con los usuarios de la cuenta del proveedor. AAM Para ver una definición de usuarios únicos, consulte UUID de la comunidad de usuarios en el [Índice de ID en el Audience Manager](/help/using/reference/ids-in-aam.md).
   * **[!UICONTROL 30 Day Provider Unique Users]**: número de usuarios únicos procedentes de la cuenta del proveedor.
   * **[!UICONTROL Your Unique Users]**: el número de usuarios únicos que provienen de su cuenta.

1. Tabla **[!UICONTROL Plan Details]**. En esta tabla se muestran los casos de uso en los que se puede suscribir a la fuente de datos, así como su modelo de precios. Consulte [Explicación de los casos de uso de fuentes de datos](#use-cases).

1. Botones de Acción del plan.
   * Haga clic en **[!UICONTROL Cancel]** para salir de la página sin realizar cambios.
   * Haga clic en **[!UICONTROL Review & Subscribe]** para suscribirse a una fuente de datos. Este botón aparece atenuado hasta que cambie un elemento [!UICONTROL Subscription] a [!UICONTROL On]. Ver también [Suscribirse a una fuente de datos pública](#subscript-public-data-feed) y [Suscribirse a una fuente de datos privada](#subscript-private-data-feed).

## Explicación de los casos de uso de fuentes de datos {#use-cases}

Como comprador de datos de [!UICONTROL Audience Marketplace], puedes comprar datos para casos de uso de superposición, modelado y activación. Cada caso de uso está diseñado para un propósito específico y limita lo que puede hacer con los datos. Estas descripciones de casos de uso pueden ayudarle a tomar la decisión correcta sobre qué tipo de plan de datos comprar.

## Realizar comparaciones con segmentos y planes de superposición {#comparisons}

<!-- c_use_cases_for_buyers.xml -->

### Segmentos y superposición

Este caso de uso le permite comparar sus rasgos con los del proveedor en un informe de superposición de [rasgos a rasgos.](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report) Además, puede crear o agregar características de proveedor a un segmento y realizar comparaciones adicionales con los informes [segmento a característica](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) y [segmento a segmento](../../../reporting/dynamic-reports/segment-segment-overlap-report.md). Las comparaciones de superposición pueden ayudarle a lo siguiente:

* **Ampliar el alcance de la audiencia:** La baja superposición sugiere que los rasgos contienen usuarios que no ha visto antes. Es posible que desee que estos rasgos intenten llegar a nuevos usuarios.
* **Mejore las audiencias existentes:** La superposición alta sugiere que sus rasgos son similares a los que posee el proveedor de datos. Es posible que desee que estos rasgos ayuden a realizar mejoras direccionales e incrementales en una audiencia ya desarrollada.

### Modelos algorítmicos

Este caso de uso le permite evaluar las características del proveedor en relación con las características con [modelado algorítmico](../../../features/algorithmic-models/understanding-models.md#understanding-models). Por ejemplo, nuestro sistema de modelado algorítmico utiliza uno de sus rasgos como base para la comparación con un rasgo de proveedor. Cuando se ejecuta el modelo, puede mostrar si las audiencias de características del proveedor comparten atributos de conversión similares a los de las características.

### Activación

Este caso de uso le permite enviar datos a un [destino](../../../features/destinations/destinations.md). En [!DNL Audience Manager], un destino es cualquier sistema de terceros (servidor de publicidad, [!DNL DSP], [!DNL DMP], exchange, etc.) con el que se desea compartir datos. Sin embargo, con un caso de uso de [!UICONTROL Activation], no se pueden ejecutar informes de superposición ni probar los datos en un modelo algorítmico.

>[!MORELIKETHIS]
>
>* [Asignación de facturación e impresión para fuentes de datos de CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Asignación de facturación e impresión para fuentes de datos con tarifa plana](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Cómo informar sobre el uso de CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)
>* [Suscribirse a una fuente de datos pública](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-public-data-feed)
>* [Descuentos para compradores de datos](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)
>* [El mercado: alrededor de](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace)
