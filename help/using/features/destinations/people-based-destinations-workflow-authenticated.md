---
description: 'Esta página incluye instrucciones paso a paso sobre cómo combinar datos de CRM sin conexión con datos de comportamiento en tiempo real para usuarios autenticados para crear segmentos de audiencia y luego enviar estos segmentos de audiencia a destinos basados en personas. '
seo-description: 'Esta página incluye instrucciones paso a paso sobre cómo combinar datos de CRM sin conexión con datos de comportamiento en tiempo real para usuarios autenticados para crear segmentos de audiencia y luego enviar estos segmentos de audiencia a destinos basados en personas.  '
seo-title: 'Flujo de trabajo C: personalización basada en Actividad autenticada combinada con datos sin conexión'
solution: Audience Manager
title: 'Flujo de trabajo C: personalización basada en Actividad autenticada combinada con datos sin conexión'
feature: People-based Destinations
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 5%

---

# Flujo de trabajo C: personalización basada en Actividad autenticada combinada con datos sin conexión {#workflow-c}

>[!IMPORTANT]
>Este artículo contiene documentación del producto pensada para guiarle en la configuración y uso de esta función. Nada de lo contenido en este documento es asesoramiento jurídico. Consulte a su propio asesor jurídico para obtener asesoramiento jurídico.

Esta página incluye instrucciones paso a paso sobre cómo combinar datos sin conexión [!DNL CRM] con datos de comportamiento en tiempo real para que los usuarios autenticados creen segmentos de audiencia y luego envíen estos segmentos de audiencia a [!DNL People-Based Destinations].

## Paso 1: Configuración de fuentes de datos {#configure-data-source-settings}

Dependiendo de si sus [DPUUID](../../reference/ids-in-aam.md) están en minúsculas y direcciones de correo electrónico con hash, es posible que tenga que configurar la fuente de datos que almacenará las direcciones de correo electrónico con hash.

 

**Escenario 1: sus  [](../../reference/ids-in-aam.md) DPUUID ya son direcciones de correo electrónico con hash en minúsculas.**

