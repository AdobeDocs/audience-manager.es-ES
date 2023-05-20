---
description: En este artículo se explica cómo configurar las audiencias personalizadas de Twitter tanto para las integraciones nuevas como para las existentes.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Configuración de las audiencias personalizadas de Twitter como un destino basado en dispositivos de autoservicio
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 1%

---

# Configurar [!DNL Twitter Custom Audiences] como destino basado en dispositivos de autoservicio {#configure-twitter}

Este artículo explica cómo configurar una integración con [Audiencias personalizadas de twitter](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## Requisitos previos {#prerequisites}

Antes de configurar su [!DNL Twitter Custom Audiences] destino, asegúrese de cumplir los siguientes requisitos previos.

* Su [!DNL Twitter Ads] La cuenta debe ser apta para la publicidad. Nuevo [!DNL Twitter Ads] Las cuentas de no son aptas para la publicidad en las 2 primeras semanas después de crearlas.
* Su [!DNL Twitter] la cuenta de usuario para la que autorizó el acceso en Audience Manager debe tener el [Administrador de audiencia de socio](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) permiso habilitado.
* Al crear la primera [!DNL Twitter Custom Audiences] en su instancia de Audience Manager, póngase en contacto con el servicio de consultoría de Adobe o con el Servicio de atención al cliente para habilitar el [!DNL Twitter] Sincronización de ID (ID de fuente de datos = 1123) para su cuenta. Esto es necesario para la sincronización correcta entre Audience Manager y [!DNL Twitter].

## Añadir un nuevo [!DNL Twitter Custom Audiences] Destino {#add-new-twitter-destination}

En esta sección se describen los pasos que debe seguir al configurar un nuevo destino basado en dispositivos para [!DNL Twitter Custom Audiences]. En este escenario se supone que no tiene [!DNL Twitter Custom Audiences] destino configurado a través de su asesor de Adobe o del Servicio de atención al cliente.

### Paso 1. Autenticar con [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

Para poder agregar el destino basado en el dispositivo, debe vincular el Audience Manager y su [!DNL Twitter Custom Audiences] cuenta. A continuación se indica cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager de y vaya a **[!DNL Administration > Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma de destino, debería verla en esta página. En caso contrario, la página está vacía.
1. Haga clic **[!DNL Add Account]**.
1. Seleccionar [!DNL Twitter Custom Audiences] y haga clic en **[!DNL Confirm]** para que se redirija a la página de autenticación.

   ![Integrated-platform](assets/dbd-integrated-platforms.png)

1. Una vez que se haya autenticado, se le redirigirá a Audience Manager, donde debería ver sus cuentas de anunciante asociadas. Seleccione la cuenta de anunciante que desee utilizar y haga clic en **[!DNL Confirm]**.

### Paso 2: Crear un nuevo destino basado en dispositivos {#step2-create-new-destination}

Después de haber vinculado al Audience Manager y a su [!DNL Twitter Custom Audiences], puede crear el nuevo destino. A continuación se indica cómo hacerlo:

>[!NOTE]
>
>No puede cambiar el nombre de un destino existente basado en dispositivos. Asegúrese de proporcionar un nombre que le ayude a identificar el destino correctamente.

1. Inicie sesión en su cuenta de Audience Manager de, vaya a **[!DNL Audience Data > Destinations]** y haga clic en **[!DNL Create Destination]**.
1. En el **[!DNL Basic Information]** , introduzca una **[!DNL Name]** y **[!DNL Description]** para su nuevo destino y utilice la siguiente configuración: ![configurar](assets/dbd-new-basic.png)
1. Haga clic **[!DNL Next]**.
1. Elija la [Etiquetas de exportación de datos](/help/using/features/data-export-controls.md#controls-labels) que desea establecer para este destino.
1. Haga clic **[!DNL Save]**.
1. En el **[!DNL Segment Mappings]** , seleccione los segmentos de audiencia que desee enviar a este destino.
1. Guarde el destino.

## Consideraciones de asignación de segmentos {#segment-mapping-considerations}

Al asignar segmentos de audiencia a [!UICONTROL Twitter], asegúrese de cumplir los siguientes requisitos de nomenclatura de segmentos:

* Proporcione nombres de asignación de segmentos legibles por un humano. Se recomienda utilizar el mismo nombre que utilizó para los segmentos del Audience Manager.
* No utilice caracteres especiales (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) en los nombres de asignación de segmentos y segmentos. Si el nombre del segmento del Audience Manager contiene estos caracteres, elimínelos antes de asignar el segmento a una [!UICONTROL Twitter] destino.

### Ejemplo

* Nombre de asignación o segmento correcto: &quot;Compradores estadounidenses y europeos&quot;;
* Nombre de asignación o segmento incorrecto: &quot;US, European 5h0p3rs&quot;.

>[!IMPORTANT]
>
>No puede cambiar los nombres de segmentos ya asignados. El Audience Manager utiliza los nombres de segmento para identificar correctamente los segmentos en la integración.

## Consideraciones de tasas de coincidencia {#match-rates-considerations}

* La integración entre Audience Manager y [!UICONTROL Twitter Custom Audiences] admite rellenos de audiencia históricos. Todas las cualificaciones de los segmentos se envían a [!UICONTROL Twitter] al crear el destino.

## Resolución de problemas {#troubleshooting}

Al configurar o enviar datos al destino de Audiencias personalizadas de Twitter, puede encontrar los errores que se describen a continuación. En esta sección se explica qué puede causar los errores y cómo corregirlos.

| Mensaje de error | Ocurrencia/Motivo | Resolución |
|---|---|---|
| `Internal server error` | Este mensaje de error se muestra en la interfaz de usuario del Audience Manager al intentar añadir un nuevo [!DNL Twitter] cuenta de con una versión obsoleta de la API de Twitter. | Contactar el servicio de atención al cliente de Adobe. |
| `Twitter Error: This request is not properly authenticated` | Este mensaje de error se muestra en la interfaz de usuario del Audience Manager al intentar asignar segmentos con nombres de segmento no admitidos al destino. | Revise los nombres de segmento asignados y asegúrese de que no contengan caracteres no admitidos. Consulte [consideraciones de asignación de segmentos](#segment-mapping-considerations) para la lista de caracteres no admitidos. |
| `Twitter Error: Account XXXXXXXXX was not found` | Este mensaje de error se muestra en la interfaz de usuario del Audience Manager cuando las credenciales configuradas para el destino no están autorizadas para acceder a la cuenta de Twitter Ads correspondiente. | <ul><li>Asegúrese de que las credenciales de la cuenta que utiliza cumplen los requisitos siguientes [requisitos previos](#prerequisites).</li><li>Vaya a la interfaz de usuario de Twitter Ads con las mismas credenciales y compruebe si las audiencias correctas se muestran en la sección correspondiente `XXXXXXXXX` cuenta. </li></ul> |