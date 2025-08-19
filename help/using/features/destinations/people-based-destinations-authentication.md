---
description: Esta página contiene instrucciones sobre cómo configurar y administrar la integración entre Audience Manager y las plataformas basadas en personas.
seo-description: This page contains guidance on how to configure and manage the integration between Audience Manager and people-based platforms.
seo-title: Authentication with People-Based Platforms
solution: Audience Manager
title: Autenticación con plataformas basadas en personas
feature: People-based Destinations
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
source-git-commit: 1809e9ee0b19a8ffb4bec38162f728d543d13701
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---


# Autenticación con plataformas basadas en personas {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Este artículo contiene documentación del producto que le guiará a través de la configuración y el uso de esta función. Nada de lo que contiene aquí es asesoramiento legal. Por favor, consulte a su propio asesor legal para obtener orientación legal.

Esta página contiene instrucciones sobre cómo configurar y administrar la integración
entre Audience Manager y plataformas basadas en personas.

>[!NOTE]
>Este es un paso obligatorio para People-Based Destinations, independientemente del escenario de implementación.

## Configurar la autenticación de plataforma basada en personas {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma social, debería verla en esta página. En caso contrario, la página está vacía.
   ![integración basada en personas](assets/pbd-config.png)
2. Haga clic en **[!UICONTROL Add Account]**.
3. Utilice el menú desplegable **[!UICONTROL People-Based Platform]** para seleccionar la plataforma con la que desea configurar la integración.
   ![plataforma basada en personas](assets/pbd-add.png)
4. Haga clic en **[!UICONTROL Confirm]** para que se le redirija a la página de autenticación de la plataforma seleccionada.
5. Una vez que se haya autenticado en su cuenta de la plataforma social, se le redirigirá a Audience Manager, donde debería ver sus cuentas de anunciante asociadas. Seleccione la cuenta de anunciante que desee usar y haga clic en **[!UICONTROL Confirm]**.
6. Audience Manager muestra una notificación en la parte superior de la página para informarle de si la cuenta se ha agregado correctamente. La notificación también le permite añadir una dirección de correo electrónico de contacto para recibir notificaciones de Adobe cuando la autenticación de la plataforma social esté a punto de caducar.

## Caducidad del token de autenticación y administración de notificaciones {#token-expiration-notification}

Audience Manager gestiona la integración con las plataformas sociales mediante tokens de autenticación que caducan después de un cierto tiempo. La duración de la validez del token está sujeta a las reglas de integración de cada plataforma social. Una vez que caduca el token de autenticación, Audience Manager no puede enviar los segmentos de audiencia a su destino. Para evitar este escenario, se recomienda añadir al menos una dirección de correo electrónico de contacto a la integración, de modo que reciba una notificación en cuanto el token de autenticación esté a punto de caducar. Cuando esto sucede, puede volver a autenticarse para asegurarse de que el destino siga recibiendo los segmentos de audiencia.

A continuación se indica cómo añadir direcciones de correo electrónico a integraciones existentes:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifique la integración para la que desea recibir notificaciones de caducidad de tokens y haga clic en el icono **[!UICONTROL Edit]**.
1. Introduzca las direcciones de correo electrónico a las que desea enviar notificaciones de caducidad de tokens, separadas por comas.
1. Haga clic en **[!UICONTROL Save]**.

## Renovación del token de autenticación {#token-renewal}

Cuando caduca un token de autenticación, se interrumpe la integración entre Audience Manager y la plataforma social correspondiente, por lo que Audience Manager ya no puede enviar segmentos de audiencia al destino. La página [!UICONTROL Integrated Accounts] muestra el estado de caducidad de cada integración en la columna [!UICONTROL Expiration] y le permite renovar la autenticación en cualquier momento.

A continuación se indica cómo renovar una autenticación caducada o a punto de caducar:
1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifique la integración para la que necesita renovar la autenticación. Las autenticaciones caducadas se marcan como [!UICONTROL Expired], mientras que las autenticaciones que están a punto de caducar pronto muestran el número restante de días autenticados.
1. Haga clic en el icono **[!UICONTROL Renew]** correspondiente en la columna [!UICONTROL Expiration]. Esto almacena en déclencheur el flujo de trabajo **[!UICONTROL Renew Account]**, que lo lleva a través de la página de autenticación de la plataforma social. Una vez autenticado, el token se renueva con la nueva fecha de caducidad.
   ![pbd-renovar](assets/pbd-renew.png)
