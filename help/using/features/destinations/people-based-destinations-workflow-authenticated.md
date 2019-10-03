---
description: 'Esta página incluye una guía paso a paso sobre cómo combinar datos de CRM sin conexión con datos de comportamiento en tiempo real para usuarios autenticados a fin de crear segmentos de audiencia y, a continuación, enviar estos segmentos de audiencia a destinos basados en personas. '
seo-description: 'Esta página incluye una guía paso a paso sobre cómo combinar datos de CRM sin conexión con datos de comportamiento en tiempo real para usuarios autenticados a fin de crear segmentos de audiencia y, a continuación, enviar estos segmentos de audiencia a destinos basados en personas.  '
seo-title: 'Flujo de trabajo C: Personalización basada en actividad autenticada combinada con datos sin conexión'
solution: Audience Manager
title: 'Flujo de trabajo C: Personalización basada en actividad autenticada combinada con datos sin conexión'
translation-type: tm+mt
source-git-commit: 0eb6a6f67d87377a044b18118fac0185219b0347

---


# Flujo de trabajo C: Personalización basada en actividad autenticada combinada con datos sin conexión {#workflow-c}

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a guiarle en la configuración y el uso de esta función. Nada de lo que aquí se incluye es asesoramiento jurídico. Por favor, consulte a su propio abogado para obtener asesoramiento jurídico.

Esta página incluye una guía paso a paso sobre cómo combinar datos sin conexión [!DNL CRM] con datos de comportamiento en tiempo real para que los usuarios autenticados creen segmentos de audiencia y luego envíen estos segmentos de audiencia a [!DNL People-Based Destinations].

## Paso 1: Configuración de fuentes de datos {#configure-data-source-settings}

Dependiendo de si los [DPUUID](../../reference/ids-in-aam.md) están en minúsculas y las direcciones de correo electrónico con hash, es posible que tenga que configurar el origen de datos que almacenará las direcciones de correo electrónico con hash.

 

**Escenario 1: los[DPUUID](../../reference/ids-in-aam.md)ya están en minúsculas y tienen direcciones de correo electrónico con hash.**

