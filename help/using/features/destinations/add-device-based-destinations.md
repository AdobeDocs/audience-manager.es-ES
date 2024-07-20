---
description: En este artículo se explica cómo configurar nuevos destinos basados en dispositivos desde la interfaz de usuario del Audience Manager.
seo-description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: Añadir nuevos destinos basados en dispositivos
feature: Destination Basics
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 1%

---

# Añadir nuevos destinos basados en dispositivos {#add-new-device-based-destinations}

En este artículo se explica cómo configurar nuevos destinos basados en dispositivos desde la interfaz de usuario del Audience Manager.

>[!IMPORTANT]
>
>Actualmente, la mayoría de los destinos basados en dispositivos no cumplen los requisitos para el flujo de trabajo de configuración de autoservicio. Si el destino basado en dispositivos que necesita agregar no se muestra en la lista de destinos, póngase en contacto con su asesor de Adobe o con Asistencia al cliente para obtener ayuda.

## Información general {#overview}

El proceso de añadir un nuevo destino basado en dispositivos consta de dos pasos principales. En primer lugar, se debe configurar la integración entre Audience Manager y el socio de destino. Una vez hecho esto, puede crear un nuevo destino basado en dispositivos.

## Requisitos previos {#prerequisites}

Al crear el primer destino basado en dispositivos con una plataforma integrada, póngase en contacto con Adobe Consulting o con el Servicio de atención al cliente para habilitar la sincronización de ID entre Audience Manager y la plataforma integrada de su cuenta. Esto es necesario para la sincronización correcta entre el Audience Manager y la plataforma de destino.

## Paso 1. Autenticar con una plataforma de destino {#step1}

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
