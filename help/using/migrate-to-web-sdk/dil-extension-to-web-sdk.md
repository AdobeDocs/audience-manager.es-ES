---
title: Migrar de la extensión de etiqueta de Audience Manager a la extensión de etiqueta del SDK web
description: Conozca los pasos para actualizar la biblioteca de recopilación de datos para Audience Manager desde la extensión de etiquetas Audience Manager a la extensión de etiquetas SDK web
exl-id: 7f0486db-4511-4311-90df-290580fdcd78
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1309'
ht-degree: 0%

---

# Actualice la biblioteca de recopilación de datos para el Audience Manager de la extensión de etiqueta de Audience Manager a la extensión de etiqueta del SDK web

## Destinatarios previstos

Esta página está destinada a los clientes de Audience Manager que utilizan la [extensión de Audience Manager](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/audience-manager/overview) para llevar los datos de recopilación web a Audience Manager. Para los clientes que utilizan la biblioteca JavaScript de AppMeasurement, lea la guía sobre cómo actualizar la biblioteca de recopilación de datos para el Audience Manager [de la biblioteca JavaScript de AppMeasurement a la biblioteca JavaScript del SDK web](appmeasurement-to-web-sdk.md).

## Ventajas y desventajas de esta ruta de implementación

El uso de este enfoque de migración tiene ventajas y desventajas. Valore cuidadosamente cada opción para decidir qué enfoque es el mejor para su organización.

| Ventajas | Desventajas |
| --- | --- |
| <ul><li>**No hay cambios de código en su sitio**: Debido a que su implementación ya tiene etiquetas instaladas, todas las actualizaciones de migración se pueden realizar en la interfaz de etiquetas.</li><li>**Utiliza su implementación existente**: Este enfoque no requiere una implementación nueva. Aunque sí requiere nuevas acciones de regla, puede reutilizar los elementos de datos y las condiciones de regla existentes con cambios mínimos.</li><li>**No requiere un esquema**: Para esta fase de migración al SDK web, no necesita un esquema XDM. En su lugar, puede rellenar el objeto `data`, que envía datos directamente a Adobe Audience Manager. Una vez completada la migración al SDK web, puede crear un esquema para su organización y utilizar la asignación de flujos de datos para rellenar los campos XDM aplicables. Si se requiere un esquema en esta fase del proceso de migración, su organización se vería obligada a utilizar un esquema XDM de Adobe Audience Manager. El uso de este esquema dificulta que su organización utilice su propio esquema en el futuro.</li></ul> | <ul><li>**Deuda técnica de la implementación**: dado que este método usa una forma modificada de la implementación existente, puede ser más difícil rastrear la lógica de la implementación y realizar cambios cuando sea necesario. El código personalizado puede ser especialmente difícil de depurar.</li><li>**Requiere asignación para enviar datos a la plataforma**: cuando su organización esté lista para usar Real-Time CDP, debe enviar datos a un conjunto de datos en Adobe Experience Platform. Esta acción requiere que cada campo del objeto `data` sea una entrada en la herramienta de asignación de secuencia de datos que lo asigne a un campo de esquema XDM. La asignación solo debe realizarse una vez para este flujo de trabajo y no implica realizar cambios de implementación. Sin embargo, es un paso adicional que no es necesario al enviar datos en un objeto XDM.</li></ul> |

El Adobe recomienda seguir esta ruta de implementación cuando tenga una implementación existente con la extensión de etiquetas de Adobe Audience Manager.

## Pasos necesarios para migrar al SDK web

Las siguientes medidas contienen objetivos concretos para alcanzar. Seleccione cada paso para obtener instrucciones detalladas sobre cómo realizarlo.

+++**1. Crear y configurar una secuencia de datos**

Siga las instrucciones siguientes para crear un conjunto de datos en la recopilación de datos de Adobe Experience Platform. Al enviar datos a este conjunto de datos, se reenvían datos al Audience Manager. En el futuro, este mismo conjunto de datos reenviará datos a Real-Time CDP.

