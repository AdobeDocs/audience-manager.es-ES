---
description: Una fuente de datos requiere un nombre, una descripción, una fuente de datos y un tipo de plan. Las fuentes se desactivan hasta que se guarda y activa la fuente. Configure fuentes de datos públicas o privadas en Audience Marketplace > Mis datos compartidos. Disponible solo para vendedores de datos.
seo-description: Una fuente de datos requiere un nombre, una descripción, una fuente de datos y un tipo de plan. Las fuentes se desactivan hasta que se guarda y activa la fuente. Configure fuentes de datos públicas o privadas en Audience Marketplace > Mis datos compartidos. Disponible solo para vendedores de datos.
seo-title: Crear, cotizar y administrar fuentes de datos
solution: Audience Manager
title: Crear, cotizar y administrar fuentes de datos
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
exl-id: e8605e94-e62a-430c-9aef-875f995fb436
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 2%

---

# Crear, cotizar y administrar fuentes de datos {#create-price-and-manage-data-feeds}

## Crear una fuente de datos pública o privada {#create-public-private-data-feed}

Una fuente de datos requiere un nombre, una descripción, una fuente de datos y un tipo de plan. Las fuentes se desactivan hasta que se guarda y activa la fuente. Configure fuentes de datos públicas o privadas en **[!UICONTROL Audience Marketplace > My Shared Data]**. Disponible solo para vendedores de datos.

<!-- t_data_feed.xml -->

Debe tener derechos de administrador para crear una fuente de datos pública o privada.
Para crear una fuente de datos:

1. Haga clic **[!UICONTROL New Data Feed]**.
1. Asigne un nombre a la fuente de datos. Los compradores de datos pueden buscar la fuente en función del nombre.
1. Proporcione una breve descripción (un máximo de 255 caracteres).

   Una buena descripción debería describir su fuente con precisión. Por ejemplo, puede incluir texto para categorías de marketing, demografía y cobertura geográfica (por ejemplo, [!DNL US] o Norteamérica). El texto de la descripción se puede buscar y ayuda a los compradores a encontrar o evaluar su fuente. Una buena descripción es una parte importante para atraer suscriptores a su fuente de datos.
1. Seleccione una fuente de datos en las opciones **[!UICONTROL Data Source]** . Las fuentes de datos están limitadas a una única fuente de datos. No se pueden asignar varias fuentes de datos a la misma fuente de datos.

   >[!IMPORTANT]
   >
   >Los rasgos actuales y futuros que pertenezcan a esta fuente de datos se compartirán con los compradores de datos como parte de esta fuente.

