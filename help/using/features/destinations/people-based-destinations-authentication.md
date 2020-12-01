---
description: 'Esta página contiene instrucciones sobre cómo configurar y administrar la integración entre las plataformas basadas en Audience Manager y en personas. '
seo-description: 'Esta página contiene instrucciones sobre cómo configurar y administrar la integración entre las plataformas basadas en Audience Manager y en personas. '
seo-title: Autenticación con plataformas basadas en personas
solution: Audience Manager
title: Autenticación con plataformas basadas en personas
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 2%

---


# Autenticación con plataformas basadas en personas {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a guiarle en la configuración y el uso de esta función. Nada de lo que aquí se incluye es asesoramiento jurídico. Por favor, consulte a su propio abogado para obtener asesoramiento jurídico.

Esta página contiene instrucciones sobre cómo configurar y administrar la integración
entre plataformas basadas en Audience Manager y plataformas basadas en personas.

>[!NOTE]
>Este es un paso obligatorio para los destinos basados en personas, independientemente del escenario de implementación.

## Configurar la autenticación de plataforma basada en usuarios {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma social, debería verla en esta página. De lo contrario, la página está vacía.
   ![integración basada en las personas](assets/pbd-config.png)
2. Haga clic **[!UICONTROL Add Account]**.
3. Utilice el menú desplegable **[!UICONTROL People-Based Platform]** para seleccionar la plataforma con la que desea configurar la integración.
   ![plataforma basada en las personas](assets/pbd-add.png)
4. Haga clic en **[!UICONTROL Confirm]** para que se le redirija a la página de autenticación de la plataforma seleccionada.
5. Una vez que se haya autenticado en la cuenta de la plataforma social, se le redirigirá al Audience Manager, donde debería ver las cuentas del anunciante asociado. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!UICONTROL Confirm]**.
6. Audience Manager muestra una notificación en la parte superior de la página para informarle de si la cuenta se agregó correctamente. La notificación también le permite agregar una dirección de correo electrónico de contacto para recibir notificaciones de Adobe cuando la autenticación de la plataforma social esté a punto de caducar.

## Administración de notificación y caducidad del autentificador {#token-expiration-notification}

El Audience Manager gestiona la integración con las plataformas sociales mediante tokens de autenticación que caducan después de una determinada cantidad de tiempo. La duración de la validez del token está sujeta a las reglas de integración de cada plataforma social. Una vez que caduca el token de autenticación, el Audience Manager no puede enviar los segmentos de audiencia a su destino. Para evitar este escenario, le recomendamos que agregue al menos una dirección de correo electrónico de contacto a su integración para que se le notifique en cuanto el autentificador esté a punto de caducar. Cuando esto sucede, puede volver a autenticarse para asegurarse de que el destino sigue recibiendo los segmentos de audiencia.

A continuación se muestra cómo agregar direcciones de correo electrónico a integraciones existentes:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifique la integración para la que desea recibir notificaciones de caducidad del token y haga clic en el icono **[!UICONTROL Edit]**.
1. Introduzca las direcciones de correo electrónico a las que desea recibir notificaciones de caducidad del token, separadas por comas.
1. Haga clic **[!UICONTROL Save]**.

## Renovación del autentificador {#token-renewal}

Cuando caduca un token de autenticación, se interrumpe la integración entre el Audience Manager y la plataforma social correspondiente, por lo que el Audience Manager ya no puede enviar segmentos de audiencia al destino. La página [!UICONTROL Integrated Accounts] muestra el estado de caducidad de cada integración en la columna [!UICONTROL Expiration] y le permite renovar la autenticación en cualquier momento.

A continuación se muestra cómo renovar una autenticación caducada o que está a punto de caducar:
1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifique la integración para la que necesita renovar la autenticación. Las autenticaciones caducadas se marcan como [!UICONTROL Expired], mientras que las autenticaciones que están a punto de caducar pronto muestran el número restante de días autenticados.
1. Haga clic en el icono correspondiente **[!UICONTROL Renew]** en la columna [!UICONTROL Expiration]. Esto desencadena el flujo de trabajo **[!UICONTROL Renew Account]**, que le lleva de nuevo a través de la página de autenticación de la plataforma social. Una vez autenticado, el token se renueva con la nueva fecha de caducidad.
   ![pbd-renew](assets/pbd-renew.png)