En este caso, vaya al [Paso 5: Configurar la autenticación de plataforma basada en personas](#configure-authentication).

 

**Escenario 2: sus  [](../../reference/ids-in-aam.md) DPUUID no son direcciones de correo electrónico con hash en minúsculas.**

En este caso, debe crear una nueva fuente de datos entre dispositivos que almacene las direcciones de correo electrónico con hash. A continuación se muestra cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** y haga clic en **[!UICONTROL Add New]**.
1. Introduzca **[!UICONTROL Name]** y **[!UICONTROL Description]** en la nueva fuente de datos.
1. En el menú desplegable **[!UICONTROL ID Type]**, seleccione **[!UICONTROL Cross Device]**.
1. En la sección **[!UICONTROL Data Source Settings]**, seleccione las opciones **[!UICONTROL Inbound]** y **[!UICONTROL Outbound]** y habilite la opción **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilice el menú desplegable para seleccionar la etiqueta **[!UICONTROL Emails(SHA256, lowercased)]** para esta fuente de datos.
   >[!IMPORTANT]
   >
   >Esta opción solo etiqueta la fuente de datos como que contiene datos con hash con ese algoritmo específico. El Audience Manager no hash los datos en este paso. Asegúrese de que las direcciones de correo electrónico que planea almacenar en esta fuente de datos ya estén hash con el algoritmo [!DNL SHA256]. De lo contrario, no podrá usarla para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulte [Incorporación de datos](people-based-destinations-prerequisites.md#data-onboarding) para conocer las preguntas más frecuentes sobre cómo debe incorporar los datos sin conexión al Audience Manager de destinos basados en personas.

Vea el siguiente vídeo para ver un tutorial en vídeo sobre cómo crear una fuente de datos para [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Paso 2: Utilice los ID declarados para hacer coincidir los DPUUID con las direcciones de correo electrónico con hash a través de llamadas HTTP en tiempo real {#match-email-addresses}

Para calificar a los usuarios autenticados para rasgos basados en reglas, debe enviar la calificación de rasgos a través de [ID declarados](../declared-ids.md).

### Ejemplo

Supongamos que ha creado las dos fuentes de datos siguientes.

| ID de fuente de datos | Contenido de la fuente de datos |
| -------------- | -------------------------- |
| 999999 | DPUUID existentes (ID de CRM) |
| 987654 | Direcciones de correo electrónico con hash |

 

A continuación, desea clasificar los ID de CRM que aparecen a continuación para la característica de la tabla.

| DPUUID (CRM ID) | La dirección de correo electrónico | Dirección de correo electrónico con hash | Rasgo |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15044 149 | ubicación = EE. UU. |

 

El ID declarado debe seguir esta sintaxis:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

En el ejemplo anterior, la llamada de ID declarada debe tener este aspecto:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Paso 3: Crear una regla de combinación de perfiles para la segmentación {#create-profile-merge-rule-segmentation}

El siguiente paso es crear una nueva regla de combinación que le ayudará a crear los segmentos de audiencia que desea enviar a su [!DNL People-Based Destinations].

>[!IMPORTANT]
>
>Si ya tiene una regla definida con las opciones **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]** , puede ir al [Paso 4 - Crear segmentos de audiencia](#create-audience-segments).

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Haga clic **[!UICONTROL Add New Rule]**.
3. Introduzca una regla de combinación de perfiles **[!UICONTROL Name]** y **[!UICONTROL Description]**.
4. En la sección **[!UICONTROL Profile Merge Rule Setup]** , seleccione la regla **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]** en la lista **[!UICONTROL Cross-Device Options]**.
5. En la lista **[!UICONTROL Cross-Device Profile Options]**, seleccione las fuentes de datos en las que desea ejecutar la segmentación. Estas deben ser las fuentes de datos que contengan sus DPUUID existentes.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Paso 4: Creación de segmentos de audiencia {#create-audience-segments}

Para crear nuevos segmentos, utilice el [Generador de segmentos](../segments/segment-builder.md). Si tiene segmentos de audiencia existentes que desea enviar a [!DNL People-Based Destinations], vaya al [Paso 5: Configurar la autenticación de plataforma basada en personas](#configure-authentication).

## Paso 5: Configuración de la autenticación de plataforma basada en personas {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma social, debería verla en esta página. De lo contrario, la página estará vacía.
   ![integración basada en personas](assets/pbd-config.png)
2. Haga clic **[!UICONTROL Add Account]**.
3. Utilice el menú desplegable **[!UICONTROL People-Based Platform]** para seleccionar la plataforma con la que desea configurar la integración.
   ![plataforma basada en personas](assets/pbd-add.png)
4. Haga clic en **[!UICONTROL Confirm]** para redirigirse a la página de autenticación de la plataforma seleccionada.
5. Una vez que se haya autenticado en la cuenta de la plataforma social, se le redirigirá al Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!UICONTROL Confirm]**.
6. Audience Manager muestra una notificación en la parte superior de la página para informarle de si la cuenta se agregó correctamente. La notificación también le permite añadir una dirección de correo electrónico de contacto para recibir notificaciones cuando la autenticación de la plataforma social esté a punto de caducar.

>[!IMPORTANT]
>
>El Audience Manager gestiona la integración con plataformas sociales mediante tokens de autenticación que caducan después de un cierto tiempo. Consulte Renovación de tokens de autenticación para obtener más información sobre cómo renovar los tokens caducados.

## Paso 6: Creación de un destino basado en personas {#create-destination}

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** y haga clic en **[!UICONTROL Create Destination]**.
1. En la sección **[!UICONTROL Basic Information]**, introduzca un **[!UICONTROL Name]** y **[!UICONTROL Description]** para la nueva fuente de datos y utilice la siguiente configuración:
   * **[!UICONTROL Category]**: Plataformas integradas;
   * **[!UICONTROL Type]**: Basadas en personas;
   * **[!UICONTROL Platform]**: seleccione la plataforma basada en personas a la que desee enviar segmentos de audiencia;
   * **[!UICONTROL Account]**: seleccione la cuenta del anunciante que desee asociada a la plataforma seleccionada.
      ![create-destination](assets/pbd-create-destination.png)
1. Haga clic **[!UICONTROL Next]**.
1. Elija el **[!UICONTROL Data Export Labels]** que desea establecer para este destino.
1. En la sección **[!UICONTROL Configuration]**, seleccione la fuente de datos que contiene los orígenes de datos con hash.
1. En la sección **[!UICONTROL Segment Mappings]** , seleccione los segmentos que desee enviar a este destino. Estos serían los segmentos que ha creado en [Paso 4: Crear segmentos de audiencia](#create-audience-segments).
1. Guarde el destino.
