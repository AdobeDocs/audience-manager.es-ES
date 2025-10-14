---
description: Este Página incluye instrucciones paso a paso sobre cómo combinar datos de CRM de sin conexión con datos de comportamiento que ya tiene en Audience Manager crear nuevos segmentos de audiencia y luego enviar estos segmentos de audiencia a destinos basados en personas.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with behavioral data that you already have in Audience Manager to create new audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow A - Personalization Based on All Online Activity Combined with Offline Data
solution: Audience Manager
title: 'Flujo de trabajo A: Personalización basada en toda la actividad en línea combinada con datos sin conexión'
feature: People-based Destinations
exl-id: 1f906955-8fe7-4cce-95d6-0e4275d523e8
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 0%

---

# Flujo de trabajo A: Personalización basada en toda la actividad en línea combinada con datos sin conexión {#workflow-a}

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a ayudarle guía a través de la configuración y el uso de esta característica. Nada de lo contenido en este documento es asesoramiento legal. Consulte a su propio asesor legal para obtener orientación legal.

Este Página incluye instrucciones paso a paso sobre cómo combinar datos de sin conexión [!DNL CRM] con datos de comportamiento que ya tiene en Audience Manager crear nuevos segmentos de audiencia y, a continuación, enviar estos segmentos de audiencia a [!DNL People-Based Destinations].

## Paso 1: Configuración de datos Origen Configuración {#configure-data-source-settings}

En función de si los [DPUUID están en minúsculas](../../reference/ids-in-aam.md) y tienen direcciones correo electrónico hash, es posible que deba configurar el fuente de datos que tienda las direcciones de correo electrónico con hash.

 

**Escenario 1: sus [DPUUID](../../reference/ids-in-aam.md) ya están en minúsculas, direcciones correo electrónico con hash.**

En este caso, debe etiquetar la fuente de datos correspondiente como tal:

