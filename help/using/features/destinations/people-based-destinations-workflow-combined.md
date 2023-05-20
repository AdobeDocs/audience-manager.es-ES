---
description: Esta página incluye instrucciones paso a paso sobre cómo combinar datos de CRM sin conexión con datos de comportamiento que ya tiene en Audience Manager para crear nuevos segmentos de audiencia y, a continuación, enviar estos segmentos de audiencia a People-Based Destinations.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with behavioral data that you already have in Audience Manager to create new audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow A - Personalization Based on All Online Activity Combined with Offline Data
solution: Audience Manager
title: 'Flujo de trabajo A: personalización basada en toda la Actividad en línea combinada con datos sin conexión'
feature: People-based Destinations
exl-id: 1f906955-8fe7-4cce-95d6-0e4275d523e8
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 6%

---

# Flujo de trabajo A: personalización basada en toda la Actividad en línea combinada con datos sin conexión {#workflow-a}

>[!IMPORTANT]
>Este artículo contiene documentación del producto que le guiará a través de la configuración y el uso de esta función. Nada de lo que contiene aquí es asesoramiento legal. Por favor, consulte a su propio asesor legal para obtener orientación legal.

Esta página incluye instrucciones paso a paso sobre cómo combinar sin conexión [!DNL CRM] datos de comportamiento que ya tiene en Audience Manager para crear nuevos segmentos de audiencia y, a continuación, envíe estos segmentos de audiencia a [!DNL People-Based Destinations].

## Paso 1: Configuración de la fuente de datos {#configure-data-source-settings}

En función de si su [DPUUID](../../reference/ids-in-aam.md) Si tiene direcciones de correo electrónico en minúsculas con hash, es posible que tenga que configurar la fuente de datos que almacenará las direcciones de correo electrónico con hash.

 

**Escenario 1: su [DPUUID](../../reference/ids-in-aam.md) ya son direcciones de correo electrónico con hash y en minúsculas.**

En este caso, debe etiquetar la fuente de datos correspondiente como tal:

