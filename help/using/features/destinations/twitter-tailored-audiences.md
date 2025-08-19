---
description: Este artículo explica cómo configurar las audiencias personalizadas de Twitter tanto para las integraciones nuevas como para las existentes.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Configuración de las audiencias personalizadas de Twitter como un destino basado en dispositivos de autoservicio
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# Configurar [!DNL Twitter Custom Audiences] como un destino basado en dispositivos de autoservicio {#configure-twitter}

Este artículo explica cómo configurar una integración con [Audiencias personalizadas de Twitter](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## Requisitos previos {#prerequisites}

Antes de configurar el destino [!DNL Twitter Custom Audiences], asegúrese de cumplir los siguientes requisitos previos.

* Su cuenta de [!DNL Twitter Ads] debe cumplir los requisitos para la publicidad. Las nuevas cuentas de [!DNL Twitter Ads] no son elegibles para la publicidad en las primeras 2 semanas después de crearlas.
* La cuenta de usuario [!DNL Twitter] para la que autorizó el acceso en Audience Manager debe tener habilitado el permiso [Administrador de audiencias de socio](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels).
* Al crear el primer destino [!DNL Twitter Custom Audiences] en su instancia de Audience Manager, póngase en contacto con Adobe Consulting o con el Servicio de atención al cliente para habilitar la sincronización de ID [!DNL Twitter] (ID de Data Source = 1123) para su cuenta. Esto es necesario para la sincronización correcta entre Audience Manager y [!DNL Twitter].

## Agregar nuevo destino [!DNL Twitter Custom Audiences] {#add-new-twitter-destination}

Esta sección describe los pasos que debe seguir al configurar un nuevo destino basado en dispositivos para [!DNL Twitter Custom Audiences]. En este escenario se da por hecho que no tiene un destino [!DNL Twitter Custom Audiences] configurado a través de su asesor de Adobe o del Servicio de atención al cliente.

### Paso 1. Autenticar con [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

Para poder agregar el destino basado en el dispositivo, debe vincular Audience Manager y su cuenta de [!DNL Twitter Custom Audiences]. A continuación se indica cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!DNL Administration > Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma de destino, debería verla en esta página. En caso contrario, la página está vacía.
1. Haga clic en **[!DNL Add Account]**.
1. Seleccione [!DNL Twitter Custom Audiences] y haga clic en **[!DNL Confirm]** para que se le redirija a la página de autenticación.

   ![plataformas integradas](assets/dbd-integrated-platforms.png)

1. Una vez que se haya autenticado, se le redirigirá a Audience Manager, donde debería ver sus cuentas de anunciante asociadas. Seleccione la cuenta de anunciante que desee usar y haga clic en **[!DNL Confirm]**.

### Paso 2: Crear un nuevo destino basado en dispositivos {#step2-create-new-destination}

Una vez que haya vinculado Audience Manager y su [!DNL Twitter Custom Audiences], podrá crear el nuevo destino. A continuación se indica cómo hacerlo:

>[!NOTE]
>
>No puede cambiar el nombre de un destino existente basado en dispositivos. Asegúrese de proporcionar un nombre que le ayude a identificar el destino correctamente.

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!DNL Audience Data > Destinations]** y haga clic en **[!DNL Create Destination]**.
1. En la sección **[!DNL Basic Information]**, escriba un **[!DNL Name]** y **[!DNL Description]** para el nuevo destino y use la configuración siguiente: ![instalación](assets/dbd-new-basic.png)
1. Haga clic en **[!DNL Next]**.
1. Elija las [etiquetas de exportación de datos](/help/using/features/data-export-controls.md#controls-labels) que desee establecer para este destino.
1. Haga clic en **[!DNL Save]**.
1. En la sección **[!DNL Segment Mappings]**, seleccione los segmentos de audiencia que desee enviar a este destino.
1. Guarde el destino.

## Consideraciones de asignación de segmentos {#segment-mapping-considerations}

Al asignar segmentos de audiencia a [!UICONTROL Twitter], asegúrese de cumplir los siguientes requisitos de nomenclatura de segmentos:

* Proporcione nombres de asignación de segmentos legibles por un humano. Se recomienda utilizar el mismo nombre que utilizó para los segmentos de Audience Manager.
* No utilice caracteres especiales (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) en los nombres de asignación de segmentos y segmentos. Si el nombre del segmento de Audience Manager contiene estos caracteres, elimínelos antes de asignar el segmento a un destino [!UICONTROL Twitter].

### Ejemplo

* Nombre de asignación o segmento correcto: &quot;Compradores estadounidenses y europeos&quot;;
* Nombre de asignación o segmento incorrecto: &quot;US, European 5h0p3rs&quot;.

>[!IMPORTANT]
>
>No puede cambiar los nombres de segmentos ya asignados. Audience Manager utiliza los nombres de los segmentos para identificar correctamente los segmentos en la integración.

## Consideraciones de tasas de coincidencia {#match-rates-considerations}

* La integración entre Audience Manager y [!UICONTROL Twitter Custom Audiences] admite rellenos históricos de audiencias. Todas las calificaciones del segmento se envían a [!UICONTROL Twitter] cuando crea el destino.

## Resolución de problemas {#troubleshooting}

Al configurar o enviar datos al destino de Audiencias personalizadas de Twitter, puede encontrar los errores que se describen a continuación. En esta sección se explica qué puede causar los errores y cómo corregirlos.

| Mensaje de error | Ocurrencia/Motivo | Resolución |
|---|---|---|
| `Internal server error` | Este mensaje de error se muestra en la interfaz de usuario de Audience Manager al intentar agregar una nueva cuenta de [!DNL Twitter] mediante una versión obsoleta de la API de Twitter. | Póngase en contacto con el Servicio de atención al cliente de Adobe. |
| `Twitter Error: This request is not properly authenticated` | Este mensaje de error se muestra en la interfaz de usuario de Audience Manager al intentar asignar segmentos con nombres de segmento no admitidos al destino. | Revise los nombres de segmento asignados y asegúrese de que no contengan caracteres no admitidos. Consulte [consideraciones sobre la asignación de segmentos](#segment-mapping-considerations) para ver la lista de caracteres no admitidos. |
| `Twitter Error: Account XXXXXXXXX was not found` | Este mensaje de error se muestra en la interfaz de usuario de Audience Manager cuando las credenciales configuradas para el destino no están autorizadas a acceder a la cuenta de Twitter Ads correspondiente. | <ul><li>Asegúrese de que las credenciales de la cuenta que está usando cumplan [los requisitos previos](#prerequisites).</li><li>Vaya a la interfaz de usuario de Twitter Ads con las mismas credenciales y compruebe si las audiencias correctas se muestran en la cuenta de `XXXXXXXXX` correspondiente. </li></ul> |