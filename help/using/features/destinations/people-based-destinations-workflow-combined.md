---
description: 'This page includes step-by-step guidance on how to combine offline CRM data with behavioral data that you already have in Audience Manager to create new audience segments, then send these audience segments to People-Based Destinations.  '
seo-description: 'This page includes step-by-step guidance on how to combine offline CRM data with behavioral data that you already have in Audience Manager to create new audience segments, then send these audience segments to People-Based Destinations.   '
seo-title: Workflow A - Personalization Based on All Online Activity Combined with Offline Data
solution: Audience Manager
title: 'Flujo de trabajo A: Personalización basada en toda la actividad en línea combinada con datos sin conexión'
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# Flujo de trabajo A: Personalización basada en toda la actividad en línea combinada con datos sin conexión {#workflow-a}

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a guiarle en la configuración y el uso de esta función. Nada de lo que aquí se incluye es asesoramiento jurídico. Por favor, consulte a su propio abogado para obtener asesoramiento jurídico.

Esta página incluye instrucciones paso a paso sobre cómo combinar datos sin conexión [!DNL CRM] con datos de comportamiento que ya tiene en Audience Manager para crear nuevos segmentos de audiencia y, a continuación, enviar estos segmentos de audiencia a [!DNL People-Based Destinations].

## Paso 1: Configuración de fuentes de datos {#configure-data-source-settings}

Dependiendo de si los [DPUUID](../../reference/ids-in-aam.md) están en minúsculas y las direcciones de correo electrónico con hash, es posible que tenga que configurar el origen de datos que almacenará las direcciones de correo electrónico con hash.

 

**Escenario 1: los[DPUUID](../../reference/ids-in-aam.md)ya están en minúsculas y tienen direcciones de correo electrónico con hash.**

En este caso, debe etiquetar la fuente de datos correspondiente como tal:

1. Vaya a [!UICONTROL Audience Data] -&gt; [!UICONTROL Data Sources].
1. Busque la fuente de datos que contiene los [DPUUID](../../reference/ids-in-aam.md)y haga clic en ella.
1. En el menú **[!UICONTROL ID Type]** desplegable, seleccione **[!UICONTROL Cross Device]**.
1. Asegúrese de que la opción [!UICONTROL Cannot be tied to personally identifiable information] está desactivada.
1. En la **[!UICONTROL Data Source Settings]** sección, seleccione las opciones **[!UICONTROL Inbound]** y **[!UICONTROL Outbound]** y active la **[!UICONTROL Share associated cross-device IDs in people-based destinations]** .
1. Utilice el menú desplegable para seleccionar la etiqueta de este origen de datos **[!UICONTROL Emails(SHA256, lowercased)]** .
   >[!IMPORTANT]
   >
   >Esta opción sólo etiqueta la fuente de datos como si contuviera datos con hash con ese algoritmo específico. Audience Manager no hash los datos en este paso. Asegúrese de que las direcciones de correo electrónico que planea almacenar en esta fuente de datos ya están marcadas con el algoritmo [!DNL SHA256] . De lo contrario, no podrás usarlo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Guarde la configuración del origen de datos.

 

**Escenario 2: sus[DPUUID](../../reference/ids-in-aam.md)no son direcciones de correo electrónico con hash en minúsculas.**

En este caso, debe crear una nueva fuente de datos entre dispositivos que almacenará las direcciones de correo electrónico con hash. A continuación se muestra cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]** y haga clic en **[!UICONTROL Add New]**.
1. Escriba un [!UICONTROL Name] y [!UICONTROL Description] para la nueva fuente de datos.
1. En el menú **[!UICONTROL ID Type]** desplegable, seleccione **[!UICONTROL Cross Device]**.
1. En la **[!UICONTROL Data Source Settings]** sección, seleccione las opciones **[!UICONTROL Inbound]** y **[!UICONTROL Outbound]** y active la **[!UICONTROL Share associated cross-device IDs in people-based destinations]** .
1. Utilice el menú desplegable para seleccionar la etiqueta de este origen de datos **[!UICONTROL Emails(SHA256, lowercased)]** .
   >[!IMPORTANT]
   >
   >This option only labels the data source as containing data hashed with that specific algorithm. Audience Manager does not hash the data at this step. Make sure the email addresses that you plan on storing in this data source are already hashed with the  algorithm. [!DNL SHA256] Otherwise, you won't be able to use it for .[!DNL People-Based Destinations]

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Save the data source settings.