1. Vaya a [experience.adobe.com](https://experience.adobe.com) e inicie sesión con sus credenciales.
1. Utilice la página de inicio o el selector de producto en la parte superior derecha para navegar a **[!UICONTROL Data Collection]**.
1. En el panel de navegación izquierdo, seleccione **[!UICONTROL Datastreams]**.
1. Seleccione **[!UICONTROL New Datastream]**.
1. Escriba el nombre que desee y seleccione **[!UICONTROL Save]**.
1. Una vez creada la secuencia de datos, seleccione **[!UICONTROL Add Service]**.
1. En el menú desplegable del servicio, seleccione **[!UICONTROL Adobe Audience Manager]**.
1. Asegúrese de que la opción **[!UICONTROL Enable XDM Flattened Fields]** esté desmarcada.

   ![Agregar servicio de Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

El conjunto de datos está listo para recibir y pasar datos al Audience Manager.

+++

+++**2. Agregue la extensión del SDK web a la propiedad de etiquetas**

Esta sección prepara la etiqueta para el grueso del esfuerzo de migración que se produce en el siguiente paso.

1. Seleccione el ícono de hamburguesa en la parte superior izquierda de la interfaz de Adobe Experience Platform y luego seleccione **[!UICONTROL Tags]**.
1. Seleccione la propiedad de etiquetas que desee.
1. En el panel de navegación izquierdo de la propiedad de etiquetas, seleccione **[!UICONTROL Extensions]**.
1. Seleccione **[!UICONTROL Catalog]** cerca de la parte superior para ver una lista de todas las extensiones disponibles.
1. Busque y seleccione la extensión **[!UICONTROL Adobe Experience Platform Web SDK]**, luego seleccione **[!UICONTROL Install]** a la derecha.

   ![Catálogo](assets/catalog.png) {style="border:1px solid lightslategray"}

1. Aparecerán los ajustes de configuración de la extensión. Busque la sección **[!UICONTROL Datastreams]** y seleccione la zona protegida que está utilizando y la secuencia de datos que creó en el paso anterior.

   ![Selección de secuencia de datos](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. Seleccione **[!UICONTROL Save]**.

La propiedad de etiquetas ahora tiene instalado el SDK web.

+++

+++**3. Crear un elemento de datos de objeto de datos**

El elemento de datos del objeto de datos proporciona un marco de trabajo intuitivo para configurar una carga útil que el SDK web utiliza para enviar a un conjunto de datos. La mayoría de las reglas que actualiza en el siguiente paso interactúan con este elemento de datos.

1. En la navegación izquierda de la interfaz de etiquetas, seleccione **[!UICONTROL Data Elements]**.
1. Seleccionar **[!UICONTROL Add Data Element]**
1. Asigne al elemento de datos la siguiente configuración:
   * **[!UICONTROL Name]**: cualquier cosa que desee, como &quot;Capa de datos&quot; u &quot;Objeto de datos&quot;
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Data Element Type]**: [!UICONTROL Variable]
   * Las casillas de verificación pueden permanecer tal cual.
1. En el lado derecho, seleccione la siguiente configuración:
   * Botón de opción Propiedad: **[!UICONTROL Data]**
   * **[!UICONTROL Solution]**: [!UICONTROL Adobe Audience Manager]
1. Seleccione **[!UICONTROL Save]**.

   ![Crear elemento de datos](assets/create-data-element.png) {style="border:1px solid lightslategray"}

La propiedad de etiquetas ahora tiene todo lo necesario para actualizar cada regla.

+++

+++**4. Actualice las reglas para utilizar la extensión del SDK web en lugar de la extensión del Audience Manager**

Este paso supone la mayor parte del esfuerzo necesario para migrar al SDK web y requiere conocer cómo funciona la implementación. A continuación se proporciona un ejemplo de cómo editar una regla de etiqueta típica. Actualice todas las reglas de etiquetas de la implementación para reemplazar todas las referencias a la extensión de Audience Manager con la extensión del SDK web.

1. En la navegación izquierda de la interfaz de etiquetas, seleccione **[!UICONTROL Rules]**.
1. Seleccione una regla para editarla.
1. Seleccione la acción **[!UICONTROL Audience Manager - Set Variables]**
1. Tenga en cuenta todas las variables de Audience Manager configuradas dentro de esta regla. Incluya ambas variables establecidas en los menús desplegables y las variables establecidas dentro del código personalizado.
1. Cambie [!UICONTROL Action Configuration] a la siguiente configuración:
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: actualizar variable
1. Asegúrese de que el objeto de datos que creó en el paso 3 esté seleccionado en la lista desplegable de la derecha, en el campo **[!UICONTROL Data element]**.
1. Establezca los pares de clave-valor del Audience Manager en sus mismos valores respectivos tal y como se configuraron en la extensión del Audience Manager.
1. Una vez replicada toda la lógica de reglas mediante la extensión del SDK web, seleccione **[!UICONTROL Keep Changes]**.
1. Repita estos pasos para cada configuración de acción que utilice la extensión de etiqueta Audience Manager para establecer valores.

Los pasos anteriores solo se aplican a las reglas que establecen valores. Los pasos siguientes reemplazan todas las acciones que usan [!UICONTROL Action Configuration] [!UICONTROL Send Event].

1. Seleccione una regla que envíe un evento de SDK web.
1. Seleccione el tipo de acción **[!UICONTROL Send Event]**.
1. Cambie [!UICONTROL Action Configuration] a la siguiente configuración:
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: [!UICONTROL Send event]
1. A la derecha, cambie la configuración de la acción a lo siguiente:
   * **[!UICONTROL Type]**: use **[!UICONTROL Web Webpagedetails Page Views]**.
   * **[!UICONTROL Data]**: seleccione el objeto de datos que creó en el paso 3.
1. Seleccione **[!UICONTROL Keep Changes]**.
1. Repita estos pasos para cada configuración de acción que utilice Audience Manager para enviar un evento.

+++

+++**5. Publish actualizó las reglas**

La publicación de reglas actualizadas sigue el mismo flujo de trabajo que cualquier otro cambio en la configuración de las etiquetas.

1. En la navegación izquierda de la interfaz de etiquetas, seleccione **[!UICONTROL Publishing Flow]**.
1. Seleccione **[!UICONTROL Add Library]**.
1. Asigne un nombre a esta confirmación de etiqueta, como &quot;Actualizar al SDK web&quot;.
1. Seleccione **[!UICONTROL Add All Changed Resources]**.
1. Seleccione **[!UICONTROL Save]**.
1. El flujo de trabajo de publicación muestra un punto naranja que indica que se está generando. Una vez que el punto se vuelva verde, los cambios estarán disponibles en el entorno de desarrollo.
1. Pruebe los cambios en el entorno de desarrollo para asegurarse de que todas las reglas se activan correctamente y de que el objeto de datos se rellena con los valores esperados.
1. Cuando esté listo, envíe la biblioteca para su aprobación, créela al entorno de ensayo y, finalmente, apruebe y publique en producción.

   ![Flujo de publicación](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. Deshabilitar extensión de Audience Manager**

Una vez que la implementación de etiquetas haya migrado completamente al SDK web, puede desactivar la extensión de Audience Manager.

1. En la navegación izquierda de la interfaz de etiquetas, seleccione **[!UICONTROL Extensions]**.
1. Busque y seleccione la extensión [!UICONTROL Audience Manager]. A la derecha, seleccione **[!UICONTROL Disable]**.
1. Siga el mismo flujo de trabajo de publicación anterior para publicar la eliminación de la extensión [!UICONTROL Audience Manager].
1. Una vez que la extensión esté desactivada en producción, puede desinstalarla por completo. Seleccione la extensión, seleccione el menú de tres puntos a la derecha y, a continuación, seleccione **[!UICONTROL Uninstall]**.
1. Siga el mismo flujo de trabajo de publicación anterior para publicar esos cambios en producción.

+++

En este punto, la implementación de Audience Manager se migra completamente al SDK web y está preparado para pasar a Real-Time CDP en el futuro.
