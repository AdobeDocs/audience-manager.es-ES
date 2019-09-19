---
description: 'Esta página contiene instrucciones sobre cómo configurar y administrar la integración entre Audience Manager y las plataformas basadas en personas. '
seo-description: 'Esta página contiene instrucciones sobre cómo configurar y administrar la integración entre Audience Manager y las plataformas basadas en personas. '
seo-title: Autenticación con plataformas basadas en personas
solution: Audience Manager
title: Autenticación con plataformas basadas en personas
translation-type: tm+mt
source-git-commit: 05f334dc3d975a0fe18b93c844889e3edb2dfafa

---


# Autenticación con plataformas basadas en personas {#authentication-with-people-based-platforms}

Esta página contiene instrucciones sobre cómo configurar y administrar la integración entre Audience Manager y las plataformas basadas en personas.

>[!NOTE]
>Este es un paso obligatorio para los destinos basados en personas, independientemente del escenario de implementación.

## Configurar la autenticación de plataforma basada en personas {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma social, debería verla en esta página. De lo contrario, la página está vacía.
   ![integración basada en las personas](assets/pbd-config.png)
1. Haga clic en **[!UICONTROL Add Account]**.
1. Utilice el menú **[!UICONTROL People-Based Platform]** desplegable para seleccionar la plataforma con la que desea configurar la integración.
   ![plataforma basada en las personas](assets/pbd-add.png)
1. Haga clic en **[!UICONTROL Confirm]** para que se le redirija a la página de autenticación de la plataforma seleccionada.
1. Una vez que se haya autenticado en la cuenta de la plataforma social, se le redirigirá a Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!UICONTROL Confirm]**.
1. Audience Manager muestra una notificación en la parte superior de la página para indicarle si la cuenta se agregó correctamente. La notificación también le permite agregar una dirección de correo electrónico de contacto para recibir notificaciones cuando la autenticación de la plataforma social esté a punto de caducar.

## Caducidad del autentificador y administración de notificaciones {#token-expiration-notification}

Audience Manager gestiona la integración con las plataformas sociales mediante tokens de autenticación que caducan después de una determinada cantidad de tiempo. La duración de la validez del token está sujeta a las reglas de integración de cada plataforma social. Una vez que caduca el autentificador, Audience Manager no puede enviar los segmentos de audiencia a su destino. Para evitar este escenario, le recomendamos que agregue al menos una dirección de correo electrónico de contacto a su integración para que se le notifique en cuanto el autentificador esté a punto de caducar. Cuando esto ocurra, puede volver a autenticarse para asegurarse de que el destino siga recibiendo segmentos de audiencia.

A continuación se muestra cómo agregar direcciones de correo electrónico a integraciones existentes:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identifique la integración para la que desea recibir notificaciones de caducidad del token y haga clic en el **[!UICONTROL Edit]** icono.
1. Introduzca las direcciones de correo electrónico a las que desea recibir notificaciones de caducidad del token, separadas por comas.
1. Haga clic en **[!UICONTROL Save]**.

## Renovación del autentificador {#token-renewal}

Cuando caduca un autentificador, se interrumpe la integración entre Audience Manager y la plataforma social correspondiente, por lo que Audience Manager ya no puede enviar segmentos de audiencia al destino. La [!UICONTROL Integrated Accounts] página muestra el estado de caducidad de cada integración en la [!UICONTROL Expiration] columna y le permite renovar la autenticación en cualquier momento.

A continuación se muestra cómo renovar una autenticación caducada o que está a punto de caducar:
1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identifique la integración para la que necesita renovar la autenticación. Las autenticaciones caducadas se marcan como [!UICONTROL Expired], mientras que las autenticaciones que están a punto de caducar pronto muestran el número restante de días autenticados.
1. Haga clic en el **[!UICONTROL Renew]** icono correspondiente de la [!UICONTROL Expiration] columna. Esto desencadena el **[!UICONTROL Renew Account]** flujo de trabajo, que le lleva de nuevo a través de la página de autenticación de la plataforma social. Una vez autenticado, el token se renueva con la nueva fecha de caducidad.
   ![pbd-renew](assets/pbd-renew.png)