En este caso, vaya al [paso 5 - Configurar la autenticación](#configure-authentication)de plataforma basada en personas.

 

**Escenario 2: sus[DPUUID](../../reference/ids-in-aam.md)no son direcciones de correo electrónico con hash en minúsculas.**

En este caso, debe crear una nueva fuente de datos entre dispositivos que almacenará las direcciones de correo electrónico con hash. A continuación se muestra cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]** y haga clic en **[!UICONTROL Add New]**.
1. Escriba un **[!UICONTROL Name]** y **[!UICONTROL Description]** para la nueva fuente de datos.
1. En el menú **[!UICONTROL ID Type]** desplegable, seleccione **[!UICONTROL Cross Device]**.
1. En la **[!UICONTROL Data Source Settings]** sección, seleccione las opciones **[!UICONTROL Inbound]** y **[!UICONTROL Outbound]** y active la **[!UICONTROL Share associated cross-device IDs in people-based destinations]** .
1. Utilice el menú desplegable para seleccionar la etiqueta de este origen de datos **[!UICONTROL Emails(SHA256, lowercased)]** .
   >[!IMPORTANT]
   >
   >Esta opción sólo etiqueta la fuente de datos como si contuviera datos con hash con ese algoritmo específico. Audience Manager no hash los datos en este paso. Asegúrese de que las direcciones de correo electrónico que planea almacenar en esta fuente de datos ya están marcadas con el algoritmo [!DNL SHA256] . De lo contrario, no podrás usarlo para [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulte [Incorporación](people-based-destinations-prerequisites.md#data-onboarding) de datos para ver las preguntas más frecuentes sobre cómo debe llevar los datos sin conexión a Audience Manager para destinos basados en personas.

Vea el siguiente vídeo para ver un tutorial de vídeo sobre cómo crear una fuente de datos para [!UICONTROL People-Based Destinations].

[!VIDEO](https://video.tv.adobe.com/v/29006/?captions=spa)

## Paso 2: Utilice ID declarados para hacer coincidir DPUUID con direcciones de correo electrónico con hash mediante llamadas HTTP en tiempo real {#match-email-addresses}

Para calificar a los usuarios autenticados para características basadas en reglas, debe enviar la calificación de características a través de ID [declarados](../declared-ids.md).

### Ejemplo

Supongamos que ha creado las dos fuentes de datos siguientes.

| ID de fuente de datos | Contenido de la fuente de datos |
| -------------- | -------------------------- |
| 999999 | DPUUID existentes (ID de CRM) |
| 987654 | Direcciones de correo electrónico con hash |

 

A continuación, desea calificar los ID de CRM siguientes para la característica de la tabla.

| DPUUID (ID de CRM) | La dirección de correo electrónico | Dirección de correo electrónico con hash | Rasgo |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

 

El ID declarado debe seguir esta sintaxis:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

En el ejemplo anterior, la llamada de ID declarada debe tener este aspecto:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Paso 3: Creación de una regla de combinación de perfiles para la segmentación {#create-profile-merge-rule-segmentation}

El siguiente paso es crear una nueva regla de combinación que le ayudará a crear los segmentos de audiencia que se enviarán a su [!DNL People-Based Destinations].

>[!IMPORTANT]
>
>Si ya tiene una regla definida con las opciones **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]** , puede ir al [paso 4 - Crear segmentos](#create-audience-segments)de audiencia.

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Profile Merge Rules]**.
2. Haga clic en **[!UICONTROL Add New Rule]**.
3. Introduzca una regla de combinación de perfiles **[!UICONTROL Name]** y **[!UICONTROL Description]**.
4. En la **[!UICONTROL Profile Merge Rule Setup]** sección , seleccione la **[!UICONTROL Current Authenticated Profiles]** regla o **[!UICONTROL Last Authenticated Profiles]** en la **[!UICONTROL Cross-Device Options]** lista.
5. En la **[!UICONTROL Cross-Device Profile Options]** lista, seleccione los orígenes de datos en los que desea ejecutar la segmentación. Deben ser las fuentes de datos que contengan los DPUUID existentes.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Paso 4: Creación de segmentos de audiencia {#create-audience-segments}

Para crear nuevos segmentos, utilice el Generador [de segmentos](../segments/segment-builder.md). Si tiene segmentos de audiencia existentes a los que desea enviar [!DNL People-Based Destinations], vaya al [paso 5 - Configurar la autenticación](#configure-authentication)de plataforma basada en personas.

## Paso 5: Configurar la autenticación de plataforma basada en personas {#configure-authentication}

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma social, debería verla en esta página. De lo contrario, la página está vacía.
   ![integración basada en las personas](assets/pbd-config.png)
2. Haga clic en **[!UICONTROL Add Account]**.
3. Utilice el menú **[!UICONTROL People-Based Platform]** desplegable para seleccionar la plataforma con la que desea configurar la integración.
   ![plataforma basada en las personas](assets/pbd-add.png)
4. Haga clic en **[!UICONTROL Confirm]** para que se le redirija a la página de autenticación de la plataforma seleccionada.
5. Una vez que se haya autenticado en la cuenta de la plataforma social, se le redirigirá a Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!UICONTROL Confirm]**.
6. Audience Manager muestra una notificación en la parte superior de la página para indicarle si la cuenta se agregó correctamente. La notificación también le permite agregar una dirección de correo electrónico de contacto para recibir notificaciones cuando la autenticación de la plataforma social esté a punto de caducar.

>[!IMPORTANT]
>
>Audience Manager gestiona la integración con las plataformas sociales mediante tokens de autenticación que caducan después de una determinada cantidad de tiempo. Consulte Renovación de autentificador para obtener más información sobre cómo renovar los tokens caducados.

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
1. En la **[!UICONTROL Segment Mappings]** sección, seleccione los segmentos que desee enviar a este destino. Serían los segmentos que creó en el [paso 4 - Crear segmentos](#create-audience-segments)de audiencia.
1. Guarde el destino.
