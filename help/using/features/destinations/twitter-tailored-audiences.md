---
description: En este artículo se explica cómo configurar Audiencias personalizadas de Twitter para integraciones nuevas y existentes.
seo-description: En este artículo se explica cómo configurar Audiencias personalizadas de Twitter para integraciones nuevas y existentes.
seo-title: Configurar Audiencias personalizadas de Twitter como un destino basado en dispositivos de autoservicio
solution: Audience Manager
title: Configurar Audiencias personalizadas de Twitter como un destino basado en dispositivos de autoservicio
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 4%

---

# Configure [!DNL Twitter Tailored Audiences] como un destino basado en dispositivos de autoservicio {#configure-twitter}

Este artículo explica cómo configurar una integración con [Audiencias personalizadas de Twitter](https://business.twitter.com/en/targeting/tailored-audiences.html).

## Requisitos previos {#prerequisites}

Antes de configurar su destino [!DNL Twitter Tailored Audiences], asegúrese de revisar los siguientes requisitos previos de Twitter que necesita cumplir.

1. Su cuenta [!DNL Twitter Ads] debe ser elegible para publicidad. Las nuevas cuentas [!DNL Twitter Ads] no pueden anunciarse en las dos primeras semanas después de crearlas.
2. Su cuenta de usuario [!DNL Twitter] para la que autorizó el acceso en el Audience Manager debe tener habilitado el permiso [Partner audience manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels).
3. Al crear el primer [!DNL Twitter Tailored Audiences] destino en la instancia de Audience Manager, póngase en contacto con el servicio de consultoría de Adobe o el Servicio de atención al cliente para habilitar la sincronización de ID [!DNL Twitter] (ID de fuente de datos = 1123) para su cuenta. Esto es necesario para la sincronización correcta entre Audience Manager y [!DNL Twitter].

## Añadir un nuevo [!DNL Twitter Tailored Audiences] destino {#add-new-twitter-destination}

En esta sección se describen los pasos que debe seguir al configurar un nuevo destino basado en dispositivos para [!DNL Twitter Tailored Audiences]. En este escenario se supone que no tiene ningún destino [!DNL Twitter Tailored Audiences] configurado a través de su asesor de Adobe o del Servicio de atención al cliente.

### Paso 1. Autenticar con [!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

Para poder agregar un destino basado en dispositivos, debe vincular al Audience Manager y su cuenta [!DNL Twitter Tailored Audiences]. A continuación se muestra cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!DNL Administration > Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma de destino, debería verla en esta página. De lo contrario, la página estará vacía.
1. Haga clic **[!DNL Add Account]**.
1. Seleccione [!DNL Twitter Tailored Audiences] y haga clic en **[!DNL Confirm]** para redirigirse a la página de autenticación.                     ![plataformas integradas](assets/dbd-integrated-platforms.png)
1. Una vez que se haya autenticado, se le redirigirá al Audience Manager, donde debería ver sus cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!DNL Confirm]**.

### Paso 2: Crear un nuevo destino basado en dispositivos {#step2-create-new-destination}

Después de haber vinculado el Audience Manager y el [!DNL Twitter Tailored Audiences], puede crear el nuevo destino. A continuación se muestra cómo hacerlo:

>[!NOTE]
>
>No puede cambiar el nombre de un destino existente basado en dispositivos. Asegúrese de proporcionar un nombre que le ayude a identificar el destino correctamente.

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!DNL Audience Data > Destinations]** y haga clic en **[!DNL Create Destination]**.
1. En la sección **[!DNL Basic Information]** , introduzca **[!DNL Name]** y **[!DNL Description]** para el nuevo destino y utilice la configuración siguiente: ![configuración](assets/dbd-new-basic.png)
1. Haga clic **[!DNL Next]**.
1. Elija las [Etiquetas de exportación de datos](/help/using/features/data-export-controls.md#controls-labels) que desea establecer para este destino.
1. Haga clic **[!DNL Save]**.
1. En la sección **[!DNL Segment Mappings]** , seleccione los segmentos de audiencia que desee enviar a este destino.
1. Guarde el destino.

## Consideraciones de asignación de segmentos {#segment-mapping-considerations}

Al asignar segmentos de audiencia a [!UICONTROL Twitter], asegúrese de cumplir los siguientes requisitos de nomenclatura de segmentos:

* Proporcione nombres de asignación de segmentos legibles en lenguaje natural. Se recomienda utilizar el mismo nombre que se utilizó para los segmentos de Audience Manager.
* No utilice caracteres especiales (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) en los nombres de asignación de segmentos y segmentos. Si el nombre del segmento del Audience Manager contiene estos caracteres, elimínelos antes de asignar el segmento a un destino [!UICONTROL Twitter].

### Ejemplo

* Nombre correcto de segmento o asignación: &quot;compradores estadounidenses y europeos&quot;;
* Nombre incorrecto de segmento o asignación: &quot;EE.UU., Europa 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>No puede cambiar los nombres de segmentos ya asignados. Audience Manager utiliza los nombres de segmentos para identificar correctamente los segmentos en la integración.

## Consideraciones de tasas de coincidencia {#match-rates-considerations}

* La integración entre Audience Manager y [!UICONTROL Twitter Tailored Audiences] admite los rellenos históricos de audiencias. Todas las cualificaciones del segmento se envían a [!UICONTROL Twitter] al crear el destino.
