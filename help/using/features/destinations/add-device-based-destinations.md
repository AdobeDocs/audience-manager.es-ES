---
description: Este artículo explica cómo configurar nuevos destinos basados en dispositivos desde la interfaz Audience Manager usuario.
seo-description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: añadir Nuevo destinos basados en dispositivos
feature: Destination Basics
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 1%

---

# añadir Nuevo destinos basados en dispositivos {#add-new-device-based-destinations}

Este artículo explica cómo configurar nuevos destinos basados en dispositivos desde la interfaz Audience Manager usuario.

>[!IMPORTANT]
>
>Actualmente, la mayoría de los destinos basados en dispositivos no son elegibles para el flujo de trabajo de configuración de autoservicio. Si el destino basado en dispositivos que debe agregar no aparece en el lista destinos, póngase en contacto con su consultor de Adobe Systems o con Asistencia al cliente para obtener ayuda.

## Información general {#overview}

El proceso de adición de un nuevo destino basado en dispositivos consta de dos pasos principales. Primero, debe configurar la integración entre Audience Manager y el destino socio. Una vez hecho esto, puede crear un nuevo destino basado en dispositivos.

## Requisitos previos {#prerequisites}

Cuando cree el primer destino basado en dispositivos con un plataforma integrada, póngase en contacto con Adobe Systems asesor o servicio de atención al cliente para habilitar la sincronización de ID entre Audience Manager y el plataforma integrada de su cuenta. Esto es necesario para la correcta sincronización entre Audience Manager y la plataforma de destino.

## Paso 1. Autenticar con un Platform de destino {#step1}

Antes de poder crear un nuevo destino basado en dispositivos, debe configurar la integración entre Audience Manager y la plataforma de destino. A continuación, le indicamos cómo hacerlo:

1. Inicie sesión en su Audience Manager cuenta y vaya a **[!DNL Administration > Integrated Accounts]**. Si ha configurado previamente una integración con una plataforma de destino, debería verla listada en este Página. De lo contrario, la Página está vacía.
1. Haga clic en **[!DNL Add Account]**.
1. Seleccione la plataforma de destino con la que desea autenticarse y haga clic para **[!DNL Confirm]** ser redirigido a la Página de autenticación de la plataforma seleccionada.

   ![plataformas integradas](assets/dbd-integrated-platforms.png)

1. Una vez que se haya autenticado en su cuenta de plataforma de destino, se le redirigirá a Audience Manager donde debería ver sus cuentas anunciante asociadas. Seleccione el cuenta anunciante que desea utilizar y haga clic en **[!DNL Confirm]**.

## Paso 2: Crear un destino Nuevo basado en dispositivos {#step2}

Una vez configurada la integración de la plataforma de destino, puede crear el nuevo destino. A continuación, le indicamos cómo hacerlo:

>[!NOTE]
>
>No puede cambiar el nombre de un destino basado en dispositivos existente. Asegúrese de proporcionar un nombre que le ayude a identificar el destino correctamente.

1. Inicie sesión en su cuenta Audience Manager, vaya a **[!DNL Audience Data > Destinations]** y haga clic en **[!DNL Create Destination]**.
1. En la **[!DNL Basic Information]** sección, introduzca un **[!DNL Name]** y **[!DNL Description]** para el nuevo destino y utilice la configuración de los lista siguientes:

   ![arreglo](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: seleccione la plataforma de destino a la que desee enviar audiencia segmentos.
   * **[!DNL Account]**: seleccione la anunciante cuenta asociada a la plataforma seleccionada.
1. Haga clic en **[!DNL Next]**.
1. Elija las etiquetas[ de exportación de ](/help/using/features/data-export-controls.md#controls-labels)datos que desea establecer para este destino.
1. Haga clic en **[!DNL Save]**.
1. En la **[!DNL Segment Mappings]** sección, seleccione los audiencia segmentos que desea enviar a este destino.
1. Guardar el destino.
