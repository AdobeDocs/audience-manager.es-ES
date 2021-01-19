---
description: Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de la funcionalidad de inclusión y a través de la Transparencia IAB y el Marco de consentimiento (TCF). En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager.
seo-description: Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de la funcionalidad de inclusión y a través de la Transparencia IAB y el Marco de consentimiento (TCF). En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager.
seo-title: Complemento de Audience Manager para el TCF de IAB
solution: Audience Manager
title: Complemento de Audience Manager para el TCF de IAB
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: ab72f0875b132eaf333d1e5308322490ac035de3
workflow-type: tm+mt
source-wordcount: '2449'
ht-degree: 40%

---


# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Información general

Un aspecto importante de las obligaciones de privacidad que usted puede tener con sus usuarios es la adquisición y transmisión de opciones de usuario sobre cómo se pueden utilizar sus datos personales (es decir, &quot;propósitos&quot;) y por quién (es decir, &quot;compañías&quot;).

Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de la [funcionalidad de inclusión](https://docs.adobe.com/content/help/es-ES/id-service/using/implementation/opt-in-service/optin-overview.html) y a través de la [Transparencia IAB y el Marco de consentimiento (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager.

>[!IMPORTANT]
>
>Audience Manager está registrado en el [TCF de IAB](https://iabeurope.eu/tcf-for-vendors/) con el ID de proveedor 565.

El complemento de Audience Manager para el TCF de IAB utiliza la [funcionalidad de inclusión](https://docs.adobe.com/content/help/es-ES/id-service/using/implementation/opt-in-service/iab.html), que a su vez forma parte de la biblioteca de [del servicio de identidad de Adobe Experience Platform (ECID)](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html).

## Alcance y limitaciones {#scope-and-limitations}

Como editor o anunciante que trabaja con Audience Manager, puede transmitir las opciones de usuario a Audience Manager según el TCF de IAB.

>[!IMPORTANT]
>
>Los reglamentos del TCF de la IAB se aplican únicamente a los visitantes situados en el Espacio Económico Europeo.

Audience Manager le ayuda a respetar las opciones de privacidad de sus usuarios y también le ofrece una manera fácil de comunicar estas opciones a todos los socios con los que trabaja.

Actualmente, Audience Manager no admite:

* Flujos de trabajo de dispositivos móviles;
* Adición del consentimiento para segmentar las exportaciones.

## Actualizando a [!DNL IAB TCF v2.0] {#upgrading}

Los clientes que estén actualizando su [!DNL Audience Manager Plug-in for IAB TCF] implementación de [!DNL IAB TCF] v1.1 a [!DNL IAB TCF] v2.0 o habilitando [!DNL IAB TCF] v2.0 por primera vez, deben seguir las mismas pautas sobre requisitos previos e implementación que se describen a continuación.

## Requisitos previos {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager admite IAB TCF v2.0.
>
>La compatibilidad con TCF v1.1 de IAB finalizará el 15 de agosto de 2020.
>
> Los clientes que deseen continuar utilizando el complemento Audience Manager para la administración de consentimiento TCF de IAB deben actualizar a la versión más reciente de [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) para obtener soporte continuo.
>
> Después de actualizar a la última versión [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases), las cadenas de consentimiento TCF v1.1 de IAB ya no serán compatibles, por lo que asegúrese de actualizar su CMP antes de actualizar a la última versión ECID.

Debe cumplir los siguientes requisitos previos para utilizar el complemento Audience Manager para IAB TCF con Audience Manager:

1. Debe utilizar el servicio de identidad de Adobe Experience Platform (ECID) en su versión 5 o una posterior. [Descargar](https://github.com/Adobe-Marketing-Cloud/id-service/releases) la última versión de ECID.
2. Debe utilizar la versión 9.0 del Audience Manager [!DNL Data Integration Library] (DIL) o posterior, descargable desde [aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases). Obtenga información sobre [DIL en la documentación de Audience Manager](../../dil/dil-overview.md). Se recomienda utilizar [Inicio de Adobe](https://docs.adobe.com/content/help/es-ES/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html) para la implementación de DIL más sencilla para Audience Manager.
3. Como alternativa, si utiliza [!DNL Server-Side Forwarding] (SSF) para importar datos en Audience Manager, debe actualizar a la versión más reciente de AppMeasurement. Descargue AppMeasurement con el [Administrador de códigos Analytics](https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/code-manager-admin.html).
4. Debe estar utilizando una Plataforma de Gestión de Consentimiento (CMP), ya sea comercial o propia, que esté integrada con IAB TCF v2.0 y esté registrada en la IAB TCF. Consulte la lista de [CMP registradas en el marco de IAB](https://iabeurope.eu/cmp-list/).

>[!WARNING]
>
>Si está utilizando una Plataforma de administración de consentimiento (CMP) que no admite IAB TCF v.2.0, el Audience Manager enviará automáticamente el parámetro `gdpr=0` en las sincronizaciones de ID, incluso si sus visitantes están en la Unión Europea. Para determinar si la validación del RGPD está activa, le recomendamos que confirme con su Plataforma de administración de consentimiento (CMP) que admite la versión v2.0 de IAB TCF.

## Recomendaciones e implementación {#recommendations}

Para habilitar la asistencia TCF de IAB en Audience Manager, consulte nuestra documentación sobre [cómo configurar IAB con inclusión](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html).

La forma más sencilla de hacerlo es mediante [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) para agregar [!DNL ECID Opt-in] a sus propiedades. Lea la documentación para la [extensión de inclusión de ECID](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html) para saber cómo se configura la extensión de Launch.

## Flujo de trabajo de opciones de usuario si se utiliza el marco de trabajo IAB {#user-choice-workflow}

Si se visita un dominio web, los usuarios pueden proponer sus opciones con respecto a cómo el editor y los proveedores externos con los que trabaja el editor utilizarán sus datos.

Los usuarios proporcionan sus opciones en forma de *consentimiento* e *interés legítimo* para los fines de la IAB a *proveedores de terceros* registrados en la lista mundial de proveedores.

La siguiente imagen es un ejemplo de un cuadro de diálogo CMP, mostrado en un visitante de un sitio web por primera vez. Tenga en cuenta que este cuadro de diálogo puede tener un aspecto muy diferente, según la aplicación del cliente.

![Cuadro de diálogo CMP](assets/cmp-example.png)

Los detalles sobre los diversos propósitos y permisos incluidos en IAB TCF v2.0 se tratan en las [Políticas marco de transparencia y consentimiento de IAB Europe](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Los usuarios pueden conceder su consentimiento o su interés legítimo (si está disponible) para una combinación de propósitos y proveedores. Por ejemplo, los usuarios podrían conceder su consentimiento para almacenar información en un dispositivo, desarrollar y mejorar productos, y conceder su consentimiento a todos los proveedores externos que la CP/RP muestre.

O, en otro ejemplo, podían conceder su consentimiento o interés legítimo para todos los fines, pero sólo concedían el consentimiento o el interés legítimo a algunos de los proveedores que la CP/RP mostraba.

Una vez que el usuario selecciona sus opciones de privacidad, las opciones del usuario se registran en la cadena TC de IAB. La cadena TC de IAB almacena la combinación de propósitos y proveedores aprobados, junto con otra información de metadatos (consulte la [página de IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) para obtener más información).

Cada proveedor registrado en el TCF de IAB evalúa la cadena de TC de IAB y toma decisiones en función de las opciones de privacidad de los usuarios. Tenga en cuenta que las opciones de privacidad de los usuarios son válidas en todos los proveedores registrados con IAB TCF.

## Propósitos requeridos por el Audience Manager {#aam-standard-purposes}

Audience Manager evalúa las opciones de los usuarios almacenadas en la cadena TC de IAB para los siguientes fines, definidas en las [Directivas marco de transparencia y consentimiento de IAB Europe](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes). Además, también puede encontrar los propósitos en la [lista de proveedor global](https://vendorlist.consensu.org/vendorlist.json).

* **Objetivo 1**: Almacenar y/o acceder a información en un dispositivo;
* **Objetivo 10**: Desarrollar y mejorar los productos;
* **Objetivo especial 1**: Garantizar la seguridad, evitar fraudes y depurar.

>[!IMPORTANT]
>
>El Audience Manager necesita el consentimiento para el propósito 1 y el propósito 10, más el consentimiento del proveedor, a fin de implementar las cookies e iniciar o cumplir las sincronizaciones de ID.
>
>De acuerdo con las [regulaciones de IAB](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_), el objetivo especial 1 (garantizar la seguridad, evitar el fraude y depurar) siempre se acepta y los usuarios no pueden oponerse a él.

## El comportamiento de Audience Manager depende de si el usuario da el consentimiento {#aam-behavior-consent}

El Audience Manager funciona de manera diferente dependiendo de si la cadena TC de IAB incluye el consentimiento del usuario para los dos fines (almacenar y/o acceder a información en un dispositivo, y desarrollar y mejorar productos) o no.

También comprobamos el consentimiento del usuario para todos los destinos con los que trabaje en Audience Manager, siempre que dichos destinos estén registrados en IAB TCF.

| Cuando el usuario *da su consentimiento*, Audience Manager: | Cuando el usuario *rechaza* el consentimiento, Audience Manager: |
|---|---|
| <ul><li>Lleva a cabo todos los casos de uso de Audience Manager que ha solicitado.</li><li>Transmite el consentimiento a terceros en sincronizaciones de ID (pasando `gdpr = 1` y la cadena de consentimiento como `gdpr_consent` en llamadas de sincronización de ID).</li><li>Evalúa y respeta el consentimiento pasado desde los píxeles del servidor de publicidad.</li><li>Respeta las sincronizaciones de ID iniciadas por el socio.</li></ul> | <ul><li>No almacena ningún dato de usuario nuevo en su instancia. Esto incluye ID de socio, señales, rasgos o datos de píxeles.</li><li>No inicia sincronizaciones de ID de terceros.</li><li>No respeta las sincronizaciones de ID iniciadas por el socio.</li><li>Exclusión al usuario de una recopilación de datos posterior.</li></ul> |

## Caso de uso del editor {#publisher-use-case}

Al implementar el complemento Audience Manager para IAB TCF, no es necesario mantener el código personalizado para la administración de consentimiento en las propiedades web a través de un mecanismo diferente con Adobe u otros proveedores externos. En la siguiente imagen y los siguientes pasos se describe el caso de uso. Empezar por la izquierda de la imagen:

1. Un usuario visita uno de sus dominios web. Siempre que utilice las versiones más recientes de las bibliotecas ECID y DIL (consulte [Requisitos previos](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), se activa el flujo de inclusión.
2. Audience Manager comprueba si se aplica el flujo IAB (`isIabContext=true`). Consulte [Recomendaciones e implementación](aam-iab-plugin.md#recommendations).
3. El Audience Manager comprueba si se aplica el RGPD (`gdpr = 1`) y si hay un CMP, registrado con IAB TCF, en la propiedad web. Por ejemplo, esto se aplicaría a los usuarios que visiten desde la Unión Europea. Tenga en cuenta que es su responsabilidad como editor establecer el indicador del RGPD.
4. Si se aplica el RGPD, el Audience Manager comprueba la cadena TC de IAB, pasada en el parámetro `gdpr_consent`, para obtener el consentimiento necesario. El Audience Manager necesita el consentimiento para almacenar y/o acceder a información en un dispositivo ([propósito 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes) de TCF de IAB), desarrollar y mejorar productos ([propósito 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes) de TCF de IAB), además del consentimiento del proveedor Audience Manager para almacenar, procesar o activar datos.
5. Si la cadena TC de IAB está presente y contiene el consentimiento necesario, el Audience Manager pasa la cadena TC de IAB a nuestros [servidores de recopilación de datos](../../reference/system-components/components-data-collection.md) (DCS).
6. El Audience Manager responde configurando una [cookie de demdex](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-am.html) en el explorador e inicia y respeta las sincronizaciones de ID de terceros.
7. Como alternativa, si la cadena TC de IAB pasada en el paso 4 no contiene todos los permisos necesarios, el Audience Manager no recopila, procesa ni activa ningún dato de usuario y no respeta ni inicia sincronizaciones de ID. Además, exclusión al usuario de los destinos con los que trabaja.

>[!IMPORTANT]
>
>Si está trabajando con socios de destino Audience Manager que requieren parámetros TCF de IAB, pero no tiene un CMP que admita TCF de IAB en su sitio web, entonces el Audience Manager envía `gdpr=0` en sincronizaciones de ID. Esto significa que el RGPD no se aplica a esos usuarios.
>
> Si no lo desea, debe habilitar la funcionalidad TCF de IAB en Audience Manager para enviar las cadenas TC de IAB correspondientes a los socios de destino.



![Caso de uso del editor](assets/publisher-use-case.png)

## Caso de uso del anunciante {#advertiser-use-case}

Audience Manager evalúa y respeta el consentimiento que se pasa en [llamadas en píxeles](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md), de acuerdo con el TCF de IAB.

Los Audience Manager pueden colocar los píxeles en las páginas de socios o en los servidores de publicidad para incluirlos en la respuesta de publicidad. En el primer caso, mediante una programación, el socio debe recuperar el parámetro de consentimiento y añadirlo al píxel antes de activarlo. En el segundo caso, que es más común y se describe en detalle a continuación, los servidores de publicidad anexan los parámetros de consentimiento que reciben de la plataforma de suministro (SSP) o de los servidores de publicidad de editor a todos los píxeles.

Audience Manager utiliza dos parámetros para transmitir el consentimiento del usuario en llamadas en píxeles:

* `gdpr` puede ser 0 (no se aplica el RGPD) o 1 (se aplica el RGPD);
* `gdpr_consent` es la cadena de consentimiento RGPD con codificación URL base64 (consulte la [especificación](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Una llamada de muestra para un píxel de impresión, con los dos parámetros, puede ser tal y como sigue:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

En la siguiente imagen y los siguientes pasos se describe el caso de uso. Empezar por la izquierda de la imagen:

1. El usuario recibe una impresión a través de un servidor de publicidad. Esto se traduce en una [llamada de píxel](../../integration/media-data-integration/impression-data-pixels.md) a nuestros Servidores de recopilación de datos (DCS).
2. Audience Manager comprueba si se aplica el indicador del RGPD. Si no lo hace, Audience Manager almacena los datos pasados en las variables `gdpr` y `gdpr_consent` en las llamadas en píxeles.
3. Si la cadena TC de IAB está presente y contiene los permisos necesarios, Audience Manager almacena los datos pasados en las variables `gdpr` y `gdpr_consent` en las llamadas en píxeles.
4. Si falta la cadena TC de IAB o carece de los permisos necesarios, Audience Manager descarta los datos pasados a las variables `gdpr` y `gdpr_consent` en las llamadas en píxeles.

![Caso de uso de anunciante](assets/advertiser-use-case.png)

## Socios de Activación que admiten el TCF de IAB {#aam-activation-partners}

El complemento Audience Manager para IAB TCF le permite reenviar la cadena IAB TC a los socios de activación respetando las opciones de privacidad de los usuarios. Para obtener información sobre qué socios de activación admiten el TCF de IAB, consulte nuestra [lista de destinos basados en el dispositivo](/help/using/features/destinations/device-based-destinations-list.md).

## Adición de consentimiento a direcciones URL enviadas a destinos de URL

La integración del Audience Manager con IAB TCF v2.0 admite la adición de consentimiento a la información enviada a [destinos URL](../../features/destinations/create-url-destination.md) que están integrados con IAB TCF v2.0. Sin embargo, el Audience Manager no realiza este proceso automáticamente para evitar que se rompan formatos de URL específicos.

Los clientes que deseen anexar su consentimiento a los datos enviados a [!DNL URL destinations] deben agregar manualmente las macros `${GDPR}` y `${GDPR_CONSENT_XXXX}` a su formato de URL, reemplazando `XXXX` por el ID del socio de destino.

Ejemplo: `http://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Consulte [Macros de destino definidas](../../features/destinations/destination-macros.md) para obtener más información sobre las macros de destino admitidas.

## Administración del consentimiento entre dispositivos

El complemento Audience Manager para IAB TCF exclusión automáticamente los ID presentes en una solicitud, cuando los visitantes del sitio no proporcionan los permisos adecuados. Si la solicitud contiene un [ID entre dispositivos (ID de CRM)](../../reference/ids-in-aam.md), el Audience Manager exclusión el ID, junto con el último dispositivo vinculado a ese [ID entre dispositivos (ID de CRM)](../../reference/ids-in-aam.md).

## Probar la ejecución de IAB {#test-iab-implementation}

Para probar que ha implementado correctamente el complemento Audience Manager para IAB TCF, lea [Caso de uso 4 en Validación del servicio de inclusión](https://docs.adobe.com/content/help/es-ES/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## IAB y exclusión en Audience Manager. Orden de prioridad. {#iab-and-optout}

Otra opción de privacidad a disposición de los usuarios es la posibilidad de exclusión de toda la recopilación de datos. Adobe proporciona a los usuarios los medios para hacerlo en la página [Sus opciones de privacidad](https://www.adobe.com/es/privacy/opt-out.html#customeruse).

Audience Manager aborda las solicitudes de exclusión en un [artículo independiente de nuestra documentación](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Los usuarios que estén exclusión de toda la recopilación de datos después de que hayan rechazado el consentimiento, no podrán volver a seleccionarlos.

>[!NOTE]
>
>**Orden de prioridad**: si el usuario opta por la recopilación de datos de exclusión mediante una herramienta de exclusión global, tal y como se describe en el enlace anterior, esto tiene prioridad sobre las verificaciones de inclusión e IAB.

## Otros recursos {#additional-resources}

* [Inclusión del servicio de identidad de Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [Marco de transparencia y consentimiento del RGPD de la IAB en Europa](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Especificaciones técnicas del marco de transparencia y consentimiento del RGPD de la IAB en Europa](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Complemento de TCF de IAB: vídeo demostrativo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)