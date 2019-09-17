---
description: En este artículo se explica cómo configurar nuevos destinos basados en dispositivos desde la interfaz de usuario de Audience Manager.
seo-description: En este artículo se explica cómo configurar nuevos destinos basados en dispositivos desde la interfaz de usuario de Audience Manager.
seo-title: Agregar nuevos destinos basados en dispositivos
solution: Audience Manager
title: Agregar nuevos destinos basados en dispositivos
translation-type: tm+mt
source-git-commit: bdf4a26fb128e4e76507ce6d7bbb19decb13173e

---


# Agregar nuevos destinos basados en dispositivos {#add-new-device-based-destinations}

En este artículo se explica cómo configurar nuevos destinos basados en dispositivos desde la interfaz de usuario de Audience Manager.

## Información general {#overview}

El proceso de agregar un nuevo destino basado en dispositivos consiste en dos pasos principales. En primer lugar, debe configurar la integración entre Audience Manager y el socio de destino. Una vez hecho esto, puede crear un nuevo destino basado en dispositivos.

## Requisitos previos {#prerequisites}

Al crear el primer destino basado en dispositivos con una plataforma integrada, póngase en contacto con el servicio de consultoría de Adobe o con el servicio de atención al cliente para habilitar la sincronización de ID entre Audience Manager y la plataforma integrada para su cuenta. Esto es necesario para la sincronización correcta entre Audience Manager y la plataforma de destino.

>[!IMPORTANT]
>
>No todos los destinos basados en dispositivos son elegibles para el flujo de trabajo de configuración de autoservicio. Si el destino basado en dispositivos que necesita añadir no se muestra en la lista de destinos, póngase en contacto con su asesor de Adobe o con el servicio de asistencia al cliente para obtener ayuda.

## Paso 1. Autenticar con una plataforma de destino {#step1}

Para poder crear un nuevo destino basado en dispositivos, debe configurar la integración entre Audience Manager y la plataforma de destino. A continuación se muestra cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!DNL Administration > Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma de destino, debería verla en esta página. De lo contrario, la página está vacía.
2. Haga clic en **[!DNL Add Account]**.
3. Seleccione la plataforma de destino con la que desea autenticarse y haga clic en **[!DNL Confirm]** para que se le redirija a la página de autenticación de la plataforma seleccionada. ![plataformas integradas](assets/dbd-integrated-platforms.png)
4. Una vez que se haya autenticado en la cuenta de la plataforma de destino, se le redirigirá a Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!DNL Confirm]**.

## Paso 2: Crear un nuevo destino basado en dispositivo {#step2}

Una vez configurada la integración de plataforma de destino, puede crear el nuevo destino. A continuación se muestra cómo hacerlo:

>[!NOTE]
>
>No se puede cambiar el nombre de un destino existente basado en dispositivo. Asegúrese de proporcionar un nombre que le ayude a identificar el destino correctamente.

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!DNL Audience Data > Destinations]** y haga clic en **[!DNL Create Destination]**.
2. En la **[!DNL Basic Information]** sección, introduzca un **[!DNL Name]** y **[!DNL Description]** para el nuevo destino y utilice la configuración de la lista siguiente: ![configuración](assets/dbd-new-basic.png)
   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**:: seleccione la plataforma de destino a la que desea enviar segmentos de audiencia.
   * **[!DNL Account]**:: seleccione la cuenta del anunciante que desee asociada a la plataforma seleccionada.
3. Haga clic en **[!DNL Next]**.
4. Elija las etiquetas [de exportación de](/help/using/features/data-export-controls.md#controls-labels) datos que desee establecer para este destino.
5. Haga clic en **[!DNL Save]**.
6. En la **[!DNL Segment Mappings]** sección, seleccione los segmentos de audiencia que desee enviar a este destino.
7. Guarde el destino.

