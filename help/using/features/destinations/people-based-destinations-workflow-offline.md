---
description: 'Esta página incluye una guía paso a paso sobre cómo generar segmentos de audiencia a partir de datos de clientes sin conexión y enviarlos a destinos basados en personas.  '
seo-description: 'Esta página incluye una guía paso a paso sobre cómo generar segmentos de audiencia a partir de datos de clientes sin conexión y enviarlos a destinos basados en personas.  '
seo-title: 'Flujo de trabajo B: Personalización basada en datos solo sin conexión'
solution: Audience Manager
title: 'Flujo de trabajo B: Personalización basada en datos solo sin conexión'
translation-type: tm+mt
source-git-commit: fb5d9eff3573048d3e8a570b342a97bce3cd8da0

---


# Workflow B - Personalization Based on Offline-Only Data {#workflow-b}

>[!IMPORTANT]
>This article contains product documentation meant to guide you through the setup and usage of this feature. Nada de lo que aquí se incluye es asesoramiento jurídico. Please consult your own legal counsel for legal guidance.

This page includes step-by-step guidance on how to build audience segments from offline-only customer data, and send them to People-Based Destinations.

## Step 1 - Onboard Offline Traits {#step-1-onboard-traits}

The first step creating audience segments in this scenario is to bring your offline customer data into Audience Manager.

>[!IMPORTANT]
>
> Before continuing, make sure that the customer activity that you are about to onboard is already defined in Audience Manager with corresponding [onboarded traits](../traits/trait-qualification-reference.md).

Regardless of whether your existing Audience Manager customer IDs (DPUUIDs) are hashed emails or not, you must perform the trait onboarding against the data source that contains your DPUUIDs.[](../../reference/ids-in-aam.md)[](../../reference/ids-in-aam.md)

### Ejemplo

You want to qualify the customer IDs from the table below for the corresponding onboarded trait IDs. Consideremos que sus [DPUUID](../../reference/ids-in-aam.md) se almacenan en un origen de datos con el ID 999999 y que su ID de socio de Audience Manager es 123.

| ID del cliente (DPUUID) | ID de característica incorporado |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />
Para calificar los ID de cliente en el ejemplo anterior para las características integradas correspondientes, debe cargar un [archivo de datos de entrada](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) con el siguiente contenido:

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

El nombre del archivo tendría este aspecto: `ftp_dpm_999999_123_TIMESTAMP.sync.gz`.
Consulte Requisitos de nombre y tamaño de archivo de [Amazon S3 para archivos](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) de datos de entrada para obtener información detallada sobre la estructura de nombres de archivo.

## Paso 2: Configuración de fuentes de datos {#configure-data-source-settings}

Dependiendo de si los [DPUUID](../../reference/ids-in-aam.md) están en minúsculas y las direcciones de correo electrónico con hash, es posible que tenga que configurar el origen de datos que almacenará las direcciones de correo electrónico con hash.

 

**Escenario 1: los[DPUUID](../../reference/ids-in-aam.md)ya están en minúsculas y tienen direcciones de correo electrónico con hash.**

En este caso, debe etiquetar la fuente de datos correspondiente como tal:

1. Vaya a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**.
1. Busque la fuente de datos que contiene los [DPUUID](../../reference/ids-in-aam.md)y haga clic en ella.
1. Asegúrese de que la opción **[!UICONTROL Cannot be tied to personally identifiable information]** está desactivada.
1. Guarde la configuración del origen de datos.

 

**Escenario 2: sus[DPUUID](../../reference/ids-in-aam.md)no son direcciones de correo electrónico con hash en minúsculas.**

