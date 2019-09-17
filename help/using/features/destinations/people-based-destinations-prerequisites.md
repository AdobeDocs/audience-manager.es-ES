---
description: 'Lea a continuación para obtener una descripción general de los requisitos del cliente que debe cumplir antes de registrarse en Destinos basados en personas.  '
seo-description: 'Lea a continuación para obtener una descripción general de los requisitos del cliente que debe cumplir antes de registrarse en Destinos basados en personas.  '
seo-title: Requisitos previos y consideraciones sobre destinos basados en personas
solution: Audience Manager
title: Requisitos previos y consideraciones
translation-type: tm+mt
source-git-commit: f3fe6abe913d98549ae6c090a2d5f721485308c2

---


# Requisitos previos y consideraciones {#prerequisites-considerations}

Lea a continuación para obtener una descripción general de los requisitos del cliente que debe cumplir antes de registrarse para [!DNL People-Based Destinations].

>[!IMPORTANT]
> Lea este artículo detenidamente antes de pasar a la fase de implementación.

## Registrarse para destinos basados en personas {#signing-up}

[!DNL People-Based Destinations] es una función de primera calidad que mejora la experiencia de Audience Manager permitiéndole activar segmentos de audiencia de origen en entornos basados en personas, dirigiéndose a su audiencia con ofertas personalizadas en redes sociales o a través del marketing por correo electrónico.

Póngase en contacto con su representante de Adobe para aprovechar esta función Premium.

## Requisitos previos específicos del socio {#partner-prerequisites}

### [!DNL Facebook]

Antes de poder usar [!DNL People-Based Destinations] para enviar segmentos de audiencia a [!DNL Facebook], asegúrese de cumplir los siguientes requisitos:

1. Su cuenta [!DNL Facebook] de usuario debe tener el permiso **Administrar campañas** habilitado para la cuenta de publicidad que planea usar.
1. Agregue la cuenta comercial de **Adobe Experience Cloud** como socio de publicidad en su [!DNL Facebook Ad Account]. Utilice `business ID=206617933627973`. Consulte [Agregar socios a su administrador](https://www.facebook.com/business/help/708679622611131) comercial para obtener más información.
   >[!IMPORTANT]
   > Al configurar los permisos para Adobe Experience Cloud, debe habilitar el permiso **Administrar campañas** . Esto es necesario para la [!DNL People-Based Destinations] integración.
1. Lea y firme las [!DNL Facebook Custom Audiences] Condiciones de servicio. Para hacerlo, vaya a `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, donde `accountID` está su [!DNL Facebook Ad Account ID].

## Integración de datos {#data-onboarding}

La ingestión de datos para [!DNL People-Based Destinations] actualmente admite hasta 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente ([!DNL CRM ID]) por transferencia por lotes. La carga de más de 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente hace que Audience Manager ingrese 10 de ellas, sin orden específico.

Al cargar más de 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente en varias transferencias por lotes, Audience Manager conserva las 10 direcciones de correo electrónico agregadas más recientes.

## Privacidad de datos {#data-privacy}

Aunque [!DNL People-Based Destinations] le permite dirigirse a audiencias en función de direcciones de correo electrónico, ninguna información de visitante identificable directamente llega a Audience Manager. En la fase de integración de datos, debe asegurarse de que las direcciones de correo electrónico que planea utilizar estén marcadas con hash con el [!DNL SHA256] algoritmo. De lo contrario, no podrá usarlos en [!DNL People-Based Destinations].

## Coincidencia de datos frente a codificación {#data-hashing-encryption}

El cifrado es una función bidireccional. También se puede descifrar cualquier información cifrada mediante la clave de descifrado correcta. El cifrado de datos en el contexto de Audience Manager supone un grave riesgo para la privacidad, ya que cualquier forma cifrada de información personal también puede descifrarse, revelando datos confidenciales de los clientes. A diferencia del cifrado, [!DNL People-Based Destinations] están diseñados para funcionar con datos con hash en su lugar, protegiendo los datos del cliente que se utilizan para la segmentación.

Hashing es una función unidireccional que recorta la entrada para producir un resultado único. Al utilizar algoritmos de hash adecuados, [!DNL SHA256]no hay forma de revertir la función de hash y revelar la información sin codificar. Las direcciones de correo electrónico que vaya a incorporar a Audience Manager deben tener un hash con el algoritmo [!DNL SHA256] . De este modo, ninguna información de identificación personal llega a Audience Manager, lo que garantiza la seguridad de los datos del cliente.

## Requisitos de hash {#hashing-requirements}

Al hash de las direcciones de correo electrónico, asegúrese de cumplir los siguientes requisitos:

* Recorte todos los espacios al inicio y al final de la cadena de correo electrónico; ejemplo: `johndoe@example.com`, no `<space>johndoe@example.com<space>`;
* Asegúrese de que la cadena con hash esté en minúsculas; ejemplo: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, no `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* No escriba la cadena.

Adobe Experience Cloud le ofrece la opción de hash de los ID de cliente a través del servicio Experience Cloud ID. Consulte [Compatibilidad con hash SHA256 para setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) para obtener información detallada sobre cómo utilizar ECID para hash los ID de cliente.

## Obtención de permisos de usuario {#obtaining-user-permission}

Dado que [!DNL People-Based Destinations] le ayuda a activar datos de audiencia de origen en canales basados en personas, es responsabilidad suya informar a sus clientes de cómo va a utilizar sus datos con fines publicitarios.

Antes de registrarse [!DNL People-Based Destinations], asegúrese de obtener el consentimiento de sus clientes antes de utilizar su información con fines publicitarios.

En caso de que sus clientes deseen excluir las campañas de publicidad, consulte Administración de [exclusión](../../overview/data-security-and-privacy/opt-out-management.md) para obtener más información sobre cómo evitar que Audience Manager siga recopilando datos.

## Aplicación de la activación de datos de origen {#enforcing-first-party-activation}

Cuando utilice [!DNL People-Based Destinations], solo puede utilizar datos de origen para activar segmentos de audiencia en canales basados en personas. No se pueden usar datos de terceros o segundos para activar audiencias en canales basados en personas.

## ID con hash autenticados integrados mediante el objetivo de ID declarado {#onboard-authenticated-declared-id}

Existen dos formas de llevar los datos sin conexión a Audience Manager para [!DNL People-Based Destinations].

* [Envíe datos](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) por lotes a Audience Manager para ingestar direcciones de correo electrónico con hash. Con este método, puede utilizar todas las direcciones de correo electrónico con hash de la [!DNL CRM] base de datos en [!DNL People-Based Destinations]. Además, al utilizar este método, también puede calificar las direcciones de correo electrónico con hash para características [integradas](../traits/trait-qualification-reference.md).
* Utilice ID [declarados](../declared-ids.md) para declarar direcciones de correo electrónico con hash al pasar ID de cliente autenticados. Al utilizar este método, Audience Manager solo envía a [!DNL People-Based Destinations] las direcciones de correo electrónico con hash los usuarios que se han autenticado en línea. Las direcciones de correo electrónico activadas a través de Facebook son solo las que aparecen en las llamadas de evento de ID declaradas. Otras direcciones de correo electrónico asociadas con el ID de cliente no se envían en tiempo real.
