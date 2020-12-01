---
description: En este artículo se explica cómo configurar Audiencias personalizadas de Twitter tanto para integraciones nuevas como existentes.
seo-description: En este artículo se explica cómo configurar Audiencias personalizadas de Twitter tanto para integraciones nuevas como existentes.
seo-title: Configurar Audiencias personalizadas de Twitter como un destino basado en dispositivos de autoservicio
solution: Audience Manager
title: Configurar Audiencias personalizadas de Twitter como un destino basado en dispositivos de autoservicio
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: 8ff76decc1cbd7f7babd619dd1ce9fe047541337
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 4%

---


# Configure [!DNL Twitter Tailored Audiences] como un destino basado en dispositivo de autoservicio {#configure-twitter}

En este artículo se explica cómo configurar una integración con [Audiencias personalizadas de Twitter](https://business.twitter.com/en/targeting/tailored-audiences.html).

## Requisitos previos {#prerequisites}

Antes de configurar el destino [!DNL Twitter Tailored Audiences], asegúrese de revisar los siguientes requisitos previos de Twitter que necesita cumplir.

1. Su cuenta [!DNL Twitter Ads] debe ser elegible para publicidad. Las cuentas nuevas [!DNL Twitter Ads] no son elegibles para publicidad en las dos primeras semanas después de crearlas.
2. Su cuenta de [!DNL Twitter] usuario para la que autorizó el acceso en Audience Manager debe tener habilitado el permiso [Administrador de audiencias de socio](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels).
3. Al crear el primer [!DNL Twitter Tailored Audiences] destino en la instancia de Audience Manager, póngase en contacto con el Servicio de consultoría de Adobe o con el Servicio de atención al cliente para habilitar la sincronización de [!DNL Twitter] ID (ID de fuente de datos = 1123) para su cuenta. Esto es necesario para la sincronización correcta entre Audience Manager y [!DNL Twitter].

## Añadir un nuevo [!DNL Twitter Tailored Audiences] destino {#add-new-twitter-destination}

Esta sección describe los pasos que debe seguir al configurar un nuevo destino basado en dispositivos para [!DNL Twitter Tailored Audiences]. En este escenario se asume que no hay ningún [!DNL Twitter Tailored Audiences] destino configurado mediante el consultor de Adobe o el Servicio de atención al cliente.

### Paso 1. Autenticar con [!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

Antes de agregar el destino basado en dispositivos, debe vincular Audience Manager y su cuenta [!DNL Twitter Tailored Audiences]. A continuación se muestra cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!DNL Administration > Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma de destino, debería verla en esta página. De lo contrario, la página está vacía.
1. Haga clic **[!DNL Add Account]**.
1. Seleccione [!DNL Twitter Tailored Audiences] y haga clic en **[!DNL Confirm]** para que se le redirija a la página de autenticación.                     ![plataformas integradas](assets/dbd-integrated-platforms.png)
1. Una vez que se haya autenticado, se le redirigirá al Audience Manager, donde debería ver sus cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!DNL Confirm]**.

### Paso 2: Crear un nuevo destino basado en dispositivo {#step2-create-new-destination}

Después de haber vinculado el Audience Manager y su [!DNL Twitter Tailored Audiences], puede crear el nuevo destino. A continuación se muestra cómo hacerlo:

>[!NOTE]
>
>No se puede cambiar el nombre de un destino existente basado en dispositivo. Asegúrese de proporcionar un nombre que le ayude a identificar el destino correctamente.

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!DNL Audience Data > Destinations]** y haga clic en **[!DNL Create Destination]**.
1. En la sección **[!DNL Basic Information]**, escriba **[!DNL Name]** y **[!DNL Description]** para el nuevo destino y utilice la configuración siguiente: ![configuración](assets/dbd-new-basic.png)
1. Haga clic **[!DNL Next]**.
1. Elija las [Etiquetas de exportación de datos](/help/using/features/data-export-controls.md#controls-labels) que desee configurar para este destino.
1. Haga clic **[!DNL Save]**.
1. En la sección **[!DNL Segment Mappings]**, seleccione los segmentos de audiencia que desee enviar a este destino.
1. Guarde el destino.

## Consideraciones de asignación de segmentos {#segment-mapping-considerations}

Al asignar segmentos de audiencia a [!UICONTROL Twitter], asegúrese de cumplir los siguientes requisitos de nomenclatura de segmentos:

* Proporcione nombres de asignación de segmentos legibles por el usuario. Se recomienda usar el mismo nombre que utilizó para los segmentos de Audience Manager.
* No utilice caracteres especiales (`,` `%` `:` `;` `@` `/` `=` `?` `$`) en los nombres de asignaciones de segmentos y segmentos. Si el nombre del segmento del Audience Manager contiene estos caracteres, elimínelos antes de asignar el segmento a un destino [!UICONTROL Twitter].

### Ejemplo

* Nombre de asignación o segmento correcto: &quot;Compradores europeos y estadounidenses&quot;;
* Nombre de asignación o segmento incorrecto: &quot;EE.UU., europeo 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>No puede cambiar los nombres de los segmentos ya asignados. Audience Manager utiliza los nombres de los segmentos para identificar correctamente los segmentos en la integración.

## Consideraciones sobre las tasas de coincidencia {#match-rates-considerations}

* La integración entre Audience Manager y [!UICONTROL Twitter Tailored Audiences] admite los rellenos de audiencia históricos. Todas las cualificaciones del segmento se envían a [!UICONTROL Twitter] al crear el destino.
