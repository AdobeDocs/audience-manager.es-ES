---
description: En este artículo se explica cómo configurar Amazon Advertising para integraciones nuevas y existentes.
solution: Audience Manager
title: Configuración de Amazon Advertising como destino de autoservicio basado en dispositivos
source-git-commit: 01f3c2d813a91b8541bd8ba8a8b030f67a4f979e
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 0%

---


# Configurar [!DNL Amazon Advertising] como destino basado en dispositivos de autoservicio {#configure-amazon}

Este artículo explica cómo configurar una integración con [Amazon Advertising](https://advertising.amazon.com/API/docs/en-us).

## Requisitos previos {#prerequisites}

Antes de configurar su [!DNL Amazon Advertising] destino, asegúrese de cumplir los siguientes requisitos previos.

* Su [!DNL Amazon] La cuenta debe ser apta para la publicidad.
* Al crear la primera [!DNL Amazon Advertising] en su instancia de Audience Manager, póngase en contacto con el servicio de consultoría de Adobe o con el Servicio de atención al cliente para habilitar el [!DNL Amazon] Sincronización de ID (ID de fuente de datos = 139200) para su cuenta. Esto es necesario para la sincronización correcta entre Audience Manager y [!DNL Amazon].
* Una vez creadas las nuevas audiencias del proveedor de datos, debería [actualizar sus metadatos](https://advertising.amazon.com/API/docs/en-us/data-provider/openapi#tag/Metadata/paths/~1v2~1dp~1audiencemetadata~1%7BaudienceId%7D/put) y añada el **[!DNL audience fees]**. Para esta operación puede utilizar el [API de Amazon Ads](https://advertising.amazon.com/API/docs/en-us/guides/onboarding/apply-for-access) o el [IU de Amazon Advertising](https://advertising.amazon.com/).

## Añadir un nuevo [!DNL Amazon Advertising] Destino {#add-new-amazon-destination}

En esta sección se describen los pasos que debe seguir al configurar un nuevo destino basado en dispositivos para [!DNL Amazon Advertising]. En este escenario se supone que no tiene [!DNL Amazon Advertising] destino configurado a través de su asesor de Adobe o del Servicio de atención al cliente.

### Paso 1. Autenticar con [!DNL Amazon Advertising] {#step1-authenticate-with-amazon}

Para poder agregar el destino basado en el dispositivo, debe vincular el Audience Manager y su [!DNL Amazon Advertising] cuenta. A continuación se indica cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager de y vaya a **[!UICONTROL Administration > Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma de destino, debería verla en esta página. En caso contrario, la página está vacía.
1. Seleccionar **[!UICONTROL Add Account]**.
1. Seleccionar [!UICONTROL Amazon Data Provider].

   ![Integrated-platform](assets/dbd-amazon-without-options.png)

1. Seleccione una de las **[!UICONTROL Amazon Data Provider]** opciones según la región donde se encuentre su [!DNL Amazon Ads] Se crea una cuenta de (Norteamérica, Europa o Extremo Oriente) y haga clic en **[!DNL Confirm]** para que se redirija a la página de autenticación.

   ![Integrated-platform](assets/dbd-amazon-with-options.png)

1. Una vez que se haya autenticado, se le redirigirá a Audience Manager, donde debería ver sus cuentas de anunciante asociadas. Seleccione la cuenta de anunciante que desee utilizar y haga clic en **[!UICONTROL Confirm]**. Al hacerlo, autorizó el acceso de Audience Manager para enviar actualizaciones para sus audiencias.

### Paso 2: Crear un nuevo destino basado en dispositivos {#step2-create-new-destination}

Después de haber vinculado al Audience Manager y a su [!DNL Amazon Advertising] cuenta, puede crear el nuevo destino. A continuación se indica cómo hacerlo:

>[!NOTE]
>
>No puede cambiar el nombre de un destino existente basado en dispositivos. Asegúrese de proporcionar un nombre que le ayude a identificar el destino correctamente.

1. Inicie sesión en su cuenta de Audience Manager de, vaya a **[!UICONTROL Audience Data > Destinations]** y seleccione **[!UICONTROL Create Destination]**.
1. En el **[!UICONTROL Basic Information]** , introduzca una **[!UICONTROL Name]** y **[!UICONTROL Description]** para su nuevo destino y utilice la siguiente configuración:

   ![configurar](assets/dbd-new-account-amazon.png)

1. Seleccionar **[!UICONTROL Next]**.
1. Elija la [Etiquetas de exportación de datos](/help/using/features/data-export-controls.md#controls-labels) que desea establecer para este destino.
1. Seleccionar **[!UICONTROL Save]**.
1. En el **[!UICONTROL Segment Mappings]** , seleccione los segmentos de audiencia que desee enviar a este destino.
1. Guarde el destino.

## Consideraciones de tasas de coincidencia {#match-rates-considerations}

La integración entre Audience Manager y [!DNL Amazon Advertising] admite rellenos de audiencia históricos. Todas las cualificaciones de los segmentos se envían a [!DNL Amazon] al crear el destino.

## Resolución de problemas {#troubleshooting}

Al configurar o enviar datos a [!DNL Amazon Advertising] destino, podría encontrar los errores que se describen a continuación. En esta sección se explica qué puede causar los errores y cómo corregirlos.

| Mensaje de error | Ocurrencia/Motivo | Resolución |
|---|---|---|
| `Internal server error` | Este mensaje de error se muestra en la interfaz de usuario del Audience Manager al intentar añadir un nuevo [!DNL Amazon] cuenta de con una versión obsoleta de la API de Amazon. | Contacte con el Servicio de atención al cliente de Adobe. |
| `Amazon Error: Account XXXXXXXXX was not found` | Este mensaje de error se muestra en la interfaz de usuario del Audience Manager cuando las credenciales configuradas para el destino no están autorizadas para acceder a la cuenta de Amazon Ads correspondiente. | <ul><li>Asegúrese de que las credenciales de la cuenta que utiliza cumplen los requisitos siguientes [requisitos previos](#prerequisites).</li><li>Vaya a la interfaz de usuario de Amazon Ads con las mismas credenciales y compruebe si las audiencias correctas se muestran en la cuenta correspondiente. </li></ul> |
