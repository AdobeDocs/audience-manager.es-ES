---
description: Esta página incluye instrucciones paso a paso sobre cómo combinar datos de CRM sin conexión con datos de comportamiento en tiempo real para que los usuarios autenticados creen segmentos de audiencia y luego envíen estos segmentos de audiencia a People-Based Destinations.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with real-time behavioral data for authenticated users to create audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow C - Personalization Based on Authenticated Activity Combined with Offline Data
solution: Audience Manager
title: 'Flujo de trabajo C: Personalization basado en actividad autenticada combinada con datos sin conexión'
feature: People-based Destinations
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 1%

---

# Flujo de trabajo C: Personalization basado en actividad autenticada combinada con datos sin conexión {#workflow-c}

>[!IMPORTANT]
>Este artículo contiene documentación del producto que le guiará a través de la configuración y el uso de esta función. Nada de lo que contiene aquí es asesoramiento legal. Por favor, consulte a su propio asesor legal para obtener orientación legal.

Esta página incluye instrucciones paso a paso sobre cómo combinar datos de [!DNL CRM] sin conexión con datos de comportamiento en tiempo real para que usuarios autenticados creen segmentos de audiencia y luego envíen estos segmentos de audiencia a [!DNL People-Based Destinations].

## Paso 1: Configuración de Data Source {#configure-data-source-settings}

Dependiendo de si sus [DPUUID](../../reference/ids-in-aam.md) son direcciones de correo electrónico con hash y minúsculas, es posible que tenga que configurar el origen de datos que almacenará las direcciones de correo electrónico con hash.

 

**Escenario 1: sus [DPUUID](../../reference/ids-in-aam.md) ya son direcciones de correo electrónico con hash y en minúsculas.**

