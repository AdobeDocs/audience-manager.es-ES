---
description: Preguntas más frecuentes sobre la función Audience Lab.
seo-description: Preguntas más frecuentes sobre la función Audience Lab.
seo-title: Preguntas más frecuentes sobre Audience Lab
solution: Audience Manager
title: Preguntas más frecuentes sobre Audience Lab
topic: API DIL
uuid: b 1 daf 99 d-af 60-4 f 65-987 d -794 a 6 d 45 d 566
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab FAQ{#audience-lab-faq}

Preguntas más frecuentes sobre la función Audience Lab.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**¿Tienen los segmentos de prueba creados en los grupos de prueba diferentes ID de segmento? How do I map the IDs to different destinations?**

Sí, los segmentos de prueba tienen diferentes ID de segmento. For destinations with [!UICONTROL Auto-fill Destination Mapping] or segments sent to [!DNL Google], [!UICONTROL Audience Lab] will handle the mapping values just like the destinations normally would.

<br> 

**¿Puede asociarse la misma característica de conversión con varios grupos de prueba?**

Sí, esto está permitido. Imagine el caso de una prueba utilizando un segmento masculino asociado a la conversión X y una prueba usando un segmento femenino asociado a la conversión X. No es importante que ambas pruebas produzcan conversiones ya que están probando dos audiencias diferentes.

<br> 

**Supongamos que un grupo de prueba utiliza un perfil autenticado para la división de segmentos de prueba. The authenticated profile is linked to 4[Audience Manager UUIDs](../reference/ids-in-aam.md). When the visitor exhibits a conversion trait from one of the four UUIDs, does[!UICONTROL Audience Lab]count this as one or four conversions?**

In this case, [!UICONTROL Audience Lab] only counts one conversion.

<br> 

**¿Qué sucede si el visitante de arriba muestra el atributo de conversión de uno de los cuatro UUID vinculados a su perfil autenticado y, a continuación, muestra también el rasgo de conversión de otros dos UUID vinculados al perfil autenticado? Does this case count as one or three conversions?**

In this case, [!UICONTROL Audience Lab] counts three conversions, one for each device that has exhibited the authentication trait.

<br> 

**¿Puede un usuario[!UICONTROL Segment: Read-Only]tener acceso, pero[!UICONTROL Audience Lab]también pruebe el acceso a la creación de segmentos?**

See [Create Segment Test Group](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) for information on how to use [!UICONTROL Audience Lab] with [!UICONTROL RBAC] privileges.

**¿Puedo utilizarlo[!UICONTROL Audience Lab]junto con[!UICONTROL Profile Link Device Graph]los gráficos de dispositivos externos ([Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html), Tapad Device Gráfico, Liveramp Device Graph)?**

For now, [!UICONTROL Audience Lab] can only split out segment populations by the devices connected to a qualifying device, when using the [!UICONTROL Profile Link Device Graph]. We are working on adding support in [!UICONTROL Audience Lab] for the other device graphs and will let you know when we do so.
