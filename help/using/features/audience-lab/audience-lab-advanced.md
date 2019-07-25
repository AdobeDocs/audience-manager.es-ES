---
description: Este artículo describe dos funciones que proporcionan funcionalidad avanzada para la plantilla de asignación duplicada de Audience Lab y el segmento Holandés.
seo-description: Este artículo describe dos funciones que proporcionan funcionalidad avanzada para la plantilla de asignación duplicada de Audience Lab y el segmento Holandés.
seo-title: Funcionalidad avanzada de Audience Lab
solution: Audience Manager
title: Funcionalidad avanzada de Audience Lab
uuid: 0 f 57 d 634-caa 0-40 da -81 a 2-c 23 fbd 299 bfd
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# [!DNL Audience Lab] Funcionalidad avanzada {#audience-lab-advanced-functionality}

This article describes two features which provide advanced functionality for [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] and [!DNL Segment Holdout].

## Duplicate Allocation Template {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

In [!DNL Audience Lab], the [!DNL Allocation Template] represents the various selections you make when creating a test group:

* Distribución de dispositivos entre segmentos de prueba;
* Asignación de segmentos de prueba a destinos;
* Los rasgos de conversión que utiliza para un grupo de prueba;
* Intervalo de fechas en el que el grupo de prueba publica en los destinos seleccionados.

Al duplicar una plantilla de asignación, puede reutilizar la misma distribución de segmentos de prueba y destinos para un segmento base diferente, en un nuevo grupo de prueba. A continuación se muestra un ejemplo de una plantilla de asignación. The image is taken from the [!UICONTROL Summary & Finalize] step in the **Create Test Group** workflow.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Uso de la plantilla de asignación duplicada

Create an initial test group, then select **[!UICONTROL Duplicate Allocation Template]** to reuse the same settings across multiple test groups. Por ejemplo, puede utilizar esta función si está ejecutando una prueba en la que desea determinar la eficacia de varios destinos para varios segmentos.

1. En la vista principal de Audience Lab, busque el grupo de prueba cuya plantilla de asignación desee reproducir en un nuevo grupo de prueba. In the drop-down box, select **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. In the [!UICONTROL Create Test Group] wizard, you can specify a base segment and rename your test segments, if you wish.
3. *No* puede modificar:

   * Distribución de dispositivos entre segmentos de prueba;
   * Características de conversión;
   * Asignación de segmentos de prueba a destinos. Solo puede rellenar la clave de asignación para los destinos que requieren uno.
   * Intervalo de fechas en el que el grupo de prueba publicará en los destinos seleccionados.

4. Review the information you added in the previous steps and select **[!UICONTROL Finalize Group]**.

## Test Segment Holdout {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] es una funcionalidad avanzada, activada en la solicitud de cliente. Please contact [!DNL Customer Care] or [!DNL Adobe Consulting] to activate this feature.

Utilice esta función para evitar que parte de la audiencia se incluya en la prueba. El porcentaje que seleccione se deja fuera de la prueba. De este modo, puede medir y comparar el número de conversiones de target (activado en destinos) y audiencias sin objetivo (grupo de holdout).

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Uso del segmento de prueba Holdout

1. Create a new test group by using the [!UICONTROL Create Test Group] wizard.
1. In the **[!UICONTROL Allocate Test Segment]** step, you can select a part of the audience to be withheld from testing.

   ![Elemento de lista](assets/test-segment-holdout.png)

1. Use el control deslizante para ajustar cuántos dispositivos desea eliminar. Observe cómo el segmento Prueba 1 y el Segmento de prueba 2 ahora solo representan el 70% del total de dispositivos.

   ![](assets/test-segment-holdout-selected.png)

1. Go through the rest of the steps in the **[!UICONTROL Create Test Group]** workflow and select **[!UICONTROL Finalize Group]** when you're satisfied with your selection. Ahora tiene un grupo de prueba con parte de la audiencia que se elimina de las pruebas.
