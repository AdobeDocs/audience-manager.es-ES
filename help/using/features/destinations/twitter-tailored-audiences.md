---
description: En este artículo se explica cómo configurar Audiencias personalizadas de Twitter para integraciones nuevas y existentes.
seo-description: En este artículo se explica cómo configurar Audiencias personalizadas de Twitter para integraciones nuevas y existentes.
seo-title: Configurar las audiencias personalizadas de Twitter como un destino basado en un dispositivo de autoservicio
solution: Audience Manager
title: Configurar las audiencias personalizadas de Twitter como un destino basado en un dispositivo de autoservicio
translation-type: tm+mt
source-git-commit: c6318921b49603015b4670a361ec85ffa29abb30

---


# Configurar [!DNL Twitter Tailored Audiences] como destino basado en dispositivos de autoservicio {#configure-twitter}

En este artículo se explica cómo configurar Audiencias [personalizadas de](https://business.twitter.com/en/targeting/tailored-audiences.html) Twitter para integraciones nuevas y existentes.

## Requisitos previos {#prerequisites}

Before you configure your  destination, make sure to review the following Twitter prerequisites that you need to meet.[!DNL Twitter Tailored Audiences]

1. Your  account must be eligible for advertising. [!DNL Twitter Ads] New [!DNL Twitter Ads] accounts are not eligible for advertising in the first 2 weeks after creating them.
1. Your Twitter user account that you authorized access for in Audience Manager must have the [Partner audience manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) permission enabled.
1. Si está [actualizando la integración existente de Twitter a una administración](#update-existing-twitter-integrations)de autoservicio, su cuenta de usuario de Twitter debe tener habilitado el permiso [de administrador](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) de publicidad.
1. Al crear el primer [!DNL Twitter Tailored Audiences] destino en la instancia de Audience Manager, póngase en contacto con el servicio de consultoría de Adobe o con el servicio de atención al cliente para habilitar la sincronización de [!DNL Twitter] ID (ID de fuente de datos = 1123) para su cuenta. Esto es necesario para la sincronización correcta entre Audience Manager y [!DNL Twitter].

## Agregar un nuevo [!DNL Twitter Tailored Audiences] destino {#add-new-twitter-destination}

Esta sección describe los pasos que debe seguir al configurar un nuevo destino basado en dispositivos para [!DNL Twitter Tailored Audiences]. En este escenario se asume que no hay ningún destino [!DNL Twitter Tailored Audiences] configurado mediante el consultor de Adobe o el Servicio de atención al cliente.

### Paso 1. Autenticar con [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Before you can add the device-based destination, you need to link Audience Manager and your [!DNL Twitter Tailored Audiences] account. Here's how to do this:

1. Log in to your Audience Manager account and go to . **[!DNL Administration > Integrated Accounts]** If you have a previously configured integration with a destination platform, you should see it listed in this page. Otherwise, the page is empty.
2. Haga clic en **[!DNL Add Account]**.
3. Select  and click  to be redirected to the authentication page.                     [!DNL Twitter Tailored Audiences]**[!DNL Confirm]**                     ![integrated-platforms](assets/dbd-integrated-platforms.png)
4. Once you've authenticated, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click .**[!DNL Confirm]**

### Paso 2: Create a New Device-Based Destination {#step2-create-new-destination}

Después de vincular Audience Manager y su [!DNL Twitter Tailored Audiences]usuario, puede crear el nuevo destino. A continuación se muestra cómo hacerlo:

>[!NOTE]
>
>No se puede cambiar el nombre de un destino existente basado en dispositivo. Asegúrese de proporcionar un nombre que le ayude a identificar el destino correctamente.

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!DNL Audience Data > Destinations]** y haga clic en **[!DNL Create Destination]**.
2. En la **[!DNL Basic Information]** sección, introduzca un **[!DNL Name]** y **[!DNL Description]** para el nuevo destino y utilice la configuración siguiente: ![configuración](assets/dbd-new-basic.png)
3. Haga clic en **[!DNL Next]**.
4. Elija las etiquetas [de exportación de](/help/using/features/data-export-controls.md#controls-labels) datos que desee establecer para este destino.
5. Haga clic en **[!DNL Save]**.
6. En la **[!DNL Segment Mappings]** sección, seleccione los segmentos de audiencia que desee enviar a este destino.
7. Guarde el destino.

## Update Existing Twitter Integrations To Self-Service Administration {#update-existing-twitter-integrations}

Para mejorar la experiencia del usuario y optimizar el proceso de configuración, estamos actualizando la integración a un modelo de autoservicio, en el que puede realizar la configuración usted mismo, desde la interfaz de usuario de Audience Manager. [!DNL Twitter Tailored Audiences] This section describes the steps you need to take to update your existing Twitter integration.

>[!IMPORTANT]
>
>Los pasos que se describen a continuación solo se aplican si tiene una integración existente con [!DNL Twitter Tailored Audiences], configurada por un asesor de Audience Manager o por el Servicio de atención al cliente. El proceso completo de actualización de su destino al modelo de autoservicio puede tardar hasta 5 días laborables. Mientras tanto, el destino sigue activo y Audience Manager continúa enviándole audiencias.
> Consulte el artículo número 3 en Requisitos [previos](#prerequisites) antes de migrar [!DNL Twitter Tailored Audiences] al modelo de autoservicio.

Siga los pasos a continuación para migrar el destino existente [!DNL Twitter Tailored Audiences] al modelo de autoservicio.

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!DNL Administration > Integrated Accounts]**.
1. Haga clic en **[!DNL Add Account]**.
1. Select  and click  to be redirected to the authentication page. [!DNL Twitter Tailored Audiences]**[!DNL Confirm]** ![integrated-platforms](assets/dbd-integrated-platforms.png)
1. Una vez que se haya autenticado con su [!DNL Twitter] cuenta, se le redirigirá a Audience Manager, donde debería ver sus cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!DNL Confirm]**.
1. Vaya a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** y haga clic en el destino de Twitter que necesita configurar.
1. Haga clic en **[!UICONTROL Edit]**. En la **[!UICONTROL Basic Information]** sección, haga clic en el menú **[!UICONTROL Integrated Account]** desplegable y seleccione la [!DNL Twitter] cuenta con la que se ha autenticado en el paso 4.
1. **[!UICONTROL Save]** el destino.

## Validación de la migración a la administración de autoservicio {#migration-validation}

La migración completa de [!DNL Twitter] integraciones existentes a la administración de autoservicio puede llevar hasta 7 días. Una vez completada la migración, Audience Manager le muestra una notificación en la interfaz de usuario.

También verá un nuevo conjunto de audiencias en su [!DNL Twitter] cuenta, con los nombres marcados por [[!DNL Adobe DMP Audience]]. Espere hasta 7 días para que la población de audiencias se rellene completamente. Once the migration is complete, you should use these new audiences instead of the old ones.

## Segment Mapping Considerations {#segment-mapping-considerations}

Al asignar segmentos de audiencia a Twitter, asegúrese de cumplir los siguientes requisitos de nomenclatura de segmentos:

* Proporcione nombres de asignación de segmentos legibles por el usuario. Se recomienda utilizar el mismo nombre que se utilizó para los segmentos de Audience Manager.
* Do not use commas in segment and segment mapping names.

### Ejemplo

* Correct segment or mapping name: "US and European Shoppers";
* Incorrect segment or mapping name: "US, European 5h0pP3rs".

>[!IMPORTANT]
>
>You cannot change the names of already mapped segments. Audience Manager utiliza los nombres de los segmentos para identificar correctamente los segmentos en la integración.

## Match Rates Considerations {#match-rates-considerations}

When using , the  and  metrics from the destination page will not display any values. [!UICONTROL Twitter Tailored Audiences][!UICONTROL Segment Addressable Audience][!UICONTROL Segment Match Rate] This is normal behavior, since audience matching along with the match rates for this destination are handled and hosted by , not Adobe.[!UICONTROL Twitter]
