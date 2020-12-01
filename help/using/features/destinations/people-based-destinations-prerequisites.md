---
description: 'Lea a continuación para obtener una descripción general de los requisitos del cliente que debe cumplir antes de registrarse en Destinos basados en personas.  '
seo-description: 'Lea a continuación para obtener una descripción general de los requisitos del cliente que debe cumplir antes de registrarse en Destinos basados en personas.  '
seo-title: Requisitos previos y consideraciones sobre destinos basados en personas
solution: Audience Manager
title: Requisitos previos y consideraciones
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: d3184195d6a51ff013a3d1fc8526ca9afd3386c2
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 3%

---


# Requisitos previos y consideraciones {#prerequisites-considerations}

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a guiarle en la configuración y el uso de esta función. Nada de lo que aquí se incluye es asesoramiento jurídico. Por favor, consulte a su propio abogado para obtener asesoramiento jurídico.

Lea a continuación para obtener una visión general de los requisitos del cliente que debe cumplir antes de registrarse para [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Lea este artículo detenidamente antes de pasar a la fase de implementación.

## Registrarse para [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] es una función de primera calidad que mejora la experiencia del Audience Manager permitiéndole activar los segmentos de audiencia de origen en entornos basados en personas, dirigiéndose a su audiencia con ofertas personalizadas en redes sociales o a través del marketing por correo electrónico.

Póngase en contacto con su representante de Adobe para aprovechar esta función de primera calidad.

## Requisitos previos específicos del socio {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Antes de utilizar [!UICONTROL People-Based Destinations] para enviar su audiencia de origen [!UICONTROL segments] a [!DNL Facebook], asegúrese de cumplir los siguientes requisitos:

1. Su cuenta de [!DNL Facebook] usuario debe tener el permiso **Administrar campañas** habilitado para la cuenta de publicidad que planea usar.
2. Añada la cuenta de negocios **Adobe Experience Cloud** como socio publicitario en su [!DNL Facebook Ad Account]. Utilice `business ID=206617933627973`. Consulte [Añadir socios a su administrador comercial](https://www.facebook.com/business/help/1717412048538897) para obtener más información.
   >[!IMPORTANT]
   > Al configurar los permisos para Adobe Experience Cloud, debe habilitar el permiso **Administrar campañas**. Es necesario para la integración de [!UICONTROL People-Based Destinations].
3. Lea y firme las [!DNL Facebook Custom Audiences] Condiciones de servicio. Para ello, vaya a `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, donde `accountID` es su [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Antes de utilizar [!UICONTROL People-Based Destinations] para enviar los segmentos de audiencia de origen a [!DNL LinkedIn], asegúrese de que su cuenta [!DNL LinkedIn Campaign Manager] tiene el [!DNL Creative Manager] nivel de permisos o superior.

Para obtener información sobre cómo editar los [!DNL LinkedIn Campaign Manager] permisos de usuario, consulte [Añadir, editar y eliminar permisos de usuario en cuentas de publicidad](https://www.linkedin.com/help/lms/answer/5753) en la documentación de LinkedIn.

Consulte [Explicación y configuración del destino basado en personas de LinkedIn](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) para obtener instrucciones de vídeo.

### [!DNL Google Customer Match] {#gcm}

Antes de poder utilizar [!UICONTROL People-Based Destinations] para enviar los segmentos de audiencia de origen a un [!DNL Google Customer Match] destino, es obligatorio que [!DNL Google] lo agregue a su lista de permitidos.

Póngase en contacto con su [!DNL Google] representante y siga las instrucciones de lista de permitidos descritas en [Use Customer Match partners para cargar la documentación de ](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) [!DNL Google] datos.

Una vez completado este proceso, puede crear su [!UICONTROL People-Based Destination].

## Integración de datos {#data-onboarding}

La ingestión de datos para [!UICONTROL People-Based Destinations] actualmente admite hasta 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente ([!DNL CRM ID]) por transferencia por lotes. La carga de más de 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente hace que el Audience Manager ingrese 10 de ellas, sin ningún orden específico.

Al cargar más de 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente en varias transferencias por lotes, el Audience Manager conserva las 10 direcciones de correo electrónico agregadas más recientes.

## Privacidad de datos {#data-privacy}

Aunque [!UICONTROL People-Based Destinations] le permite destinatario de audiencias basadas en direcciones de correo electrónico con hash cargadas por usted, se le prohíbe cargar cualquier información de visitante directamente identificable en el Audience Manager. En la fase de integración de datos, debe asegurarse de que las direcciones de correo electrónico que planea utilizar estén marcadas con hash con el algoritmo [!DNL SHA256]. De lo contrario, no podrá usarlos en [!UICONTROL People-Based Destinations].

## Codificación de datos con hash {#data-hashing-encryption}

El cifrado es una función bidireccional. También se puede descifrar cualquier información cifrada mediante la clave de descifrado correcta. El cifrado de datos en el contexto del Audience Manager plantea graves riesgos, ya que también se puede descifrar cualquier forma cifrada de información personal identificable. A diferencia del cifrado, [!UICONTROL People-Based Destinations] están diseñados para funcionar con datos con hash en su lugar.

Hashing es una función unidireccional que recorta la entrada para producir un resultado único. Al utilizar algoritmos de hash adecuados, como [!DNL SHA256], no hay forma de revertir la función de hash y revelar la información sin codificar. Las direcciones de correo electrónico que se incorporarán al Audience Manager deben estar marcadas con el algoritmo [!DNL SHA256]. De este modo, puede asegurarse de que ninguna dirección de correo electrónico sin hash llegue al Audience Manager.

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

Adobe Experience Cloud le ofrece la opción de hash de los ID de cliente a través de [!DNL Adobe Experience Platform Identity Service (ECID)]. Consulte [Compatibilidad con hash SHA256 para setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) para obtener información detallada sobre cómo utilizar ECID para hash los ID de cliente.

## Obtención de permisos de usuario {#obtaining-user-permission}

Dado que [!UICONTROL People-Based Destinations] le ayuda a activar datos de audiencia de origen en canales basados en personas, es su responsabilidad informar y obtener los consentimientos necesarios de sus clientes sobre cómo va a utilizar sus datos para fines publicitarios u otros fines.

Antes de registrarse para [!UICONTROL People-Based Destinations], asegúrese de obtener el consentimiento de sus clientes antes de utilizar su información con fines publicitarios.

En caso de que sus clientes deseen excluir las campañas de publicidad, consulte [Administración de exclusión](../../overview/data-security-and-privacy/data-privacy-requests.md) para obtener más información sobre cómo evitar que el Audience Manager recopile más datos.

## Implementación de la Activación de datos de origen {#enforcing-first-party-activation}

Al utilizar [!UICONTROL People-Based Destinations], solo puede utilizar datos de origen para activar segmentos de audiencia en canales basados en personas. No se pueden usar datos de terceros o segundos para la activación de audiencias en canales basados en personas.

Cuando utilice [!UICONTROL People-Based Destinations], utilice [Data Export Controls](../data-export-controls.md) para etiquetar sus [!UICONTROL data sources] y [!UICONTROL destinations] según las pautas y los requisitos de las plataformas de destino y los proveedores de datos.

## ID con hash autenticados integrados mediante el objetivo de ID declarado {#onboard-authenticated-declared-id}

Existen dos maneras de incluir los datos sin conexión a Audience Manager para [!UICONTROL People-Based Destinations].

* [Enviar ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) Audience Manager de datos por lotes para ingestar direcciones de correo electrónico con hash. Con este método, puede elegir utilizar las direcciones de correo electrónico con hash de la base de datos [!DNL CRM] en [!UICONTROL People-Based Destinations]. Además, al utilizar este método, también puede calificar las direcciones de correo electrónico con hash para [características integradas](../traits/trait-and-segment-qualification-reference.md).
* Utilice [ID declarados](../declared-ids.md) para declarar direcciones de correo electrónico con hash al pasar ID de cliente autenticados. Al utilizar este método, Audience Manager, en su nombre, sólo envía [!UICONTROL People-Based Destinations] las direcciones de correo electrónico con hash a los usuarios que se han autenticado en línea. Las direcciones de correo electrónico activadas mediante canales basados en personas son solo las que se encuentran en las llamadas declaradas al evento de ID. Otras direcciones de correo electrónico asociadas con el ID de cliente no se envían en tiempo real.