En este caso, vaya al [paso 5: Configurar el Authentication de Platform](#configure-authentication) basado en personas.

 

**Escenario 2: los [DPUUID](../../reference/ids-in-aam.md) no son direcciones de correo electrónico con valores hash en minúsculas.**

En este caso, debe crear una nueva fuente de datos dispositivos cruzada que tienda sus direcciones correo electrónico hash. A continuación, le indicamos cómo hacerlo:

1. Inicie sesión en su Audience Manager cuenta, vaya a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** y haga clic en **[!UICONTROL Add New]**.
1. Escriba **[!UICONTROL Name]** y **[!UICONTROL Description]** para el nuevo origen de datos.
1. En el menú desplegable **[!UICONTROL ID Type]**, seleccione **[!UICONTROL Cross Device]**.
1. En la sección **[!UICONTROL Data Source Settings]**, seleccione las opciones **[!UICONTROL Inbound]** y **[!UICONTROL Outbound]**, y habilite la opción **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilice el menú desplegable para seleccionar la etiqueta de este **[!UICONTROL Emails(SHA256, lowercased)]** fuente de datos.
   >[!IMPORTANT]
   >
   >Esta opción solo etiqueta el fuente de datos como que contiene datos hash con ese algoritmo específico. Audience Manager no hash los datos en este paso. Asegúrese de que las direcciones correo electrónico que tiene previsto almacenar en este fuente de datos ya tengan valores hash con el [!DNL SHA256] algoritmo. De lo contrario, no podrá usarlo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulte [Incorporación de datos](people-based-destinations-prerequisites.md#data-onboarding) para ver las preguntas más frecuentes sobre cómo debe llevar los datos sin conexión a Audience Manager para destinos basados en personas.

Vea el siguiente vídeo para ver un tutorial sobre cómo crear un origen de datos para [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Paso 2: Uso de ID declarados para hacer coincidir DPUUID con direcciones de correo electrónico con hash a través de llamadas HTTP en tiempo real {#match-email-addresses}

Para calificar a usuarios autenticados para rasgos basados en reglas, debe enviar la calificación de rasgos mediante [ID declarados](../declared-ids.md).

### Ejemplo

Supongamos que ha creado las dos fuentes de datos siguientes.

| ID de fuente de datos | Contenido de fuente de datos |
| -------------- | -------------------------- |
| 999999 | DPUUID existentes (ID CRM) |
| 987654 | Direcciones correo electrónico hash |

 

A continuación, querrá calificar los ID de CRM siguientes para el rasgo de la tabla.

| DPUUID (ID CRM) | La dirección de correo electrónico | Dirección de correo electrónico hash | Rasgo |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

 

El ID declarado debe seguir esta sintaxis:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

En el ejemplo anterior, la llamada de ID declarada debe tener este aspecto:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Paso 3: Creación de una regla de combinación de perfiles para la segmentación {#create-profile-merge-rule-segmentation}

El siguiente paso es crear un nuevo regla de combinación que le ayudará a crear los segmentos audiencia para enviar a su [!DNL People-Based Destinations]archivo .

>[!IMPORTANT]
>
>Si ya tiene un regla definido con las opciones o **[!UICONTROL Current Authenticated Profiles]**, puede ir al **[!UICONTROL Last Authenticated Profiles]** paso 4: Crear Segmentos de [ audiencia.](#create-audience-segments)

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Haga clic en **[!UICONTROL Add New Rule]**.
3. Especifique una combinación perfil regla **[!UICONTROL Name]** y **[!UICONTROL Description]**.
4. En la sección **[!UICONTROL Profile Merge Rule Setup]**, seleccione la regla **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]** de la lista **[!UICONTROL Cross-Device Options]**.
5. En la lista **[!UICONTROL Cross-Device Profile Options]**, seleccione los orígenes de datos en los que desea ejecutar la segmentación. Estas deben ser las fuentes de datos que contengan los DPUUID existentes.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Paso 4: Crear segmentos de audiencia {#create-audience-segments}

Para crear nuevos segmentos, utilice el Generador[ de ](../segments/segment-builder.md)segmentos. Si ya tiene segmentos de audiencia que desea enviar a [!DNL People-Based Destinations], vaya al [Paso 5: Configurar la Authentication de Platform](#configure-authentication) basadas en personas.

## Paso 5: Configuración de la autenticación de plataforma basada en personas {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma social, debería verla en esta página. En caso contrario, la página está vacía.
   ![integración basada en personas](assets/pbd-config.png)
2. Haga clic en **[!UICONTROL Add Account]**.
3. Utilice el menú desplegable **[!UICONTROL People-Based Platform]** para seleccionar la plataforma con la que desea configurar la integración.
   ![plataforma basada en personas](assets/pbd-add.png)
4. Haga clic en **[!UICONTROL Confirm]** para que se le redirija a la página de autenticación de la plataforma seleccionada.
5. Una vez que se haya autenticado en su cuenta de la plataforma social, se le redirigirá a Audience Manager, donde debería ver sus cuentas de anunciante asociadas. Seleccione la cuenta de anunciante que desee usar y haga clic en **[!UICONTROL Confirm]**.
6. Audience Manager muestra una notificación en la parte superior de la página para informarle de si la cuenta se ha agregado correctamente. La notificación también le permite añadir una dirección de correo electrónico de contacto para recibir notificaciones cuando la autenticación de la plataforma social esté a punto de caducar.

>[!IMPORTANT]
>
>Audience Manager gestiona la integración con plataformas sociales a través de tokens de autenticación que caducan después de un cierto período de tiempo. Consulte Authentication renovación de tokens para obtener más información sobre cómo renovar los tokens caducados.

## Paso 6: Crear un destino basado en personas {#create-destination}

1. Inicie sesión en su Audience Manager cuenta, vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** y haga clic en **[!UICONTROL Create Destination]**.
1. En la **[!UICONTROL Basic Information]** sección, introduzca un **[!UICONTROL Name]** y **[!UICONTROL Description]** para el nuevo fuente de datos y utilice la siguiente configuración:
   * **[!UICONTROL Category]**: Plataformas Integradas;
   * **[!UICONTROL Type]**: basado en personas;
   * **[!UICONTROL Platform]**: seleccione la plataforma basada en personas a la que desee enviar segmentos de audiencia;
   * **[!UICONTROL Account]**: seleccione la cuenta de anunciante deseada asociada con la plataforma seleccionada.
     ![crear destino](assets/pbd-create-destination.png)
1. Haga clic en **[!UICONTROL Next]**.
1. Elija el(la) **[!UICONTROL Data Export Labels]** que desea(n) establecer para este destino.
1. En la sección **[!UICONTROL Configuration]**, seleccione el origen de datos que contiene los orígenes de datos con hash.
1. En la sección **[!UICONTROL Segment Mappings]**, seleccione los segmentos que desee enviar a este destino. Estos serían los segmentos que creó en [Paso 4 - Crear segmentos de audiencia](#create-audience-segments).
1. Guarde el destino.
