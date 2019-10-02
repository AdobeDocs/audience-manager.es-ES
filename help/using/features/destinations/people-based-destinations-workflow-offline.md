---
description: 'Esta página incluye una guía paso a paso sobre cómo generar segmentos de audiencia a partir de datos de clientes sin conexión y enviarlos a destinos basados en personas.  '
seo-description: 'Esta página incluye una guía paso a paso sobre cómo generar segmentos de audiencia a partir de datos de clientes sin conexión y enviarlos a destinos basados en personas.  '
seo-title: 'Flujo de trabajo B: Personalización basada en datos solo sin conexión'
solution: Audience Manager
title: 'Flujo de trabajo B: Personalización basada en datos solo sin conexión'
translation-type: tm+mt
source-git-commit: ad9c077f538759e195a83d47e0ef36ccffa25c7e

---


# Flujo de trabajo B: Personalización basada en datos solo sin conexión {#workflow-b}

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a guiarle en la configuración y el uso de esta función. Nada de lo que aquí se incluye es asesoramiento jurídico. Por favor, consulte a su propio abogado para obtener asesoramiento jurídico.

Esta página incluye una guía paso a paso sobre cómo generar segmentos de audiencia a partir de datos de clientes sin conexión y enviarlos a destinos basados en personas.

## Paso 1: Características sin conexión integradas {#step-1-onboard-traits}

The first step creating audience segments in this scenario is to bring your offline customer data into Audience Manager.

>[!IMPORTANT]
>
> Antes de continuar, asegúrese de que la actividad de cliente que va a incorporar ya está definida en Audience Manager con las características [integradas correspondientes](../traits/trait-qualification-reference.md).

Independientemente de si los ID de cliente de Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) existentes son o no correos electrónicos con hash, debe realizar la incorporación de características en el origen de datos que contiene los [DPUUID](../../reference/ids-in-aam.md).

### Ejemplo

Desea calificar los ID de cliente de la tabla siguiente para los ID de característica incorporados correspondientes. Let's consider that your DPUUIDs are stored in a data source with the ID 999999, and your Audience Manager Partner ID is 123.[](../../reference/ids-in-aam.md)

| Customer ID (DPUUID) | Onboarded Trait ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />
To qualify the customer IDs in the example above for the corresponding onboarded traits, you must upload an [inbound data file](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) with the following contents:

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

1. Go to  -&gt; .**[!UICONTROL Audience Data]****[!UICONTROL Data Sources]**
1. Find the data source that contains your DPUUIDs, and click it.[](../../reference/ids-in-aam.md)
1. Asegúrese de que la opción **[!UICONTROL Cannot be tied to personally identifiable information]** está desactivada.
1. Save the data source settings.

 

**Escenario 2: sus[DPUUID](../../reference/ids-in-aam.md)no son direcciones de correo electrónico con hash en minúsculas.**

