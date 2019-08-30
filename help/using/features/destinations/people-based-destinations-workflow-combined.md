---
description: 'Esta página incluye instrucciones paso a paso sobre cómo combinar datos CRM sin conexión con datos de comportamiento que ya tiene en Audience Manager para crear nuevos segmentos de audiencia y, después, enviar estos segmentos de audiencia a Destinos basados en personas.  '
seo-description: 'Esta página incluye instrucciones paso a paso sobre cómo combinar datos CRM sin conexión con datos de comportamiento que ya tiene en Audience Manager para crear nuevos segmentos de audiencia y, después, enviar estos segmentos de audiencia a Destinos basados en personas.   '
seo-title: 'Flujo de trabajo A: Personalización basada en toda la actividad en línea combinada con datos sin conexión'
solution: Audience Manager
title: 'Flujo de trabajo A: Personalización basada en toda la actividad en línea combinada con datos sin conexión'
translation-type: tm+mt
source-git-commit: d0e343e3fbaf527e9b630dc2dbc851d8f8f4c0b2

---


# Flujo de trabajo A: Personalización basada en toda la actividad en línea combinada con datos sin conexión {#workflow-a}

Esta página incluye instrucciones paso a paso sobre cómo combinar datos sin conexión [!DNL CRM] con datos de comportamiento que ya tiene en Audience Manager para crear nuevos segmentos de audiencia y, a continuación, enviar estos segmentos de audiencia a [!DNL People-Based Destinations].

## Paso 1: Configuración de la configuración de fuentes de datos {#configure-data-source-settings}

Según si [los DPUUID](../../reference/ids-in-aam.md) tienen en minúscula y direcciones de correo electrónico con hash, es posible que necesite configurar la fuente de datos que almacenará las direcciones de correo electrónico con hash.

 

**Escenario 1: los[dpuuid](../../reference/ids-in-aam.md)ya están en minúsculas y tienen direcciones de correo electrónico con hash.**

En este caso, debe tener que etiquetar la fuente de datos correspondiente como tal:

1. Vaya a [!UICONTROL Audience Data] -&gt; [!UICONTROL Data Sources].
1. Busque la fuente de datos que contiene [los dpuuid](../../reference/ids-in-aam.md)y haga clic en ella.
1. Asegúrese de que la opción [!UICONTROL Cannot be tied to personally identifiable information] esté desactivada.
1. Guarde la configuración de fuente de datos.

 

**Escenario 2: los[DPUUID](../../reference/ids-in-aam.md)no tienen en minúsculas las direcciones de correo electrónico con hash.**

