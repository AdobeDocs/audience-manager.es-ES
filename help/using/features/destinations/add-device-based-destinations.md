---
description: En este artículo se explica cómo configurar nuevos destinos basados en dispositivos desde la interfaz de usuario del Audience Manager.
seo-description: En este artículo se explica cómo configurar nuevos destinos basados en dispositivos desde la interfaz de usuario del Audience Manager.
seo-title: Añadir nuevos destinos basados en dispositivos
solution: Audience Manager
title: Añadir nuevos destinos basados en dispositivos
feature: Conceptos básicos de destino
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 4%

---

# Añadir nuevos destinos basados en dispositivos {#add-new-device-based-destinations}

En este artículo se explica cómo configurar nuevos destinos basados en dispositivos desde la interfaz de usuario del Audience Manager.

>[!IMPORTANT]
>
>Actualmente, la mayoría de los destinos basados en dispositivos no son aptos para el flujo de trabajo de configuración de autoservicio. Si el destino basado en dispositivos que debe añadir no se muestra en la lista de destinos, póngase en contacto con el asesor de Adobe o con la asistencia al cliente para obtener ayuda.

## Información general {#overview}

El proceso de adición de un nuevo destino basado en dispositivos consta de dos pasos principales. En primer lugar, debe configurar la integración entre el Audience Manager y el socio de destino. Una vez hecho esto, puede crear un nuevo destino basado en dispositivos.

## Requisitos previos {#prerequisites}

Al crear el primer destino basado en dispositivos con una plataforma integrada, póngase en contacto con el servicio de consultoría de Adobe o con el Servicio de atención al cliente para habilitar la sincronización de ID entre el Audience Manager y la plataforma integrada de su cuenta. Esto es necesario para la sincronización correcta entre el Audience Manager y la plataforma de destino.

## Paso 1. Autenticar con una plataforma de destino {#step1}

Para poder crear un nuevo destino basado en dispositivos, debe configurar la integración entre Audience Manager y la plataforma de destino. A continuación se muestra cómo hacerlo:

1. Inicie sesión en su cuenta de Audience Manager y vaya a **[!DNL Administration > Integrated Accounts]**. Si tiene una integración configurada anteriormente con una plataforma de destino, debería verla en esta página. De lo contrario, la página estará vacía.
1. Haga clic **[!DNL Add Account]**.
1. Seleccione la plataforma de destino con la que desea autenticarse y haga clic en **[!DNL Confirm]** para redirigirse a la página de autenticación de la plataforma seleccionada.

   ![plataformas integradas](assets/dbd-integrated-platforms.png)

1. Una vez que se haya autenticado en la cuenta de la plataforma de destino, se le redirigirá al Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic en **[!DNL Confirm]**.

## Paso 2: Crear un nuevo destino basado en dispositivos {#step2}

Una vez configurada la integración de la plataforma de destino, puede crear el nuevo destino. A continuación se muestra cómo hacerlo:

>[!NOTE]
>
>No puede cambiar el nombre de un destino existente basado en dispositivos. Asegúrese de proporcionar un nombre que le ayude a identificar el destino correctamente.

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!DNL Audience Data > Destinations]** y haga clic en **[!DNL Create Destination]**.
1. En la sección **[!DNL Basic Information]**, introduzca un **[!DNL Name]** y **[!DNL Description]** para el nuevo destino y utilice la configuración de la lista siguiente:

   ![configuración](assets/dbd-new-basic.png)

   * **[!DNL Category]**:  [!DNL Integrated Platforms];
   * **[!DNL Type]**:  [!DNL Device-Based];
   * **[!DNL Platform]**: seleccione la plataforma de destino a la que desea enviar segmentos de audiencia.
   * **[!DNL Account]**: seleccione la cuenta del anunciante que desee asociada a la plataforma seleccionada.
1. Haga clic **[!DNL Next]**.
1. Elija las [Etiquetas de exportación de datos](/help/using/features/data-export-controls.md#controls-labels) que desea establecer para este destino.
1. Haga clic **[!DNL Save]**.
1. En la sección **[!DNL Segment Mappings]** , seleccione los segmentos de audiencia que desee enviar a este destino.
1. Guarde el destino.
