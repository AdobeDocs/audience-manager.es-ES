---
description: En este artículo se explica cómo configurar nuevos destinos basados en dispositivos desde la interfaz de usuario de Audience Manager.
seo-description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: Añadir nuevos destinos basados en dispositivos
feature: Destination Basics
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
TQID: https://experienceleague.adobe.com/E8htvz6eNU2PBT3d-oCbQDzrFRf28-Wlb3HES8n69DE
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: c814092e-2730-45e8-a12d-e084529f52cbid: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: c138d302-73f0-4186-93ea-10c4ba52f943id: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 420
ht-degree: 2%

---

# Añadir nuevos destinos basados en dispositivos {#add-new-device-based-destinations}

En este artículo se explica cómo configurar nuevos destinos basados en dispositivos desde la interfaz de usuario de Audience Manager.

>[!IMPORTANT]
>
>Actualmente, la mayoría de los destinos basados en dispositivos no cumplen los requisitos para el flujo de trabajo de configuración de autoservicio. Si el destino basado en dispositivos que necesita agregar no se muestra en la lista de destinos, póngase en contacto con su asesor de Adobe o con Asistencia al cliente para obtener ayuda.

## Información general {#overview}

El proceso de añadir un nuevo destino basado en dispositivos consta de dos pasos principales. En primer lugar, se debe configurar la integración entre Audience Manager y el socio de destino. Una vez hecho esto, puede crear un nuevo destino basado en dispositivos.

## Requisitos previos {#prerequisites}

Al crear el primer destino basado en dispositivos con una plataforma integrada, póngase en contacto con Adobe Consulting o con el Servicio de atención al cliente para habilitar la sincronización de ID entre Audience Manager y la plataforma integrada de su cuenta. Esto es necesario para la sincronización correcta entre Audience Manager y la plataforma de destino.

## Paso 1: Autenticar con una plataforma de destino {#step1}

Para poder crear un nuevo destino basado en dispositivos, debe configurar la integración entre Audience Manager y la plataforma de destino. A continuación se indica cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!DNL Administration > Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma de destino, debería verla en esta página. En caso contrario, la página está vacía.
1. Haga clic en **[!DNL Add Account]**.
1. Seleccione la plataforma de destino con la que desea autenticarse y haga clic en **[!DNL Confirm]** para que se le redirija a la página de autenticación de la plataforma seleccionada.

   ![plataformas integradas](assets/dbd-integrated-platforms.png)

1. Una vez que se haya autenticado en la cuenta de la plataforma de destino, se le redirigirá a Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta de anunciante que desee usar y haga clic en **[!DNL Confirm]**.

## Paso 2: Crear un nuevo destino basado en dispositivos {#step2}

Después de configurar la integración de la plataforma de destino, puede crear el nuevo destino. A continuación se indica cómo hacerlo:

>[!NOTE]
>
>No puede cambiar el nombre de un destino existente basado en dispositivos. Asegúrese de proporcionar un nombre que le ayude a identificar el destino correctamente.

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!DNL Audience Data > Destinations]** y haga clic en **[!DNL Create Destination]**.
1. En la sección **[!DNL Basic Information]**, escriba un **[!DNL Name]** y **[!DNL Description]** para el nuevo destino y use la configuración de la lista siguiente:

   ![instalación](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: seleccione la plataforma de destino a la que desee enviar segmentos de audiencia.
   * **[!DNL Account]**: seleccione la cuenta de anunciante deseada asociada con la plataforma seleccionada.
1. Haga clic en **[!DNL Next]**.
1. Elija las [etiquetas de exportación de datos](/help/using/features/data-export-controls.md#controls-labels) que desee establecer para este destino.
1. Haga clic en **[!DNL Save]**.
1. En la sección **[!DNL Segment Mappings]**, seleccione los segmentos de audiencia que desee enviar a este destino.
1. Guarde el destino.
