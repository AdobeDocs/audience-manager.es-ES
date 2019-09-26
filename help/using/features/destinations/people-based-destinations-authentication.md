---
description: 'Esta página contiene instrucciones sobre cómo configurar y administrar la integración entre Audience Manager y las plataformas basadas en personas. '
seo-description: 'Esta página contiene instrucciones sobre cómo configurar y administrar la integración entre Audience Manager y las plataformas basadas en personas. '
seo-title: Autenticación con plataformas basadas en personas
solution: Audience Manager
title: Autenticación con plataformas basadas en personas
translation-type: tm+mt
source-git-commit: 6093def9c5853572c064a4e398d5e328bcb9d181

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
1. Audience Manager muestra una notificación en la parte superior de la página para indicarle si la cuenta se agregó correctamente. La notificación también le permite agregar una dirección de correo electrónico de contacto para recibir notificaciones de Adobe cuando la autenticación de la plataforma social esté a punto de caducar.

## Caducidad del autentificador y administración de notificaciones {#token-expiration-notification}

Audience Manager gestiona la integración con las plataformas sociales mediante tokens de autenticación que caducan después de una determinada cantidad de tiempo. La duración de la validez del token está sujeta a las reglas de integración de cada plataforma social. Una vez que caduca el autentificador, Audience Manager no puede enviar los segmentos de audiencia a su destino. Para evitar este escenario, le recomendamos que agregue al menos una dirección de correo electrónico de contacto a su integración para que se le notifique en cuanto el autentificador esté a punto de caducar. Cuando esto ocurra, puede volver a autenticarse para asegurarse de que el destino siga recibiendo segmentos de audiencia.

A continuación se muestra cómo agregar direcciones de correo electrónico a integraciones existentes:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identifique la integración para la que desea recibir notificaciones de caducidad del token y haga clic en el **[!UICONTROL Edit]** icono.
1. Introduzca las direcciones de correo electrónico a las que desea recibir notificaciones de caducidad del token, separadas por comas.
1. Haga clic en **[!UICONTROL Save]**.

## Renovación del autentificador {#token-renewal}

When an authentication token expires, the integration between Audience Manager and the corresponding social platform is interrupted, so Audience Manager cannot send audience segments to the destination anymore. The [!UICONTROL Integrated Accounts] page shows you the expiration status of each integration in the [!UICONTROL Expiration] column, and allows you to renew the authentication at any time.

Here's how to renew an expired or about-to-expire authentication:
1. Log in to your Audience Manager account and go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identify the integration that you need to renew authentication for. Expired authentications are marked as , while authentications that are about to expire soon show the remaining number of authenticated days.[!UICONTROL Expired]
1. Click the corresponding  icon in the  column. **[!UICONTROL Renew]**[!UICONTROL Expiration] This triggers the  workflow, which takes you back through the social platform's authentication page. **[!UICONTROL Renew Account]** Once you authenticate, the token is renewed with the new expiration date.
   ![pbd-renew](assets/pbd-renew.png)
