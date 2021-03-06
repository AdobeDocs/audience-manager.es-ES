---
description: 'Esta página incluye instrucciones paso a paso sobre cómo crear segmentos de audiencia a partir de datos de clientes que solo están sin conexión y enviarlos a Destinos basados en personas.  '
seo-description: 'Esta página incluye instrucciones paso a paso sobre cómo crear segmentos de audiencia a partir de datos de clientes que solo están sin conexión y enviarlos a Destinos basados en personas.  '
seo-title: 'Flujo de trabajo B: personalización basada en datos solo sin conexión'
solution: Audience Manager
title: 'Flujo de trabajo B: personalización basada en datos solo sin conexión'
feature: Destinos basados en personas
exl-id: d980de26-3133-4ae3-80c2-8c3bf2480bbd
source-git-commit: 87c3169083f0dc66490e6a8c808e16371f1d78c0
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 6%

---

# Flujo de trabajo B: personalización basada en datos solo sin conexión {#workflow-b}

>[!IMPORTANT]
>Este artículo contiene documentación del producto pensada para guiarle en la configuración y uso de esta función. Nada de lo contenido en este documento es asesoramiento jurídico. Consulte a su propio asesor jurídico para obtener asesoramiento jurídico.

Esta página incluye instrucciones paso a paso sobre cómo crear segmentos de audiencia a partir de datos de clientes que solo están sin conexión y enviarlos a Destinos basados en personas.

## Paso 1: Incorporar características sin conexión {#step-1-onboard-traits}

El primer paso para crear segmentos de audiencia en este escenario es introducir los datos de clientes sin conexión en Audience Manager.

>[!IMPORTANT]
>
> Antes de continuar, asegúrese de que la actividad del cliente que está a punto de incorporar ya esté definida en Audience Manager con los [rasgos integrados](../traits/trait-and-segment-qualification-reference.md) correspondientes.

Independientemente de si los ID de cliente de Audience Manager existentes ([DPUUIDs](../../reference/ids-in-aam.md)) son correos electrónicos con hash o no, debe realizar la incorporación de rasgos en relación con la fuente de datos que contiene sus [DPUUID](../../reference/ids-in-aam.md).

### Ejemplo

Desea clasificar los ID de cliente de la siguiente tabla para los ID de rasgo incorporados correspondientes. Consideremos que sus [DPUUIDs](../../reference/ids-in-aam.md) se almacenan en una fuente de datos con el ID 999999, y que su ID de fuente de datos de Audience Manager es 123.

| ID de cliente (DPUUID) | ID de rasgo incorporado |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />

Para calificar los ID de cliente en el ejemplo anterior para los rasgos integrados correspondientes, debe cargar un [archivo de datos entrantes](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) con el siguiente contenido:

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

El nombre del archivo tendría este aspecto: `ftp_dpm_999999_123_TIMESTAMP.sync.gz`.
Consulte [Requisitos de tamaño de archivo y nombre de Amazon S3 para archivos de datos entrantes](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) para obtener información detallada sobre la estructura de nombres de archivo.

## Paso 2: Configuración de fuentes de datos {#configure-data-source-settings}

Dependiendo de si sus [DPUUID](../../reference/ids-in-aam.md) están en minúsculas y direcciones de correo electrónico con hash, es posible que tenga que configurar la fuente de datos que almacenará las direcciones de correo electrónico con hash.

 

**Escenario 1: sus  [](../../reference/ids-in-aam.md) DPUUID ya son direcciones de correo electrónico con hash en minúsculas.**

En este caso, debe etiquetar la fuente de datos correspondiente como tal:

1. Vaya a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**.
1. Busque la fuente de datos que contiene sus [DPUUIDs](../../reference/ids-in-aam.md) y haga clic en ella.
1. Asegúrese de que la opción **[!UICONTROL Cannot be tied to personally identifiable information]** no esté seleccionada.
1. Guarde la configuración de la fuente de datos.

 

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

## Paso 3: Hacer coincidir los DPUUID con las direcciones de correo electrónico con hash mediante la sincronización de ID basada en archivos {#match-ids-emails}

