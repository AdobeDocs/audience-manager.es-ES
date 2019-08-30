---
description: 'Esta página incluye instrucciones paso a paso sobre cómo combinar datos CRM sin conexión con datos de comportamiento en tiempo real para los usuarios autenticados a fin de crear segmentos de audiencia y, a continuación, enviar estos segmentos de audiencia a destinos basados en personas. '
seo-description: 'Esta página incluye instrucciones paso a paso sobre cómo combinar datos CRM sin conexión con datos de comportamiento en tiempo real para los usuarios autenticados a fin de crear segmentos de audiencia y, a continuación, enviar estos segmentos de audiencia a destinos basados en personas.  '
seo-title: 'Flujo de trabajo C: Personalización basada en actividades autenticadas combinada con datos sin conexión'
solution: Audience Manager
title: 'Flujo de trabajo C: Personalización basada en actividades autenticadas combinada con datos sin conexión'
translation-type: tm+mt
source-git-commit: fdb17c46dd66794cfb744b77e8e5c8be9fd65dd5

---


# Flujo de trabajo C: Personalización basada en actividades autenticadas combinada con datos sin conexión {#workflow-c}

Esta página incluye instrucciones paso a paso sobre cómo combinar datos sin conexión [!DNL CRM] con datos de comportamiento en tiempo real para los usuarios autenticados a fin de crear segmentos de audiencia y, a continuación, enviar estos segmentos de audiencia a [!DNL People-Based Destinations].

## Paso 1: Configuración de la configuración de fuentes de datos {#configure-data-source-settings}

Según si [los DPUUID](../../reference/ids-in-aam.md) tienen en minúscula y direcciones de correo electrónico con hash, es posible que necesite configurar la fuente de datos que almacenará las direcciones de correo electrónico con hash.

**Escenario 1: los[dpuuid](../../reference/ids-in-aam.md)ya están en minúsculas y tienen direcciones de correo electrónico con hash.**

En este caso, pase al [paso 5 - Configurar la autenticación de plataforma basada en personas](#configure-authentication).

**Escenario 2: los[DPUUID](../../reference/ids-in-aam.md)no tienen en minúsculas las direcciones de correo electrónico con hash.**

En este caso, debe crear una nueva fuente de datos entre dispositivos que guarde las direcciones de correo electrónico con hash. A continuación se muestra cómo hacer esto:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]** y haga clic **[!UICONTROL Add New]** en.
1. Introduzca un **[!UICONTROL Name]** y **[!UICONTROL Description]** para la nueva fuente de datos.
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

## Paso 2: Uso de ID declarados para hacer coincidir los DPUUID con direcciones de correo electrónico hash a través de llamadas HTTP en tiempo real {#match-email-addresses}

Para calificar a los usuarios autenticados para características basadas en reglas, debe enviar la cualificación de características a través [de los ID declarados](../declared-ids.md).

### Ejemplo

Supongamos que ha creado las dos fuentes de datos siguientes.

| ID de fuente de datos | Contenido de fuente de datos |
| -------------- | -------------------------- |
| 999999 | DPUUIDS existentes (ID de CRM) |
| 987654 | Direcciones de correo electrónico con hash |

A continuación, debe calificar los ID de CRM a continuación para la característica de la tabla.

| DPUUID (ID de CRM) | La dirección de correo electrónico | Dirección de correo electrónico con hash | Rasgo |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

El ID declarado debe seguir esta sintaxis:

`https://yourDomain.demdex.net/event?d_cid_ic=myHashedEmailDataSourceID%01myHashedEmail&d_cid_ic=myCrmDataSourceID%01myCRMID&key=value`

En el ejemplo anterior, la llamada de ID declarada debería tener este aspecto:

`https://yourDomain.demdex.net/event?d_cid_ic=987654%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=999999%0168079982765673198504052656074456196039&location=US`

## Paso 3: Creación de una regla de combinación de perfiles para segmentación {#create-profile-merge-rule-segmentation}

El siguiente paso está creando una nueva regla de combinación que le ayudará a crear segmentos de audiencia para enviarlos a [!DNL People-Based Destinations]su.

>[!IMPORTANT]
>
>Si ya tiene una regla definida con las opciones **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]** opciones, puede omitir el [paso 4 - Crear segmentos de audiencia](#create-audience-segments).

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Profile Merge Rules]**.
2. Haga clic en **[!UICONTROL Add New Rule]**.
3. Introduzca una regla de combinación de perfiles **[!UICONTROL Name]** y **[!UICONTROL Description]**.
4. En **[!UICONTROL Profile Merge Rule Setup]** la sección, seleccione **[!UICONTROL All Cross-Device Profiles]** la regla de **[!UICONTROL Cross-Device Options]** la lista.
5. En **[!UICONTROL Cross-Device Profile Options]** la lista, seleccione las fuentes de datos en las que desee ejecutar la segmentación. Deben ser las fuentes de datos que contengan sus dpuuid existentes.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Paso 4 - Creación de segmentos de audiencia {#create-audience-segments}

Para crear nuevos segmentos, utilice [el Generador de segmentos](../segments/segment-builder.md). Si tiene segmentos de audiencia existentes a los [!DNL People-Based Destinations]que desea enviar, vaya al [paso 5 - Configurar la autenticación de plataforma basada en personas](#configure-authentication).

## Paso 5: Configurar la autenticación por plataforma basada en personas {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada previamente con una plataforma social, debe verlo en esta página. De lo contrario, la página está vacía.
   ![integración basada en personas](assets/pbd-config.png)
2. Haga clic en **[!UICONTROL Add Account]**.
3. Utilice el menú **[!UICONTROL People-Based Platform]** desplegable para seleccionar la plataforma con la que desea configurar la integración.
   ![plataforma basada en personas](assets/pbd-add.png)
4. Haga clic para **[!UICONTROL Confirm]** que se le redirija a la página de autenticación de la plataforma seleccionada.
5. Una vez que haya autenticado en su cuenta de plataforma social, se le redirigirá a Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic **[!UICONTROL Confirm]** en.
6. Audience Manager muestra una notificación en la parte superior de la página para saber si la cuenta se agregó correctamente. La notificación también permite agregar una dirección de correo electrónico de contacto para recibir notificaciones cuando la autenticación de plataforma social está a punto de caducar.

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
1. En **[!UICONTROL Segment Mappings]** la sección, seleccione los segmentos que desee enviar a este destino. Serán los segmentos que creó en [el Paso 4 - Crear segmentos de audiencia](#create-audience-segments).
1. Guarde el destino.
