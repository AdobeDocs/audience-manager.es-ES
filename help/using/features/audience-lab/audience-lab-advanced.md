---
description: Este artículo describe dos funciones que proporcionan funcionalidad avanzada para la plantilla de asignación duplicada de Audience Lab y la retención de segmentos.
seo-description: Este artículo describe dos funciones que proporcionan funcionalidad avanzada para la plantilla de asignación duplicada de Audience Lab y la retención de segmentos.
seo-title: Funcionalidad avanzada de Audience Lab
solution: Audience Manager
title: Funcionalidad avanzada de Audience Lab
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
feature: 'Audience Lab '
exl-id: 40b2c8c2-63c0-485d-8217-beab34d7a7f1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 2%

---

# [!DNL Audience Lab] Funcionalidad avanzada  {#audience-lab-advanced-functionality}

Este artículo describe dos funciones que proporcionan funcionalidad avanzada para [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] y [!DNL Segment Holdout].

## Duplicar plantilla de asignación {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

En [!DNL Audience Lab], [!DNL Allocation Template] representa las distintas selecciones que realiza al crear un grupo de prueba:

* La distribución de dispositivos entre segmentos de prueba;
* La asignación de segmentos de prueba a destinos;
* Los rasgos de conversión que utilice para un grupo de prueba;
* Intervalo de fechas en el que el grupo de prueba publica en los destinos seleccionados.

Al duplicar una plantilla de asignación, puede reutilizar la misma distribución de segmentos de prueba y destinos para un segmento base diferente, en un nuevo grupo de prueba. A continuación se muestra un ejemplo de plantilla de asignación. La imagen se toma del paso [!UICONTROL Summary & Finalize] del flujo de trabajo **Crear grupo de prueba**.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Uso de plantillas de asignación duplicadas

Cree un grupo de prueba inicial y luego seleccione **[!UICONTROL Duplicate Allocation Template]** para reutilizar la misma configuración en varios grupos de prueba. Por ejemplo, puede utilizar esta función si está ejecutando una prueba en la que quiera determinar la eficacia de varios destinos para varios segmentos.

1. En la vista principal de Audience Lab, busque el grupo de prueba cuya plantilla de asignación desee reproducir en un nuevo grupo de prueba. En el cuadro desplegable, seleccione **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. En el asistente [!UICONTROL Create Test Group] puede especificar un segmento base y cambiar el nombre de los segmentos de prueba, si lo desea.
3. *no puede* modificar:

   * La distribución de dispositivos entre segmentos de prueba;
   * Los rasgos de conversión;
   * La asignación de segmentos de prueba a destinos. Solo puede rellenar la clave de asignación para los destinos que la requieran.
   * Intervalo de fechas en el que el grupo de prueba publicará en los destinos seleccionados.

4. Revise la información añadida en los pasos anteriores y seleccione **[!UICONTROL Finalize Group]**.

## Probar resistencia de segmentos {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] es una funcionalidad avanzada que se activa a petición del cliente. Póngase en contacto con [!DNL Customer Care] o [!DNL Adobe Consulting] para activar esta función.

Utilice esta función para impedir que parte de la audiencia se incluya en la prueba. El porcentaje seleccionado se excluye de la prueba. De este modo, puede medir y comparar el número de conversiones de audiencias de destino (activadas en los destinos) y de destino (grupos de exclusión).

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Uso de la Holdout del segmento de prueba

1. Cree un nuevo grupo de prueba utilizando el asistente [!UICONTROL Create Test Group].
1. En el paso **[!UICONTROL Allocate Test Segment]**, puede seleccionar una parte de la audiencia que no debe probar.

   ![Elemento de lista](assets/test-segment-holdout.png)

1. Utilice el control deslizante para ajustar cuántos dispositivos desea mantener fuera de las pruebas. Observe que el segmento de prueba 1 y el segmento de prueba 2 ahora solo representan el 70 % del total de dispositivos.

   ![](assets/test-segment-holdout-selected.png)

1. Siga los demás pasos del flujo de trabajo **[!UICONTROL Create Test Group]** y seleccione **[!UICONTROL Finalize Group]** cuando esté satisfecho con la selección. Ahora tiene un grupo de prueba con parte de la audiencia retenida en la prueba.
