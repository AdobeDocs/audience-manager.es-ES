---
description: Preguntas más frecuentes sobre la función de laboratorio de Audiencia.
seo-description: Preguntas más frecuentes sobre la función de laboratorio de Audiencia.
seo-title: Preguntas más frecuentes sobre el laboratorio de Audiencia
solution: Audience Manager
title: Preguntas más frecuentes sobre el laboratorio de Audiencia
topic: DIL API
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Preguntas más frecuentes sobre el laboratorio de Audiencia{#audience-lab-faq}

Preguntas más frecuentes sobre la función de laboratorio de Audiencia.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**¿Los segmentos de prueba creados en los grupos de prueba tienen ID de segmento diferentes? ¿Cómo asigno los ID a diferentes destinos?**

Sí, los segmentos de prueba tienen ID de segmento diferentes. En el caso de los destinos con [!UICONTROL Auto-fill Destination Mapping] o segmentos enviados a [!DNL Google], [!UICONTROL Audience Lab] gestionará los valores de asignación como lo harían normalmente los destinos.

<br> 

**¿Puede asociarse la misma característica de conversión con varios grupos de prueba?**

Sí, esto está permitido. Piense en un caso de una prueba que utiliza un segmento masculino asociado a la conversión X y una prueba que utiliza un segmento femenino asociado a la conversión X. No importa que ambas pruebas estén generando conversiones, ya que están probando dos audiencias diferentes.

<br> 

**Supongamos que un grupo de prueba utiliza un perfil autenticado para la división del segmento de prueba. El perfil autenticado está vinculado a 4 UUID del Administrador de[Audiencias](../reference/ids-in-aam.md). Cuando el visitante muestra una característica de conversión de uno de los cuatro UUID, ¿[!UICONTROL Audience Lab]lo cuenta como una o cuatro conversiones?**

En este caso, [!UICONTROL Audience Lab] solo cuenta una conversión.

<br> 

**¿Qué sucede si el visitante del caso anterior muestra primero la característica de conversión de uno de los cuatro UUID vinculados a su perfil autenticado y, a continuación, también muestra la característica de conversión de otros dos UUID vinculados al perfil autenticado? ¿Se cuenta este caso como una o tres conversiones?**

En este caso, [!UICONTROL Audience Lab] cuenta tres conversiones, una para cada dispositivo que ha mostrado la característica de autenticación.

<br> 

**¿Puede un usuario tener[!UICONTROL Segment: Read-Only]acceso, pero también[!UICONTROL Audience Lab]probar el acceso a la creación de segmentos?**

Consulte [Crear grupo](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) de prueba de segmentos para obtener información sobre cómo usar [!UICONTROL Audience Lab] con [!UICONTROL RBAC] privilegios.

**¿Puedo usar[!UICONTROL Audience Lab]junto con los gráficos de dispositivos[!UICONTROL Profile Link Device Graph]y externos ([Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html), Tapad Device Graph, Liveramp Device Graph)?**

Por ahora, [!UICONTROL Audience Lab] solo puede dividir las poblaciones de segmentos por los dispositivos conectados a un dispositivo que cumpla los requisitos, al usar el [!UICONTROL Profile Link Device Graph]. Estamos trabajando en agregar compatibilidad con [!UICONTROL Audience Lab] los otros gráficos de dispositivos y le informaremos cuando lo hagamos.
