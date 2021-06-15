---
description: Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de la funcionalidad de inclusión y a través de la Transparencia IAB y el Marco de consentimiento (TCF). En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager.
seo-description: Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de la funcionalidad de inclusión y a través de la Transparencia IAB y el Marco de consentimiento (TCF). En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager.
seo-title: Complemento de Audience Manager para el TCF de IAB
solution: Audience Manager
title: Complemento de Audience Manager para el TCF de IAB
feature: Administración de datos y privacidad
exl-id: aa6bc415-e52b-4900-951d-ccf51d907aa2
source-git-commit: 8fc6c96bf9e8216ef4458989c87f1f93ea9f0347
workflow-type: tm+mt
source-wordcount: '2441'
ht-degree: 40%

---

# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Información general

Un aspecto importante de las obligaciones de privacidad que puede tener con respecto a los usuarios es la adquisición y transmisión de las opciones del usuario sobre cómo se pueden utilizar sus datos personales (es decir, &quot;motivos&quot;) y quién (es decir, &quot;empresas&quot;).

Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de la [funcionalidad de inclusión](https://docs.adobe.com/content/help/es-ES/id-service/using/implementation/opt-in-service/optin-overview.html) y a través de la [Transparencia IAB y el Marco de consentimiento (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager.

>[!IMPORTANT]
>
>El Audience Manager está registrado en el [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) con el ID de proveedor 565.

El complemento de Audience Manager para el TCF de IAB utiliza la [funcionalidad de inclusión](https://docs.adobe.com/content/help/es-ES/id-service/using/implementation/opt-in-service/iab.html), que a su vez forma parte de la biblioteca de [del servicio de identidad de Adobe Experience Platform (ECID)](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html).

## Alcance y limitaciones {#scope-and-limitations}

Como editor o anunciante que trabaja con Audience Manager, puede transmitir las opciones de usuario a Audience Manager según el TCF de IAB.

>[!IMPORTANT]
>
>Los reglamentos del TCF de la IAB se aplican únicamente a los visitantes situados en el Espacio Económico Europeo.

Audience Manager le ayuda a respetar las opciones de privacidad de los usuarios y también le proporciona una manera fácil de comunicar estas opciones a todos los socios con los que trabaje.

Actualmente, Audience Manager no admite:

* Flujos de trabajo de dispositivos móviles;
* Añadir consentimiento para las exportaciones de segmentos.

## Actualizando a [!DNL IAB TCF v2.0] {#upgrading}

Los clientes que actualicen su implementación [!DNL Audience Manager Plug-in for IAB TCF] de [!DNL IAB TCF] v1.1 a [!DNL IAB TCF] v2.0, o que habiliten [!DNL IAB TCF] v2.0 por primera vez, deben seguir las mismas directrices sobre requisitos previos e implementación que se describen a continuación.

## Requisitos previos {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager es compatible con IAB TCF v2.0.
>
>La compatibilidad con IAB TCF v1.1 finalizará el 15 de agosto de 2020.
>
> Los clientes que deseen seguir utilizando el complemento de Audience Manager para IAB TCF para la administración de consentimiento deben actualizar a la versión más reciente de [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) para obtener asistencia.
>
> Después de actualizar a la última versión de [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases), las cadenas de consentimiento TCF v1.1 de IAB ya no serán compatibles, por lo que asegúrese de actualizar su CMP antes de actualizar a la última versión de ECID.

Debe cumplir los siguientes requisitos previos para utilizar el complemento Audience Manager para IAB TCF con Audience Manager:

1. Debe utilizar el servicio de identidad de Adobe Experience Platform (ECID) en su versión 5 o una posterior. [Descargar](https://github.com/Adobe-Marketing-Cloud/id-service/releases) la última versión de ECID.
2. Debe utilizar el Audience Manager [!DNL Data Integration Library] (DIL) versión 9.0 o posterior, descargable desde [aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases). Obtenga información sobre [DIL en la documentación de Audience Manager](../../dil/dil-overview.md). Se recomienda utilizar [Adobe Launch](https://docs.adobe.com/content/help/es-ES/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html) para la implementación de DIL más sencilla para Audience Manager.
3. Alternativamente, si utiliza [!DNL Server-Side Forwarding] (SSF) para importar datos a Audience Manager, debe actualizar a la última versión de AppMeasurement. Descargue AppMeasurement con el [Administrador de códigos Analytics](https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/code-manager-admin.html).
4. Debe utilizar una plataforma de administración de consentimiento (CMP), ya sea comercial o propia, que esté integrada con IAB TCF v2.0 y esté registrada en el TCF de IAB. Consulte la lista de [CMP registradas en el marco de IAB](https://iabeurope.eu/cmp-list/).

>[!WARNING]
>
>Si utiliza una plataforma de administración de consentimiento (CMP) que no sea compatible con IAB TCF v.2.0, el Audience Manager enviará automáticamente el parámetro `gdpr=0` en las sincronizaciones de ID, incluso si los visitantes están en la Unión Europea. Para determinar si la validación del RGPD está activa, le recomendamos que confirme con su Plataforma de administración de consentimiento (CMP) que es compatible con IAB TCF v2.0.

## Recomendaciones e implementación {#recommendations}

Para habilitar la asistencia TCF de IAB en Audience Manager, consulte nuestra documentación sobre [cómo configurar IAB con inclusión](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html).

La forma más sencilla de hacerlo es mediante [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html?lang=en) para agregar [!DNL ECID Opt-in] a sus propiedades. Lea la documentación para la [extensión de inclusión de ECID](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html) para saber cómo se configura la extensión de Launch.

## Flujo de trabajo de opciones de usuario si se utiliza el marco de trabajo IAB {#user-choice-workflow}

Si se visita un dominio web, los usuarios pueden proponer sus opciones con respecto a cómo el editor y los proveedores externos con los que trabaja el editor utilizarán sus datos.

Los usuarios proponen sus opciones en forma de *consentimiento* y *interés legítimo* para los propósitos de la IAB a *proveedores de terceros* registrados en la lista global de proveedores.

La siguiente imagen es un ejemplo de un cuadro de diálogo CMP, mostrado en un visitante de un sitio web por primera vez. Tenga en cuenta que este cuadro de diálogo puede tener un aspecto muy diferente, según la aplicación del cliente.

![Cuadro de diálogo CMP](assets/cmp-example.png)

Los detalles sobre los distintos propósitos y permisos incluidos en IAB TCF v2.0 se tratan en las [Políticas del marco de transparencia y consentimiento de IAB Europe](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Los usuarios pueden dar su consentimiento o interés legítimo (si está disponible) para una combinación de propósitos y proveedores. Por ejemplo, los usuarios pueden dar su consentimiento para almacenar información en un dispositivo, desarrollar y mejorar productos y dar su consentimiento a todos los proveedores externos que muestre la CMP.

O, en otro ejemplo, podrían dar su consentimiento o interés legítimo a todos los efectos, pero sólo concederían el consentimiento o el interés legítimo a algunos de los proveedores mostrados por la CP/RP.

Una vez que el usuario selecciona sus opciones de privacidad, las opciones del usuario se registran en la cadena TC de IAB. La cadena TC de IAB almacena la combinación de propósitos y proveedores aprobados, junto con otra información de metadatos (consulte la [página IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) para obtener más información).

Cada proveedor registrado en el TCF de IAB evalúa la cadena de TC de IAB y toma decisiones en función de las opciones de privacidad de los usuarios. Tenga en cuenta que las opciones de privacidad de los usuarios son válidas en todos los proveedores registrados con IAB TCF.

## Finalidades requeridas por el Audience Manager {#aam-standard-purposes}

El Audience Manager evalúa las opciones de los usuarios almacenadas en la cadena TC de IAB para los siguientes fines, definidos en las [Políticas del marco de transparencia y consentimiento de IAB Europe](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions).

* **Objetivo 1**: Almacenar o acceder a información en un dispositivo;
* **Objetivo 10**: Desarrollar y mejorar los productos;
* **Objetivo especial 1**: Asegúrese de la seguridad, evite el fraude y depure.

>[!IMPORTANT]
>
>El Audience Manager necesita consentimiento para las Finalidades 1 y 10, además del consentimiento del proveedor, para poder implementar cookies e iniciar o cumplir sincronizaciones de ID.
>
>De acuerdo con las [regulaciones de IAB](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_), el Objetivo especial 1 (garantizar la seguridad, evitar el fraude y depurar) siempre está aceptado y los usuarios no pueden objetar a él.

## El comportamiento de Audience Manager depende de si el usuario da el consentimiento {#aam-behavior-consent}

El Audience Manager funciona de forma diferente dependiendo de si la cadena TC de IAB incluye el consentimiento del usuario para las dos finalidades (almacenar y/o acceder a la información en un dispositivo, y desarrollar y mejorar productos) o no.

También comprobamos el consentimiento del usuario para todos los destinos con los que trabaje en Audience Manager, siempre que dichos destinos estén registrados en IAB TCF.

| Cuando el usuario *da su consentimiento*, Audience Manager: | Cuando el usuario *rechaza* el consentimiento, Audience Manager: |
|---|---|
| <ul><li>Lleva a cabo todos los casos de uso de Audience Manager que ha solicitado.</li><li>Transmite el consentimiento a terceros en sincronizaciones de ID (pasando `gdpr = 1` y la cadena de consentimiento como `gdpr_consent` en llamadas de sincronización de ID).</li><li>Evalúa y respeta el consentimiento pasado desde los píxeles del servidor de publicidad.</li><li>Respeta las sincronizaciones de ID iniciadas por el socio.</li></ul> | <ul><li>No almacena ningún dato de usuario nuevo en su instancia. Esto incluye ID de socio, señales, rasgos o datos de píxeles.</li><li>No inicia sincronizaciones de ID de terceros.</li><li>No respeta las sincronizaciones de ID iniciadas por el socio.</li><li>Excluye al usuario de una recopilación de datos adicional.</li></ul> |

## Caso de uso del editor {#publisher-use-case}

Al implementar el complemento Audience Manager para TCF de IAB, no es necesario mantener el código personalizado para la administración de consentimiento en las propiedades web a través de un mecanismo diferente con Adobe u otros proveedores de terceros. En la siguiente imagen y los siguientes pasos se describe el caso de uso. Empezar por la izquierda de la imagen:

1. Un usuario visita uno de sus dominios web. Siempre que utilice las versiones más recientes de las bibliotecas ECID y DIL (consulte [Requisitos previos](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), se activa el flujo de inclusión.
2. Audience Manager comprueba si se aplica el flujo IAB (`isIabContext=true`). Consulte [Recomendaciones e implementación](aam-iab-plugin.md#recommendations).
3. El Audience Manager comprueba si se aplica el RGPD (`gdpr = 1`) y si hay un CMP, registrado con IAB TCF, en la propiedad web. Por ejemplo, esto se aplicaría a los usuarios que visiten desde la Unión Europea. Tenga en cuenta que, como editor, es su responsabilidad establecer el indicador del RGPD.
4. Si se aplica el RGPD, el Audience Manager comprueba la cadena TC de IAB, pasada en el parámetro `gdpr_consent`, para obtener el consentimiento necesario. El Audience Manager necesita consentimiento para almacenar o acceder a información en un dispositivo ([IAB TCF Puramente 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), desarrollar y mejorar productos ([IAB TCF Purance 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), además del consentimiento del proveedor Audience Manager para almacenar, procesar o activar datos.
5. Si la cadena TC de IAB está presente y contiene el consentimiento necesario, el Audience Manager pasa la cadena TC de IAB a nuestros [servidores de recopilación de datos](../../reference/system-components/components-data-collection.md) (DCS).
6. El Audience Manager responde configurando una [cookie demdex](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-am.html) en el explorador e inicia y respeta las sincronizaciones de ID de terceros.
7. Alternativamente, si la cadena de TC de IAB pasada en el paso 4 no contiene todos los permisos necesarios, el Audience Manager no recopila, procesa ni activa datos de usuario y no respeta ni inicia sincronizaciones de ID. Además, excluye al usuario de los destinos con los que trabaja.

>[!IMPORTANT]
>
>Si está trabajando con socios de destino de Audience Manager que requieren parámetros TCF de IAB, pero no tiene una CMP compatible con IAB TCF en su sitio web, el Audience Manager envía `gdpr=0` en sincronizaciones de ID. Esto significa que el RGPD no se aplica a esos usuarios.
>
> Si no lo desea, debe habilitar la funcionalidad TCF de IAB en Audience Manager para enviar las cadenas TC de IAB apropiadas a los socios de destino.



![Caso de uso del editor](assets/publisher-use-case.png)

## Caso de uso del anunciante {#advertiser-use-case}

Audience Manager evalúa y respeta el consentimiento que se pasa en [llamadas en píxeles](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md), de acuerdo con el TCF de IAB.

Los clientes Audience Manager pueden colocar los píxeles en las páginas de socios o en servidores de publicidad para incluirlos en la respuesta de publicidad. En el primer caso, mediante una programación, el socio debe recuperar el parámetro de consentimiento y añadirlo al píxel antes de activarlo. En el segundo caso, que es más común y se describe en detalle a continuación, los servidores de publicidad anexan los parámetros de consentimiento que reciben de la plataforma de suministro (SSP) o de los servidores de publicidad de editor a todos los píxeles.

Audience Manager utiliza dos parámetros para transmitir el consentimiento del usuario en llamadas en píxeles:

* `gdpr` puede ser 0 (no se aplica el RGPD) o 1 (se aplica el RGPD);
* `gdpr_consent` es la cadena de consentimiento RGPD con codificación URL base64 (consulte la [especificación](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Una llamada de muestra para un píxel de impresión, con los dos parámetros, puede ser tal y como sigue:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

En la siguiente imagen y los siguientes pasos se describe el caso de uso. Empezar por la izquierda de la imagen:

1. El usuario recibe una impresión a través de un servidor de publicidad. Esto se traduce en una [llamada en píxeles](../../integration/media-data-integration/impression-data-pixels.md) a nuestros servidores de recopilación de datos (DCS).
2. Audience Manager comprueba si se aplica el indicador del RGPD. Si no es así, Audience Manager almacena los datos pasados en las variables `gdpr` y `gdpr_consent` en las llamadas en píxeles.
3. Si la cadena TC de IAB está presente y contiene los permisos necesarios, Audience Manager almacena los datos pasados en las variables `gdpr` y `gdpr_consent` en las llamadas en píxeles.
4. Si falta la cadena TC de IAB o no tiene los permisos necesarios, el Audience Manager descarta los datos pasados en las variables `gdpr` y `gdpr_consent` en las llamadas en píxeles.

![Caso de uso de anunciante](assets/advertiser-use-case.png)

## Socios de Activación que admiten el TCF de IAB {#aam-activation-partners}

El complemento Audience Manager para el TCF de IAB le permite reenviar la cadena de TC de IAB a los socios de activación, respetando al mismo tiempo las opciones de privacidad de los usuarios. Para obtener información sobre qué socios de activación admiten el TCF de IAB, consulte nuestra [lista de destinos basados en el dispositivo](/help/using/features/destinations/device-based-destinations-list.md).

## Añadir consentimiento a direcciones URL enviadas a destinos URL

La integración del Audience Manager con IAB TCF v2.0 admite la adición de consentimiento a la información enviada a [destinos URL](../../features/destinations/create-url-destination.md) que están integrados con IAB TCF v2.0. Sin embargo, este proceso no lo realiza automáticamente el Audience Manager para evitar romper formatos URL específicos.

Los clientes que deseen adjuntar el consentimiento a los datos enviados a [!DNL URL destinations] deben añadir manualmente las macros `${GDPR}` y `${GDPR_CONSENT_XXXX}` a su formato de URL, sustituyendo `XXXX` por el ID del socio de destino.

Ejemplo: `http://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Consulte [Macros de destino definidas](../../features/destinations/destination-macros.md) para obtener más información sobre las macros de destino admitidas.

## Administración de consentimiento entre dispositivos

El complemento Audience Manager para el TCF de IAB excluye automáticamente los ID presentes en una solicitud, cuando los visitantes del sitio no proporcionan los permisos adecuados. Si la solicitud contiene un [ID entre dispositivos (CRM ID)](../../reference/ids-in-aam.md), el Audience Manager decide excluirse el ID, junto con el último dispositivo vinculado a ese [ID entre dispositivos (CRM ID)](../../reference/ids-in-aam.md).

## Probar la ejecución de IAB {#test-iab-implementation}

Para comprobar que ha implementado correctamente el complemento de Audience Manager para IAB TCF, lea [Caso de uso 4 en Validación del servicio de inclusión (Opt-in)](https://docs.adobe.com/content/help/es-ES/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## IAB y exclusión en Audience Manager. Orden de prioridad. {#iab-and-optout}

Otra opción de privacidad a disposición de los usuarios es la posibilidad de exclusión de toda la recopilación de datos. Adobe proporciona a los usuarios los medios para hacerlo en la página [Sus opciones de privacidad](https://www.adobe.com/es/privacy/opt-out.html#customeruse).

Audience Manager aborda las solicitudes de exclusión en un [artículo independiente de nuestra documentación](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Los usuarios que se excluyen de toda recopilación de datos después de que declinan el consentimiento, no pueden volver a seleccionarse.

>[!NOTE]
>
>**Orden de prioridad**: si el usuario opta por la recopilación de datos de exclusión mediante una herramienta de exclusión global, tal y como se describe en el enlace anterior, esto tiene prioridad sobre las verificaciones de inclusión e IAB.

## Otros recursos {#additional-resources}

* [Inclusión del servicio de identidad de Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [Marco de transparencia y consentimiento del RGPD de la IAB en Europa](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Especificaciones técnicas del marco de transparencia y consentimiento del RGPD de la IAB en Europa](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Complemento de TCF de IAB: vídeo demostrativo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
