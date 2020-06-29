---
description: En este artículo se explica cómo configurar Audiencias personalizadas de Twitter tanto para integraciones nuevas como existentes.
seo-description: En este artículo se explica cómo configurar Audiencias personalizadas de Twitter tanto para integraciones nuevas como existentes.
seo-title: Configurar Audiencias personalizadas de Twitter como un destino basado en dispositivos de autoservicio
solution: Audience Manager
title: Configurar Audiencias personalizadas de Twitter como un destino basado en dispositivos de autoservicio
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 1%

---


# Configurar [!DNL Twitter Tailored Audiences] como destino basado en dispositivos de autoservicio {#configure-twitter}

En este artículo se explica cómo configurar una integración con Audiencias [personalizadas de](https://business.twitter.com/en/targeting/tailored-audiences.html)Twitter.

## Requisitos previos {#prerequisites}

Antes de configurar su [!DNL Twitter Tailored Audiences] destino, asegúrese de revisar los siguientes requisitos previos de Twitter que necesita cumplir.

1. Su [!DNL Twitter Ads] cuenta debe ser elegible para publicidad. Las nuevas [!DNL Twitter Ads] cuentas no son elegibles para publicidad en las dos primeras semanas después de crearlas.
2. Su cuenta [!DNL Twitter] de usuario para la que autorizó el acceso en Audience Manager debe tener habilitado el permiso del administrador [de audiencias de](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) socio.
3. Al crear el primer [!DNL Twitter Tailored Audiences] destino en la instancia de Audience Manager, póngase en contacto con el servicio de consultoría de Adobe o con el servicio de atención al cliente para habilitar la sincronización de [!DNL Twitter] ID (ID de fuente de datos = 1123) para su cuenta. Esto es necesario para la sincronización correcta entre Audience Manager y [!DNL Twitter].

## Añadir un nuevo [!DNL Twitter Tailored Audiences] destino {#add-new-twitter-destination}

En esta sección se describen los pasos que debe seguir al configurar un nuevo destino basado en dispositivos para [!DNL Twitter Tailored Audiences]. En este escenario se asume que no hay ningún destino [!DNL Twitter Tailored Audiences] configurado mediante el consultor de Adobe o el Servicio de atención al cliente.

### Paso 1. Autenticar con [!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

Antes de agregar el destino basado en dispositivos, debe vincular Audience Manager y su [!DNL Twitter Tailored Audiences] cuenta. A continuación se muestra cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!DNL Administration > Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma de destino, debería verla en esta página. De lo contrario, la página está vacía.
1. Haga clic **[!DNL Add Account]**.
1. Seleccione [!DNL Twitter Tailored Audiences] y haga clic en **[!DNL Confirm]** para que se le redirija a la página de autenticación.                     ![plataformas integradas](assets/dbd-integrated-platforms.png)
1. Una vez que se haya autenticado, se le redirigirá al Audience Manager, donde debería ver sus cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!DNL Confirm]**.

### Paso 2: Crear un nuevo destino basado en dispositivo {#step2-create-new-destination}

Una vez que haya vinculado al Audience Manager y al [!DNL Twitter Tailored Audiences]usuario, puede crear el nuevo destino. A continuación se muestra cómo hacerlo:

>[!NOTE]
>
>No se puede cambiar el nombre de un destino existente basado en dispositivo. Asegúrese de proporcionar un nombre que le ayude a identificar el destino correctamente.

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!DNL Audience Data > Destinations]** y haga clic en **[!DNL Create Destination]**.
1. En la **[!DNL Basic Information]** sección, introduzca un **[!DNL Name]** y **[!DNL Description]** para el nuevo destino y utilice la configuración siguiente: ![configurar](assets/dbd-new-basic.png)
1. Haga clic **[!DNL Next]**.
1. Elija las etiquetas [de exportación de](/help/using/features/data-export-controls.md#controls-labels) datos que desee establecer para este destino.
1. Haga clic **[!DNL Save]**.
1. En la **[!DNL Segment Mappings]** sección, seleccione los segmentos de audiencia que desee enviar a este destino.
1. Guarde el destino.

## Consideraciones sobre la asignación de segmentos {#segment-mapping-considerations}

Al asignar segmentos de audiencia a [!UICONTROL Twitter], asegúrese de cumplir los siguientes requisitos de nomenclatura de segmentos:

* Proporcione nombres de asignación de segmentos legibles por el usuario. Se recomienda usar el mismo nombre que utilizó para los segmentos de Audience Manager.
* No utilice caracteres especiales (`,``%` `:``;` `@` `/` `=` `?` `$`) en los nombres de asignación de segmentos y segmentos. Si el nombre del segmento del Audience Manager contiene estos caracteres, elimínelos antes de asignar el segmento a un [!UICONTROL Twitter] destino.

### Ejemplo

* Nombre de asignación o segmento correcto: &quot;Compradores europeos y estadounidenses&quot;;
* Nombre de asignación o segmento incorrecto: &quot;EE.UU., europeo 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>No puede cambiar los nombres de los segmentos ya asignados. Audience Manager utiliza los nombres de los segmentos para identificar correctamente los segmentos en la integración.

## Consideraciones sobre las tasas de coincidencia {#match-rates-considerations}

* Al utilizar [!UICONTROL Twitter Tailored Audiences], las métricas [!UICONTROL Segment Addressable Audience] y [!UICONTROL Segment Match Rate] de la página de destino no mostrarán ningún valor. Esto es normal, ya que la coincidencia de audiencias junto con las tasas de coincidencia de este destino son gestionadas y alojadas por [!UICONTROL Twitter], no por Adobe.
* La integración entre Audience Manager y [!UICONTROL Twitter Tailored Audiences] admite los rellenos de audiencia históricos. Todas las cualificaciones del segmento se envían [!UICONTROL Twitter] al crear el destino.