1. En [!UICONTROL Plan Types], seleccione las opciones que desee utilizar y haga clic en **[!UICONTROL Add Plan]**.

   Las fuentes pueden contener varios planes. Los planes pueden contener varios casos de uso. Para obtener más información, consulte [Tipos de plan para fuentes de datos](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Haga clic en **[!UICONTROL Save]** para guardar la fuente de datos *sin* activarla.
1. Para guardar y activar una fuente de datos:
   1. Mueva el control deslizante **[!UICONTROL Availability]** a **[!UICONTROL Active]**.
   1. Haga clic **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* Las fuentes de datos guardadas y activadas no se pueden eliminar.
   >* Los compradores solo ven las fuentes activas.


### Opcional: Crear una fuente de datos privada

En la sección [!UICONTROL Settings], mueva el control deslizante a:

* **[!UICONTROL Private]** y  **[!UICONTROL Branded]**: La  [!UICONTROL Marketplace] lista del comprador muestra el nombre del vendedor en la columna del proveedor y todos los demás datos están ocultos.

* **[!UICONTROL Private]** y  **[!UICONTROL Unbranded]**: La  [!UICONTROL Marketplace] lista del comprador muestra únicamente el nombre y la descripción de la fuente de datos. El nombre del proveedor de datos aparece como [!UICONTROL Private Seller].

Para ver el aspecto que tiene una fuente privada para los compradores, consulte la sección compradores en [Fuentes de datos privadas](../../../features/audience-marketplace/marketplace-private-feeds.md).

## Desactivar una fuente de datos de un suscriptor {#deactivate-data-feed}

Como proveedor de datos [!UICONTROL Audience Marketplace], puede revocar el acceso del comprador a una fuente de datos suscrita. Es posible que desee eliminar un comprador de una fuente por motivos como el pago tardío o la falta de pago de las tarifas, o si utilizan datos de características incorrectamente.

<!-- marketplace-deactiva4te-subscribers.xml -->

Para revocar un suscriptor:

1. En [!UICONTROL My Shared Data], busque la fuente que está utilizando el suscriptor.

   >[!NOTE]
   >
   >Las fuentes de datos con cuentas vencidas se marcan con un icono de triángulo/signo de exclamación.

1. En la columna [!UICONTROL Subscribers] , haga clic en el número azul que cuenta los suscriptores de esa fuente. Se abre la página de detalles de la suscripción.
1. Mueva el control deslizante **[!UICONTROL Subscription]** a **[!UICONTROL Off]**. Se abre una ventana del cuadro de diálogo de confirmación.
1. En la ventana emergente [!UICONTROL Confirmation], haga clic en **[!UICONTROL Yes]** para desactivar una suscripción o en **[!UICONTROL Cancel]** para salir sin realizar cambios de suscripción.

### Qué sucede después de desactivar un suscriptor

Al revocar el acceso a una fuente de datos, se envía un mensaje de correo electrónico de notificación a todos los usuarios administradores de la cuenta del comprador de datos. El correo electrónico incluye un archivo adjunto que enumera los rasgos revocados. Esta lista ayuda a los suscriptores a encontrar y eliminar características desactivadas de sus segmentos y modelos.

### Facturación y desactivación de fuentes

Después de eliminar el acceso a una fuente de datos, los suscriptores son responsables de las tarifas del mes anterior o actual, según el momento en que desactive la fuente.

## Tipos de plan para fuentes de datos {#plan-types}

[!DNL Plan types] son componentes esenciales de una fuente de  [!UICONTROL Audience Marketplace] datos. Como proveedor de datos, le permiten crear varios casos de uso y opciones de precio para sus fuentes. Además, puede ser una buena estrategia crear algunos planes para cada fuente de datos. Esto ofrece a los compradores diferentes opciones para elegir entre buscar datos para modelar o enviar a un destino.

[Cree una fuente de datos ](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) para seleccionar  [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Tipos de planes y opciones de casos de uso {#plan-types-use-cases}

<!-- c_feed_options.xml -->

La configuración [!UICONTROL Use Case] permite a los vendedores controlar cómo los compradores pueden utilizar sus datos.

### Segmentos y superposición

Un caso de uso **[!UICONTROL Segments and Overlap]** crea un plan que permite a los compradores comparar los datos de características en un [informe de superposición de características](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Además, los compradores pueden agregar sus datos a segmentos y realizar comparaciones con los informes [segmento a rasgo](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) y [segmento a segmento](../../../reporting/dynamic-reports/segment-segment-overlap-report.md).

Cada fuente de datos debe incluir al menos un [!UICONTROL Segments and Overlap] caso de uso. Los compradores no pueden suscribirse a otros planes de una fuente de datos si la fuente no contiene un caso de uso [!UICONTROL Segments and Overlap], ya sea por sí solo o en combinación con otro caso de uso.

Las comparaciones de superposición pueden ayudar a los compradores a:

* **Ampliar alcance de la audiencia:**  la superposición baja sugiere que las características contienen usuarios que el comprador no ha visto antes. Como resultado, es posible que los compradores deseen que estos rasgos agreguen nuevos usuarios a sus segmentos de audiencia.
* **Mejorar audiencias existentes:** la superposición alta sugiere que las características contienen usuarios similares a los que ya conoce un comprador. Como resultado, es posible que los compradores deseen que estos rasgos contribuyan a mejorar de forma gradual y con objetivos concretos a las audiencias desarrolladas.

Establezca el precio de este caso de uso como se indica a continuación:

* Unidad de medida: Tarifa plana
* Precio: Gratuito (0,00 dólares)

### Modelado

Un caso de uso **[!UICONTROL Modeling]** crea un plan que permite a los compradores comparar sus rasgos con los de [modelado algorítmico](../../../features/algorithmic-models/understanding-models.md#understanding-models). Los compradores consultan los resultados del modelo para encontrar nuevas audiencias en los datos que compartan atributos de conversión similares con las suyas. Establezca el precio de este caso de uso como se indica a continuación:

* Unidad de medida: Tarifa plana
* Precio: Precio de precio de mercado o descuento

### Activation

Un caso de uso **[!UICONTROL Activation]** permite que los compradores envíen datos a un [destino](../../../features/destinations/destinations.md). Con este caso de uso, los compradores no pueden comparar los datos con un informe de superposición o en un modelo algorítmico. Establezca el precio de este caso de uso como se indica a continuación:

* Unidad de medida: [!DNL CPM]
* Precio: [!DNL CPM] tasa de mercado

## Opciones de facturación y precio {#billing}

Las opciones de facturación y precio controlan cómo pagan los compradores sus datos.

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
   <td colname="col2"> <b><span class="uicontrol"> Mensualmente en </span></b> Arresis es la única opción. El ciclo de facturación finaliza el décimo día de cada mes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Unidad de medida</span></b> </td> 
   <td colname="col2">Cobrar a los compradores de datos una tarifa CPM o una tarifa fija. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Con los precios de CPM, los compradores de datos deben informar sobre el uso. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Con el precio de tarifa fija, los compradores de datos no informan del uso porque se les cobra una tasa fija. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Precio</span></b> </td>
   <td colname="col2"> La cantidad que un vendedor cobra al comprador como tasa CPM o precio de tarifa fija, en dólares. </td>
  </tr> 
 </tbody> 
</table>

## Notas del plan {#plan-notes}

En el campo **[!UICONTROL Additional Notes]**, dedique un tiempo a describir cada plan de datos en una fuente. Una descripción breve y buena ayuda a los compradores a comprender el contenido o el propósito de cada plan en una fuente de datos. Los compradores pueden leer fuentes de datos y planificar descripciones a medida que buscan o evalúan nuevas fuentes de datos.

## Administrar solicitudes de fuentes de datos privadas {#manage-private-requests}

Flujos de trabajo del proveedor para administrar solicitudes de fuentes privadas de compradores.

Para revisar, aprobar o rechazar solicitudes de comprador, vaya a [!UICONTROL My Shared Data] y:

<!-- t_private_feed_workflows.xml -->

1. Haga clic en el nombre de la fuente de datos privada.
2. Haga clic en **[!UICONTROL Access Requests]** para revisar todos los compradores que desean acceder a su fuente de datos.
3. En la sección [!UICONTROL Allow Access] de cada cuadro de solicitud, haga clic en la marca de verificación para aprobar una solicitud o en la X para denegar el acceso.
4. Confirme o cancele la acción seleccionada en la ventana emergente de confirmación.

## Descuentos para proveedores de datos {#discounts}

En [!UICONTROL Audience Marketplace], los descuentos le permiten reducir el precio publicado de una fuente de datos para suscriptores individuales. Puede ofrecer descuentos a los suscriptores que hayan enviado una solicitud de suscripción o a los suscriptores que hayan solicitado detalles sobre una fuente de datos. Los descuentos se aplican a las fuentes de [!DNL CPM] y a las fuentes de tasa plana. Los descuentos pueden ser útiles cuando desea proporcionar incentivos de suscripción para nuevos clientes o para premiar la lealtad del cliente.

## Aplicar descuentos a una fuente de datos {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Para descontar una fuente, añada una cantidad de descuento como % al campo de descuento y confirme los cambios. Los proveedores de datos pueden descontar una fuente de datos en [!UICONTROL Audience Marketplace] desde:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

En estos ejemplos, el vendedor ha añadido un 10 % de descuento a la fuente de datos [!UICONTROL Software Audience].

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Revisar fuentes con descuento {#review-discounted-feeds}

Los proveedores de datos pueden ver todos sus suscriptores y fuentes con descuento en **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [Fuentes de datos privadas](../../../features/audience-marketplace/marketplace-private-feeds.md)