>[!NOTE]
>
> See Data Onboarding for frequently asked questions about how you should bring your offline data into Audience Manager for People-Based Destinations.[](people-based-destinations-prerequisites.md#data-onboarding)

## Step 2 - Match DPUUIDs to Hashed Email Addresses via File-Based ID Synchronization {#match-ids-emails}

>[!IMPORTANT]
>
> This step only applies to Scenario 2 described above. [](people-based-destinations-workflow-combined.md#configure-data-source-settings) If your existing DPUUIDs are already hashed email addresses, skip to Step 3 - Create a Profile Merge Rule for Segmentation.[](../../reference/ids-in-aam.md)[](people-based-destinations-workflow-combined.md#create-merge-rule)

Let's say you want to match your existing DPUUIDs to the hashed email addresses from the table below (right column), and store the hashed email addresses in the new data source that you created at Step 1 - Configure Data Source Settings.[](../../reference/ids-in-aam.md)[](people-based-destinations-workflow-combined.md#configure-data-source-settings)

| DPUUID (ID de CRM) | La dirección de correo electrónico | Hashed email address |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

You can link up to 10 hashed email addresses to a single DPUUID. [](../../reference/ids-in-aam.md) To do this, separate the hashed email addresses with a comma, inside the synchronization file.

In our example, you would now have two data sources.

| ID de fuente de datos | Contenido de la fuente de datos |
| -------------- | -------------------------- |
| 999999 | DPUUID existentes (ID de CRM) |
| 987654 | Direcciones de correo electrónico con hash |

 

El archivo [de sincronización](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) de ID tendría el siguiente contenido:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

El archivo [de sincronización de](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ID debe seguir esta estructura de nomenclatura:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

En el ejemplo anterior, el nombre del archivo tendría este aspecto:
`c2c_id_999999_987654_1560431657.sync`

[Descargue el archivo de ejemplo aquí](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync).

## Paso 3: Creación de una regla de combinación de perfiles para la segmentación {#create-merge-rule}

El siguiente paso es crear una nueva regla de combinación que le ayudará a crear los segmentos de audiencia para enviarlos a los destinos basados en personas.

>[!IMPORTANT]
>
> Si ya tiene una regla definida con las opciones [!UICONTROL Current Authenticated Profiles] o [!UICONTROL Last Authenticated Profiles] , puede ir al [paso 4 - Crear segmentos](people-based-destinations-workflow-combined.md#create-audience-segments)de audiencia.

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Profile Merge Rules]**.
1. Haga clic en **[!UICONTROL Add New Rule]**.
1. Introduzca una regla de combinación de perfiles **[!UICONTROL Name]** y **[!UICONTROL Description]**.
1. En la **[!UICONTROL Profile Merge Rule Setup]** sección, seleccione las opciones **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]** .
1. En la **[!UICONTROL Cross-Device Profile Options]** lista, seleccione los orígenes de datos en los que desea ejecutar la segmentación. Deben ser las fuentes de datos que contengan los [DPUUID](../../reference/ids-in-aam.md)existentes.

## Paso 4: Creación de segmentos de audiencia {#create-audience-segments}

Para crear nuevos segmentos de audiencia, utilice el Generador [de segmentos](../segments/segment-builder.md). Si tiene segmentos de audiencia existentes a los que desea enviar [!DNL People-Based Destinations], vaya al [paso 5 - Configurar la autenticación](people-based-destinations-workflow-combined.md#configure-authentication)de plataforma basada en personas.

## Paso 5: Configurar la autenticación de plataforma basada en personas {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma social, debería verla en esta página. De lo contrario, la página está vacía.
   ![integración basada en las personas](assets/pbd-config.png)
1. Haga clic en **[!UICONTROL Add Account]**.
1. Utilice el menú **[!UICONTROL People-Based Platform]** desplegable para seleccionar la plataforma con la que desea configurar la integración.
   ![plataforma basada en las personas](assets/pbd-add.png)
1. Haga clic en **[!UICONTROL Confirm]** para que se le redirija a la página de autenticación de la plataforma seleccionada.
1. Una vez que se haya autenticado en la cuenta de la plataforma social, se le redirigirá a Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!UICONTROL Confirm]**.
1. Audience Manager displays a notification at the top of the page to let you know whether the account was successfully added. The notification also allows you to add a contact email address to receive notifications when the social platform authentication is about to expire.

>[!IMPORTANT]
>
>A udience Manager handles the integration with social platforms through authentication tokens that expire after a certain amount of time. Consulte Renovación de autentificador para obtener más información sobre cómo renovar los tokens caducados.

## Paso 6: Creación de un destino basado en personas {#create-destination}

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** y haga clic en **[!UICONTROL Create Destination]**.
1. En la **[!UICONTROL Basic Information]** sección , introduzca una **[!UICONTROL Name]** y **[!UICONTROL Description]** para la nueva fuente de datos y utilice la siguiente configuración:
   * **[!UICONTROL Category]**:: Plataformas integradas;
   * **[!UICONTROL Type]**:: Basado en personas;
   * **[!UICONTROL Platform]**:: seleccione la plataforma basada en personas a la que desee enviar segmentos de audiencia;
   * **[!UICONTROL Account]**:: seleccione la cuenta del anunciante que desee asociada a la plataforma seleccionada.
      ![create-destination](assets/pbd-create-destination.png)
1. Haga clic en **[!UICONTROL Next]**.
1. Elija el **[!UICONTROL Data Export Labels]** que desea establecer para este destino.
1. En la **[!UICONTROL Configuration]** sección , seleccione el origen de datos que contiene las fuentes de datos con hash.
1. En la **[!UICONTROL Segment Mappings]** sección, seleccione los segmentos que desee enviar a este destino. Serían los segmentos que creó en el [paso 4 - Crear segmentos](people-based-destinations-workflow-combined.md#create-audience-segments)de audiencia.
1. Guarde el destino.
