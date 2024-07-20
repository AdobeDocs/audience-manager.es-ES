---
description: Lea a continuación para obtener una descripción general de los requisitos de los clientes que debe cumplir antes de registrarse en People-Based Destinations.
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Requisitos previos y consideraciones
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: 2b823855994f394261a66e896ef7de7bb7a5450f
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 2%

---


# Requisitos previos y consideraciones {#prerequisites-considerations}

>[!IMPORTANT]
>Este artículo contiene documentación del producto que le guiará a través de la configuración y el uso de esta función. Nada de lo que contiene aquí es asesoramiento legal. Por favor, consulte a su propio asesor legal para obtener orientación legal.

Lea a continuación para obtener una descripción general de los requisitos de los clientes que debe cumplir antes de registrarse en [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Lea este artículo detenidamente antes de pasar a la fase de implementación.

## Registrándose para [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] es una funcionalidad Premium que mejora la experiencia del Audience Manager al permitirle activar segmentos de audiencia de origen en entornos basados en personas, dirigiendo la audiencia a ofertas personalizadas en redes sociales o mediante marketing por correo electrónico.

Póngase en contacto con el representante del Adobe para aprovechar esta función Premium.

## Requisitos previos específicos del socio {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Antes de poder usar [!UICONTROL People-Based Destinations] para enviar la audiencia de origen [!UICONTROL segments] a [!DNL Facebook], asegúrese de cumplir los siguientes requisitos:

1. La cuenta de usuario [!DNL Facebook] debe tener habilitado el permiso **Administrar campañas** para la cuenta de publicidad que planea usar.
2. Agrega la cuenta comercial de **Adobe Experience Cloud** como socio de publicidad en tu [!DNL Facebook Ad Account]. Utilice `business ID=206617933627973`. Consulte [Agregar socios a su administrador comercial](https://www.facebook.com/business/help/1717412048538897) para obtener más información.

   >[!IMPORTANT]
   >Al configurar los permisos para Adobe Experience Cloud, debe habilitar el permiso **Administrar campañas**. Es necesario para la integración de [!UICONTROL People-Based Destinations].

3. Lea y firme los términos de servicio de [!DNL Facebook Custom Audiences]. Para ello, vaya a `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, donde `accountID` es su [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Antes de poder usar [!UICONTROL People-Based Destinations] para enviar los segmentos de audiencia de origen a [!DNL LinkedIn], asegúrese de que su cuenta de [!DNL LinkedIn Campaign Manager] tenga el nivel de permiso de [!DNL Creative Manager] o superior.

Para obtener información sobre cómo editar los permisos de usuario de [!DNL LinkedIn Campaign Manager], consulte [Agregar, editar y quitar permisos de usuario en cuentas de Advertising](https://www.linkedin.com/help/lms/answer/5753) en la documentación de LinkedIn.

Consulte [Explicación y configuración del destino basado en personas de LinkedIn](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) para obtener instrucciones en vídeo.

### [!DNL Google Customer Match] {#gcm}

Antes de poder usar [!UICONTROL People-Based Destinations] para enviar los segmentos de audiencia de origen a un destino de [!DNL Google Customer Match], asegúrese de leer y cumplir la directiva de Google sobre el uso de [!DNL Customer Match], descrita en [Documentación de asistencia de Google](https://support.google.com/google-ads/answer/6299717).

A continuación, asegúrese de que su cuenta de [!DNL Google] esté configurada para un nivel de permisos de [!DNL Standard] o superior. Consulte la [documentación de Google Ads](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&amp;rd=1) para obtener más información.

Google permite automáticamente a los clientes con cuentas compatibles.

## Incorporación de datos {#data-onboarding}

>[!IMPORTANT]
>
>Todos los clientes de Audience Manager pueden ingerir correos electrónicos con hash sin registrarse en [!UICONTROL People-Based Destinations].

La ingesta de datos de [!UICONTROL People-Based Destinations] admite actualmente hasta 10 direcciones de correo electrónico con hash vinculadas a un id. de cliente ([!DNL CRM ID]), por transferencia en lote.

La carga de más de 10 direcciones de correo electrónico con hash vinculadas a un ID de cliente en varias transferencias por lotes hace que el Audience Manager conserve las 10 direcciones de correo electrónico añadidas más recientemente.

Para introducir identificadores hash, [cree una fuente de datos entre dispositivos para los identificadores hash](../create-data-source-hashed-emails.md) y habilite la opción **[!UICONTROL Share associated cross-device IDs in people-based destinations and/or hashed email workflows]**.

![Imagen de la interfaz de usuario del Audience Manager que muestra la opción de compartir los ID asociados entre dispositivos en destinos basados en personas o flujos de trabajo de correo electrónico con hash](assets/data-source-share-ids.png)

## Privacidad de datos {#data-privacy}

Aunque [!UICONTROL People-Based Destinations] le permite segmentar audiencias en función de las direcciones de correo electrónico con hash que haya cargado, sigue teniendo prohibido cargar información de visitantes directamente identificable en Audience Manager. En la fase de incorporación de datos, debe asegurarse de que las direcciones de correo electrónico que planea utilizar tengan un cifrado hash con el algoritmo [!DNL SHA256]. De lo contrario, no podrá usarlos en [!UICONTROL People-Based Destinations].

## Hash de datos frente a cifrado {#data-hashing-encryption}

El cifrado es una función bidireccional. Cualquier información cifrada también se puede descifrar, utilizando la clave de descifrado correcta. El cifrado de datos en el contexto de Audience Manager plantea riesgos graves, ya que cualquier forma cifrada de información personal identificable también se puede descifrar. A diferencia del cifrado, [!UICONTROL People-Based Destinations] están diseñados para trabajar con datos con hash.

El hash es una función unidireccional que desplaza la entrada para producir un resultado único. Al utilizar algoritmos hash adecuados, como [!DNL SHA256], no hay forma de revertir la función de hash y mostrar la información no codificada. Las direcciones de correo electrónico que incorporará al Audience Manager deben tener un cifrado hash con el algoritmo [!DNL SHA256]. De este modo, puede asegurarse de que ninguna dirección de correo electrónico sin hash llegue al Audience Manager.

## Requisitos de hash {#hashing-requirements}

Al crear valores hash de las direcciones de correo electrónico, asegúrese de cumplir con los siguientes requisitos:

* Recortar todos los espacios iniciales y finales de la cadena de correo electrónico; ejemplo: `johndoe@example.com`, no `<space>johndoe@example.com<space>`;
* Al crear valores hash de las cadenas de correo electrónico, asegúrese de usar la cadena en minúsculas;
   * Ejemplo: `example@email.com`, no `EXAMPLE@EMAIL.COM`;
* Asegúrese de que la cadena con hash esté en minúscula
   * Ejemplo: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, no `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* No salar la cuerda.

Vea el siguiente vídeo para conocer los requisitos de hash de [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud le da la opción de hash los ID de cliente mediante [!DNL Adobe Experience Platform Identity Service (ECID)]. Consulte [Soporte hash SHA256 para setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) para obtener información detallada sobre cómo usar ECID para hash los ID de cliente.

## Obteniendo permiso de usuario {#obtaining-user-permission}

Dado que [!UICONTROL People-Based Destinations] le ayuda a activar datos de audiencia de origen en canales basados en personas, es su responsabilidad informar y obtener el consentimiento necesario de sus clientes sobre cómo utilizarán sus datos para publicidad u otros fines.

Antes de registrarse en [!UICONTROL People-Based Destinations], asegúrese de obtener el consentimiento de sus clientes antes de utilizar su información con fines publicitarios.

En caso de que tus clientes deseen optar por no participar en campañas publicitarias, consulta [Administración de exclusión](../../overview/data-security-and-privacy/data-privacy-requests.md) para obtener detalles sobre cómo impedir que el Audience Manager siga recopilando datos.

## Forzar la activación de datos de origen {#enforcing-first-party-activation}

Al usar [!UICONTROL People-Based Destinations], solo se pueden usar datos de origen para activar segmentos de audiencia en canales basados en personas. No se puede utilizar ningún dato de segundo nivel o de terceros para la activación de audiencias en canales basados en personas.

Cuando use [!UICONTROL People-Based Destinations], use [Controles de exportación de datos](../data-export-controls.md) para etiquetar a [!UICONTROL data sources] y [!UICONTROL destinations] según las directrices y los requisitos de las plataformas de destino y los proveedores de datos.

## Incorporación de ID con hash autenticados mediante la segmentación de ID declarados {#onboard-authenticated-declared-id}

Existen dos maneras de incluir los datos sin conexión a Audience Manager para [!UICONTROL People-Based Destinations].

* [Enviar datos por lotes](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) al Audience Manager para introducir direcciones de correo electrónico con hash. Con este método, puede elegir usar las direcciones de correo electrónico con hash de su base de datos [!DNL CRM] en [!UICONTROL People-Based Destinations]. Además, al utilizar este método, también puede clasificar las direcciones de correo electrónico con hash para [rasgos incorporados](../traits/trait-and-segment-qualification-reference.md).
* Use [ID declarados](../declared-ids.md) para declarar direcciones de correo electrónico con hash al pasar ID de clientes autenticados. Al utilizar este método, el Audience Manager, en su nombre, solo envía a [!UICONTROL People-Based Destinations] las direcciones de correo electrónico con hash de los usuarios que se han autenticado en línea. Las direcciones de correo electrónico activadas a través de canales basados en personas solo son las que aparecen en las llamadas de evento de ID declaradas. Otras direcciones de correo electrónico asociadas con el ID de cliente no se envían en tiempo real.
