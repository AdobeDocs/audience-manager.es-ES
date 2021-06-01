---
description: Preguntas frecuentes sobre Audience Lab.
seo-description: Preguntas frecuentes sobre Audience Lab.
seo-title: Preguntas frecuentes sobre Audience Lab
solution: Audience Manager
title: Preguntas frecuentes sobre Audience Lab
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
feature: 'Audience Lab '
exl-id: 25bdabb5-2ba8-45d2-81ca-05c0590d7d96
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 100%

---

# Preguntas frecuentes sobre Audience Lab {#audience-lab-faq}

Preguntas frecuentes sobre Audience Lab.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**¿Los segmentos de prueba creados en los grupos de prueba tienen ID de segmento diferentes? ¿Cómo asigno los ID a diferentes destinos?**

Sí, los segmentos de prueba tienen ID de segmento diferentes. En el caso de los destinos con [!UICONTROL Auto-fill Destination Mapping] o segmentos enviados a [!DNL Google], [!UICONTROL Audience Lab] gestionará los valores de asignación como lo harían normalmente los destinos.

<br> 

**¿Puede asociarse el mismo rasgo de conversión con varios grupos de pruebas?**

Sí, se puede hacer. Pongamos un ejemplo en el que se utiliza un segmento Masculino asociado a la conversión X y una prueba que utiliza un segmento Femenino asociado a la conversión X. No importa que ambas pruebas estén generando conversiones, ya que están probando dos audiencias diferentes.

<br> 

**Supongamos que un grupo de prueba utiliza un perfil autenticado para la división del segmento de prueba. El perfil autenticado está vinculado a 4 [UUID de Audience Manager](../reference/ids-in-aam.md). Cuando el visitante muestra un rasgo de conversión de uno de los cuatro UUID, ¿[!UICONTROL Audience Lab] lo cuenta como una o cuatro conversiones?**

En este caso, [!UICONTROL Audience Lab] solo cuenta una conversión.

<br> 

**¿Qué sucede si el visitante del caso anterior muestra primero el rasgo de conversión de uno de los cuatro UUID vinculados a su perfil autenticado y, a continuación, también muestra el rasgo de conversión de otros dos UUID vinculados al perfil autenticado? ¿Se cuenta este caso como una o como tres conversiones?**

En este caso, [!UICONTROL Audience Lab] cuenta como tres conversiones, una para cada dispositivo que ha mostrado el rasgo de autenticación.

<br> 

**¿Puede un usuario tener acceso a [!UICONTROL Segment: Read-Only], pero también acceso para probar la creación de segmentos de [!UICONTROL Audience Lab]?**

Consulte [Crear grupo de prueba de segmentos](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) para obtener información sobre cómo usar [!UICONTROL Audience Lab] con privilegios [!UICONTROL RBAC].

**¿Puedo usar [!UICONTROL Audience Lab] junto con [!UICONTROL Profile Link Device Graph] y los gráficos de dispositivos externos ([Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/es-ES/device-co-op/using/home.html), Tapad Device Graph, Liveramp Device Graph)?**

Por ahora, [!UICONTROL Audience Lab] solo puede dividir las poblaciones de segmentos por los dispositivos conectados a un dispositivo que cumpla los requisitos, al usar el [!UICONTROL Profile Link Device Graph]. Estamos trabajando para que [!UICONTROL Audience Lab] admita los otros gráficos de dispositivos y le informaremos cuando lo consigamos.