1. Vaya a [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Busque el fuente de datos que contiene sus [DPUUID](../../reference/ids-in-aam.md) y haga clic en él.
1. En el **[!UICONTROL ID Type]** menú desplegable, seleccione **[!UICONTROL Cross Device]**.
1. Asegúrese de que la opción [!UICONTROL Cannot be tied to personally identifiable information] no esté marcada.
1. En la **[!UICONTROL Data Source Settings]** sección, seleccione las **[!UICONTROL Inbound]** opciones y **[!UICONTROL Outbound]** y habilite la **[!UICONTROL Share associated cross-device IDs in people-based destinations]** opción.
1. Utilice el menú desplegable para seleccionar la etiqueta de este **[!UICONTROL Emails(SHA256, lowercased)]** fuente de datos.
   >[!IMPORTANT]
   >
   >Esta opción solo etiqueta el fuente de datos como que contiene datos hash con ese algoritmo específico. Audience Manager no hash los datos en este paso. Asegúrese de que las direcciones correo electrónico que tiene previsto almacenar en este fuente de datos ya tengan valores hash con el [!DNL SHA256] algoritmo. De lo contrario, no podrá usarlo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Guardar la configuración de fuente de datos.

 

**Escenario 2: los [DPUUID](../../reference/ids-in-aam.md) no son direcciones de correo electrónico con valores hash en minúsculas.**

En este caso, debe crear una nueva fuente de datos dispositivos cruzada que tienda sus direcciones correo electrónico hash. A continuación, le indicamos cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** y haga clic en **[!UICONTROL Add New]**.
1. Escriba un [!UICONTROL Name] y [!UICONTROL Description] para el nuevo fuente de datos.
1. En el **[!UICONTROL ID Type]** menú desplegable, seleccione **[!UICONTROL Cross Device]**.
1. En la **[!UICONTROL Data Source Settings]** sección, seleccione las **[!UICONTROL Inbound]** opciones y **[!UICONTROL Outbound]** y habilite la **[!UICONTROL Share associated cross-device IDs in people-based destinations]** opción.
1. Utilice el menú desplegable para seleccionar la etiqueta de este **[!UICONTROL Emails(SHA256, lowercased)]** fuente de datos.
   >[!IMPORTANT]
   >
   >Esta opción solo etiqueta el fuente de datos como que contiene datos hash con ese algoritmo específico. Audience Manager no hash los datos en este paso. Asegúrese de que las direcciones correo electrónico que tiene previsto almacenar en este fuente de datos ya tengan valores hash con el [!DNL SHA256] algoritmo. De lo contrario, no podrá usarlo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Guardar la configuración de fuente de datos.

Vea el vídeo siguiente para ver un vídeo tutorial de cómo crear un fuente de datos para [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/32174?captions=spa)

>[!NOTE]
>
> Consulte [Incorporación](people-based-destinations-prerequisites.md#data-onboarding) de datos para ver las preguntas más frecuentes sobre cómo debe incorporar sus datos de sin conexión a Audience Manager para destinos basados en personas.

## Paso 2: Hacer coincidir los DPUUID con las direcciones de correo electrónico con hash mediante la sincronización de ID basada en Archivo {#match-ids-emails}

>[!IMPORTANT]
>
> Este paso solo se aplica al [escenario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) descrito anteriormente. Si sus [DPUUID](../../reference/ids-in-aam.md) existentes ya son direcciones correo electrónico hash, vaya al [Paso 3: Crear una regla de combinación de perfiles para segmentación](people-based-destinations-workflow-combined.md#create-merge-rule).

Supongamos que desea hacer coincidir sus DPUUID existentes [con las direcciones de correo electrónico con hash de la tabla siguiente (columna derecha) y tienda las direcciones de correo electrónico con hash en el nuevo fuente de datos que creó en &#x200B;](../../reference/ids-in-aam.md)Paso 1: Configurar datos Origen Configuración[.](people-based-destinations-workflow-combined.md#configure-data-source-settings)

| DPUUID (ID CRM) | La dirección de correo electrónico | Dirección de correo electrónico hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Puede vincular hasta 10 direcciones correo electrónico con hash a un solo [DPUUID.](../../reference/ids-in-aam.md) Para ello, separe las direcciones de correo electrónico con hash con un `<TAB>`, dentro del archivo de sincronización.

En nuestro ejemplo, ahora tendría dos fuentes de datos.

| ID de origen de datos | Contenido de las fuentes de datos |
| -------------- | -------------------------- |
| 999999 | DPUUID existentes (ID CRM) |
| 987654 | Direcciones correo electrónico hash |

 

El [archivo](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) de sincronización de ID tendrá el siguiente contenido:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

El [archivo](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) de sincronización de ID debe seguir esta estructura de nombres:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

En el ejemplo anterior, el nombre de archivo se vería gustar esto:`c2c_id_999999_987654_1560431657.sync`

[Descargue el archivo de ejemplo aquí](assets/c2c_id_999999_987654_1560431657.sync).

Una vez que haya creado el archivo de sincronización de ID, debe cargar a un [!DNL Amazon S3] bucket. Para obtener información sobre cómo cargar archivos de sincronización de ID, consulte [Envío de datos de Lote a Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Paso 3: Crear una regla de combinación de perfiles para segmentación {#create-merge-rule}

El siguiente paso es crear un nuevo regla de combinación que le ayudará a crear los segmentos de audiencia para enviar a sus destinos basados en personas.

>[!IMPORTANT]
>
> Si ya tiene un regla definido con las opciones o[!UICONTROL Current Authenticated Profiles], puede ir al [!UICONTROL Last Authenticated Profiles]paso 4: Crear Segmentos de [&#x200B; audiencia.](people-based-destinations-workflow-combined.md#create-audience-segments)

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Haga clic en **[!UICONTROL Add New Rule]**.
1. Especifique una combinación perfil regla **[!UICONTROL Name]** y **[!UICONTROL Description]**.
1. En la **[!UICONTROL Profile Merge Rule Setup]** sección, seleccione las **[!UICONTROL Current Authenticated Profiles]** opciones o **[!UICONTROL Last Authenticated Profiles]** .
1. En el **[!UICONTROL Cross-Device Profile Options]** lista, seleccione las fuentes de datos en las que desea ejecutar el segmentación. Estas deben ser las fuentes de datos que contengan sus DPUUID[&#x200B; existentes](../../reference/ids-in-aam.md).

## Paso 4: Crear segmentos de audiencia {#create-audience-segments}

Para crear nuevos segmentos audiencia, utilice el Generador[&#x200B; de &#x200B;](../segments/segment-builder.md)segmentos. Si ya tiene segmentos de audiencia que desea enviar a [!DNL People-Based Destinations], vaya al [Paso 5: Configurar la Authentication de Platform](people-based-destinations-workflow-combined.md#configure-authentication) basadas en personas.

## Paso 5: Configuración de Authentication de Platform basadas en personas {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si ha configurado previamente una integración con una plataforma social, debería verla en este Página. De lo contrario, la Página está vacía.
   ![Integración basada en personas](assets/pbd-config.png)
1. Haga clic en **[!UICONTROL Add Account]**.
1. Utilice el **[!UICONTROL People-Based Platform]** menú desplegable para seleccionar la plataforma con la que desea configurar la integración.
   ![Plataforma basada en personas](assets/pbd-add.png)
1. Haga clic para **[!UICONTROL Confirm]** ser redirigido a la Página de autenticación de la plataforma seleccionada.
1. Una vez que se haya autenticado en su plataforma social cuenta, se le redirigirá a Audience Manager donde debería ver sus cuentas anunciante asociadas. Seleccione el cuenta anunciante que desea utilizar y haga clic en **[!UICONTROL Confirm]**.
1. Audience Manager muestra un notificación en la parte superior del Página para que sepa si el cuenta se ha agregado correctamente. El notificación también le permite agregar una dirección de correo electrónico de contacto para recibir notificaciones cuando la autenticación plataforma social está a punto de caducar.

>[!IMPORTANT]
>
>Un administrador de udience maneja la integración con plataformas sociales a través de tokens de autenticación que caducan después de un cierto período de tiempo. Consulte Authentication renovación de tokens para obtener más información sobre cómo renovar los tokens caducados.

## Paso 6: Crear un destino basado en personas {#create-destination}

1. Inicie sesión en su Audience Manager cuenta, vaya a **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** y haga clic en **[!UICONTROL Create Destination]**.
1. En la **[!UICONTROL Basic Information]** sección, introduzca un **[!UICONTROL Name]** y **[!UICONTROL Description]** para el nuevo fuente de datos y utilice la siguiente configuración:
   * **[!UICONTROL Category]**: Plataformas Integradas;
   * **[!UICONTROL Type]**: Basado en Personas;
   * **[!UICONTROL Platform]**: seleccione la plataforma basada en personas a la que desee enviar audiencia segmentos;
   * **[!UICONTROL Account]**: seleccione la anunciante cuenta asociada a la plataforma seleccionada.
     ![create-destination](assets/pbd-create-destination.png)
1. Haga clic en **[!UICONTROL Next]**.
1. Elija el **[!UICONTROL Data Export Labels]** que desea establecer para este destino.
1. En la **[!UICONTROL Configuration]** sección, seleccione la fuente de datos que contiene las fuentes de datos hash.
1. En la **[!UICONTROL Segment Mappings]** sección, seleccione los segmentos que desea enviar a este destino. Estos serían los segmentos que creó en [el Paso 4: Crear Segmentos de audiencia.](people-based-destinations-workflow-combined.md#create-audience-segments)
1. Guardar el destino.
