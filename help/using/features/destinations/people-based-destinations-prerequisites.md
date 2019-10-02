---
description: 'Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.  '
seo-description: 'Lea a continuación para obtener una descripción general de los requisitos del cliente que debe cumplir antes de registrarse en Destinos basados en personas.  '
seo-title: Requisitos previos y consideraciones sobre destinos basados en personas
solution: Audience Manager
title: Requisitos previos y consideraciones
translation-type: tm+mt
source-git-commit: ad9c077f538759e195a83d47e0ef36ccffa25c7e

---


# Prerequisites and Considerations {#prerequisites-considerations}

>[!IMPORTANT]
>This article contains product documentation meant to guide you through the setup and usage of this feature. Nothing contained herein is legal advice. Please consult your own legal counsel for legal guidance.

Read below for an overview of customer requirements that you need to meet before signing up for .[!DNL People-Based Destinations]

>[!IMPORTANT]
> Lea este artículo detenidamente antes de pasar a la fase de implementación.

## Registrarse para destinos basados en personas {#signing-up}

[!DNL People-Based Destinations] es una función de primera calidad que mejora la experiencia de Audience Manager permitiéndole activar los segmentos de audiencia de origen en entornos basados en personas, dirigiéndose a la audiencia con ofertas personalizadas en redes sociales o a través del marketing por correo electrónico.

Póngase en contacto con su representante de Adobe para aprovechar esta función Premium.

## Requisitos previos específicos del socio {#partner-prerequisites}

### [!DNL Facebook]

Antes de poder usar [!DNL People-Based Destinations] para enviar segmentos de audiencia de origen a [!DNL Facebook], asegúrese de cumplir los siguientes requisitos:

1. Su cuenta [!DNL Facebook] de usuario debe tener el permiso **Administrar campañas** habilitado para la cuenta de publicidad que planea usar.
1. Agregue la cuenta comercial de **Adobe Experience Cloud** como socio de publicidad en su [!DNL Facebook Ad Account]. Utilice `business ID=206617933627973`. Consulte [Agregar socios a su administrador](https://www.facebook.com/business/help/708679622611131) comercial para obtener más información.
   >[!IMPORTANT]
   > Al configurar los permisos para Adobe Experience Cloud, debe habilitar el permiso **Administrar campañas** . Esto es necesario para la [!DNL People-Based Destinations] integración.
1. Lea y firme las [!DNL Facebook Custom Audiences] Condiciones de servicio. Para hacerlo, vaya a `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, donde `accountID` está su [!DNL Facebook Ad Account ID].

## Integración de datos {#data-onboarding}

La ingestión de datos para [!DNL People-Based Destinations] actualmente admite hasta 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente ([!DNL CRM ID]) por transferencia por lotes. La carga de más de 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente hace que Audience Manager ingrese 10 de ellas, sin orden específico.

Al cargar más de 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente en varias transferencias por lotes, Audience Manager conserva las 10 direcciones de correo electrónico agregadas más recientes.

## Privacidad de datos {#data-privacy}

Aunque [!DNL People-Based Destinations] le permite dirigirse a audiencias en función de direcciones de correo electrónico con hash cargadas por usted, no podrá cargar en Audience Manager ninguna información de visitante directamente identificable. En la fase de integración de datos, debe asegurarse de que las direcciones de correo electrónico que planea utilizar estén marcadas con hash con el [!DNL SHA256] algoritmo. De lo contrario, no podrá usarlos en [!DNL People-Based Destinations].

## Coincidencia de datos frente a codificación {#data-hashing-encryption}

El cifrado es una función bidireccional. También se puede descifrar cualquier información cifrada mediante la clave de descifrado correcta. El cifrado de datos en el contexto de Audience Manager plantea serios riesgos, ya que también se puede descifrar cualquier forma cifrada de información personal. A diferencia del cifrado, [!DNL People-Based Destinations] están diseñados para funcionar con datos con hash.

Hashing es una función unidireccional que recorta la entrada para producir un resultado único. Al utilizar algoritmos de hash adecuados, [!DNL SHA256]no hay forma de revertir la función de hash y revelar la información sin codificar. The email addresses that you will onboard to Audience Manager must be hashed with the  algorithm. [!DNL SHA256] This way, you can ensure that no unhashed email addresses reach Audience Manager.

## Hashing Requirements {#hashing-requirements}

When hashing the email addresses, make sure to comply with the following requirements:

* Trim all leading and trailing spaces from the email string; example: , not ;`johndoe@example.com``<space>johndoe@example.com<space>`
* When hashing the email strings, make sure to hash the lowercase string;
   * Ejemplo: , not ;`example@email.com``EXAMPLE@EMAIL.COM`
* Make sure the hashed string is all lowercase
   * Ejemplo: , not ;`55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149``55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`
* Do not salt the string.

Adobe Experience Cloud le ofrece la opción de hash de los ID de cliente a través del servicio Experience Cloud ID. Consulte [Compatibilidad con hash SHA256 para setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) para obtener información detallada sobre cómo utilizar ECID para hash los ID de cliente.

## Obtención de permisos de usuario {#obtaining-user-permission}

Since  helps you activate first-party audience data in people-based channels, it is your responsibility to inform and obtain any necessary consents from your customers of how you will use their data for advertising or other purposes.[!DNL People-Based Destinations]

Before you sign up for , make sure to obtain your customers' consent before using their information for advertising purposes.[!DNL People-Based Destinations]

In case your customers wish to opt-out of advertising campaigns, see Opt-out Management for details on how to stop Audience Manager from collecting data any further.[](../../overview/data-security-and-privacy/opt-out-management.md)

## Enforcing First-Party Data Activation {#enforcing-first-party-activation}

Cuando utilice [!DNL People-Based Destinations], solo puede utilizar datos de origen para activar segmentos de audiencia en canales basados en personas. No se pueden usar datos de terceros o segundos para activar audiencias en canales basados en personas.

## ID con hash autenticados integrados mediante el objetivo de ID declarado {#onboard-authenticated-declared-id}

Existen dos formas de llevar los datos sin conexión a Audience Manager para [!DNL People-Based Destinations].

* [Envíe datos](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) por lotes a Audience Manager para ingestar direcciones de correo electrónico con hash. Con este método, puede elegir utilizar las direcciones de correo electrónico con hash de la [!DNL CRM] base de datos en [!DNL People-Based Destinations]. Además, al utilizar este método, también puede calificar las direcciones de correo electrónico con hash para características [integradas](../traits/trait-qualification-reference.md).
* Utilice ID [declarados](../declared-ids.md) para declarar direcciones de correo electrónico con hash al pasar ID de cliente autenticados. Al utilizar este método, Audience Manager, en su nombre, solo envía a [!DNL People-Based Destinations] las direcciones de correo electrónico con hash los usuarios que se han autenticado en línea. Las direcciones de correo electrónico activadas a través de canales basados en personas son solo las que aparecen en las llamadas de evento de ID declaradas. Otras direcciones de correo electrónico asociadas con el ID de cliente no se envían en tiempo real.
