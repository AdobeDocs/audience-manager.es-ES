---
description: En este artículo se explica cómo configurar Audiencias personalizadas de Twitter para integraciones nuevas y existentes.
seo-description: En este artículo se explica cómo configurar Audiencias personalizadas de Twitter para integraciones nuevas y existentes.
seo-title: Configurar las audiencias personalizadas de Twitter como un destino basado en un dispositivo de autoservicio
solution: Audience Manager
title: Configurar las audiencias personalizadas de Twitter como un destino basado en un dispositivo de autoservicio
translation-type: tm+mt
source-git-commit: 7966cac59b982b5f36af6975607df64545b74058

---


# Configurar [!DNL Twitter Tailored Audiences] como destino basado en dispositivos de autoservicio {#configure-twitter}

En este artículo se explica cómo configurar Audiencias [personalizadas de](https://business.twitter.com/en/targeting/tailored-audiences.html) Twitter para integraciones nuevas y existentes.

## Requisitos previos {#prerequisites}

Antes de configurar su [!DNL Twitter Tailored Audiences] destino, asegúrese de revisar los siguientes requisitos previos de Twitter que necesita cumplir.

1. Su [!DNL Twitter Ads] cuenta debe ser elegible para publicidad. Las nuevas [!DNL Twitter Ads] cuentas no son elegibles para publicidad en las dos primeras semanas después de crearlas.
1. La cuenta de usuario de Twitter para la que autorizó el acceso en Audience Manager debe tener habilitado el permiso de administrador [de público](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) asociado.
1. Si está [actualizando la integración existente de Twitter a una administración](#update-existing-twitter-integrations)de autoservicio, su cuenta de usuario de Twitter debe tener habilitado el permiso [de administrador](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) de publicidad.
1. Al crear el primer [!DNL Twitter Tailored Audiences] destino en la instancia de Audience Manager, póngase en contacto con el servicio de consultoría de Adobe o con el servicio de atención al cliente para habilitar la sincronización de [!DNL Twitter] ID (ID de fuente de datos = 1123) para su cuenta. Esto es necesario para la sincronización correcta entre Audience Manager y [!DNL Twitter].

## Agregar un nuevo [!DNL Twitter Tailored Audiences] destino {#add-new-twitter-destination}

Esta sección describe los pasos que debe seguir al configurar un nuevo destino basado en dispositivos para [!DNL Twitter Tailored Audiences]. En este escenario se asume que no hay ningún destino [!DNL Twitter Tailored Audiences] configurado mediante el consultor de Adobe o el Servicio de atención al cliente.

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

## Actualizar Las Integraciones De Twitter Existentes A La Administración De Autoservicio {#update-existing-twitter-integrations}

Para mejorar la experiencia del usuario y optimizar el proceso de configuración, estamos actualizando la integración a un modelo de autoservicio, en el que puede realizar la configuración usted mismo, desde la interfaz de usuario de Audience Manager. [!DNL Twitter Tailored Audiences] En esta sección se describen los pasos que debe seguir para actualizar la integración existente de Twitter.

>[!IMPORTANT]
>
>Los pasos que se describen a continuación solo se aplican si tiene una integración existente con [!DNL Twitter Tailored Audiences], configurada por un asesor de Audience Manager o por el Servicio de atención al cliente.
> Consulte el artículo número 3 en Requisitos [previos](#prerequisites) antes de migrar [!DNL Twitter Tailored Audiences] al modelo de autoservicio.

Siga los pasos a continuación para migrar el destino existente [!DNL Twitter Tailored Audiences] al modelo de autoservicio.

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!DNL Administration > Integrated Accounts]**.
1. Haga clic en **[!DNL Add Account]**.
1. Seleccione [!DNL Twitter Tailored Audiences] y haga clic en **[!DNL Confirm]** para que se le redirija a la página de autenticación. ![plataformas integradas](assets/dbd-integrated-platforms.png)
1. Una vez que se haya autenticado con su [!DNL Twitter] cuenta, se le redirigirá a Audience Manager, donde debería ver sus cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!DNL Confirm]**.
1. Vaya a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** y haga clic en el destino de Twitter que necesita configurar.
1. Haga clic en **[!UICONTROL Edit]**. En la **[!UICONTROL Basic Information]** sección, haga clic en el menú **[!UICONTROL Integrated Account]** desplegable y seleccione la [!DNL Twitter] cuenta con la que se ha autenticado en el paso 4.
1. **[!UICONTROL Save]** el destino.

<!-- ## Validating the Migration to Self-Service Administration {#migration-validation}

The complete migration of existing [!DNL Twitter] integrations to self-service administration can take up to 7 days. Once the migration is complete, Audience Manager shows you a notification in the UI.

You will also see a new set of audiences in your [!DNL Twitter] account, with their names prefixed by [[!DNL Adobe DMP Audience]]. Please allow up to 7 days for the audience population to be completely backfilled. Once the migration is complete, you should use these new audiences instead of the old ones. -->

## Consideraciones sobre la asignación de segmentos {#segment-mapping-considerations}

Al asignar segmentos de audiencia a Twitter, asegúrese de cumplir los siguientes requisitos de nomenclatura de segmentos:

* Proporcione nombres de asignación de segmentos legibles por el usuario. Se recomienda utilizar el mismo nombre que se utilizó para los segmentos de Audience Manager.
* No utilice comas en los nombres de asignaciones de segmentos y segmentos.

### Ejemplo

* Nombre de asignación o segmento correcto: "Compradores europeos y estadounidenses";
* Nombre de asignación o segmento incorrecto: "EE.UU., europeo 5h0pP3rs".

>[!IMPORTANT]
>
>No puede cambiar los nombres de los segmentos ya asignados. Audience Manager utiliza los nombres de los segmentos para identificar correctamente los segmentos en la integración.

## Consideraciones sobre las tasas de coincidencia {#match-rates-considerations}

Al utilizar [!UICONTROL Twitter Tailored Audiences], las métricas [!UICONTROL Segment Addressable Audience] y [!UICONTROL Segment Match Rate] de la página de destino no mostrarán ningún valor. Esto es normal, ya que la coincidencia de audiencias junto con las tasas de coincidencia para este destino se gestionan y alojan en [!UICONTROL Twitter], no en Adobe.