En este caso, debe crear una nueva fuente de datos entre dispositivos que almacenará las direcciones de correo electrónico con hash. A continuación se muestra cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]** y haga clic en **[!UICONTROL Add New]**.
1. Escriba un **[!UICONTROL Name]** y **[!UICONTROL Description]** para la nueva fuente de datos.
1. En el menú **[!UICONTROL ID Type]** desplegable, seleccione **[!UICONTROL Cross Device]**.
1. En la **[!UICONTROL Data Source Settings]** sección, seleccione las opciones **[!UICONTROL Inbound]** y **[!UICONTROL Outbound]** y active la **[!UICONTROL Share associated cross-device IDs in people-based destinations]** .
1. Utilice el menú desplegable para seleccionar la etiqueta de este origen de datos **[!UICONTROL Emails(SHA256, lowercased)]** .
   >[!IMPORTANT]
   >
   >Esta opción sólo etiqueta la fuente de datos como si contuviera datos con hash con ese algoritmo específico. Audience Manager does not hash the data at this step. Asegúrese de que las direcciones de correo electrónico que planea almacenar en esta fuente de datos ya están marcadas con el algoritmo [!DNL SHA256] . De lo contrario, no podrás usarlo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > See Data Onboarding for frequently asked questions about how you should bring your offline data into Audience Manager for People-Based Destinations.[](people-based-destinations-prerequisites.md#data-onboarding)

## Step 3 - Match DPUUIDs to Hashed Email Addresses via File-Based ID Synchronization {#match-ids-emails}

>[!IMPORTANT]
>
> This step only applies to Scenario 2 described above. [](people-based-destinations-workflow-offline.md#configure-data-source-settings) If your existing DPUUIDs are already hashed email addresses, skip to Step 4 - Create a Profile Merge Rule for Segmentation.[](../../reference/ids-in-aam.md)[](#create-profile-merge-rule)

Supongamos que desea hacer coincidir los [DPUUID](../../reference/ids-in-aam.md) existentes desde el ejemplo del paso 1 con las direcciones de correo electrónico con hash de la tabla siguiente (columna derecha) y almacenar las direcciones de correo electrónico con hash en la nueva fuente de datos que creó en el [paso 2 - Configurar la fuente de datos](#configure-data-source-settings).

As a reminder, you would now have two data sources:

| ID de fuente de datos | Data source contents |
| -------------- | -------------------------- |
| 999999 | DPUUID existentes (ID de CRM) |
| 987654 | Direcciones de correo electrónico con hash |

| DPUUID (ID de CRM) | La dirección de correo electrónico | Hashed email address |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

In our example, your ID synchronization file would have the following contents:[](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

The ID synchronization file must follow this naming structure:[](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

In the example above, the file name would look like this:
`c2c_id_999999_987654_1560431657.sync`

[Download example file here.](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync)

Once you've created your ID synchronization file, you need to upload it to an  bucket. [!DNL Amazon S3] Para obtener información sobre cómo cargar archivos de sincronización de ID, consulte [Envío de datos por lotes a Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Step 4 - Create a Profile Merge Rule for Segmentation {#create-profile-merge-rule}

El siguiente paso es crear una nueva regla de combinación que le ayudará a crear los segmentos de audiencia que se enviarán a su [!DNL People-Based Destinations].

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Profile Merge Rules]**.
2. Haga clic [!UICONTROL Add New Rule].
3. Introduzca una regla de combinación de perfiles **[!UICONTROL Name]** y **[!UICONTROL Description]**.
4. En la **[!UICONTROL Profile Merge Rule Setup]** , seleccione la **[!UICONTROL All Cross-Device Profiles]** regla en la **[!UICONTROL Cross-Device Options]** lista.
5. En la **[!UICONTROL Cross-Device Profile Options]** lista, seleccione el origen de datos con el que se han incorporado sus características.
   ![merge-rule-setup](assets/pbd-pmr.png)

## Paso 5: Crear segmentos de audiencia {#create-audience-segments}

Para crear nuevos segmentos a partir de datos solo sin conexión, utilice el Generador [de](../segments/segment-builder.md) segmentos y asegúrese de utilizar la nueva regla de combinación de perfiles que creó en el paso anterior al crear el segmento.

## Paso 6: Configurar la autenticación de plataforma basada en personas {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma social, debería verla en esta página. De lo contrario, la página está vacía.
   ![integración basada en las personas](assets/pbd-config.png)
1. Haga clic en **[!UICONTROL Add Account]**.
1. Utilice el menú **[!UICONTROL People-Based Platform]** desplegable para seleccionar la plataforma con la que desea configurar la integración.
   ![plataforma basada en las personas](assets/pbd-add.png)
1. Haga clic en **[!UICONTROL Confirm]** para que se le redirija a la página de autenticación de la plataforma seleccionada.
1. Una vez que se haya autenticado en la cuenta de la plataforma social, se le redirigirá a Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!UICONTROL Confirm]**.
1. Audience Manager muestra una notificación en la parte superior de la página para indicarle si la cuenta se agregó correctamente. La notificación también le permite agregar una dirección de correo electrónico de contacto para recibir notificaciones cuando la autenticación de la plataforma social esté a punto de caducar.

>[!IMPORTANT]
>
>A udience Manager handles the integration with social platforms through authentication tokens that expire after a certain amount of time. See Authentication Token Renewal for details on how to renew the expired tokens.

## Step 7 - Create a People-Based Destination {#create-destination}

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** y haga clic en **[!UICONTROL Create Destination]**.
1. In the  section, enter a  and  for your new data source, and use the following settings:**[!UICONTROL Basic Information]****[!UICONTROL Name]****[!UICONTROL Description]**
   * **[!UICONTROL Category]**:: Plataformas integradas;
   * **[!UICONTROL Type]**:: Basado en personas;
   * **[!UICONTROL Platform]**:: seleccione la plataforma basada en personas a la que desee enviar segmentos de audiencia;
   * **[!UICONTROL Account]**:: select the desired advertiser account associated with the selected platform.
      ![create-destination](assets/pbd-create-destination.png)
1. Haga clic en **[!UICONTROL Next]**.
1. Elija el **[!UICONTROL Data Export Labels]** que desea establecer para este destino.
1. En la **[!UICONTROL Configuration]** sección , seleccione el origen de datos que contiene las fuentes de datos con hash.
1. En la **[!UICONTROL Segment Mappings]** sección, seleccione los segmentos que desee enviar a este destino. Serían los segmentos que creó en el [paso 5 - Crear segmentos](people-based-destinations-workflow-offline.md#create-audience-segments)de audiencia.
1. Guarde el destino.