1. Ir a [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Busque la fuente de datos que contiene su [DPUUID](../../reference/ids-in-aam.md)y haga clic en él.
1. En el **[!UICONTROL ID Type]** menú desplegable, seleccione **[!UICONTROL Cross Device]**.
1. Asegúrese de que la opción [!UICONTROL Cannot be tied to personally identifiable information] está desmarcada.
1. En el **[!UICONTROL Data Source Settings]** , seleccione las dos opciones **[!UICONTROL Inbound]** y **[!UICONTROL Outbound]** y habilite la opción **[!UICONTROL Share associated cross-device IDs in people-based destinations]** opción.
1. Utilice el menú desplegable para seleccionar la variable **[!UICONTROL Emails(SHA256, lowercased)]** para esta fuente de datos.
   >[!IMPORTANT]
   >
   >Esta opción solo etiqueta la fuente de datos como que contiene datos con hash con ese algoritmo específico. El Audience Manager no hace un hash de los datos en este paso. Asegúrese de que las direcciones de correo electrónico que planea almacenar en esta fuente de datos ya tengan un cifrado hash con la variable [!DNL SHA256] algoritmo. De lo contrario, no podrá usarlo para lo siguiente [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Guarde la configuración de la fuente de datos.

 

**Escenario 2: su [DPUUID](../../reference/ids-in-aam.md) no son direcciones de correo electrónico con hash y en minúsculas.**

En este caso, debe crear una nueva fuente de datos entre dispositivos que almacene sus direcciones de correo electrónico con hash. A continuación se indica cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager de y vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** y haga clic en **[!UICONTROL Add New]**.
1. Introduzca una [!UICONTROL Name] y [!UICONTROL Description] para la nueva fuente de datos.
1. En el **[!UICONTROL ID Type]** menú desplegable, seleccione **[!UICONTROL Cross Device]**.
1. En el **[!UICONTROL Data Source Settings]** , seleccione las dos opciones **[!UICONTROL Inbound]** y **[!UICONTROL Outbound]** y habilite la opción **[!UICONTROL Share associated cross-device IDs in people-based destinations]** opción.
1. Utilice el menú desplegable para seleccionar la variable **[!UICONTROL Emails(SHA256, lowercased)]** para esta fuente de datos.
   >[!IMPORTANT]
   >
   >Esta opción solo etiqueta la fuente de datos como que contiene datos con hash con ese algoritmo específico. El Audience Manager no hace un hash de los datos en este paso. Asegúrese de que las direcciones de correo electrónico que planea almacenar en esta fuente de datos ya tengan un cifrado hash con la variable [!DNL SHA256] algoritmo. De lo contrario, no podrá usarlo para lo siguiente [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Guarde la configuración de la fuente de datos.

Vea el siguiente vídeo para ver un tutorial sobre cómo crear una fuente de datos para [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> Consulte [Incorporación de datos](people-based-destinations-prerequisites.md#data-onboarding) para obtener las preguntas más frecuentes sobre cómo debe llevar los datos sin conexión a Audience Manager para destinos basados en personas.

## Paso 2: Hacer coincidir DPUUID con direcciones de correo electrónico con hash mediante la sincronización de ID basada en archivos {#match-ids-emails}

>[!IMPORTANT]
>
> Este paso solo se aplica a [Escenario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) descrito anteriormente. Si su [DPUUID](../../reference/ids-in-aam.md) ya son direcciones de correo electrónico con hash, saltarse a [Paso 3: Creación de una regla de combinación de perfiles para la segmentación](people-based-destinations-workflow-combined.md#create-merge-rule).

Supongamos que desea hacer coincidir su existente [DPUUID](../../reference/ids-in-aam.md) a las direcciones de correo electrónico con hash de la siguiente tabla (columna derecha) y almacene las direcciones de correo electrónico con hash en la nueva fuente de datos que creó en [Paso 1: Configuración de la fuente de datos](people-based-destinations-workflow-combined.md#configure-data-source-settings).

| DPUUID (ID DE CRM) | La dirección de correo electrónico | Dirección de correo electrónico con hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Puede vincular hasta 10 direcciones de correo electrónico con hash a una sola [DPUUID](../../reference/ids-in-aam.md). Para ello, separe las direcciones de correo electrónico con hash con una `<TAB>`, dentro del archivo de sincronización.

En nuestro ejemplo, ahora tendría dos fuentes de datos.

| ID de fuente de datos | Contenido de fuente de datos |
| -------------- | -------------------------- |
| 999999 | DPUUID existentes (CRM ID) |
| 987654 | Direcciones de correo electrónico con hash |

 

Su [Archivo de sincronización de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) tendría el siguiente contenido:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

El [Archivo de sincronización de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) debe seguir esta estructura de nomenclatura:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

En el ejemplo anterior, el nombre de archivo tendría este aspecto:
`c2c_id_999999_987654_1560431657.sync`

[Descargue el archivo de ejemplo aquí](assets/c2c_id_999999_987654_1560431657.sync).

Una vez creado el archivo de sincronización de ID, debe cargarlo en una [!DNL Amazon S3] cubo. Para obtener información sobre cómo cargar archivos de sincronización de ID, consulte [Enviar datos por lotes al Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Paso 3: Creación de una regla de combinación de perfiles para la segmentación {#create-merge-rule}

El siguiente paso es crear una nueva regla de combinación que le ayudará a crear los segmentos de audiencia que desea enviar a sus destinos basados en personas.

>[!IMPORTANT]
>
> Si ya tiene una regla definida con la variable [!UICONTROL Current Authenticated Profiles] o [!UICONTROL Last Authenticated Profiles] opciones, puede saltar a [Paso 4: Creación de segmentos de audiencia](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Inicie sesión en su cuenta de Audience Manager de y vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Haga clic **[!UICONTROL Add New Rule]**.
1. Introducir una regla de combinación de perfiles **[!UICONTROL Name]** y **[!UICONTROL Description]**.
1. En el **[!UICONTROL Profile Merge Rule Setup]** , seleccione la **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]** opciones.
1. En el **[!UICONTROL Cross-Device Profile Options]** , seleccione las fuentes de datos en las que desea ejecutar la segmentación. Estas deben ser las fuentes de datos que contengan el [DPUUID](../../reference/ids-in-aam.md).

## Paso 4: Creación de segmentos de audiencia {#create-audience-segments}

Para crear nuevos segmentos de audiencia, utilice el [Generador de segmentos](../segments/segment-builder.md). Si tiene segmentos de audiencia existentes que quiere enviar a [!DNL People-Based Destinations], saltarse a [Paso 5: Configuración de la autenticación de plataforma basada en personas](people-based-destinations-workflow-combined.md#configure-authentication).

## Paso 5: Configuración de la autenticación de plataforma basada en personas {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager de y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma social, debería verla en esta página. En caso contrario, la página está vacía.
   ![people-based-integration](assets/pbd-config.png)
1. Haga clic **[!UICONTROL Add Account]**.
1. Utilice el **[!UICONTROL People-Based Platform]** menú desplegable para seleccionar la plataforma con la que desea configurar la integración.
   ![people-based-platform](assets/pbd-add.png)
1. Clic **[!UICONTROL Confirm]** para que se redirija a la página de autenticación de la plataforma seleccionada.
1. Una vez que se haya autenticado en su cuenta de la plataforma social, se le redirigirá a Audience Manager, donde debería ver sus cuentas de anunciante asociadas. Seleccione la cuenta de anunciante que desee utilizar y haga clic en **[!UICONTROL Confirm]**.
1. Audience Manager muestra una notificación en la parte superior de la página para informarle de si la cuenta se ha agregado correctamente. La notificación también le permite añadir una dirección de correo electrónico de contacto para recibir notificaciones cuando la autenticación de la plataforma social esté a punto de caducar.

>[!IMPORTANT]
>
>Un Audience Manager gestiona la integración con las plataformas sociales a través de tokens de autenticación que caducan después de un cierto período de tiempo. Consulte Renovación del token de autenticación para obtener más información sobre cómo renovar los tokens caducados.

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
1. En el **[!UICONTROL Segment Mappings]** , seleccione los segmentos que desea enviar a este destino. Estos serían los segmentos que creó en [Paso 4: Creación de segmentos de audiencia](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Guarde el destino.
