---
description: 'Esta página incluye instrucciones paso a paso sobre cómo generar segmentos de audiencia a partir de datos de clientes sin conexión y enviarlos a destinos basados en personas.  '
seo-description: 'Esta página incluye instrucciones paso a paso sobre cómo generar segmentos de audiencia a partir de datos de clientes sin conexión y enviarlos a destinos basados en personas.  '
seo-title: 'Flujo de trabajo B: personalización basada en datos solo sin conexión'
solution: Audience Manager
title: 'Flujo de trabajo B: personalización basada en datos solo sin conexión'
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 6%

---


# Flujo de trabajo B: personalización basada en datos solo sin conexión {#workflow-b}

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a guiarle en la configuración y el uso de esta función. Nada de lo que aquí se incluye es asesoramiento jurídico. Por favor, consulte a su propio abogado para obtener asesoramiento jurídico.

Esta página incluye instrucciones paso a paso sobre cómo generar segmentos de audiencia a partir de datos de clientes sin conexión y enviarlos a destinos basados en personas.

## Paso 1: Características sin conexión integradas {#step-1-onboard-traits}

El primer paso para crear segmentos de audiencia en este escenario es llevar los datos de clientes sin conexión al Audience Manager.

>[!IMPORTANT]
>
> Antes de continuar, asegúrese de que la actividad del cliente que está a punto de incorporar ya está definida en Audience Manager con las características [integradas correspondientes](../traits/trait-and-segment-qualification-reference.md).

Independientemente de si los ID de cliente del Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) son correos electrónicos con hash o no, debe realizar la incorporación con la característica en el origen de datos que contiene los [DPUUID](../../reference/ids-in-aam.md).

### Ejemplo

Desea calificar los ID de cliente de la tabla siguiente para los ID de rasgo incorporados correspondientes. Consideremos que sus [DPUUID](../../reference/ids-in-aam.md) se almacenan en una fuente de datos con el ID 999999 y su ID de socio Audience Manager es 123.

| ID del cliente (DPUUID) | ID de característica incorporado |
| -------------------------------------- | ------------------- |
| 6807998276567319850405265607456196039 | 12345, 23456 |
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
Consulte [Requisitos de nombre y tamaño de archivo de Amazon S3 para archivos de datos de entrada](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) para obtener información detallada sobre la estructura de nombres de archivo.

## Paso 2: Configuración de fuentes de datos {#configure-data-source-settings}

Según si los [DPUUID](../../reference/ids-in-aam.md) son direcciones de correo electrónico en minúsculas y con hash, es posible que tenga que configurar el origen de datos que almacenará las direcciones de correo electrónico con hash.

 

**Escenario 1: sus  [](../../reference/ids-in-aam.md) DPUUIDsya tienen direcciones de correo electrónico con hash en minúsculas.**

En este caso, debe etiquetar la fuente de datos correspondiente como tal:

1. Vaya a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**.
1. Busque la fuente de datos que contiene sus [DPUUID](../../reference/ids-in-aam.md) y haga clic en ella.
1. Asegúrese de que la opción **[!UICONTROL Cannot be tied to personally identifiable information]** está desactivada.
1. Guarde la configuración del origen de datos.

 

**Escenario 2: sus direcciones de correo electrónico con hash  [](../../reference/ids-in-aam.md) DPUUID no están en minúsculas.**

