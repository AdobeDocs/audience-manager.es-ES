---
description: Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de la funcionalidad de inclusión y a través de la compatibilidad con Transparency y Consent Fremework de IAB (Transparency). En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager.
seo-description: Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de la funcionalidad de inclusión y a través de la compatibilidad con Transparency y Consent Fremework de IAB (Transparency). En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager.
seo-title: Complemento de Audience Manager para IAB TCF
solution: Audience Manager
title: Complemento de Audience Manager para IAB TCF
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Complemento de Audience Manager para IAB TCF {#aam-iab-plugin}

## Información general

Un aspecto importante de las obligaciones de privacidad que tiene con respecto a los usuarios es la adquisición y la transmisión de las elecciones del usuario sobre cómo se pueden utilizar sus datos personales (por ejemplo: “motivos”) y quién (por ejemplo: “empresas”).

Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de [la funcionalidad de inclusión](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html) y a través [de la compatibilidad con Transparency y Consent Fremework de IAB (Transparency)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager. Audience Manager está registrado en IAB TCF con el ID del proveedor 565.

El complemento de Audience Manager para IAB TCF utiliza la funcionalidad [de selección](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html), que, a su vez, es parte de la biblioteca Servicio de ID de Adobe [Experience Cloud (ECID)](https://marketing.adobe.com/resources/help/en_US/mcvid/) .

## Ámbito y limitaciones {#scope-and-limitations}

Como editor o anunciante que trabaja con Audience Manager, puede transmitir las opciones de usuario a Audience Manager según IAB TCF. Esto proporciona una manera fácil y coherente de comunicar las opciones de usuario a todos los socios con los que trabaja y de Audience Manager puede ayudarle a respetar las opciones de privacidad de los usuarios.

La compatibilidad de IAB TCF descrita en este artículo representa la primera fase de la compatibilidad planificada de Audience Manager para el marco IAB. Actualmente, Audience Manager no admite:

* Flujos de trabajo de dispositivos móviles;
* Administración de consentimiento entre dispositivos;
* Anexar consentimiento a direcciones URL enviadas a [destinos URL](/help/using/features/destinations/create-url-destination.md);
* Anexar consentimiento a segmentos.

## Requisitos previos {#prerequisites}

Debe cumplir los requisitos previos para utilizar el IAB TCF con Audience Manager:

1. Debe utilizar el servicio Experience Cloud ID (ECID) versión 4.1 o posterior. [Descargue](https://github.com/Adobe-Marketing-Cloud/id-service/releases) la versión ECID más reciente.
2. 
   1. Debe utilizar la biblioteca de integración de datos de Audience Manager (DIL) versión 9.0 o posterior, descargable desde [aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases). Obtenga información sobre [DIL en la documentación de Audience Manager](/help/using/dil/dil-overview.md).
   2. Como alternativa, si utiliza Reenvío de servidor (SSF) para importar datos en Audience Manager, debe actualizar a la versión más reciente de appmeasurement. Descargue appmeasurement usando el [Administrador de códigos de Analytics](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).
3. Debe utilizar una plataforma de administración de consentimiento (CMP), ya sea comercial o suya, que admita IAB y esté registrada en IAB TCF. Consulte la lista de [ICC registrados dentro del marco de IAB](https://advertisingconsent.eu/cmp-list/).

## Recomendaciones y cómo implementar {#recommendations}

Para habilitar la compatibilidad de IAB TCF en Audience Manager, lea nuestra documentación sobre [cómo configurar IAB con inclusión](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html).

Esto se realiza más fácilmente utilizando [Adobe Launch](https://docs.adobelaunch.com/) para instrumentar ECID Opt-in en sus propiedades. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## Flujo de trabajo de opciones de usuario al utilizar el marco IAB {#user-choice-workflow}

Al visitar una propiedad web, los usuarios pueden proporcionar sus opciones con respecto a la forma en que el editor y los proveedores externos con los que trabaja el editor utilizan sus datos. Los usuarios proporcionan sus opciones en forma *de fines estándar* y permisos para *proveedores externos* registrados en la lista de proveedores global. La imagen siguiente representa un ejemplo de un cuadro de diálogo CMP, que se muestra a un visitante nuevo de un sitio web. Tenga en cuenta que este cuadro de diálogo puede tener un aspecto muy distinto según la implementación del cliente.

![Cuadro de diálogo CMP](/help/using/overview/aam-gdpr/assets/cmp.png)

Los objetivos estándar de la estructura IAB son:

* Almacenamiento y almacenamiento de información
* Personalización
* Selección, entrega e informe de publicidad
* Selección, entrega y creación de contenido
* vídeo 

Consulte la página de especificación del marco [IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) para obtener una descripción de los cinco fines estándar.

Los usuarios pueden otorgar su consentimiento para una combinación de fines estándar y proveedores. Por ejemplo, los usuarios podrían otorgar su consentimiento para el almacenamiento, personalización y medición y conceder su consentimiento a todos los proveedores de terceros que muestra la CMP. O bien, en otro ejemplo, pueden otorgar su consentimiento para los cinco propósitos estándar pero sólo conceder consentimiento a algunos de los proveedores que ven la CMP.

Una vez que el usuario selecciona las opciones de privacidad, las opciones de usuario se registran en la cadena de consentimiento IAB TCF. La cadena de consentimiento IAB TCF almacena la combinación de fines aprobados y proveedores junto con otra información de metadatos (consulte la página [IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) para obtener más información). Todos los proveedores registrados en la IAB TCF evaluarán la cadena de consentimiento IAB TCF y toman decisiones basadas en las opciones de privacidad de los usuarios. Tenga en cuenta que las opciones de privacidad de los usuarios son válidas en todos los proveedores aprobados.

## Propósitos estándar necesarios por Audience Manager {#aam-standard-purposes}

Audience Manager evalúa las opciones de los usuarios almacenadas en la cadena de consentimiento de IAB TFC para:

* Almacenamiento y almacenamiento de información (ID de propósito 1 en la lista de proveedores [globales](https://vendorlist.consensu.org/vendorlist.json))
* Personalización (ID de propósito 2)
* Medición (ID de propósito 5)
* El proveedor de Audience Manager para almacenar, procesar o activar datos para un editor.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## El comportamiento de Audience Manager depende de si el usuario concede consentimiento {#aam-behavior-consent}

Audience Manager funciona de forma diferente dependiendo de si Audience Manager detecta en la cadena de consentimiento IAB TCF que el usuario ha proporcionado el consentimiento para los tres propósitos (almacenamiento, personalización, medición) o no.

| Cuando el usuario *proporcione consentimiento*, Audience Manager: | Cuando el usuario *rechaza* el consentimiento, Audience Manager: |
|---|---|
| <ul><li>Ejecuta todos los casos de uso de Audience Manager que ha solicitado.</li><li>Transmite consentimiento a terceros en sincronizaciones de ID (pasando gdpr = 1 y la cadena de consentimiento como gdpr_ permission en las llamadas de sincronización de ID).</li><li>Evalúa y respeta el consentimiento pasado desde píxeles del servidor de publicidad.</li><li>Honra sincronizaciones de ID iniciadas por el socio.</li></ul> | <ul><li>No almacena ningún dato de usuario nuevo en su instancia. Esto incluye los ID de socio, señales, características o datos de píxeles.</li><li>No inicia sincronizaciones de ID de terceros.</li><li>No respeta las sincronizaciones de ID iniciadas por el socio.</li></ul> |



## Caso de uso del editor {#publisher-use-case}

Al implementar la IAB TCF, no es necesario mantener el código personalizado para la administración de consentimiento en sus propiedades web a través de un mecanismo diferente con Adobe u otros proveedores de terceros. El caso de uso se describe en la imagen y en los pasos siguientes. Comience desde la izquierda de la imagen:

1. Un usuario visita una de sus propiedades web. Siempre que utilice las versiones más recientes de las bibliotecas ECID y DIL (consulte [Requisitos previos](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites)), se activa el flujo de selección.
2. Audience Manager comprueba si se aplica el flujo IAB (`isIabContext=true`). Consulte [Recomendaciones y cómo implementar](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations).
3. Audience Manager comprueba si el RGPD se aplica (`gdpr = 1`) y si hay una CMP, registrada con IAB, en la propiedad web. Por ejemplo, esto se aplicaría a los usuarios que visitan el sitio de la Unión Europea. Tenga en cuenta que es responsabilidad suya establecer el indicador del RGPD.
4. Si se aplica el RGPD, Audience Manager comprueba la cadena de consentimiento IAB TCF, que se transfiere en el parámetro `gdpr_consent`, para los permisos necesarios. Audience Manager necesita permisos para almacenamiento, personalización, medición, además del consentimiento del proveedor de Audience Manager, para almacenar, procesar o activar datos.
5. Si la cadena de consentimiento IAB TCF está presente y contiene los permisos necesarios, Audience Manager pasa la cadena de consentimiento IAB TCF a nuestros [servidores de recopilación de datos](/help/using/reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager responde estableciendo una [cookie demdex](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) en el navegador. Audience Manager también inicia y respeta sincronizaciones de ID de terceros.
7. Alternativamente, si la cadena de consentimiento IAB TCF pasada en el paso 5 no contiene todos los permisos necesarios, Audience Manager no recopila, procesa ni activa datos y no respeta ni inicia sincronizaciones de ID.

![Caso de uso del editor](assets/publisher-use-case.png)

## Caso de uso del anunciante {#advertiser-use-case}

Audience Manager evalúa y respeta el consentimiento pasado en llamadas [](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)de píxeles, de conformidad con la IAB TCF.

Los clientes de Audience Manager generalmente colocan píxeles en las páginas de socios o en servidores de publicidad para incluirlos en la respuesta de publicidad. En el primer caso, el socio debe recuperar mediante programación el parámetro de consentimiento y agregarlo al píxel antes de activarlo. En el segundo caso, que es más común y se describe detalladamente a continuación, los servidores de publicidad anexan los parámetros de consentimiento que reciben de la plataforma de suministro (SSP) o servidores de publicidad del editor a todos los píxeles.

Audience Manager utiliza dos parámetros para transmitir el consentimiento del usuario en llamadas de píxeles:

* `gdpr` puede ser 0 (el RGPD no se aplica) o 1 (se aplica RGPD);
* `gdpr_consent` es la cadena de consentimiento del RDPD con codificación de URL segura 64 (consulte [especificación](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)). Una llamada de muestra para un píxel de impresión, con los dos parámetros, podría verse como se muestra a continuación:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

El caso de uso se describe en la imagen y en los pasos siguientes. Comience desde la izquierda de la imagen:

1. Al usuario se le suministra una impresión mediante un servidor de publicidad. Esto se traduce en una llamada de píxeles a nuestros servidores de recopilación de datos (DCS).
1. Audience Manager comprueba si se aplica el indicador RGPD. Si no lo hace, Audience Manager almacena los datos pasados en variables de macro en llamadas de píxeles.
1. Si la cadena de consentimiento está presente y contiene los permisos necesarios, Audience Manager almacena los datos pasados en variables de macro en llamadas de píxeles.
1. Si falta la cadena de consentimiento o carece de los permisos requeridos, Audience Manager deja los datos pasados en variables de macro en llamadas de píxeles.

![Caso de uso del anunciante](assets/advertiser-use-case.png)

## Socios de activación que admiten IAB TCF {#aam-activation-partners}

El complemento de Audience Manager para IAB TCF permite reenviar la cadena de consentimiento IAB TCF a los socios de activación respetando las opciones de privacidad de los usuarios. Para obtener información sobre qué socios de activación admiten IAB TCF (precisión desde el 7 de julio de 2019), consulte la hoja **[de Excel asociada](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx)**.

## Probar la implementación de IAB {#test-iab-implementation}

Para comprobar que ha implementado correctamente el complemento de Audience Manager para IAB TCF, lea [el caso de uso 4 en la implementación de métodos de validación y IAB](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html).

## IAB y exclusión en Audience Manager. Orden de prioridad. {#iab-and-optout}

Otra opción de privacidad a la disposición de los usuarios es la posibilidad de excluir toda la recopilación de datos. Adobe proporciona a los usuarios los medios para hacerlo dentro de [la página Opciones](https://www.adobe.com/privacy/opt-out.html#customeruse) de privacidad.

Audience Manager trata la administración de exclusiones en un artículo [independiente de nuestra documentación](/help/using/overview/data-security-and-privacy/opt-out-management.md).

>[!NOTE]
>
>**Orden de prioridad** : si el usuario renuncia a la recopilación de datos utilizando una herramienta de exclusión global, tal como se describe en el vínculo anterior, tiene prioridad sobre las verificaciones de inclusión y IAB.

## Recursos adicionales {#additional-resources}

* [Inclusión del servicio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [Marco de consentimiento y transparencia de IAB Europa GDPR](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Especificaciones técnicas del marco de consentimiento y transparencia de IAB Europa GDPR](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Complemento IAB TCF: demostración de vídeo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)