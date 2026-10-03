---
title: Configuración de una fuente de datos para flujos de trabajo de correo electrónico con hash
description: Obtenga información sobre cómo crear una fuente de datos para almacenar correos electrónicos con hash para flujos de trabajo de correo electrónico con hash.
solution: Audience Manager
feature: Data Sources
exl-id: fb235dcb-e02f-41ac-ba3f-a1feb30b23dd
TQID: 'https://experienceleague.adobe.com/dPV7bJC5zIBkj1EX43q4FWU7XP0gs-dhBYTcW8mApL4'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: c814092e-2730-45e8-a12d-e084529f52cb
    internal-label: Destinations
  - id: d8f86c1e-15ad-457f-9d6f-5e756573fad4
    internal-label: Audience Marketplace
subfeature_v2:
  - id: d921db59-bd4a-43dc-97e6-4ff4611f1ae8
    internal-label: Data sources
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 0%
---
# Configuración de una fuente de datos para flujos de trabajo de correo electrónico con hash

Los flujos de trabajo de correo electrónico con hash, como People-Based Destinations, requieren que cree una fuente de datos para almacenar las direcciones de correo electrónico con hash.

Siga los pasos a continuación para crear y configurar una fuente de datos para correos electrónicos con hash.

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** y haga clic en **[!UICONTROL Add New]**.
1. Escriba **[!UICONTROL Name]** y **[!UICONTROL Description]** para el nuevo origen de datos.
1. En el menú desplegable **[!UICONTROL ID Type]**, seleccione **[!UICONTROL Cross Device]**.
   ![Imagen de la interfaz de usuario de Audience Manager que muestra la sección de detalles de la fuente de datos.](../features/assets/create-hashed-email-data-source.png)
1. En la sección **[!UICONTROL Data Source Settings]**, seleccione las opciones **[!UICONTROL Inbound]** y **[!UICONTROL Outbound]**, y habilite la opción **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilice el menú desplegable para seleccionar la etiqueta **[!UICONTROL Emails(SHA256, lowercased)]** para este origen de datos.

   >[!IMPORTANT]
   >
   >Esta opción solo etiqueta la fuente de datos como que contiene datos con hash con ese algoritmo específico. Audience Manager no almacena en hash los datos en este paso. Asegúrese de que las direcciones de correo electrónico que planea almacenar en este origen de datos ya tengan un cifrado hash con el algoritmo [!DNL SHA256]. De lo contrario, no podrá utilizarlo para flujos de trabajo de correo electrónico con hash.

   ![Imagen de la interfaz de usuario de Audience Manager que muestra la sección de configuración del origen de datos.](../features/assets/data-source-settings.png)
