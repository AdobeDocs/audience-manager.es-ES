---
title: Migración de la extensión de etiqueta de Audience Manager a la extensión de etiqueta del SDK web
description: Comprender los pasos para actualizar su biblioteca de recopilación de datos para Audience Manager desde la extensión Audience Manager etiqueta a la extensión de etiqueta del SDK web
exl-id: 7f0486db-4511-4311-90df-290580fdcd78
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1309'
ht-degree: 0%

---

# Actualice el biblioteca de recopilación de datos para Audience Manager de la extensión etiqueta de Audience Manager a la extensión de etiqueta del SDK web

## Previsto audiencia

Este Página está destinado a Audience Manager clientes que utilizan la extensión[ Audience Manager ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview)etiqueta para poner en Audience Manager datos de colección web. Para los clientes que utilicen el biblioteca de JavaScript AppMeasurement, lea la guía sobre cómo actualizar su biblioteca de recopilación de datos para Audience Manager [desde el biblioteca de JavaScript de AppMeasurement al biblioteca de JavaScript del](appmeasurement-to-web-sdk.md) SDK web.

## Ventajas y desventajas de esta ruta de implementación

El uso de este enfoque de migración tiene ventajas y desventajas. Sopese cuidadosamente cada opción para decidir qué enfoque es mejor para su organización.

| Ventajas | Desventajas |
| --- | --- |
| <ul><li>**No hay cambios de código en el sitio**: Dado que su implementación ya tiene etiquetas instaladas, todas las actualizaciones de migración se pueden realizar en la interfaz de etiquetas.</li><li>**Utiliza sus implementación** existentes: Este enfoque no requiere un nuevo implementación neto. Aunque requiere nuevas acciones regla, puede reutilizar los elementos de datos existentes y regla condiciones con cambios mínimos.</li><li>**No necesita un esquema**: para este fase de migración al SDK web, no necesita un esquema XDM. En su lugar, puede rellenar el `data` objeto, que envía los datos directamente a Adobe Audience Manager. Una vez completada la migración al SDK web, puede crear un esquema para su organización y utilizar la asignación de secuencias de datos para rellenar los campos XDM aplicables. Si se necesitara un esquema en este fase del proceso de migración, su organización se vería obligada a utilizar un esquema XDM Adobe Audience Manager. El uso de este esquema hace que sea más difícil para su organización utilizar sus propios esquema en el futuro.</li></ul> | <ul><li>**Deuda** técnica de implementación: Dado que este enfoque utiliza una forma modificada de su implementación existente, puede ser más difícil rastrear implementación lógica y realizar cambios cuando sea necesario. El código personalizado puede ser particularmente difícil de depurar.</li><li>**Requiere asignación para enviar datos a Platform**: Cuando su organización esté lista para usar CDP en tiempo real, debe enviar datos a un conjunto de datos en Adobe Experience Platform. Esta acción requiere que cada campo del `data` objeto sea una entrada en el herramienta de asignación del flujo de datos que lo asigna a un campo de esquema XDM. Para este flujo de trabajo, el mapeo solo debe realizarse una vez, y no implica realizar cambios implementación. Sin embargo, es un paso adicional que no es necesario al enviar datos en un objeto XDM.</li></ul> |

Adobe Systems recomienda seguir esta ruta de implementación cuando tenga un implementación existente que use la extensión Adobe Audience Manager etiqueta.

## Pasos necesarios para migrar al SDK web

Los siguientes pasos contienen objetivos concretos hacia los que trabajar. Seleccione cada paso para obtener instrucciones detalladas sobre cómo realizarlo.

+++**1. Crear y configurar un flujo de datos**

Siga las instrucciones a continuación para crear un flujo de datos en Adobe Experience Platform recopilación de datos. Cuando envía datos a este flujo de datos, este reenvía datos a Audience Manager. En el futuro, este mismo flujo de datos reenvía datos a CDP en tiempo real.

