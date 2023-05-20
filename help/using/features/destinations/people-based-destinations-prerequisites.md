---
description: Lea a continuación para obtener una descripción general de los requisitos de los clientes que debe cumplir antes de registrarse en People-Based Destinations.
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Requisitos previos y consideraciones
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: cd40e1e3cc2199d1937950934d674cfad301f3e8
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 3%

---

# Requisitos previos y consideraciones {#prerequisites-considerations}

>[!IMPORTANT]
>Este artículo contiene documentación del producto que le guiará a través de la configuración y el uso de esta función. Nada de lo que contiene aquí es asesoramiento legal. Por favor, consulte a su propio asesor legal para obtener orientación legal.

Lea a continuación para obtener una descripción general de los requisitos de los clientes que debe cumplir antes de registrarse en [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Lea este artículo detenidamente antes de pasar a la fase de implementación.

## Suscripción a [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] es una funcionalidad Premium que mejora la experiencia del Audience Manager al permitirle activar segmentos de audiencia propios en entornos basados en personas, dirigiéndose a su audiencia con ofertas personalizadas en redes sociales o mediante marketing por correo electrónico.

Póngase en contacto con el representante del Adobe para aprovechar esta función Premium.

## Requisitos previos específicos del socio {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Antes de usar [!UICONTROL People-Based Destinations] para enviar la audiencia de origen [!UICONTROL segments] hasta [!DNL Facebook], asegúrese de cumplir los siguientes requisitos:

1. Su [!DNL Facebook] la cuenta de usuario debe tener el **Administración de campañas** permiso habilitado para la cuenta de Ad que planea usar.
2. Añada el **Adobe Experience Cloud** cuenta comercial como socio publicitario en su [!DNL Facebook Ad Account]. Utilice `business ID=206617933627973`. Consulte [Añadir socios a su administrador comercial](https://www.facebook.com/business/help/1717412048538897) para obtener más información.
   >[!IMPORTANT]
   > Al configurar los permisos para Adobe Experience Cloud, debe habilitar la variable **Administración de campañas** permiso. Es necesario para la integración de [!UICONTROL People-Based Destinations].
3. Lea y firme el [!DNL Facebook Custom Audiences] Condiciones del servicio. Para ello, vaya a `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, donde `accountID` es su [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Antes de usar [!UICONTROL People-Based Destinations] para enviar los segmentos de audiencia de origen a [!DNL LinkedIn], compruebe que su [!DNL LinkedIn Campaign Manager] La cuenta tiene el [!DNL Creative Manager] o un nivel de permiso superior.

Para obtener información sobre cómo editar su [!DNL LinkedIn Campaign Manager] permisos de usuario, consulte [Agregar, editar y quitar permisos de usuario en cuentas publicitarias](https://www.linkedin.com/help/lms/answer/5753) en la documentación de LinkedIn.

Consulte [Explicación y configuración del destino basado en personas de LinkedIn](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) para obtener instrucciones de vídeo.

### [!DNL Google Customer Match] {#gcm}

Antes de usar [!UICONTROL People-Based Destinations] para enviar los segmentos de audiencia de origen a un [!DNL Google Customer Match] destino, asegúrese de leer y cumplir la política de Google para utilizar [!DNL Customer Match], se describe en la [Documentación de asistencia de Google](https://support.google.com/google-ads/answer/6299717).

A continuación, asegúrese de que su [!DNL Google] La cuenta de está configurada para una [!DNL Standard] o un nivel de permiso superior. Consulte la [Documentación de Google Ads](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&amp;rd=1) para obtener más información.

Google permite automáticamente a los clientes con cuentas compatibles.

## Integración de datos {#data-onboarding}

Ingesta de datos para [!UICONTROL People-Based Destinations] admite actualmente hasta 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente ([!DNL CRM ID]), por transferencia de lotes. La carga de más de 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente hace que el Audience Manager introduzca 10 de ellas, sin un orden específico.

La carga de más de 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente en varias transferencias por lotes hace que el Audience Manager conserve las 10 direcciones de correo electrónico añadidas más recientemente.

## Privacidad de datos {#data-privacy}

Aunque [!UICONTROL People-Based Destinations] Si le permite segmentar audiencias en función de las direcciones de correo electrónico con hash que haya cargado, no le está permitido cargar en Audience Manager información de visitantes directamente identificable. En la fase de incorporación de datos, debe asegurarse de que las direcciones de correo electrónico que planea utilizar tengan un cifrado hash con el [!DNL SHA256] algoritmo. De lo contrario, no podrá usarlos en [!UICONTROL People-Based Destinations].

## Hash de datos frente a cifrado {#data-hashing-encryption}

El cifrado es una función bidireccional. Cualquier información cifrada también se puede descifrar, utilizando la clave de descifrado correcta. El cifrado de datos en el contexto de Audience Manager plantea riesgos graves, ya que cualquier forma cifrada de información personal identificable también se puede descifrar. A diferencia del cifrado, [!UICONTROL People-Based Destinations] están diseñadas para trabajar con datos con hash.

El hash es una función unidireccional que desplaza la entrada para producir un resultado único. Mediante algoritmos hash adecuados, como [!DNL SHA256]Sin embargo, no hay forma de revertir la función de hash y mostrar la información no codificada. Las direcciones de correo electrónico que incorporará al Audience Manager deben tener un cifrado hash con la variable [!DNL SHA256] algoritmo. De este modo, puede asegurarse de que ninguna dirección de correo electrónico sin hash llegue al Audience Manager.

## Requisitos de hash {#hashing-requirements}

Al crear valores hash de las direcciones de correo electrónico, asegúrese de cumplir con los siguientes requisitos:

* Recortar todos los espacios iniciales y finales de la cadena de correo electrónico; ejemplo: `johndoe@example.com`, no `<space>johndoe@example.com<space>`;
* Al crear valores hash de las cadenas de correo electrónico, asegúrese de usar la cadena en minúsculas;
   * Ejemplo: `example@email.com`, no `EXAMPLE@EMAIL.COM`;
* Asegúrese de que la cadena con hash esté en minúscula
   * Ejemplo: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, no `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* No salar la cuerda.

Vea el siguiente vídeo para comprender los requisitos de hash de [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud le ofrece la opción de hash los ID de cliente con el [!DNL Adobe Experience Platform Identity Service (ECID)]. Consulte [Soporte hash SHA 256 para setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) para obtener información detallada sobre cómo utilizar ECID para hash los ID de cliente.

## Obteniendo permiso de usuario {#obtaining-user-permission}

Desde [!UICONTROL People-Based Destinations] le ayuda a activar datos de audiencia propios en canales basados en personas; es su responsabilidad informar y obtener el consentimiento necesario de sus clientes sobre cómo utilizará sus datos para publicidad u otros fines.

Antes de registrarse en [!UICONTROL People-Based Destinations], asegúrese de obtener el consentimiento de sus clientes antes de utilizar su información con fines publicitarios.

En caso de que los clientes deseen excluirse de las campañas publicitarias, consulte [Administración de la exclusión](../../overview/data-security-and-privacy/data-privacy-requests.md) para obtener más información sobre cómo impedir que el Audience Manager siga recopilando datos.

## Forzar la activación de datos de origen {#enforcing-first-party-activation}

Al utilizar [!UICONTROL People-Based Destinations]Sin embargo, solo puede utilizar datos de origen para activar segmentos de audiencia en canales basados en personas. No se puede utilizar ningún dato de segundo nivel o de terceros para la activación de audiencias en canales basados en personas.

Al utilizar [!UICONTROL People-Based Destinations], use [Controles de exportación de datos](../data-export-controls.md) para etiquetar su [!UICONTROL data sources] y [!UICONTROL destinations] según las directrices y los requisitos de las plataformas de destino y los proveedores de datos.

## Incorporación de ID con hash autenticados mediante la segmentación de ID declarados {#onboard-authenticated-declared-id}

Existen dos maneras de incluir los datos sin conexión a Audience Manager para [!UICONTROL People-Based Destinations].

* [Enviar datos por lotes](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) al Audience Manager para introducir direcciones de correo electrónico con hash. Con este método, puede elegir utilizar las direcciones de correo electrónico con hash de su [!DNL CRM] base de datos en [!UICONTROL People-Based Destinations]. Además, al utilizar este método, también puede clasificar las direcciones de correo electrónico con hash para [Características integradas](../traits/trait-and-segment-qualification-reference.md).
* Uso [ID declarados](../declared-ids.md) para declarar direcciones de correo electrónico con hash al pasar ID de cliente autenticados. Al utilizar este método, Audience Manager, en su nombre, solo envía a [!UICONTROL People-Based Destinations] las direcciones de correo electrónico con hash de los usuarios que se han autenticado en línea. Las direcciones de correo electrónico activadas a través de canales basados en personas solo son las que aparecen en las llamadas de evento de ID declaradas. Otras direcciones de correo electrónico asociadas con el ID de cliente no se envían en tiempo real.
