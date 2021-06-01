---
description: 'Esta página contiene instrucciones sobre cómo configurar y administrar la integración entre plataformas basadas en Audience Manager y personas. '
seo-description: 'Esta página contiene instrucciones sobre cómo configurar y administrar la integración entre plataformas basadas en Audience Manager y personas. '
seo-title: Autenticación con plataformas basadas en personas
solution: Audience Manager
title: Autenticación con plataformas basadas en personas
feature: Destinos basados en personas
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 2%

---

# Autenticación con plataformas basadas en personas {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Este artículo contiene documentación del producto pensada para guiarle en la configuración y uso de esta función. Nada de lo contenido en este documento es asesoramiento jurídico. Consulte a su propio asesor jurídico para obtener asesoramiento jurídico.

Esta página contiene instrucciones sobre cómo configurar y administrar la integración
entre plataformas basadas en Audience Manager y personas.

>[!NOTE]
>Este es un paso obligatorio para los destinos basados en personas, independientemente del escenario de implementación.

## Configurar la autenticación de plataforma basada en personas {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma social, debería verla en esta página. De lo contrario, la página estará vacía.
   ![integración basada en personas](assets/pbd-config.png)
2. Haga clic **[!UICONTROL Add Account]**.
3. Utilice el menú desplegable **[!UICONTROL People-Based Platform]** para seleccionar la plataforma con la que desea configurar la integración.
   ![plataforma basada en personas](assets/pbd-add.png)
4. Haga clic en **[!UICONTROL Confirm]** para redirigirse a la página de autenticación de la plataforma seleccionada.
5. Una vez que se haya autenticado en la cuenta de la plataforma social, se le redirigirá al Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!UICONTROL Confirm]**.
6. Audience Manager muestra una notificación en la parte superior de la página para informarle de si la cuenta se agregó correctamente. La notificación también le permite añadir una dirección de correo electrónico de contacto para recibir notificaciones de Adobe cuando la autenticación de la plataforma social está a punto de caducar.

## Caducidad del token de autenticación y administración de notificaciones {#token-expiration-notification}

El Audience Manager gestiona la integración con plataformas sociales mediante tokens de autenticación que caducan después de un cierto tiempo. La duración de la validez del token está sujeta a las reglas de integración de cada plataforma social. Una vez que caduca el token de autenticación, el Audience Manager no puede enviar los segmentos de audiencia al destino. Para evitar este escenario, se recomienda añadir al menos una dirección de correo electrónico de contacto a la integración, de modo que se le notifique en cuanto el token de autenticación esté a punto de caducar. Cuando esto suceda, puede volver a autenticarse para asegurarse de que el destino siga recibiendo los segmentos de audiencia.

A continuación se muestra cómo añadir direcciones de correo electrónico a integraciones existentes:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifique la integración para la que desea recibir notificaciones de caducidad del token y haga clic en el icono **[!UICONTROL Edit]**.
1. Introduzca las direcciones de correo electrónico a las que desea recibir las notificaciones de caducidad del token, separadas por comas.
1. Haga clic **[!UICONTROL Save]**.

## Renovación de tokens de autenticación {#token-renewal}

Cuando caduca un token de autenticación, se interrumpe la integración entre el Audience Manager y la plataforma social correspondiente, de modo que el Audience Manager ya no pueda enviar segmentos de audiencia al destino. La página [!UICONTROL Integrated Accounts] muestra el estado de caducidad de cada integración en la columna [!UICONTROL Expiration] y le permite renovar la autenticación en cualquier momento.

A continuación se muestra cómo renovar una autenticación caducada o que está a punto de caducar:
1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifique la integración para la que necesita renovar la autenticación. Las autenticaciones caducadas se marcan como [!UICONTROL Expired], mientras que las autenticaciones que están a punto de caducar pronto muestran el número restante de días autenticados.
1. Haga clic en el icono **[!UICONTROL Renew]** correspondiente de la columna [!UICONTROL Expiration]. Esto déclencheur el flujo de trabajo **[!UICONTROL Renew Account]** , que le devuelve a través de la página de autenticación de la plataforma social. Una vez autenticado, el token se renueva con la nueva fecha de caducidad.
   ![pbd-renovar](assets/pbd-renew.png)
