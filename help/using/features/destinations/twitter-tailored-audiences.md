---
description: En este artículo se explica cómo configurar Audiencias personalizadas de Twitter para integraciones nuevas y existentes.
seo-description: En este artículo se explica cómo configurar Audiencias personalizadas de Twitter para integraciones nuevas y existentes.
seo-title: Configurar las audiencias personalizadas de Twitter como un destino basado en un dispositivo de autoservicio
solution: Audience Manager
title: Configurar las audiencias personalizadas de Twitter como un destino basado en un dispositivo de autoservicio
translation-type: tm+mt
source-git-commit: 4af2d7a4e2162f8d69273cf76aecb5f1ff00e7b6

---


# Configurar [!DNL Twitter Tailored Audiences] como destino basado en dispositivos de autoservicio {#configure-twitter}

En este artículo se explica cómo configurar una integración con Audiencias [personalizadas de](https://business.twitter.com/en/targeting/tailored-audiences.html)Twitter.

## Requisitos previos {#prerequisites}

Antes de configurar su [!DNL Twitter Tailored Audiences] destino, asegúrese de revisar los siguientes requisitos previos de Twitter que necesita cumplir.

1. Su [!DNL Twitter Ads] cuenta debe ser elegible para publicidad. Las nuevas [!DNL Twitter Ads] cuentas no son elegibles para publicidad en las dos primeras semanas después de crearlas.
2. Su cuenta [!DNL Twitter] de usuario para la que autorizó el acceso en Audience Manager debe tener habilitado el permiso de administrador [de público](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) asociado.
3. Al crear el primer [!DNL Twitter Tailored Audiences] destino en la instancia de Audience Manager, póngase en contacto con el servicio de consultoría de Adobe o con el servicio de atención al cliente para habilitar la sincronización de [!DNL Twitter] ID (ID de fuente de datos = 1123) para su cuenta. Esto es necesario para la sincronización correcta entre Audience Manager y [!DNL Twitter].

## Agregar un nuevo [!DNL Twitter Tailored Audiences] destino {#add-new-twitter-destination}

En esta sección se describen los pasos que debe seguir al configurar un nuevo destino basado en dispositivos para [!DNL Twitter Tailored Audiences]. En este escenario se asume que no hay ningún destino [!DNL Twitter Tailored Audiences] configurado mediante el consultor de Adobe o el Servicio de atención al cliente.

### Paso 1. Autenticar con [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Para poder agregar el destino basado en dispositivos, debe vincular Audience Manager con su [!DNL Twitter Tailored Audiences] cuenta. A continuación se muestra cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!DNL Administration > Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma de destino, debería verla en esta página. De lo contrario, la página está vacía.
1. Haga clic en **[!DNL Add Account]**.
1. Seleccione [!DNL Twitter Tailored Audiences] y haga clic en **[!DNL Confirm]** para que se le redirija a la página de autenticación.                     ![plataformas integradas](assets/dbd-integrated-platforms.png)
1. Una vez autenticado, se le redirige a Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!DNL Confirm]**.

### Paso 2: Crear un nuevo destino basado en dispositivo {#step2-create-new-destination}

Después de vincular Audience Manager y su [!DNL Twitter Tailored Audiences]usuario, puede crear el nuevo destino. A continuación se muestra cómo hacerlo:

