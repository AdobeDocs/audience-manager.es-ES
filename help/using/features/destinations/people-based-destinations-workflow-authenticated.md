---
description: Esta página incluye instrucciones paso a paso sobre cómo combinar datos de CRM sin conexión con datos de comportamiento en tiempo real para que los usuarios autenticados creen segmentos de audiencia y luego envíen estos segmentos de audiencia a People-Based Destinations.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with real-time behavioral data for authenticated users to create audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow C - Personalization Based on Authenticated Activity Combined with Offline Data
solution: Audience Manager
title: 'Flujo de trabajo C: personalización basada en Actividad autenticada combinada con datos sin conexión'
feature: People-based Destinations
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 5%

---

# Flujo de trabajo C: personalización basada en Actividad autenticada combinada con datos sin conexión {#workflow-c}

>[!IMPORTANT]
>Este artículo contiene documentación del producto que le guiará a través de la configuración y el uso de esta función. Nada de lo que contiene aquí es asesoramiento legal. Por favor, consulte a su propio asesor legal para obtener orientación legal.

Esta página incluye instrucciones paso a paso sobre cómo combinar sin conexión [!DNL CRM] datos con datos de comportamiento en tiempo real para que los usuarios autenticados creen segmentos de audiencia y luego envíen estos segmentos de audiencia a [!DNL People-Based Destinations].

## Paso 1: Configuración de la fuente de datos {#configure-data-source-settings}

En función de si su [DPUUID](../../reference/ids-in-aam.md) Si tiene direcciones de correo electrónico en minúsculas con hash, es posible que tenga que configurar la fuente de datos que almacenará las direcciones de correo electrónico con hash.

 

**Escenario 1: su [DPUUID](../../reference/ids-in-aam.md) ya son direcciones de correo electrónico con hash y en minúsculas.**

