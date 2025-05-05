---
description: Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de la funcionalidad de inclusión y a través de la Transparencia IAB y el Marco de consentimiento (TCF). En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager.
seo-description: Adobe provides you with the means to manage and communicate your users' privacy choices through the Opt-in functionality and through IAB Transparency and Consent Framework (TCF) support. This article describes the Audience Manager use cases that support the IAB TCF and how to implement IAB TCF support in Audience Manager.
seo-title: Audience Manager Plug-in for IAB TCF
solution: Audience Manager
title: Complemento de Audience Manager para el TCF de IAB
feature: Data Governance & Privacy
exl-id: aa6bc415-e52b-4900-951d-ccf51d907aa2
source-git-commit: 8b370a64d80b40124abee91351cbef09711243d4
workflow-type: tm+mt
source-wordcount: '2173'
ht-degree: 29%

---

# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Información general

Un aspecto importante de las obligaciones de privacidad que puede tener con respecto a los usuarios es la adquisición y transmisión de las opciones del usuario sobre cómo se pueden utilizar sus datos personales (por ejemplo, &quot;fines&quot;) y quién (por ejemplo, &quot;empresas&quot;).

Adobe le proporciona los medios para gestionar y comunicar las opciones de privacidad de los usuarios a través de la [funcionalidad de inclusión](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=es) y a través de la [Transparencia IAB y el Marco de consentimiento (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

En este artículo se describen casos de uso de Audience Manager que admiten el TCF de IAB y cómo implementar la compatibilidad con TCF de IAB en Audience Manager.

>[!IMPORTANT]
>
>El Audience Manager está registrado en [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) con el identificador de proveedor 565.

El complemento de Audience Manager para el TCF de IAB utiliza la funcionalidad [Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html?lang=es), que a su vez forma parte de la biblioteca [Adobe Experience Platform Identity Service (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es).

## Alcance y limitaciones {#scope-and-limitations}

Como editor o anunciante que trabaja con Audience Manager, puede transmitir las opciones de usuario a Audience Manager según el TCF de IAB.

>[!IMPORTANT]
>
>Las regulaciones del TCF de la IAB se aplican solo a los visitantes ubicados en el Espacio Económico Europeo.

Audience Manager le ayuda a respetar las opciones de privacidad de sus usuarios y también le ofrece una forma sencilla de comunicar estas opciones a todos los socios con los que trabaje.

Actualmente, Audience Manager no admite:

* Flujos de trabajo de dispositivos móviles;
* Añadir el consentimiento a las exportaciones de segmentos.

## Actualizando a [!DNL IAB TCF v2.2] {#upgrading}

Los clientes que actualicen su implementación de [!DNL Audience Manager Plug-in for IAB TCF] de [!DNL IAB TCF] v1.1 a [!DNL IAB TCF] v2.2, o que habiliten [!DNL IAB TCF] v2.2 por primera vez, deben seguir las mismas directrices sobre requisitos previos e implementación que se describen a continuación.

## Requisitos previos {#prerequisites}

>[!IMPORTANT]
>
>El Audience Manager admite IAB TCF v2.2.
>
>La compatibilidad con IAB TCF v1.1 finalizará el 15 de agosto de 2020.
>
> Los clientes que deseen seguir usando el complemento de Audience Manager para el TCF de IAB para la administración de consentimiento deben actualizar a la versión más reciente de [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) para obtener soporte continuo.
>
> Después de actualizar a la última versión de [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases), las cadenas de consentimiento IAB TCF v1.1 ya no serán compatibles, por lo que asegúrese de actualizar su CMP antes de actualizar a la última versión de ECID.

Debe cumplir los siguientes requisitos previos para utilizar el complemento de Audience Manager para IAB TCF con Audience Manager:

1. Debe utilizar el servicio de identidad de Adobe Experience Platform (ECID) en su versión 5 o una posterior. [Descargar](https://github.com/Adobe-Marketing-Cloud/id-service/releases) la última versión de ECID.
2. Debe utilizar el Audience Manager [!DNL Data Integration Library] (DIL) versión 9.0 o posterior, descargable desde [aquí](https://github.com/Adobe-Marketing-Cloud/dil/releases). Obtenga información sobre [DIL en la documentación de Audience Manager](../../dil/dil-overview.md). Se recomienda usar la [extensión de etiquetas de Adobe Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=es) para facilitar la implementación de Audience Manager por parte del DIL.
3. Alternativamente, si utiliza [!DNL Server-Side Forwarding] (SSF) para importar datos en Audience Manager, debe actualizar a la última versión de AppMeasurement. Descargue AppMeasurement con el [Administrador de códigos Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html?lang=es).
4. Debe utilizar una plataforma de administración de consentimiento (CMP), ya sea comercial o propia, integrada con IAB TCF v2.2 y registrada en IAB TCF. Consulte la lista de [CMP registradas en el marco de IAB](https://iabeurope.eu/cmp-list/).

>[!WARNING]
>
>Si utiliza una plataforma de administración de consentimiento (CMP) que no es compatible con IAB TCF v2.2, Audience Manager enviará automáticamente el parámetro `gdpr=0` en las sincronizaciones de ID, aunque los visitantes estén en la Unión Europea. Para determinar si la validación del RGPD está activa, le recomendamos que confirme con su plataforma de administración de consentimiento (CMP) que es compatible con IAB TCF v2.2.

## Recommendations y cómo implementar {#recommendations}

Para habilitar la asistencia TCF de IAB en Audience Manager, consulte nuestra documentación sobre [cómo configurar IAB con inclusión](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html?lang=es).

La forma más sencilla de hacerlo es usando [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es) para agregar [!DNL ECID Opt-in] a tus propiedades. Lea la documentación de la [extensión de inclusión de ECID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=es) para saber cómo configurar la extensión de etiquetas.

## Flujo de trabajo de elección del usuario al utilizar el marco IAB {#user-choice-workflow}

Al visitar un dominio web, los usuarios pueden proporcionar sus opciones con respecto a cómo el editor y los proveedores externos con los que trabaja el editor utilizarán sus datos.

Los usuarios proponen sus opciones en forma de *consentimiento* con fines de la IAB a *proveedores de terceros* registrados en la lista global de proveedores.

La siguiente imagen es un ejemplo de un cuadro de diálogo CMP, mostrado en un visitante de un sitio web por primera vez. Tenga en cuenta que este cuadro de diálogo puede tener un aspecto muy diferente, según la aplicación del cliente.

![Cuadro de diálogo CMP](assets/cmp-example.png)

Los detalles sobre los diversos propósitos y permisos incluidos en IAB TCF v2.2 se tratan en las [Políticas del marco de transparencia y consentimiento de IAB Europe](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Los usuarios pueden dar su consentimiento para una combinación de propósitos y proveedores. Por ejemplo, los usuarios pueden dar su consentimiento para almacenar información en un dispositivo, desarrollar y mejorar productos y dar su consentimiento a todos los proveedores externos que muestre la CMP.

En otro ejemplo, pueden dar su consentimiento a todos los efectos pero solo dar su consentimiento a algunos de los proveedores mostrados por la CMP.

Una vez que el usuario selecciona sus opciones de privacidad, las opciones del usuario se registran en la cadena IAB TC. La cadena IAB TC almacena la combinación de propósitos y proveedores aprobados, junto con otra información de metadatos (consulte la [página IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) para obtener más información).

Todos los proveedores registrados en el TCF de IAB evalúan la cadena IAB TC y toman decisiones basadas en las opciones de privacidad de los usuarios. Tenga en cuenta que las opciones de privacidad de los usuarios son válidas en todos los proveedores registrados con IAB TCF.

## Finalidades requeridas por el Audience Manager {#aam-standard-purposes}

El Audience Manager evalúa las opciones de los usuarios almacenadas en la cadena IAB TC para los siguientes fines, definidos en las [políticas del marco de transparencia y consentimiento de IAB Europe](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions).

* **Propósito 1**: almacenar o tener acceso a información en un dispositivo;
* **Propósito 10**: desarrollar y mejorar productos;
* **Propósito especial 1**: garantice la seguridad, evite el fraude y depure.

>[!IMPORTANT]
>
>El Audience Manager necesita consentimiento para las Finalidades 1 y 10, además del consentimiento del proveedor, para poder implementar cookies e iniciar o cumplir sincronizaciones de ID.
>
>Según las [regulaciones de la IAB](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_), el propósito especial 1 (garantizar la seguridad, evitar el fraude y depurar) siempre cuenta con el consentimiento y los usuarios no pueden oponerse a él.

## El comportamiento del Audience Manager depende de si el usuario da el consentimiento {#aam-behavior-consent}

El Audience Manager funciona de forma diferente en función de si la cadena IAB TC incluye el consentimiento del usuario para los dos fines (almacenar o acceder a información en un dispositivo y desarrollar y mejorar productos) o no.

También comprobamos el consentimiento del usuario para todos los destinos con los que trabaja en Audience Manager, siempre y cuando dichos destinos estén registrados en IAB TCF.

| Cuando el usuario *da su consentimiento*, Audience Manager: | Cuando el usuario *rechaza* el consentimiento, Audience Manager: |
|---|---|
| <ul><li>Lleva a cabo todos los casos de uso de Audience Manager que ha solicitado.</li><li>Transmite el consentimiento a terceros en sincronizaciones de ID (pasando `gdpr = 1` y la cadena de consentimiento como `gdpr_consent` en llamadas de sincronización de ID).</li><li>Evalúa y respeta el consentimiento pasado desde los píxeles del servidor de publicidad.</li><li>Respeta las sincronizaciones de ID iniciadas por el socio.</li></ul> | <ul><li>No almacena ningún dato de usuario nuevo en su instancia. Esto incluye ID de socio, señales, rasgos o datos de píxeles.</li><li>No inicia sincronizaciones de ID de terceros.</li><li>No respeta las sincronizaciones de ID iniciadas por el socio.</li><li>Excluye al usuario de cualquier recopilación de datos adicional.</li></ul> |

## Caso de uso del editor {#publisher-use-case}

Al implementar el complemento Audience Manager para el TCF de IAB, no es necesario mantener el código personalizado para la administración de consentimientos en las propiedades web a través de un mecanismo diferente con Adobe u otros proveedores de terceros. En la siguiente imagen y los siguientes pasos se describe el caso de uso. Empezar por la izquierda de la imagen:

1. Un usuario visita uno de sus dominios web. Siempre que utilice las versiones más recientes de las bibliotecas ECID y DIL (consulte [Requisitos previos](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), se activa el flujo de inclusión.
2. Audience Manager comprueba si se aplica el flujo IAB (`isIabContext=true`). Consulte [Recomendaciones e implementación](aam-iab-plugin.md#recommendations).
3. El Audience Manager comprueba si el RGPD se aplica (`gdpr = 1`) y si hay un CMP, registrado con IAB TCF, en la propiedad web. Por ejemplo, esto se aplicaría a los usuarios que visiten desde la Unión Europea. Tenga en cuenta que, como editor, es su responsabilidad establecer el indicador del RGPD.
4. Si se aplica el RGPD, Audience Manager comprueba la cadena IAB TC, pasada en el parámetro `gdpr_consent`, para obtener el consentimiento requerido. El Audience Manager necesita consentimiento para almacenar o acceder a información en un dispositivo ([propósito TCF de IAB 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), desarrollar y mejorar productos ([propósito TCF de IAB 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), además del consentimiento del proveedor del Audience Manager para almacenar, procesar o activar datos.
5. Si la cadena IAB TC está presente y contiene el consentimiento requerido, el Audience Manager pasa la cadena IAB TC a nuestros [servidores de recopilación de datos](../../reference/system-components/components-data-collection.md) (DCS).
6. El Audience Manager responde configurando una [cookie demdex](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html?lang=es) en el explorador e inicia y respeta las sincronizaciones de ID de terceros.
7. Alternativamente, si la cadena IAB TC pasada en el paso 4 no contiene todos los permisos necesarios, Audience Manager no recopila, procesa ni activa ningún dato de usuario y no respeta ni inicia sincronizaciones de ID. Además, excluye al usuario de los destinos con los que trabaja.

>[!IMPORTANT]
>
>Si está trabajando con socios de destino Audience Manager que requieren parámetros TCF de IAB, pero no tiene una CMP que admita TCF de IAB en el sitio web, el Audience Manager enviará `gdpr=0` en sincronizaciones de ID. Esto significa que el RGPD no se aplica a esos usuarios.
>
> Si no lo desea, debe habilitar la funcionalidad TCF de IAB en Audience Manager para enviar las cadenas TC de IAB adecuadas a los socios de destino.



![Caso de uso del editor](assets/publisher-use-case.png)

## Caso de uso del anunciante {#advertiser-use-case}

Audience Manager evalúa y respeta el consentimiento que se pasa en [llamadas en píxeles](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md), de acuerdo con el TCF de IAB.

Los píxeles pueden ser colocados por los clientes de Audience Manager en las páginas de socios o se colocan en servidores de publicidad para incluirlos en la respuesta de publicidad. En el primer caso, mediante una programación, el socio debe recuperar el parámetro de consentimiento y añadirlo al píxel antes de activarlo. En el segundo caso, que es más común y se describe en detalle a continuación, los servidores de publicidad anexan los parámetros de consentimiento que reciben de la plataforma de suministro (SSP) o de los servidores de publicidad de editor a todos los píxeles.

Audience Manager utiliza dos parámetros para transmitir el consentimiento del usuario en llamadas en píxeles:

* `gdpr` puede ser 0 (no se aplica el RGPD) o 1 (se aplica el RGPD);
* `gdpr_consent` es la cadena de consentimiento RGPD con codificación URL base64 (consulte la [especificación](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Una llamada de muestra para un píxel de impresión, con los dos parámetros, puede ser tal y como sigue:

```
https://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

En la siguiente imagen y los siguientes pasos se describe el caso de uso. Empezar por la izquierda de la imagen:

1. El usuario recibe una impresión a través de un servidor de publicidad. Esto se traduce en una llamada de [píxel](../../integration/media-data-integration/impression-data-pixels.md) a nuestros servidores de recopilación de datos (DCS).
2. Audience Manager comprueba si se aplica el indicador del RGPD. Si no es así, el Audience Manager almacena los datos pasados en las variables `gdpr` y `gdpr_consent` en llamadas en píxeles.
3. Si la cadena IAB TC está presente y contiene los permisos necesarios, Audience Manager almacena los datos pasados en las variables `gdpr` y `gdpr_consent` en llamadas en píxeles.
4. Si falta la cadena IAB TC o no tiene los permisos necesarios, el Audience Manager descarta los datos pasados en las variables `gdpr` y `gdpr_consent` en llamadas en píxeles.

![Caso de uso de anunciante](assets/advertiser-use-case.png)

## Socios de activación que admiten el TCF de IAB {#aam-activation-partners}

El complemento Audience Manager para el TCF de IAB le permite reenviar la cadena IAB TC a los socios de activación, respetando al mismo tiempo las opciones de privacidad de los usuarios. Para obtener información sobre qué socios de activación admiten el TCF de IAB, consulte nuestra [lista de destinos basados en el dispositivo](/help/using/features/destinations/device-based-destinations-list.md).

## Añadir consentimiento a direcciones URL enviadas a destinos URL

La integración de Audience Manager con IAB TCF v2.2 admite la adición del consentimiento a la información enviada a [destinos de URL](../../features/destinations/create-url-destination.md) integrados con IAB TCF v2.2. Sin embargo, este proceso no lo realiza automáticamente el Audience Manager para evitar romper formatos de URL específicos.

Los clientes que deseen anexar el consentimiento a los datos enviados a [!DNL URL destinations] deben agregar manualmente las macros `${GDPR}` y `${GDPR_CONSENT_XXXX}` a su formato de dirección URL y reemplazar `XXXX` por el identificador del socio de destino.

Ejemplo: `https://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Consulte [Macros de destino definidas](../../features/destinations/destination-macros.md) para obtener más información sobre las macros de destino admitidas.

## Administración de consentimiento entre dispositivos

El complemento de Audience Manager para el TCF de IAB excluye automáticamente los ID presentes en una solicitud cuando los visitantes del sitio no proporcionan los permisos adecuados. Si la solicitud contiene [ID en varios dispositivos (CRM ID)](../../reference/ids-in-aam.md), el Audience Manager excluye el ID, junto con el último dispositivo vinculado a ese [ID en varios dispositivos (CRM ID)](../../reference/ids-in-aam.md).

## Prueba de la implementación de IAB {#test-iab-implementation}

Para comprobar que ha implementado correctamente el complemento de Audience Manager para el TCF de IAB, lea [Caso de uso 4 en Validación del servicio de inclusión](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html?lang=es#section-64331998954d4892960dcecd744a6d88).

## IAB y exclusión en Audience Manager. Orden de prioridad. {#iab-and-optout}

Otra opción de privacidad a disposición de los usuarios es la posibilidad de exclusión de toda la recopilación de datos. Adobe proporciona a los usuarios los medios para hacerlo en la página [Sus opciones de privacidad](https://www.adobe.com/es/privacy/opt-out.html#customeruse).

Audience Manager aborda las solicitudes de exclusión en un [artículo independiente de nuestra documentación](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Los usuarios que se excluyen de toda recopilación de datos después de rechazar el consentimiento no pueden volver a incluirse.

>[!NOTE]
>
>**Orden de prioridad**: si el usuario opta por la recopilación de datos de exclusión mediante una herramienta de exclusión global, tal y como se describe en el enlace anterior, esto tiene prioridad sobre las verificaciones de inclusión e IAB.

## Recursos adicionales {#additional-resources}

* [Inclusión del servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=es)
* [Marco de transparencia y consentimiento del RGPD de la IAB en Europa](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Especificaciones técnicas del marco de transparencia y consentimiento del RGPD de la IAB en Europa](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Complemento de TCF de IAB: vídeo demostrativo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