1. Navegue hasta [experience.adobe.com](https://experience.adobe.com) e inicie sesión con sus credenciales.
1. Utilice el selector página de inicio o producto de la parte superior derecha para desplazarse hasta **[!UICONTROL Data Collection]**.
1. En el navegación izquierdo, seleccione **[!UICONTROL Datastreams]**.
1. Seleccione **[!UICONTROL New Datastream]**.
1. Introduzca el nombre que desee y, a continuación, seleccione **[!UICONTROL Save]**.
1. Una vez creado el flujo de datos, seleccione **[!UICONTROL Add Service]**.
1. En el menú desplegable de servicio, seleccione **[!UICONTROL Adobe Audience Manager]**.
1. Asegúrese de que la **[!UICONTROL Enable XDM Flattened Fields]** opción no esté marcada.

   ![añadir servicio Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

El flujo de datos ya está listo para recibir y pasar datos a Audience Manager.

+++

+++**2. añadir la extensión del SDK web a su Propiedad de etiqueta**

Esta sección prepara su etiqueta para la mayor parte del esfuerzo de migración que tiene lugar en el siguiente paso.

1. Seleccione el icono de hamburguesa en la parte superior izquierda de la interfaz de Adobe Experience Platform y, a continuación, seleccione **[!UICONTROL Tags]**.
1. Seleccione el Propiedad de etiqueta que desee.
1. En la navegación izquierda del Propiedad etiqueta, seleccione **[!UICONTROL Extensions]**.
1. Seleccione **[!UICONTROL Catalog]** cerca de la parte superior para ver una lista de todas las extensiones disponibles.
1. Search extensión y selecciónela **[!UICONTROL Adobe Experience Platform Web SDK]** y, a continuación, seleccione **[!UICONTROL Install]** en el lado derecho.

   ![Catálogo](assets/catalog.png) {style="border:1px solid lightslategray"}

1. Aparecen los ajustes de configuración de la extensión. Busque la **[!UICONTROL Datastreams]** sección y seleccione el entorno de pruebas que está utilizando y el flujo de datos que creó en el paso anterior.

   ![Selección de flujo de datos](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. Seleccione **[!UICONTROL Save]**.

El etiqueta Propiedad ya tiene instalado el SDK web.

+++

+++**3. Crear un elemento de datos de objeto de datos**

El elemento de datos del objeto de datos proporciona una marco de trabajo intuitiva para configurar una carga útil que el SDK web utiliza para enviar a un flujo de datos. La mayoría de las reglas que actualiza en el paso siguiente interactúan con este elemento de datos.

1. En la navegación izquierda de la interfaz de etiquetas, seleccione **[!UICONTROL Data Elements]**.
1. Escoger **[!UICONTROL Add Data Element]**
1. Asigne al elemento de datos la siguiente configuración:
   * **[!UICONTROL Name]**: cualquier cosa que pueda gustar, como &quot;Capa de datos&quot; u &quot;Objeto de datos&quot;
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Data Element Type]**: [!UICONTROL Variable]
   * Las casillas de verificación pueden permanecer como están.
1. En el lado derecho, seleccione la siguiente configuración:
   * botón de radio de la propiedad: **[!UICONTROL Data]**
   * **[!UICONTROL Solution]**: [!UICONTROL Adobe Audience Manager]
1. Seleccione **[!UICONTROL Save]**.

   ![Crear elemento de datos](assets/create-data-element.png) {style="border:1px solid lightslategray"}

Ahora su Propiedad etiqueta tiene todo lo necesario para actualizar cada regla.

+++

+++**4. Actualizar reglas para utilizar la extensión del SDK web en lugar de la extensión de Audience Manager**

Este paso contiene la mayor parte del esfuerzo necesario para migrar al SDK web y requiere conocimiento de cómo funciona su implementación. A continuación se ofrece un ejemplo de cómo editar un regla de etiqueta típico. Actualizar todo etiqueta reglas del implementación reemplazar todas las referencias a la extensión Audience Manager por la extensión del SDK web.

1. En la navegación izquierda de la interfaz de etiquetas, seleccione **[!UICONTROL Rules]**.
1. Seleccione el regla que desea editar.
1. Seleccione la acción **[!UICONTROL Audience Manager - Set Variables]**
1. Tenga en cuenta todas las variables Audience Manager establecidas en este regla. Incluya tanto las variables configuradas en los menús desplegables como las variables configuradas en el código personalizado.
1. Cambie a [!UICONTROL Action Configuration] la siguiente configuración:
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: Actualización variable
1. Asegúrese de que el objeto de datos que creó en el paso 3 está seleccionado en el menú desplegable de la derecha, en el **[!UICONTROL Data element]** campo.
1. Establezca los pares clave-valor Audience Manager en sus mismos valores respectivos que se configuraron en la extensión Audience Manager.
1. Una vez que toda la lógica regla se haya replicado mediante la extensión del SDK web, seleccione **[!UICONTROL Keep Changes]**.
1. Repita estos pasos para cada configuración de acción que utilice la extensión etiqueta de Audience Manager para establecer valores.

Los pasos anteriores solo se aplican a las reglas que establecen valores. Los pasos siguientes reemplazan todas las acciones que utilizan el [!UICONTROL Action Configuration] [!UICONTROL Send Event].

1. Seleccione un regla que envíe un evento de SDK web.
1. Seleccione el tipo **[!UICONTROL Send Event]** de acción.
1. Cambie a [!UICONTROL Action Configuration] la siguiente configuración:
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: [!UICONTROL Send event]
1. A la derecha, cambie la configuración de la acción a lo siguiente:
   * **[!UICONTROL Type]**: Uso **[!UICONTROL Web Webpagedetails Page Views]**.
   * **[!UICONTROL Data]**: Seleccione el objeto de datos que creó en el paso 3.
1. Seleccione **[!UICONTROL Keep Changes]**.
1. Repita estos pasos para cada configuración de acción que utilice Audience Manager para enviar una evento.

+++

+++**5. Publish reglas actualizadas**

Publicación reglas actualizadas siguen la misma flujo de trabajo que cualquier otro cambio en la configuración de etiquetas.

1. En la navegación izquierda de la interfaz de etiquetas, seleccione **[!UICONTROL Publishing Flow]**.
1. Seleccione **[!UICONTROL Add Library]**.
1. Asigne a este etiqueta confirmación un nombre, como &quot;Actualizar a SDK web&quot;.
1. Seleccione **[!UICONTROL Add All Changed Resources]**.
1. Seleccione **[!UICONTROL Save]**.
1. El flujo de trabajo de publicación muestra un punto naranja que indica que se está generando. Una vez que el punto se vuelve verde, los cambios estarán disponibles en su entorno de desarrollo.
1. Pruebe los cambios en el entorno de desarrollo para asegurarse de que todas las reglas se activan correctamente y de que el objeto de datos se rellena con los valores esperados.
1. Cuando esté listo, envíe el biblioteca para su aprobación, versión al ensayo y, finalmente, apruebe y publicar a producción.

   ![Publicación flujo](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. Deshabilitar Audience Manager extensión**

Una vez que el implementación de etiqueta se haya migrado completamente al SDK web, puede desactivar la extensión Audience Manager.

1. En la navegación izquierda de la interfaz de etiquetas, seleccione **[!UICONTROL Extensions]**.
1. Localice y seleccione la [!UICONTROL Audience Manager] extensión. A la derecha, seleccione **[!UICONTROL Disable]**.
1. Siga el mismo flujo de trabajo de publicación anterior para publicar la eliminación de la [!UICONTROL Audience Manager] extensión.
1. Una vez que la extensión esté deshabilitada en producción, puede desinstalarla por completo. Seleccione la extensión, seleccione el menú de tres puntos de la derecha y, a continuación, seleccione .**[!UICONTROL Uninstall]**
1. Siga el mismo flujo de trabajo de publicación anterior para publicar esos cambios a la producción.

+++

En este punto, su implementación Audience Manager se ha migrado completamente al SDK web y está preparado para pasar a CDP en tiempo real en el futuro.
