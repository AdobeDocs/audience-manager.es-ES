---
description: Utilice el Visor de perfiles de visitantes para mostrar el estado actual de un perfil de usuario para el explorador actual, incluidos sus rasgos y segmentos. Para cada rasgo, puede ver su SID, nombre, detalles sobre cómo se realizaron los rasgos de visitante (de origen o de terceros), la fecha de realización y la frecuencia de las realizaciones. Para cada segmento, puede ver su SID, nombre y fecha de inscripción al segmento. También puede ver el perfil del visitante para otro ID de perfil de Audience Manager (UUID). El Visor de perfiles de visitantes resulta útil para solucionar problemas.
keywords: ubicación;parámetro de ubicación
seo-description: Use the Visitor Profile Viewer to display the current state of a user profile for the current browser, including its traits and segments. For each trait, you can view its SID, name, details about how visitor traits were realized (first- or third-party), the realization date, and the frequency of realizations. For each segment, you can view its SID, name, and the segment membership date. You can also view the visitor profile for another Audience Manager profile ID (UUID). The Visitor Profile Viewer is helpful for troubleshooting purposes.
seo-title: Visitor Profile Viewer
solution: Audience Manager
title: Visor de perfiles de visitante
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: Traits
exl-id: 6c1ee14c-6f78-4e45-9b88-24ace8400079
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Visor de perfiles de visitante {#visitor-profile-viewer}

Use [!UICONTROL Visitor Profile Viewer] para mostrar el estado actual de un perfil de usuario para el explorador actual, incluidos sus rasgos y segmentos. Para cada rasgo, puede ver su [!UICONTROL SID], nombre, detalles sobre cómo se realizaron los rasgos de visitante (de origen o de terceros), la fecha de realización y la frecuencia de las realizaciones. Para cada segmento, puede ver su [!UICONTROL SID], nombre y la fecha de inscripción al segmento. También puede ver el perfil del visitante para otro ID de perfil de Audience Manager ([!UICONTROL UUID]). [!UICONTROL Visitor Profile Viewer] es útil para solucionar problemas.

>[!NOTE]
>
>* El acceso requiere permisos de [!UICONTROL Administrator].
>* La información sobre segmentos realizados y rasgos incorporados aparece en la interfaz de usuario con un retraso de 24 horas.

<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. Haga clic en **[!UICONTROL Tools]** > **[!UICONTROL Visitor Profile Viewer]**.

1. *(Opcional)* Haga clic en el nombre del rasgo para mostrarlo en [!UICONTROL Trait Builder].

   Para obtener más información, consulte [Características](../features/traits/trait-details-page.md).

1. *(Opcional)* Haga clic en el nombre del segmento para mostrar ese segmento en [!UICONTROL Segment Builder].

   Para obtener más información, consulte [Segmentos](../features/segments/segments-purpose.md).

1. *(Condicional)* En el cuadro **[!UICONTROL UUID]**, especifique otro ID de perfil de Audience Manager y, a continuación, haga clic en **[!UICONTROL Refresh]** para ver los rasgos y segmentos de ese usuario.