En este caso, saltarse a [Paso 5: Configuración de la autenticación de plataforma basada en personas](#configure-authentication).

 

**Escenario 2: su [DPUUID](../../reference/ids-in-aam.md) no son direcciones de correo electrónico con hash y en minúsculas.**

En este caso, debe crear una nueva fuente de datos entre dispositivos que almacene sus direcciones de correo electrónico con hash. A continuación se indica cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager de y vaya a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** y haga clic en **[!UICONTROL Add New]**.
1. Introduzca una **[!UICONTROL Name]** y **[!UICONTROL Description]** para la nueva fuente de datos.
1. En el **[!UICONTROL ID Type]** menú desplegable, seleccione **[!UICONTROL Cross Device]**.
1. En el **[!UICONTROL Data Source Settings]** , seleccione las dos opciones **[!UICONTROL Inbound]** y **[!UICONTROL Outbound]** y habilite la opción **[!UICONTROL Share associated cross-device IDs in people-based destinations]** opción.
1. Utilice el menú desplegable para seleccionar la variable **[!UICONTROL Emails(SHA256, lowercased)]** para esta fuente de datos.
   >[!IMPORTANT]
   >
   >Esta opción solo etiqueta la fuente de datos como que contiene datos con hash con ese algoritmo específico. El Audience Manager no hace un hash de los datos en este paso. Asegúrese de que las direcciones de correo electrónico que planea almacenar en esta fuente de datos ya tengan un cifrado hash con la variable [!DNL SHA256] algoritmo. De lo contrario, no podrá usarlo para lo siguiente [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulte [Incorporación de datos](people-based-destinations-prerequisites.md#data-onboarding) para obtener las preguntas más frecuentes sobre cómo debe llevar los datos sin conexión a Audience Manager para destinos basados en personas.

Vea el siguiente vídeo para ver un tutorial sobre cómo crear una fuente de datos para [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Paso 2: Uso de ID declarados para hacer coincidir DPUUID con direcciones de correo electrónico con hash a través de llamadas HTTP en tiempo real {#match-email-addresses}

Para calificar a los usuarios autenticados para los rasgos basados en reglas, debe enviar la calificación de rasgos mediante [ID declarados](../declared-ids.md).

### Ejemplo

Supongamos que ha creado las dos fuentes de datos siguientes.

| ID de fuente de datos | Contenido de fuente de datos |
| -------------- | -------------------------- |
| 999999 | DPUUID existentes (CRM ID) |
| 987654 | Direcciones de correo electrónico con hash |

 

A continuación, desea clasificar los ID de CRM siguientes para el rasgo de la tabla.

| DPUUID (ID DE CRM) | La dirección de correo electrónico | Dirección de correo electrónico con hash | Rasgo |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

 

El ID declarado debe seguir esta sintaxis:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

En el ejemplo anterior, la llamada de ID declarada debe tener este aspecto:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Paso 3: Creación de una regla de combinación de perfiles para la segmentación {#create-profile-merge-rule-segmentation}

El siguiente paso es crear una nueva regla de combinación que le ayudará a crear los segmentos de audiencia que desea enviar a su [!DNL People-Based Destinations].

>[!IMPORTANT]
>
>Si ya tiene una regla definida con la variable **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]** opciones, puede saltar a [Paso 4: Creación de segmentos de audiencia](#create-audience-segments).

1. Inicie sesión en su cuenta de Audience Manager de y vaya a **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Haga clic **[!UICONTROL Add New Rule]**.
3. Introducir una regla de combinación de perfiles **[!UICONTROL Name]** y **[!UICONTROL Description]**.
4. En el **[!UICONTROL Profile Merge Rule Setup]** , seleccione la **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]** regla desde el **[!UICONTROL Cross-Device Options]** lista.
5. En el **[!UICONTROL Cross-Device Profile Options]** , seleccione las fuentes de datos en las que desea ejecutar la segmentación. Estas deben ser las fuentes de datos que contengan los DPUUID existentes.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Paso 4: Creación de segmentos de audiencia {#create-audience-segments}

Para crear nuevos segmentos, utilice la variable [Generador de segmentos](../segments/segment-builder.md). Si tiene segmentos de audiencia existentes que quiere enviar a [!DNL People-Based Destinations], saltarse a [Paso 5: Configuración de la autenticación de plataforma basada en personas](#configure-authentication).

## Paso 5: Configuración de la autenticación de plataforma basada en personas {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager de y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma social, debería verla en esta página. En caso contrario, la página está vacía.
   ![people-based-integration](assets/pbd-config.png)
2. Haga clic **[!UICONTROL Add Account]**.
3. Utilice el **[!UICONTROL People-Based Platform]** menú desplegable para seleccionar la plataforma con la que desea configurar la integración.
   ![people-based-platform](assets/pbd-add.png)
4. Clic **[!UICONTROL Confirm]** para que se redirija a la página de autenticación de la plataforma seleccionada.
5. Una vez que se haya autenticado en su cuenta de la plataforma social, se le redirigirá a Audience Manager, donde debería ver sus cuentas de anunciante asociadas. Seleccione la cuenta de anunciante que desee utilizar y haga clic en **[!UICONTROL Confirm]**.
6. Audience Manager muestra una notificación en la parte superior de la página para informarle de si la cuenta se ha agregado correctamente. La notificación también le permite añadir una dirección de correo electrónico de contacto para recibir notificaciones cuando la autenticación de la plataforma social esté a punto de caducar.

>[!IMPORTANT]
>
>Audience Manager gestiona la integración con las plataformas sociales a través de tokens de autenticación que caducan después de un cierto tiempo. Consulte Renovación del token de autenticación para obtener más información sobre cómo renovar los tokens caducados.

## Paso 6: Creación de un destino basado en personas {#create-destination}

1. Inicie sesión en su cuenta de Audience Manager de, vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** y haga clic en **[!UICONTROL Create Destination]**.
1. En el **[!UICONTROL Basic Information]** , introduzca una **[!UICONTROL Name]** y **[!UICONTROL Description]** para la nueva fuente de datos y utilice la siguiente configuración:
   * **[!UICONTROL Category]**: Plataformas integradas;
   * **[!UICONTROL Type]**: Basado En Personas;
   * **[!UICONTROL Platform]**: seleccione la plataforma basada en personas a la que desee enviar segmentos de audiencia;
   * **[!UICONTROL Account]**: seleccione la cuenta de anunciante asociada con la plataforma seleccionada.
      ![create-destination](assets/pbd-create-destination.png)
1. Haga clic **[!UICONTROL Next]**.
1. Elija la **[!UICONTROL Data Export Labels]** que desea establecer para este destino.
1. En el **[!UICONTROL Configuration]** , seleccione la fuente de datos que contiene las fuentes de datos con hash.
1. En el **[!UICONTROL Segment Mappings]** , seleccione los segmentos que desea enviar a este destino. Estos serían los segmentos que creó en [Paso 4: Creación de segmentos de audiencia](#create-audience-segments).
1. Guarde el destino.
