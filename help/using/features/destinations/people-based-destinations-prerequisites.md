---
description: 'Lea más abajo para obtener información general sobre los requisitos de los clientes que debe cumplir antes de registrarse en los destinos basados en personas.  '
seo-description: 'Lea más abajo para obtener información general sobre los requisitos de los clientes que debe cumplir antes de registrarse en los destinos basados en personas.  '
seo-title: Requisitos previos y consideraciones de destinos basados en personas
solution: Audience Manager
title: Requisitos previos y consideraciones
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# Requisitos previos y consideraciones {#prerequisites-considerations}

Lea más abajo para obtener información general sobre los requisitos de los clientes que debe cumplir antes de registrarse [!DNL People-Based Destinations].

>[!IMPORTANT]
> Lea detenidamente este artículo antes de pasar a la fase de implementación.

## Registro para destinos basados en personas {#signing-up}

[!DNL People-Based Destinations] es una funcionalidad Premium que mejora la experiencia de Audience Manager permitiéndole activar segmentos de audiencia de origen en entornos basados en personas, dirigiendo a su audiencia con ofertas personalizadas en redes sociales o mediante marketing por correo electrónico.

Póngase en contacto con su representante de ventas de Adobe para obtener más detalles [!DNL People-Based Destinations]sobre cómo se puede registrar.

## Requisitos previos específicos del socio {#partner-prerequisites}

### [!DNL Facebook]

Antes de utilizar [!DNL People-Based Destinations] para enviar segmentos de audiencia, [!DNL Facebook]asegúrese de cumplir los siguientes requisitos:

1. Su [!DNL Facebook] cuenta de usuario debe tener habilitado el permiso **Administrar campañas** para la cuenta de publicidad que vaya a utilizar.
1. Agregue la cuenta comercial de **Adobe Experience Cloud** como socio de publicidad en [!DNL Facebook Ad Account]su. Utilice `business ID=206617933627973`. Consulte [Agregar socios a su Administrador comercial](https://www.facebook.com/business/help/708679622611131) para obtener más información.
   >[!IMPORTANT]
   > Al configurar los permisos para Adobe Experience Cloud, debe habilitar el permiso **Administrar campañas** . Esto es necesario para [!DNL People-Based Destinations] la integración.
1. Lea y firme [!DNL Facebook Custom Audiences] los términos de servicio. Para hacerlo, vaya a `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, donde `accountID` es [!DNL Facebook Ad Account ID]su.

## Integración de datos {#data-onboarding}

La ingesta de datos admite [!DNL People-Based Destinations] actualmente hasta 10 direcciones de correo electrónico hash vinculadas a un ID de cliente ([!DNL CRM ID]) por transferencia por lotes. Al cargar más de 10 direcciones de correo electrónico con hash vinculado a un ID de cliente, Audience Manager transfiere 10 de ellas, sin orden específico.

Al cargar más de 10 direcciones de correo electrónico con hash, vinculadas a un ID de cliente en varias transferencias por lotes, Audience Manager conserva las 10 direcciones de correo electrónico más recientes agregadas.

## Privacidad de datos {#data-privacy}

Aunque [!DNL People-Based Destinations] le permite dirigirse a audiencias basadas en direcciones de correo electrónico, ninguna información de visitante directamente identificada llega a Audience Manager. En la fase de integración de datos, debe asegurarse de que las direcciones de correo electrónico que vaya a utilizar tengan hash con el [!DNL SHA256] algoritmo. De lo contrario, no podrá usarlas [!DNL People-Based Destinations]en.

## Hash de datos frente a cifrado {#data-hashing-encryption}

La codificación es una función bidireccional. Cualquier información cifrada también se puede descifrar usando la clave de descifrado correcta. La codificación de datos en el contexto de Audience Manager supone un grave riesgo de privacidad, ya que cualquier tipo cifrado de información personal también puede descifrarse, revelando datos de clientes sensibles. En oposición a la codificación, [!DNL People-Based Destinations] se diseñan para trabajar con datos hash en lugar de proteger los datos del cliente que se usan para la segmentación.

Hash es una función unidireccional que elimina la entrada para producir un resultado único. Al utilizar algoritmos de hash adecuados, como [!DNL SHA256], no hay forma de revertir la función hash y revelar la información unscruned. Las direcciones de correo electrónico que se remitan a Audience Manager deben estar hash con el [!DNL SHA256] algoritmo. De este modo, ninguna información de identificación personal llega a Audience Manager, lo que mantiene seguros los datos del cliente.

## Requisitos de hash {#hashing-requirements}

Al hash las direcciones de correo electrónico, asegúrese de cumplir con los siguientes requisitos:

* Recortar todos los espacios al inicio y al final de la cadena de correo electrónico; ejemplo: `johndoe@example.com`, no `<space>johndoe@example.com<space>`;
* Asegúrese de que la cadena hash esté todo en minúsculas; ejemplo: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, no `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* No salt la cadena.

Adobe Experience Cloud le ofrece la opción de hash ID de cliente a través del servicio Experience Cloud ID. Consulte [SHA 256 Hing Support for setcustomerids](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) para obtener información detallada sobre cómo utilizar ECID para hash ID de cliente.

## Obtención de permisos de usuario {#obtaining-user-permission}

Puesto [!DNL People-Based Destinations] que ayuda a activar datos de audiencia de origen en canales basados en personas, es responsabilidad suya informar a sus clientes de cómo utilizará sus datos con fines publicitarios.

Antes de registrarse, [!DNL People-Based Destinations]asegúrese de obtener el consentimiento de sus clientes antes de utilizar su información con fines publicitarios.

Si los clientes desean optar por la exclusión de las campañas publicitarias, consulte [Administración](../../overview/data-security-and-privacy/opt-out-management.md) de exclusión para obtener detalles sobre cómo detener la recopilación de datos por Audience Manager.

## Reforzar la activación de datos de origen {#enforcing-first-party-activation}

Al utilizar [!DNL People-Based Destinations], solo se pueden usar datos de origen para activar segmentos de audiencia en canales basados en personas. No se pueden utilizar datos de segunda o de terceros para la activación de audiencias en canales basados en personas.

## ID hash autenticados de Onboard a través de Targeting de ID declarado {#onboard-authenticated-declared-id}

Existen dos maneras de introducir los datos sin conexión en Audience Manager.[!DNL People-Based Destinations]

* [Envíe datos por lotes](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) a Audience Manager para ingestar direcciones de correo electrónico con hash. Con este método, puede utilizar todas las direcciones de correo electrónico con hash de la [!DNL CRM] base de datos en [!DNL People-Based Destinations]. Además, al utilizar este método, también puede calificar las direcciones de correo electrónico hash para [características integradas](../traits/trait-qualification-reference.md).
* Utilice [ID declarados](../declared-ids.md) para declarar direcciones de correo electrónico con hash al pasar ID de cliente autenticados. Al utilizar este método, Audience Manager solo envía a [!DNL People-Based Destinations] las direcciones de correo electrónico hash de usuarios que se hayan autenticado en línea. Las direcciones de correo electrónico activadas a través de Facebook son sólo las de las llamadas de eventos de ID declarados. Otras direcciones de correo electrónico asociadas con el ID de cliente no se envían en tiempo real.
