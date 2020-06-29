---
description: Este artículo describe dos funciones que proporcionan funcionalidad avanzada para la plantilla de asignación de Duplicados del laboratorio de Audiencia y la retención de segmentos.
seo-description: Este artículo describe dos funciones que proporcionan funcionalidad avanzada para la plantilla de asignación de Duplicados del laboratorio de Audiencia y la retención de segmentos.
seo-title: Funcionalidad avanzada del laboratorio de Audiencia
solution: Audience Manager
title: Funcionalidad avanzada del laboratorio de Audiencia
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---


# [!DNL Audience Lab] Funcionalidad avanzada {#audience-lab-advanced-functionality}

Este artículo describe dos funciones que proporcionan funcionalidad avanzada para [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] y [!DNL Segment Holdout].

## Plantilla de asignación de Duplicados {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

En [!DNL Audience Lab], [!DNL Allocation Template] representa las distintas selecciones que realiza al crear un grupo de prueba:

* La distribución de dispositivos entre los segmentos de prueba;
* Asignación de segmentos de prueba a destinos;
* Las características de conversión que utiliza para un grupo de prueba;
* Intervalo de fechas en el que el grupo de prueba publica en los destinos seleccionados.

Al duplicar una plantilla de asignación, puede reutilizar la misma distribución de segmentos y destinos de prueba para un segmento base diferente, en un nuevo grupo de prueba. A continuación se muestra un ejemplo de una plantilla de asignación. La imagen se toma del [!UICONTROL Summary & Finalize] paso del flujo de trabajo **Crear grupo** de pruebas.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Uso de la plantilla de asignación de Duplicados

Cree un grupo de prueba inicial y, a continuación, seleccione **[!UICONTROL Duplicate Allocation Template]** para reutilizar la misma configuración en varios grupos de prueba. Por ejemplo, puede utilizar esta función si ejecuta una prueba en la que desea determinar la eficacia de varios destinos para varios segmentos.

1. En la vista principal del laboratorio de Audiencia, busque el grupo de prueba cuya plantilla de asignación desee reproducir en un nuevo grupo de prueba. En el cuadro desplegable, seleccione **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. En el [!UICONTROL Create Test Group] asistente, puede especificar un segmento base y cambiar el nombre de los segmentos de prueba, si lo desea.
3. No *puede* modificar:

   * La distribución de dispositivos entre los segmentos de prueba;
   * Las características de conversión;
   * Asignación de segmentos de prueba a destinos. Solo puede rellenar la clave de asignación para los destinos que la requieran.
   * Intervalo de fechas en el que el grupo de prueba publicará en los destinos seleccionados.

4. Revise la información agregada en los pasos anteriores y seleccione **[!UICONTROL Finalize Group]**.

## Probar retención de segmentos {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] es una funcionalidad avanzada, que se activa a petición del cliente. Póngase en contacto [!DNL Customer Care] o [!DNL Adobe Consulting] para activar esta función.

Utilice esta función para evitar que parte de la audiencia se incluya en la prueba. El porcentaje seleccionado se excluye de la prueba. De este modo, puede medir y comparar el número de conversiones desde audiencias objetivo (activadas en destinos) y sin objetivo (grupos de exclusión).

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Uso de la retención de segmentos de prueba

1. Cree un nuevo grupo de prueba con el [!UICONTROL Create Test Group] asistente.
1. En el **[!UICONTROL Allocate Test Segment]** paso, puede seleccionar una parte de la audiencia que se va a retener de las pruebas.

   ![Elemento de Lista](assets/test-segment-holdout.png)

1. Utilice el control deslizante para ajustar cuántos dispositivos desea mantener fuera de las pruebas. Observe cómo el segmento de prueba 1 y el segmento de prueba 2 ahora solo representan el 70 % del total de dispositivos.

   ![](assets/test-segment-holdout-selected.png)

1. Siga el resto de los pasos del **[!UICONTROL Create Test Group]** flujo de trabajo y selecciónelo **[!UICONTROL Finalize Group]** cuando esté satisfecho con la selección. Ahora tiene un grupo de prueba con una parte de la audiencia retenida de la prueba.