En este caso, debe crear una nueva fuente de datos entre dispositivos que almacenará las direcciones de correo electrónico con hash. A continuación se muestra cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]** y haga clic en **[!UICONTROL Add New]**.
1. Escriba un **[!UICONTROL Name]** y **[!UICONTROL Description]** para la nueva fuente de datos.
1. En el menú **[!UICONTROL ID Type]** desplegable, seleccione **[!UICONTROL Cross Device]**.
1. In the  section, select both the  and  options, and enable the  option.**[!UICONTROL Data Source Settings]****[!UICONTROL Inbound]****[!UICONTROL Outbound]****[!UICONTROL Share associated cross-device IDs in people-based destinations]**
1. Use the drop-down menu to select the  label for this data source.**[!UICONTROL Emails(SHA256, lowercased)]**
   >[!IMPORTANT]
   >
   >This option only labels the data source as containing data hashed with that specific algorithm. Audience Manager no hash los datos en este paso. Make sure the email addresses that you plan on storing in this data source are already hashed with the  algorithm. [!DNL SHA256] De lo contrario, no podrás usarlo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulte [Incorporación](people-based-destinations-prerequisites.md#data-onboarding) de datos para ver las preguntas más frecuentes sobre cómo debe llevar los datos sin conexión a Audience Manager para destinos basados en personas.

## Paso 3: Hacer coincidir los DPUUID con las direcciones de correo electrónico con hash mediante la sincronización de ID basada en archivos {#match-ids-emails}

>[!IMPORTANT]
>
> Este paso solo se aplica al [escenario 2](people-based-destinations-workflow-offline.md#configure-data-source-settings) descrito anteriormente. Si los [DPUUID](../../reference/ids-in-aam.md) existentes ya tienen direcciones de correo electrónico con hash, vaya al [paso 4 - Crear una regla de combinación de perfiles para la segmentación](#create-profile-merge-rule).

Supongamos que desea hacer coincidir los [DPUUID](../../reference/ids-in-aam.md) existentes desde el ejemplo del paso 1 con las direcciones de correo electrónico con hash de la tabla siguiente (columna derecha) y almacenar las direcciones de correo electrónico con hash en la nueva fuente de datos que creó en el [paso 2 - Configurar la fuente de datos](#configure-data-source-settings).

Como recordatorio, ahora tendría dos fuentes de datos:

| ID de fuente de datos | Contenido de la fuente de datos |
| -------------- | -------------------------- |
| 999999 | DPUUID existentes (ID de CRM) |
| 987654 | Direcciones de correo electrónico con hash |

| DPUUID (ID de CRM) | La dirección de correo electrónico | Dirección de correo electrónico con hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

En nuestro ejemplo, el archivo [de sincronización de](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ID tendría el siguiente contenido:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

El archivo [de sincronización de](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ID debe seguir esta estructura de nomenclatura:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

In the example above, the file name would look like this:
`c2c_id_999999_987654_1560431657.sync`

[Descargue el archivo de ejemplo aquí](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync).

Una vez creado el archivo de sincronización de ID, debe cargarlo en un [!DNL Amazon S3] bloque. Para obtener información sobre cómo cargar archivos de sincronización de ID, consulte [Envío de datos por lotes a Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Paso 4: Creación de una regla de combinación de perfiles para la segmentación {#create-profile-merge-rule}

El siguiente paso es crear una nueva regla de combinación que le ayudará a crear los segmentos de audiencia que se enviarán a su [!DNL People-Based Destinations].

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Profile Merge Rules]**.
2. Haga clic [!UICONTROL Add New Rule].
3. Enter a profile merge rule  and .**[!UICONTROL Name]****[!UICONTROL Description]**
4. In the  section, select the  rule from the  list.**[!UICONTROL Profile Merge Rule Setup]****[!UICONTROL All Cross-Device Profiles]****[!UICONTROL Cross-Device Options]**
5. En la **[!UICONTROL Cross-Device Profile Options]** lista, seleccione el origen de datos con el que se han incorporado sus características.
   ![merge-rule-setup](assets/pbd-pmr.png)

## Paso 5: Crear segmentos de audiencia {#create-audience-segments}

Para crear nuevos segmentos a partir de datos solo sin conexión, utilice el Generador [de](../segments/segment-builder.md) segmentos y asegúrese de utilizar la nueva regla de combinación de perfiles que creó en el paso anterior al crear el segmento.

## Paso 6: Configurar la autenticación de plataforma basada en personas {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma social, debería verla en esta página. De lo contrario, la página está vacía.
   ![people-based-integration](assets/pbd-config.png)
1. Haga clic en **[!UICONTROL Add Account]**.
1. Use the  drop-down menu to select the platform that you want to configure the integration with.**[!UICONTROL People-Based Platform]**
   ![people-based-platform](assets/pbd-add.png)
1. Click  to be redirected to the authentication page of the selected platform.**[!UICONTROL Confirm]**
1. Una vez que se haya autenticado en la cuenta de la plataforma social, se le redirigirá a Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!UICONTROL Confirm]**.
1. Audience Manager muestra una notificación en la parte superior de la página para indicarle si la cuenta se agregó correctamente. La notificación también le permite agregar una dirección de correo electrónico de contacto para recibir notificaciones cuando la autenticación de la plataforma social esté a punto de caducar.

>[!IMPORTANT]
>
>Audience Manager gestiona la integración con las plataformas sociales mediante tokens de autenticación que caducan después de una determinada cantidad de tiempo. Consulte Renovación de autentificador para obtener más información sobre cómo renovar los tokens caducados.

## Paso 7: Creación de un destino basado en personas {#create-destination}

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
1. En la **[!UICONTROL Segment Mappings]** sección, seleccione los segmentos que desee enviar a este destino. This would be the segments that you created at Step 5 - Create Audience Segments.[](people-based-destinations-workflow-offline.md#create-audience-segments)
1. Guarde el destino.