En este caso, debe crear una nueva fuente de datos entre dispositivos que guarde las direcciones de correo electrónico con hash. A continuación se muestra cómo hacer esto:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**, y haga clic **[!UICONTROL Add New]** en.
1. Introduzca un [!UICONTROL Name] y [!UICONTROL Description] para la nueva fuente de datos.
1. En el menú **[!UICONTROL ID Type]** desplegable, seleccione **[!UICONTROL Cross Device]**.
1. En la **[!UICONTROL Data Source Settings]** sección, seleccione las opciones **[!UICONTROL Inbound]** y **[!UICONTROL Outbound]** las opciones y habilite **[!UICONTROL Share associated cross-device IDs in people-based destinations]** la opción.
1. Utilice el menú desplegable para seleccionar **[!UICONTROL Emails(SHA256, lowercased)]** la etiqueta para esta fuente de datos.
   >[!IMPORTANT]
   >
   >Esta opción sólo etiqueta el origen de datos como los datos que contienen hash con ese algoritmo específico. Audience Manager no hash los datos en este paso. Asegúrese de que las direcciones de correo electrónico planeadas para almacenar en esta fuente de datos ya están hash con [!DNL SHA256] el algoritmo. De lo contrario, no podrá utilizarla [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

>[!NOTE]
>
> Consulte [Integración](people-based-destinations-prerequisites.md#data-onboarding) de datos para obtener más información sobre cómo debe traer los datos sin conexión a Audience Manager para destinos basados en personas.

## Paso 2: Coincidencia de DPUUIDS con direcciones de correo electrónico hash mediante sincronización de ID basada en archivos {#match-ids-emails}

>[!IMPORTANT]
>
> Este paso solo se aplica al [escenario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) descrito anteriormente. Si los [DPUUID ya existentes](../../reference/ids-in-aam.md) son direcciones de correo electrónico con hash, vaya al [paso 3 - Cree una regla de combinación de perfiles para segmentación](people-based-destinations-workflow-combined.md#create-merge-rule).

Supongamos que desea hacer coincidir los [dpuuid existentes](../../reference/ids-in-aam.md) con las direcciones de correo electrónico con hash de la tabla siguiente (columna derecha) y almacenar las direcciones de correo electrónico con hash en la nueva fuente de datos que creó en [el paso 1 - Configurar la configuración de fuentes de datos](people-based-destinations-workflow-combined.md#configure-data-source-settings).

| DPUUID (ID de CRM) | La dirección de correo electrónico | Dirección de correo electrónico con hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Puede vincular hasta 10 direcciones de correo electrónico con hash a un único [DPUUID](../../reference/ids-in-aam.md). Para ello, separe las direcciones de correo electrónico con hash con una coma, dentro del archivo de sincronización.

En nuestro ejemplo, ahora tendrá dos fuentes de datos.

| ID de fuente de datos | Contenido de fuente de datos |
| -------------- | -------------------------- |
| 999999 | DPUUIDS existentes (ID de CRM) |
| 987654 | Direcciones de correo electrónico con hash |

 

El archivo de sincronización [de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) tendría el siguiente contenido:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

El archivo de sincronización [de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) debe seguir esta estructura de nombres:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

En el ejemplo anterior, el nombre del archivo tendría este aspecto:`c2c_id_999999_987654_1560431657.sync`


[Descargue aquí el archivo de ejemplo](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync).

## Paso 3: Creación de una regla de combinación de perfiles para segmentación {#create-merge-rule}

El siguiente paso está creando una nueva regla de combinación que le ayudará a crear segmentos de audiencia para enviarlos a destinos basados en personas.

>[!IMPORTANT]
>
> Si ya tiene una regla definida con las opciones [!UICONTROL Current Authenticated Profiles] o [!UICONTROL Last Authenticated Profiles] opciones, puede omitir el [paso 4 - Crear segmentos de audiencia](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Profile Merge Rules]**.
1. Haga clic en **[!UICONTROL Add New Rule]**.
1. Introduzca una regla de combinación de perfiles **[!UICONTROL Name]** y **[!UICONTROL Description]**.
1. En **[!UICONTROL Profile Merge Rule Setup]** la sección, seleccione las **[!UICONTROL Current Authenticated Profiles]** opciones o las **[!UICONTROL Last Authenticated Profiles]** opciones.
1. En **[!UICONTROL Cross-Device Profile Options]** la lista, seleccione las fuentes de datos en las que desee ejecutar la segmentación. Deben ser las fuentes de datos que contengan sus [dpuuid existentes](../../reference/ids-in-aam.md).

## Paso 4 - Creación de segmentos de audiencia {#create-audience-segments}

Para crear nuevos segmentos de audiencia, utilice el Generador [de segmentos](../segments/segment-builder.md). Si tiene segmentos de audiencia existentes a los [!DNL People-Based Destinations]que desea enviar, vaya al [paso 5 - Configurar la autenticación de plataforma basada en personas](people-based-destinations-workflow-combined.md#configure-authentication).

## Paso 5: Configurar la autenticación por plataforma basada en personas {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada previamente con una plataforma social, debe verlo en esta página. De lo contrario, la página está vacía.
   ![integración basada en personas](assets/pbd-config.png)
1. Haga clic en **[!UICONTROL Add Account]**.
1. Utilice el menú **[!UICONTROL People-Based Platform]** desplegable para seleccionar la plataforma con la que desea configurar la integración.
   ![plataforma basada en personas](assets/pbd-add.png)
1. Haga clic para **[!UICONTROL Confirm]** que se le redirija a la página de autenticación de la plataforma seleccionada.
1. Una vez que haya autenticado en su cuenta de plataforma social, se le redirigirá a Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic **[!UICONTROL Confirm]** en.
1. Audience Manager muestra una notificación en la parte superior de la página para saber si la cuenta se agregó correctamente. La notificación también permite agregar una dirección de correo electrónico de contacto para recibir notificaciones cuando la autenticación de plataforma social está a punto de caducar.

>[!IMPORTANT]
>
>Un Administrador de udiencias gestiona la integración con plataformas sociales a través de tokens de autenticación que caducan después de una determinada cantidad de tiempo. Consulte Renovación del autentificador de autentificación para obtener detalles sobre cómo renovar los tokens caducados.

## Paso 6 - Creación de un destino basado en personas {#create-destination}

1. Inicie sesión en su cuenta de Audience Manager, vaya **[!UICONTROL Audience Data]** a &gt; **[!UICONTROL Destinations]** y haga clic **[!UICONTROL Create Destination]** en.
1. En **[!UICONTROL Basic Information]** la sección, introduzca un **[!UICONTROL Name]** y **[!UICONTROL Description]** para la nueva fuente de datos y use la siguiente configuración:
   * **[!UICONTROL Category]**: Plataformas integradas;
   * **[!UICONTROL Type]**: Basado en personas;
   * **[!UICONTROL Platform]**: seleccionar la plataforma basada en las personas a la que desee enviar segmentos de audiencia;
   * **[!UICONTROL Account]**: seleccione la cuenta del anunciante que desee asociada con la plataforma seleccionada.
      ![create-destination](assets/pbd-create-destination.png)
1. Haga clic en **[!UICONTROL Next]**.
1. Elija la **[!UICONTROL Data Export Labels]** que desee definir para este destino.
1. En **[!UICONTROL Configuration]** la sección, seleccione la fuente de datos que contiene las fuentes de datos con hash.
1. En **[!UICONTROL Segment Mappings]** la sección, seleccione los segmentos que desee enviar a este destino. Serán los segmentos que creó en [el Paso 4 - Crear segmentos de audiencia](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Guarde el destino.