>[!NOTE]
>
>No se puede cambiar el nombre de un destino existente basado en dispositivo. Asegúrese de proporcionar un nombre que le ayude a identificar el destino correctamente.

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!DNL Audience Data > Destinations]** y haga clic en **[!DNL Create Destination]**.
1. En la **[!DNL Basic Information]** sección, introduzca un **[!DNL Name]** y **[!DNL Description]** para el nuevo destino y utilice la configuración siguiente: ![configuración](assets/dbd-new-basic.png)
1. Haga clic en **[!DNL Next]**.
1. Elija las etiquetas [de exportación de](/help/using/features/data-export-controls.md#controls-labels) datos que desee establecer para este destino.
1. Haga clic en **[!DNL Save]**.
1. En la **[!DNL Segment Mappings]** sección, seleccione los segmentos de audiencia que desee enviar a este destino.
1. Guarde el destino.

<!--
## Update Existing Twitter Integrations To Self-Service Administration {#update-existing-twitter-integrations}

To improve the user experience and streamline the configuration process, we are upgrading the [!DNL Twitter Tailored Audiences] integration to a self-service model, where you can perform the configuration yourself, from the Audience Manager UI. This section describes the steps you need to take to update your existing Twitter integration.

>[!IMPORTANT]
>
>The steps described below only apply if you have an existing integration with [!DNL Twitter Tailored Audiences], configured by an Audience Manager consultant or Customer Care.
> See item number 3 in [Prerequisites](#prerequisites) before migrating your [!DNL Twitter Tailored Audiences] to the self-service model.

Follow the steps below to migrate your existing [!DNL Twitter Tailored Audiences] destination to the self-service model.

1. Log in to your Audience Manager account and go to **[!DNL Administration > Integrated Accounts]**.
2. Click **[!DNL Add Account]**.
3. Select [!DNL Twitter Tailored Audiences] and click **[!DNL Confirm]** to be redirected to the authentication page. ![integrated-platforms](assets/dbd-integrated-platforms.png)
4. Once you've authenticated with your [!DNL Twitter] account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click **[!DNL Confirm]**.
5. Go to **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** and click the Twitter destination that you need to configure.
6. Click **[!UICONTROL Edit]**. In the **[!UICONTROL Basic Information]** section, click the **[!UICONTROL Integrated Account]** drop-down menu and select the [!DNL Twitter] account that you have authenticated with at Step 4.
7. **[!UICONTROL Save]** the destination.

## Validating the Migration to Self-Service Administration {#migration-validation}

The complete migration of existing [!DNL Twitter] integrations to self-service administration can take up to 7 days. Once the migration is complete, Audience Manager shows you a notification in the UI.

You will also see a new set of audiences in your [!DNL Twitter] account, with their names prefixed by [[!DNL Adobe DMP Audience]]. Please allow up to 7 days for the audience population to be completely backfilled. Once the migration is complete, you should use these new audiences instead of the old ones. -->

## Consideraciones sobre la asignación de segmentos {#segment-mapping-considerations}

Al asignar segmentos de audiencia a [!UICONTROL Twitter], asegúrese de cumplir los siguientes requisitos de nomenclatura de segmentos:

* Proporcione nombres de asignación de segmentos legibles por el usuario. Se recomienda utilizar el mismo nombre que se utilizó para los segmentos de Audience Manager.
* No utilice caracteres especiales (`,``%` `:``;` `@` `/` `=` `?` `$`) en los nombres de asignación de segmentos y segmentos. Si el nombre del segmento de Audience Manager contiene estos caracteres, elimínelos antes de asignar el segmento a un [!UICONTROL Twitter] destino.

### Ejemplo

* Nombre de asignación o segmento correcto: "Compradores europeos y estadounidenses";
* Nombre de asignación o segmento incorrecto: "EE.UU., europeo 5h0pP3rs".

>[!IMPORTANT]
>
>No puede cambiar los nombres de los segmentos ya asignados. Audience Manager utiliza los nombres de los segmentos para identificar correctamente los segmentos en la integración.

## Consideraciones sobre las tasas de coincidencia {#match-rates-considerations}

* Al utilizar [!UICONTROL Twitter Tailored Audiences], las métricas [!UICONTROL Segment Addressable Audience] y [!UICONTROL Segment Match Rate] de la página de destino no mostrarán ningún valor. Esto es normal, ya que la coincidencia de audiencias junto con las tasas de coincidencia para este destino se gestionan y alojan en [!UICONTROL Twitter], no en Adobe.
* Actualmente, la integración entre Audience Manager y [!UICONTROL Twitter Tailored Audiences] no admite los rellenos de audiencia históricos. Esto significa que solo se envían en tiempo real las cualificaciones de segmentos que se producen *después* de que el segmento se asigne a un destino de Twitter [!UICONTROL Twitter] .
