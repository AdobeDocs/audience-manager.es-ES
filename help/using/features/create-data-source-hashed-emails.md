---
title: Configuración de una fuente de datos para flujos de trabajo de correo electrónico con hash
description: Obtenga información sobre cómo crear una fuente de datos para almacenar correos electrónicos con hash para flujos de trabajo de correo electrónico con hash.
solution: Audience Manager
feature: Data Sources
source-git-commit: b88f180808ec9723a2a5324441733f6383f6302d
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---


# Configuración de una fuente de datos para flujos de trabajo de correo electrónico con hash

Los flujos de trabajo de correo electrónico con hash, como People-Based Destinations, requieren que cree una fuente de datos para almacenar las direcciones de correo electrónico con hash.

Siga los pasos a continuación para crear y configurar una fuente de datos para correos electrónicos con hash.

1. Inicie sesión en su cuenta de Audience Manager de y vaya a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** y haga clic en **[!UICONTROL Add New]**.
1. Introduzca una **[!UICONTROL Name]** y **[!UICONTROL Description]** para la nueva fuente de datos.
1. En el **[!UICONTROL ID Type]** menú desplegable, seleccione **[!UICONTROL Cross Device]**.
   ![Imagen de la IU del Audience Manager que muestra la sección de detalles de la fuente de datos.](../features/assets/create-hashed-email-data-source.png)
1. En el **[!UICONTROL Data Source Settings]** , seleccione las dos opciones **[!UICONTROL Inbound]** y **[!UICONTROL Outbound]** y habilite la opción **[!UICONTROL Share associated cross-device IDs in people-based destinations]** opción.
1. Utilice el menú desplegable para seleccionar la variable **[!UICONTROL Emails(SHA256, lowercased)]** para esta fuente de datos.

   >[!IMPORTANT]
   >
   >Esta opción solo etiqueta la fuente de datos como que contiene datos con hash con ese algoritmo específico. El Audience Manager no hace un hash de los datos en este paso. Asegúrese de que las direcciones de correo electrónico que planea almacenar en esta fuente de datos ya tengan un cifrado hash con la variable [!DNL SHA256] algoritmo. De lo contrario, no podrá utilizarlo para flujos de trabajo de correo electrónico con hash.

   ![Imagen de la IU del Audience Manager que muestra la sección de configuración de la fuente de datos.](../features/assets/data-source-settings.png)


