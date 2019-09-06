---
description: 'Esta página contiene instrucciones sobre cómo configurar y administrar la integración entre Audience Manager y plataformas basadas en personas. '
seo-description: 'Esta página contiene instrucciones sobre cómo configurar y administrar la integración entre Audience Manager y plataformas basadas en personas. '
seo-title: Autenticación con plataformas basadas en personas
solution: Audience Manager
title: Autenticación con plataformas basadas en personas
translation-type: tm+mt
source-git-commit: 05f334dc3d975a0fe18b93c844889e3edb2dfafa

---


# Autenticación con plataformas basadas en personas {#authentication-with-people-based-platforms}

Esta página contiene instrucciones sobre cómo configurar y administrar la integración entre Audience Manager y plataformas basadas en personas.

>[!NOTE]
>Es un paso obligatorio para destinos basados en personas, independientemente del escenario de implementación.

## Configurar autenticación de plataforma basada en personas {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada previamente con una plataforma social, debe verlo en esta página. De lo contrario, la página está vacía.
   ![integración basada en personas](assets/pbd-config.png)
1. Haga clic en **[!UICONTROL Add Account]**.
1. Utilice el menú **[!UICONTROL People-Based Platform]** desplegable para seleccionar la plataforma con la que desea configurar la integración.
   ![plataforma basada en personas](assets/pbd-add.png)
1. Haga clic para **[!UICONTROL Confirm]** que se le redirija a la página de autenticación de la plataforma seleccionada.
1. Una vez que haya autenticado en su cuenta de plataforma social, se le redirigirá a Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic **[!UICONTROL Confirm]** en.
1. Audience Manager muestra una notificación en la parte superior de la página para saber si la cuenta se agregó correctamente. La notificación también permite agregar una dirección de correo electrónico de contacto para recibir notificaciones cuando la autenticación de plataforma social está a punto de caducar.

## Caducidad de autentificador de autentificación y administración de notificaciones {#token-expiration-notification}

Audience Manager gestiona la integración con plataformas sociales a través de tokens de autenticación que caducan después de una determinada cantidad de tiempo. La duración de la validez del token está sujeta a las reglas de integración de cada plataforma social. Cuando caduca el autentificador de autenticación, Audience Manager no puede enviar segmentos de audiencia al destino. Para evitar este escenario, recomendamos agregar al menos una dirección de correo electrónico de contacto a la integración, de modo que reciba notificaciones en cuanto el autentificador de autenticación esté a punto de caducar. Cuando esto sucede, puede volver a autenticarse para asegurarse de que el destino sigue recibiendo los segmentos de audiencia.

A continuación se muestra cómo agregar direcciones de correo electrónico a integraciones existentes:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identifique la integración en la que desee recibir las notificaciones de caducidad del token y haga clic en **[!UICONTROL Edit]** el icono.
1. Introduzca las direcciones de correo electrónico que desee recibir de las notificaciones de caducidad del token, separadas por comas.
1. Haga clic en **[!UICONTROL Save]**.

## Renovación del autentificador de autentificación {#token-renewal}

Cuando caduca un token de autenticación, se interrumpe la integración entre Audience Manager y la plataforma social correspondiente, por lo que Audience Manager no puede enviar segmentos de audiencia al destino. [!UICONTROL Integrated Accounts] La página muestra el estado de caducidad de cada integración en [!UICONTROL Expiration] la columna y permite renovar la autenticación en cualquier momento.

A continuación se muestra cómo renovar una autenticación caducada o sobre caduca:
1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identificar la integración para la que debe renovar la autenticación. Las autenticaciones caducadas se marcan como [!UICONTROL Expired], mientras que las autenticaciones que estén a punto de caducar muestran el número restante de días autenticados.
1. Haga clic en el icono correspondiente **[!UICONTROL Renew]** de la [!UICONTROL Expiration] columna. Esto activa el **[!UICONTROL Renew Account]** flujo de trabajo, que le lleva hacia atrás por la página de autenticación de la plataforma social. Una vez autenticada, el token se renovará con la nueva fecha de caducidad.
   ![pbd-renew](assets/pbd-renew.png)
