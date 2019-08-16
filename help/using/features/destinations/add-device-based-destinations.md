---
description: Este artículo explica cómo configurar nuevos destinos basados en dispositivos desde la interfaz de usuario de Audience Manager.
seo-description: Este artículo explica cómo configurar nuevos destinos basados en dispositivos desde la interfaz de usuario de Audience Manager.
seo-title: Agregar nuevos destinos basados en dispositivo
solution: Audience Manager
title: Agregar nuevos destinos basados en dispositivo
translation-type: tm+mt
source-git-commit: b492065756d45ee6dfb185cc387409dea72a9923

---


# Agregar nuevos destinos basados en dispositivo {#add-new-device-based-destinations}

Este artículo explica cómo configurar nuevos destinos basados en dispositivos desde la interfaz de usuario de Audience Manager.

## Información general {#overview}

El proceso de agregar un nuevo destino basado en dispositivo consiste en dos pasos principales. Primero, debe configurar la integración entre Audience Manager y el socio de destino. Una vez hecho esto, puede crear un nuevo destino basado en dispositivo.

>[!IMPORTANT]
>
>No todos los destinos basados en dispositivos son elegibles para el flujo de trabajo de configuración de autoservicio. Si el destino basado en dispositivos que necesita agregar no se muestra en la lista de destinos, póngase en contacto con su consultor de Adobe o con Asistencia al cliente para obtener ayuda.

## Paso 1. Autenticar con una plataforma de destino {#step1}

Para poder crear un nuevo destino basado en dispositivos, debe configurar la integración entre Audience Manager y la plataforma de destino. A continuación se muestra cómo hacer esto:

1. Inicie sesión en su cuenta de Audience Manager y vaya **[!DNL Administration > Integrated Accounts]** a. Si tiene una integración configurada previamente con una plataforma de destino, debería verlo en esta página. De lo contrario, la página está vacía.
2. Haga clic en **[!DNL Add Account]**.
3. Seleccione la plataforma de destino a la que desee autenticar y haga clic **[!DNL Confirm]** para redireccionar a la página de autenticación de la plataforma seleccionada. ![plataformas integradas](assets/dbd-integrated-platforms.png)
4. Una vez que haya autenticado en su cuenta de plataforma de destino, se le redirigirá a Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic **[!DNL Confirm]** en.

## Paso 2: Crear un nuevo destino basado en dispositivo {#step2}

Una vez configurada la integración de la plataforma de destino, puede crear el nuevo destino. A continuación se muestra cómo hacer esto:

>[!NOTE]
>
>No puede cambiar el nombre de un destino existente basado en dispositivo. Asegúrese de proporcionar un nombre que le ayude a identificar el destino correctamente.

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!DNL Audience Data > Destinations]** y haga clic **[!DNL Create Destination]** en.
2. En **[!DNL Basic Information]** la sección, introduzca un **[!DNL Name]** y **[!DNL Description]** para el nuevo destino y utilice la configuración de la lista siguiente: ![configurar](assets/dbd-new-basic.png)
3. Haga clic en **[!DNL Next]**.
4. Elija las etiquetas de exportación [de datos](/help/using/features/data-export-controls.md#controls-labels) que desee definir para este destino.
5. Haga clic en **[!DNL Save]**.
6. En **[!DNL Segment Mappings]** la sección, seleccione los segmentos de audiencia que desee enviar a este destino.
7. Guarde el destino.

* **[!DNL Category]**: [!DNL Integrated Platforms];
* **[!DNL Type]**: [!DNL Device-Based];
* **[!DNL Platform]**: seleccione la plataforma de destino a la que desee enviar segmentos de audiencia.
* **[!DNL Account]**: seleccione la cuenta del anunciante que desee asociada con la plataforma seleccionada.