>[!IMPORTANT]
>
> Este paso solo se aplica al [Escenario 2](people-based-destinations-workflow-offline.md#configure-data-source-settings) descrito anteriormente. Si los [DPUUIDs](../../reference/ids-in-aam.md) existentes ya son direcciones de correo electrónico con hash, vaya al [Paso 4: Crear una regla de combinación de perfiles para la segmentación](#create-profile-merge-rule).

Supongamos que desea hacer coincidir los [DPUUID](../../reference/ids-in-aam.md) existentes del ejemplo del paso 1 con las direcciones de correo electrónico con hash de la siguiente tabla (columna derecha) y almacenar las direcciones de correo electrónico con hash en la nueva fuente de datos que creó en el [paso 2: Configuración de fuentes de datos](#configure-data-source-settings).

Como recordatorio, ahora tendría dos fuentes de datos:

| ID de fuente de datos | Contenido de la fuente de datos |
| -------------- | -------------------------- |
| 999999 | DPUUID existentes (ID de CRM) |
| 987654 | Direcciones de correo electrónico con hash |

| DPUUID (ID de CRM) | La dirección de correo electrónico | Dirección de correo electrónico con hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15044 149 |
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

## Paso 4: Creación de una regla de combinación de perfiles para la segmentación {#create-profile-merge-rule}

El siguiente paso es crear una nueva regla de combinación que le ayudará a crear los segmentos de audiencia que desea enviar a su [!DNL People-Based Destinations].

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Haga clic [!UICONTROL Add New Rule].
3. Introduzca una regla de combinación de perfiles **[!UICONTROL Name]** y **[!UICONTROL Description]**.
4. En la sección **[!UICONTROL Profile Merge Rule Setup]** , seleccione la regla **[!UICONTROL All Cross-Device Profiles]** de la lista **[!UICONTROL Cross-Device Options]**.
5. En la lista **[!UICONTROL Cross-Device Profile Options]**, seleccione la fuente de datos con la que se incorporan sus rasgos.
   ![merge-rule-setup](assets/pbd-pmr.png)

## Paso 5: Creación de segmentos de audiencia {#create-audience-segments}

Para crear nuevos segmentos a partir de datos solo sin conexión, utilice el [Generador de segmentos](../segments/segment-builder.md) y asegúrese de utilizar la nueva regla de combinación de perfiles que creó en el paso anterior al crear el segmento.

## Paso 6: Configuración de la autenticación de plataforma basada en personas {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma social, debería verla en esta página. De lo contrario, la página estará vacía.
   ![integración basada en personas](assets/pbd-config.png)
1. Haga clic **[!UICONTROL Add Account]**.
1. Utilice el menú desplegable **[!UICONTROL People-Based Platform]** para seleccionar la plataforma con la que desea configurar la integración.
   ![plataforma basada en personas](assets/pbd-add.png)
1. Haga clic en **[!UICONTROL Confirm]** para redirigirse a la página de autenticación de la plataforma seleccionada.
1. Una vez que se haya autenticado en la cuenta de la plataforma social, se le redirigirá al Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!UICONTROL Confirm]**.
1. Audience Manager muestra una notificación en la parte superior de la página para informarle de si la cuenta se agregó correctamente. La notificación también le permite añadir una dirección de correo electrónico de contacto para recibir notificaciones cuando la autenticación de la plataforma social esté a punto de caducar.

>[!IMPORTANT]
>
>El Audience Manager gestiona la integración con plataformas sociales mediante tokens de autenticación que caducan después de un cierto tiempo. Consulte Renovación de tokens de autenticación para obtener más información sobre cómo renovar los tokens caducados.

## Paso 7: Creación de un destino basado en personas {#create-destination}

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
1. En la sección **[!UICONTROL Segment Mappings]** , seleccione los segmentos que desee enviar a este destino. Estos serían los segmentos que creó en el [Paso 5: Crear segmentos de audiencia](people-based-destinations-workflow-offline.md#create-audience-segments).
1. Guarde el destino.
