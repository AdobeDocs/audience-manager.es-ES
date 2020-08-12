---
description: 'Lea a continuación para obtener una descripción general de los requisitos del cliente que debe cumplir antes de registrarse en Destinos basados en personas.  '
seo-description: 'Lea a continuación para obtener una descripción general de los requisitos del cliente que debe cumplir antes de registrarse en Destinos basados en personas.  '
seo-title: Requisitos previos y consideraciones sobre destinos basados en personas
solution: Audience Manager
title: Requisitos previos y consideraciones
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: 2e32f9ebff487ae8dfb2088ec1bbfcea1daa00a1
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 3%

---


# Requisitos previos y consideraciones {#prerequisites-considerations}

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a guiarle en la configuración y el uso de esta función. Nada de lo que aquí se incluye es asesoramiento jurídico. Por favor, consulte a su propio abogado para obtener asesoramiento jurídico.

Lea a continuación para obtener una descripción general de los requisitos del cliente que debe cumplir antes de registrarse para [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Lea este artículo detenidamente antes de pasar a la fase de implementación.

## Registrarse para [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] es una función de primera calidad que mejora la experiencia del Audience Manager permitiéndole activar los segmentos de audiencia de origen en entornos basados en personas, dirigiéndose a su audiencia con ofertas personalizadas en redes sociales o a través del marketing por correo electrónico.

Póngase en contacto con su representante de Adobe para aprovechar esta función de primera calidad.

## Requisitos previos específicos del socio {#partner-prerequisites}

### [!DNL Facebook]

Antes de poder usar [!UICONTROL People-Based Destinations] para enviar su audiencia de origen [!UICONTROL segments] a [!DNL Facebook], asegúrese de cumplir los siguientes requisitos:

1. Su cuenta [!DNL Facebook] de usuario debe tener el permiso **Administrar campañas** habilitado para la cuenta de publicidad que planea usar.
2. Add the **Adobe Experience Cloud** business account as an advertising partner in your [!DNL Facebook Ad Account]. Utilice `business ID=206617933627973`. See [Add Partners to Your Business Manager](https://www.facebook.com/business/help/1717412048538897) for details.
   >[!IMPORTANT]
   > When configuring the permissions for Adobe Experience Cloud, you must enable the **Manage campaigns** permission. Es necesario para la integración de [!UICONTROL People-Based Destinations].
3. Lea y firme las [!DNL Facebook Custom Audiences] Condiciones de servicio. Para ello, vaya a `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, donde `accountID` es su [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn]

Antes de poder usar [!UICONTROL People-Based Destinations] para enviar segmentos de audiencia de origen a [!DNL LinkedIn], asegúrese de que su [!DNL LinkedIn Campaign Manager] cuenta tenga el nivel de permisos [!DNL Creative Manager] o superior.

Para obtener información sobre cómo editar los permisos [!DNL LinkedIn Campaign Manager] de usuario, consulte [Añadir, editar y eliminar permisos de usuario en cuentas](https://www.linkedin.com/help/lms/answer/5753) de publicidad en la documentación de LinkedIn.

Consulte [Explicación y configuración del destino](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) basado en personas de LinkedIn para obtener instrucciones en vídeo.

### [!DNL Google Customer Match]

Antes de poder usar [!UICONTROL People-Based Destinations] para enviar segmentos de audiencia de origen a un [!DNL Google Customer Match] destino, es obligatorio que [!DNL Google] le añada a su lista de permitidos.

Póngase en contacto con su [!DNL Google] representante y siga las instrucciones de lista de permitidos que se describen en [Utilizar socios de Coincidencia con el cliente para cargar la documentación de datos](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507)[!DNL Google] .

Una vez completado este proceso, puede crear su [!UICONTROL People-Based Destination].

## Integración de datos {#data-onboarding}

La ingestión de datos para [!UICONTROL People-Based Destinations] actualmente admite hasta 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente ([!DNL CRM ID]) por transferencia por lotes. La carga de más de 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente hace que el Audience Manager ingrese 10 de ellas, sin ningún orden específico.

Al cargar más de 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente en varias transferencias por lotes, el Audience Manager conserva las 10 direcciones de correo electrónico agregadas más recientes.

## Privacidad de datos {#data-privacy}

Aunque [!UICONTROL People-Based Destinations] le permite realizar destinatarios de audiencias en función de direcciones de correo electrónico con hash cargadas por usted, sigue estando prohibido cargar cualquier información de visitante directamente identificable en el Audience Manager. En la fase de integración de datos, debe asegurarse de que las direcciones de correo electrónico que planea utilizar estén marcadas con hash con el [!DNL SHA256] algoritmo. De lo contrario, no podrá usarlos en [!UICONTROL People-Based Destinations].

## Coincidencia de datos frente a codificación {#data-hashing-encryption}

El cifrado es una función bidireccional. También se puede descifrar cualquier información cifrada mediante la clave de descifrado correcta. El cifrado de datos en el contexto del Audience Manager plantea graves riesgos, ya que también se puede descifrar cualquier forma cifrada de información personal identificable. A diferencia del cifrado, [!UICONTROL People-Based Destinations] están diseñados para funcionar con datos con hash.

Hashing es una función unidireccional que recorta la entrada para producir un resultado único. Al utilizar algoritmos de hash adecuados, como [!DNL SHA256], no hay forma de revertir la función de hash y revelar la información sin codificar. Las direcciones de correo electrónico que va a incluir en el Audience Manager deben estar marcadas con el algoritmo [!DNL SHA256] . De este modo, puede asegurarse de que ninguna dirección de correo electrónico sin hash llegue al Audience Manager.

## Requisitos de hash {#hashing-requirements}

Al hash de las direcciones de correo electrónico, asegúrese de cumplir los siguientes requisitos:

* Recorte todos los espacios al inicio y al final de la cadena de correo electrónico; ejemplo: `johndoe@example.com`, no `<space>johndoe@example.com<space>`;
* Al aplicar hash a las cadenas de correo electrónico, asegúrese de que la cadena está en minúsculas;
   * Ejemplo: `example@email.com`, no `EXAMPLE@EMAIL.COM`;
* Asegúrese de que la cadena con hash esté en minúsculas
   * Ejemplo: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, no `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* No escriba la cadena.

Vea el siguiente vídeo para conocer los requisitos de hash de [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud le ofrece la opción de hash de los ID de cliente a través del [!DNL Adobe Experience Platform Identity Service (ECID)]. Consulte [Compatibilidad con hash SHA256 para setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) para obtener información detallada sobre cómo utilizar ECID para hash los ID de cliente.

## Obtención de permisos de usuario {#obtaining-user-permission}

Dado que [!UICONTROL People-Based Destinations] le ayuda a activar datos de audiencia de origen en canales basados en personas, es responsabilidad suya informar y obtener los consentimientos necesarios de sus clientes sobre cómo va a utilizar sus datos para fines publicitarios u otros fines.

Antes de registrarse [!UICONTROL People-Based Destinations], asegúrese de obtener el consentimiento de sus clientes antes de utilizar su información con fines publicitarios.

En caso de que sus clientes deseen excluir las campañas de publicidad, consulte Administración de [exclusión](../../overview/data-security-and-privacy/data-privacy-requests.md) para obtener más información sobre cómo evitar que el Audience Manager recopile más datos.

## Aplicación de la Activación de datos de origen {#enforcing-first-party-activation}

Cuando utilice [!UICONTROL People-Based Destinations], solo puede utilizar datos de origen para activar segmentos de audiencia en canales basados en personas. No se pueden usar datos de terceros o segundos para la activación de audiencias en canales basados en personas.

Cuando utilice [!UICONTROL People-Based Destinations], utilice Controles [de exportación](../data-export-controls.md) de datos para etiquetar el contenido [!UICONTROL data sources] y [!UICONTROL destinations] según las directrices y los requisitos de las plataformas de destino y los proveedores de datos.

## ID con hash autenticados integrados mediante el objetivo de ID declarado {#onboard-authenticated-declared-id}

Existen dos maneras de incluir los datos sin conexión a Audience Manager para [!UICONTROL People-Based Destinations].

* [Enviar datos](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) por lotes al Audience Manager para ingestar direcciones de correo electrónico con hash. Con este método, puede elegir utilizar las direcciones de correo electrónico con hash de la [!DNL CRM] base de datos en [!UICONTROL People-Based Destinations]. Además, al utilizar este método, también puede calificar las direcciones de correo electrónico con hash para características [integradas](../traits/trait-and-segment-qualification-reference.md).
* Use [Declared IDs](../declared-ids.md) to declare hashed email addresses when passing in authenticated customer IDs. When using this method, Audience Manager, on your behalf, only sends to [!UICONTROL People-Based Destinations] the hashed email addresses from users who have authenticated online. Las direcciones de correo electrónico activadas mediante canales basados en personas son solo las que se encuentran en las llamadas declaradas al evento de ID. Otras direcciones de correo electrónico asociadas con el ID de cliente no se envían en tiempo real.
