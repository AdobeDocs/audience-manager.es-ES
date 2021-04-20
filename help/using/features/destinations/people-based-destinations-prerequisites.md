---
description: 'Lea a continuación para obtener una descripción general de los requisitos del cliente que debe cumplir antes de registrarse en People-Based Destinations.  '
seo-description: 'Lea a continuación para obtener una descripción general de los requisitos del cliente que debe cumplir antes de registrarse en People-Based Destinations.  '
seo-title: Requisitos previos y consideraciones sobre los destinos basados en personas
solution: Audience Manager
title: Requisitos previos y consideraciones
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 3%

---

# Requisitos previos y consideraciones {#prerequisites-considerations}

>[!IMPORTANT]
>Este artículo contiene documentación del producto pensada para guiarle en la configuración y uso de esta función. Nada de lo contenido en este documento es asesoramiento jurídico. Consulte a su propio asesor jurídico para obtener asesoramiento jurídico.

Lea a continuación para obtener una descripción general de los requisitos del cliente que debe cumplir antes de registrarse en [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Lea este artículo detenidamente antes de pasar a la fase de implementación.

## Registrarse para [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] es una función Premium que mejora la experiencia del Audience Manager permitiéndole activar los segmentos de audiencia propios en entornos basados en personas, dirigiéndose a la audiencia con ofertas personalizadas en redes sociales o a través del marketing por correo electrónico.

Póngase en contacto con su representante de Adobe para aprovechar esta función Premium.

## Requisitos previos específicos del socio {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Antes de utilizar [!UICONTROL People-Based Destinations] para enviar la audiencia de origen [!UICONTROL segments] a [!DNL Facebook], asegúrese de cumplir los siguientes requisitos:

1. Su cuenta de usuario [!DNL Facebook] debe tener el permiso **Administrar campañas** habilitado para la cuenta de anuncio que planea usar.
2. Agregue la cuenta comercial **Adobe Experience Cloud** como socio publicitario en su [!DNL Facebook Ad Account]. Utilice `business ID=206617933627973`. Consulte [Agregar socios a su administrador empresarial](https://www.facebook.com/business/help/1717412048538897) para obtener más información.
   >[!IMPORTANT]
   > Al configurar los permisos para Adobe Experience Cloud, debe habilitar el permiso **Administrar campañas**. Es necesario para la integración de [!UICONTROL People-Based Destinations].
3. Lea y firme las [!DNL Facebook Custom Audiences] Condiciones de servicio. Para ello, vaya a `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, donde `accountID` es su [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Antes de usar [!UICONTROL People-Based Destinations] para enviar los segmentos de audiencia de origen a [!DNL LinkedIn], asegúrese de que su cuenta [!DNL LinkedIn Campaign Manager] tenga el nivel de permiso [!DNL Creative Manager] o superior.

Para obtener información sobre cómo editar los permisos de usuario de [!DNL LinkedIn Campaign Manager], consulte [Agregar, editar y eliminar permisos de usuario en cuentas publicitarias](https://www.linkedin.com/help/lms/answer/5753) en la documentación de LinkedIn.

Consulte [Explicación y configuración del destino basado en personas de LinkedIn](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) para ver instrucciones de vídeo.

### [!DNL Google Customer Match] {#gcm}

Antes de poder utilizar [!UICONTROL People-Based Destinations] para enviar los segmentos de audiencia de origen a un destino [!DNL Google Customer Match], es obligatorio que [!DNL Google] lo añada a su lista de permitidos.

Póngase en contacto con su representante de [!DNL Google] y siga las instrucciones de lista de permitidos descritas en [Use Customer Match partners para cargar la documentación de datos](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) [!DNL Google].

Una vez completado este proceso, puede crear su [!UICONTROL People-Based Destination].

## Integración de datos {#data-onboarding}

Actualmente, la ingesta de datos para [!UICONTROL People-Based Destinations] admite hasta 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente ([!DNL CRM ID]) por transferencia por lotes. La carga de más de 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente hace que el Audience Manager las ingeste en 10 de ellas, sin orden específico.

Al cargar más de 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente en varias transferencias por lotes, el Audience Manager conserva las 10 direcciones de correo electrónico agregadas más recientes.

## Privacidad de datos {#data-privacy}

Aunque [!UICONTROL People-Based Destinations] permite segmentar audiencias en función de direcciones de correo electrónico con hash cargadas, se le prohíbe cargar en Audience Manager cualquier información de visitante directamente identificable. En la fase de incorporación de datos, debe asegurarse de que las direcciones de correo electrónico que planea utilizar tengan un cifrado hash con el algoritmo [!DNL SHA256]. De lo contrario, no podrá usarlos en [!UICONTROL People-Based Destinations].

## Data Hashing frente a cifrado {#data-hashing-encryption}

El cifrado es una función bidireccional. La información cifrada también se puede descifrar utilizando la clave de descifrado correcta. El cifrado de datos en el contexto del Audience Manager plantea graves riesgos, ya que también se puede descifrar cualquier forma cifrada de información personal. A diferencia del cifrado, [!UICONTROL People-Based Destinations] están diseñados para funcionar con datos con hash en su lugar.

El hash es una función unidireccional que recorta la entrada para producir un resultado único. Al utilizar algoritmos de hash adecuados, como [!DNL SHA256], no hay forma de invertir la función de hash y revelar la información sin codificar. Las direcciones de correo electrónico que incorporará al Audience Manager deben tener un cifrado hash con el algoritmo [!DNL SHA256]. De este modo, puede asegurarse de que ninguna dirección de correo electrónico sin hash llegue al Audience Manager.

## Requisitos hash {#hashing-requirements}

Al hash de las direcciones de correo electrónico, asegúrese de cumplir con los siguientes requisitos:

* Recorte todos los espacios al principio y al final de la cadena de correo electrónico; ejemplo: `johndoe@example.com`, no `<space>johndoe@example.com<space>`;
* Al hash de las cadenas de correo electrónico, asegúrese de usar un hash para la cadena en minúsculas;
   * Ejemplo: `example@email.com`, no `EXAMPLE@EMAIL.COM`;
* Asegúrese de que la cadena con hash esté en minúscula
   * Ejemplo: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, no `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* No sal la cadena.

Vea el siguiente vídeo para comprender los requisitos de hash de [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud le ofrece la opción de hash con los ID de cliente a través de [!DNL Adobe Experience Platform Identity Service (ECID)]. Consulte [Soporte hash SHA256 para setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) para obtener información detallada sobre cómo utilizar ECID para hash con los ID de cliente.

## Obtención de permiso de usuario {#obtaining-user-permission}

Dado que [!UICONTROL People-Based Destinations] le ayuda a activar los datos de audiencia de origen en canales basados en personas, es su responsabilidad informar y obtener cualquier consentimiento necesario de sus clientes sobre cómo usará sus datos para publicidad u otros fines.

Antes de registrarse en [!UICONTROL People-Based Destinations], asegúrese de obtener el consentimiento de sus clientes antes de utilizar su información con fines publicitarios.

Si sus clientes desean excluirse de las campañas publicitarias, consulte [Administración de la exclusión](../../overview/data-security-and-privacy/data-privacy-requests.md) para obtener más información sobre cómo impedir que el Audience Manager recopile datos más adelante.

## Aplicación de la activación de datos de origen {#enforcing-first-party-activation}

Al utilizar [!UICONTROL People-Based Destinations], solo puede utilizar datos de origen para activar segmentos de audiencia en canales basados en personas. No puede usar datos de segundo nivel o de terceros para la activación de audiencias en canales basados en personas.

Cuando utilice [!UICONTROL People-Based Destinations], utilice [Controles de exportación de datos](../data-export-controls.md) para etiquetar sus [!UICONTROL data sources] y [!UICONTROL destinations] según las directrices y los requisitos de las plataformas de destino y los proveedores de datos.

## ID con hash autenticados integrados mediante el objetivo de ID declarados {#onboard-authenticated-declared-id}

Existen dos maneras de incluir los datos sin conexión a Audience Manager para [!UICONTROL People-Based Destinations].

* [Envíe el Audience Manager de ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) datos por lotes para introducir direcciones de correo electrónico con hash. Con este método, puede elegir utilizar las direcciones de correo electrónico con hash de la base de datos [!DNL CRM] en [!UICONTROL People-Based Destinations]. Además, al utilizar este método, también puede clasificar las direcciones de correo electrónico con hash para [características integradas](../traits/trait-and-segment-qualification-reference.md).
* Utilice [ID declarados](../declared-ids.md) para declarar las direcciones de correo electrónico con hash al pasar los ID de cliente autenticados. Al utilizar este método, el Audience Manager, en su nombre, solo envía a [!UICONTROL People-Based Destinations] las direcciones de correo electrónico con hash de los usuarios que se han autenticado en línea. Las direcciones de correo electrónico activadas a través de canales basados en personas son solo las que aparecen en las llamadas de evento de ID declaradas. Otras direcciones de correo electrónico asociadas con el ID de cliente no se envían en tiempo real.