En este caso, debe crear una nueva fuente de datos entre dispositivos que almacenará las direcciones de correo electrónico con hash. A continuación se muestra cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** y haga clic en **[!UICONTROL Add New]**.
1. Escriba **[!UICONTROL Name]** y **[!UICONTROL Description]** para la nueva fuente de datos.
1. En el menú desplegable **[!UICONTROL ID Type]**, seleccione **[!UICONTROL Cross Device]**.
1. En la sección **[!UICONTROL Data Source Settings]**, seleccione las opciones **[!UICONTROL Inbound]** y **[!UICONTROL Outbound]** y habilite la opción **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilice el menú desplegable para seleccionar la etiqueta **[!UICONTROL Emails(SHA256, lowercased)]** para este origen de datos.
   >[!IMPORTANT]
   >
   >Esta opción sólo etiqueta la fuente de datos como si contuviera datos con hash con ese algoritmo específico. El Audience Manager no hash los datos en este paso. Asegúrese de que las direcciones de correo electrónico que planea almacenar en esta fuente de datos ya están marcadas con el algoritmo [!DNL SHA256]. De lo contrario, no podrá utilizarlo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulte [Inicio de datos](people-based-destinations-prerequisites.md#data-onboarding) para ver las preguntas más frecuentes sobre cómo debe llevar los datos sin conexión a Audience Manager para destinos basados en personas.

Vea el siguiente vídeo para ver un tutorial de vídeo sobre cómo crear una fuente de datos para [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Paso 3: Hacer coincidir los DPUUID con las direcciones de correo electrónico con hash mediante la sincronización de ID basada en archivos {#match-ids-emails}

>[!IMPORTANT]
>
> Este paso solo se aplica al [escenario 2](people-based-destinations-workflow-offline.md#configure-data-source-settings) descrito anteriormente. Si los [DPUUID](../../reference/ids-in-aam.md) existentes ya tienen direcciones de correo electrónico con hash, vaya a [Paso 4 - Crear una regla de combinación de Perfiles para la segmentación](#create-profile-merge-rule).

Supongamos que desea hacer coincidir los [DPUUID](../../reference/ids-in-aam.md) existentes desde el ejemplo del Paso 1 con las direcciones de correo electrónico con hash de la tabla siguiente (columna derecha) y almacenar las direcciones de correo electrónico con hash en la nueva fuente de datos que creó en [Paso 2 - Configurar la fuente de datos](#configure-data-source-settings).

Como recordatorio, ahora tendría dos fuentes de datos:

| ID de fuente de datos | Contenido de la fuente de datos |
| -------------- | -------------------------- |
| 999999 | DPUUID existentes (ID de CRM) |
| 987654 | Direcciones de correo electrónico con hash |

| DPUUID (ID de CRM) | La dirección de correo electrónico | Dirección de correo electrónico con hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 6807998276567319850405265607456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041 149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

En nuestro ejemplo, su [archivo de sincronización de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) tendría el siguiente contenido:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

El [archivo de sincronización de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) debe seguir esta estructura de nombres:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

En el ejemplo anterior, el nombre del archivo tendría este aspecto:
`c2c_id_999999_987654_1560431657.sync`

[Descargue el archivo de ejemplo aquí](assets/c2c_id_999999_987654_1560431657.sync).

Una vez creado el archivo de sincronización de ID, debe cargarlo en un bloque [!DNL Amazon S3]. Para obtener información sobre cómo cargar archivos de sincronización de ID, consulte [Envío de datos por lotes al Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Paso 4: Crear una regla de combinación de Perfiles para la segmentación {#create-profile-merge-rule}

El siguiente paso es crear una nueva regla de combinación que le ayudará a crear los segmentos de audiencia para enviarlos a su [!DNL People-Based Destinations].

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Haga clic [!UICONTROL Add New Rule].
3. Introduzca una regla de combinación de perfiles **[!UICONTROL Name]** y **[!UICONTROL Description]**.
4. En la sección **[!UICONTROL Profile Merge Rule Setup]**, seleccione la regla **[!UICONTROL All Cross-Device Profiles]** de la lista **[!UICONTROL Cross-Device Options]**.
5. En la lista **[!UICONTROL Cross-Device Profile Options]**, seleccione el origen de datos con el que se incorporan sus características.
   ![merge-rule-setup](assets/pbd-pmr.png)

## Paso 5: Crear segmentos de Audiencia {#create-audience-segments}

Para crear nuevos segmentos a partir de datos solo sin conexión, utilice el [Generador de segmentos](../segments/segment-builder.md) y asegúrese de utilizar la nueva regla de combinación de perfiles que creó en el paso anterior al crear el segmento.

## Paso 6: Configurar la autenticación de plataforma basada en usuarios {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma social, debería verla en esta página. De lo contrario, la página está vacía.
   ![integración basada en las personas](assets/pbd-config.png)
1. Haga clic **[!UICONTROL Add Account]**.
1. Utilice el menú desplegable **[!UICONTROL People-Based Platform]** para seleccionar la plataforma con la que desea configurar la integración.
   ![plataforma basada en las personas](assets/pbd-add.png)
1. Haga clic en **[!UICONTROL Confirm]** para que se le redirija a la página de autenticación de la plataforma seleccionada.
1. Una vez que se haya autenticado en la cuenta de la plataforma social, se le redirigirá al Audience Manager, donde debería ver las cuentas del anunciante asociado. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!UICONTROL Confirm]**.
1. Audience Manager muestra una notificación en la parte superior de la página para informarle de si la cuenta se agregó correctamente. La notificación también le permite agregar una dirección de correo electrónico de contacto para recibir notificaciones cuando la autenticación de la plataforma social esté a punto de caducar.

>[!IMPORTANT]
>
>El Audience Manager gestiona la integración con las plataformas sociales mediante tokens de autenticación que caducan después de una determinada cantidad de tiempo. Consulte Renovación de autentificador para obtener más información sobre cómo renovar los tokens caducados.

## Paso 7: Crear un destino basado en personas {#create-destination}

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** y haga clic en **[!UICONTROL Create Destination]**.
1. En la sección **[!UICONTROL Basic Information]**, escriba **[!UICONTROL Name]** y **[!UICONTROL Description]** para la nueva fuente de datos y utilice la siguiente configuración:
   * **[!UICONTROL Category]**:: Plataformas integradas;
   * **[!UICONTROL Type]**:: Basado en personas;
   * **[!UICONTROL Platform]**:: seleccione la plataforma basada en personas a la que desee enviar segmentos de audiencia;
   * **[!UICONTROL Account]**:: seleccione la cuenta del anunciante que desee asociada a la plataforma seleccionada.
      ![create-destination](assets/pbd-create-destination.png)
1. Haga clic **[!UICONTROL Next]**.
1. Elija el **[!UICONTROL Data Export Labels]** que desea establecer para este destino.
1. En la sección **[!UICONTROL Configuration]**, seleccione el origen de datos que contiene las fuentes de datos con hash.
1. En la sección **[!UICONTROL Segment Mappings]**, seleccione los segmentos que desee enviar a este destino. Serían los segmentos que creó en [Paso 5 - Crear segmentos de Audiencia](people-based-destinations-workflow-offline.md#create-audience-segments).
1. Guarde el destino.
