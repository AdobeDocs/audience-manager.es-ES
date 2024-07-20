---
title: Actualice la biblioteca de recopilación de datos para el Audience Manager de la biblioteca JavaScript de AppMeasurement a la biblioteca JavaScript del SDK web.
description: Conozca los pasos para actualizar la biblioteca de recopilación de datos para Audience Manager de la biblioteca JavaScript de AppMeasurement a la biblioteca JavaScript del SDK web.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---

# Actualice la biblioteca de recopilación de datos para el Audience Manager de la biblioteca JavaScript de AppMeasurement a la biblioteca JavaScript del SDK web

## Destinatarios previstos {#intended-audience}

Esta página está destinada a los clientes de Audience Manager que utilizan el AppMeasurement para introducir datos de recopilación web en Audience Manager. Para los clientes que usan la [extensión de Audience Manager](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview), lea la guía sobre cómo actualizar la biblioteca de recopilación de datos para el Audience Manager [desde la extensión de Audience Manager a la extensión de etiqueta del SDK web](dil-extension-to-web-sdk.md).

## Ventajas y desventajas de esta ruta de implementación

El uso de este enfoque de migración tiene ventajas y desventajas. Valore cuidadosamente cada opción para decidir qué enfoque es el mejor para su organización.

| Ventajas | Desventajas |
| --- | --- |
| <ul><li>**Utiliza su implementación existente**: Aunque este enfoque requiere algunos cambios de implementación, no requiere una implementación completamente nueva desde cero. Puede utilizar la capa de datos y el código existentes con cambios mínimos en la lógica de implementación.</li><li>**No requiere un esquema**: Para esta fase de migración al SDK web, no necesita un esquema XDM. En su lugar, puede rellenar el objeto `data`, que envía los datos directamente al Audience Manager. Una vez completada la migración al SDK web, puede crear un esquema para su organización y utilizar la asignación de flujos de datos para rellenar los campos XDM aplicables. Si se requiere un esquema en esta fase del proceso de migración, su organización se vería obligada a utilizar un esquema XDM de Audience Manager. El uso de este esquema dificulta que su organización utilice su propio esquema en el futuro.</li></ul> | <ul><li>**Deuda técnica de la implementación**: dado que este método usa una forma modificada de la implementación existente, puede ser más difícil rastrear la lógica de la implementación y realizar cambios en el futuro cuando sea necesario.</li><li>**Requiere asignación para enviar datos a la plataforma**: cuando su organización esté lista para usar Real-Time CDP, debe enviar datos a un conjunto de datos en Adobe Experience Platform. Esta acción requiere que cada campo del objeto `data` sea una entrada en la herramienta de asignación de secuencia de datos que lo asigne a un campo de esquema XDM. La asignación solo debe realizarse una vez para este flujo de trabajo y no implica realizar cambios de implementación. Sin embargo, es un paso adicional que no es necesario al enviar datos en un objeto XDM.</li></ul> |

El Adobe recomienda seguir esta ruta de implementación en los siguientes casos:

* Tiene una implementación existente de mediante la biblioteca JavaScript de AppMeasurement de Adobe Analytics. Si tiene una implementación que usa la extensión de etiquetas de Audience Manager, siga [Migrar de la extensión de etiquetas de Audience Manager a la extensión de etiquetas del SDK web](dil-extension-to-web-sdk.md) en su lugar.
* Tiene intención de utilizar Real-Time CDP en el futuro, pero no desea reemplazar la implementación de Audience Manager con una implementación de SDK web desde cero. Reemplazar la implementación desde cero en el SDK web requiere el mayor esfuerzo, pero también ofrece la arquitectura de implementación a largo plazo más viable. Si su organización desea realizar el esfuerzo de una implementación limpia del SDK web, consulte la [documentación del SDK web](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) para obtener más información.

## Pasos necesarios para migrar al SDK web

Las siguientes medidas contienen objetivos concretos para alcanzar. Haga clic en cada paso para obtener instrucciones detalladas sobre cómo hacerlo.

+++**1. Crear y configurar una secuencia de datos**

Cree una secuencia de datos en la recopilación de datos de Adobe Experience Platform. Al enviar datos a este conjunto de datos, se reenvían datos al Audience Manager. En el futuro, este mismo conjunto de datos reenviará datos a Real-Time CDP.

1. Vaya a [experience.adobe.com](https://experience.adobe.com) e inicie sesión con sus credenciales.
1. Utilice la página de inicio o el selector de producto en la parte superior derecha para navegar a **[!UICONTROL Data Collection]**.
1. En el panel de navegación izquierdo, seleccione **[!UICONTROL Datastreams]**.
1. Seleccione **[!UICONTROL New Datastream]**.
1. Escriba el nombre que desee y seleccione **[!UICONTROL Save]**.
1. Una vez creada la secuencia de datos, seleccione **[!UICONTROL Add Service]**.
1. En el menú desplegable del servicio, seleccione **[!UICONTROL Audience Manager]**.

   ![Agregar servicio de Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

El conjunto de datos está listo para recibir y pasar datos al Audience Manager. Tenga en cuenta el ID de la secuencia de datos, ya que este ID es necesario al configurar el SDK web en código.

+++

+++**2. Instale la biblioteca JavaScript del SDK web**

Consulte [Instalar el SDK web mediante la biblioteca JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) para obtener información detallada y bloques de código que utilizar. Hacer referencia a la última versión de `alloy.js` para que se puedan usar sus llamadas al método.

+++

+++**3. Configurar el SDK web**

Configure la implementación para que apunte a la secuencia de datos creada en el paso 1 mediante el comando del SDK web [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview). El comando `configure` debe estar establecido en todas las páginas para que pueda incluirlo junto con el código de instalación de la biblioteca.

Use las propiedades [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) y [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) en el comando `configure` del SDK web:

* Establezca `edgeConfigId` en el ID de secuencia de datos recuperado del paso anterior.
* Establezca `orgId` en el ID de organización de IMS de su organización.

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Opcionalmente, puede establecer otras propiedades en el comando [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) en función de los requisitos de implementación de su organización.

+++

+++**4. Actualizar lógica de código para utilizar una carga útil JSON**

Cambie la implementación del Audience Manager para que no dependa de `AppMeasurement.js` ni del objeto `s`. En su lugar, establezca variables en un objeto JavaScript con formato correcto, que se convierte en un objeto JSON cuando se envía al Adobe. Tener una [capa de datos](https://experienceleague.adobe.com/en/docs/analytics/implementation/prepare/data-layer) en el sitio ayuda enormemente a la hora de establecer valores, ya que puede seguir haciendo referencia a esos mismos valores.

Para enviar datos al Audience Manager, la carga del SDK web debe utilizar `data.__adobe.audiencemanager` con todas las variables de análisis establecidas dentro de este objeto. Las variables de este objeto comparten nombres y formatos idénticos a los de sus equivalentes de variables de AppMeasurement. Por ejemplo, si establece la variable `products`, no la divida en objetos individuales como lo haría con XDM. En su lugar, inclúyala como una cadena exactamente como es si establece la variable `s.products`:

```json
{
  "data": {
    "__adobe": {
      "audiencemanager": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

En última instancia, esta carga útil contiene todos los valores deseados y todas las referencias al objeto `s` en su implementación se eliminan. Puede utilizar cualquiera de los recursos que proporciona JavaScript para establecer este objeto de carga útil, incluida la notación de puntos para establecer valores individuales.

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {audiencemanager: {}}}};
dataObj.data.__adobe.audiencemanager.pageName = window.document.title;
dataObj.data.__adobe.audiencemanager.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{audiencemanager:{...a}}}};
```

+++

+++**5. Actualizar las llamadas de método para utilizar el SDK web**

Actualice todas las instancias en las que llame a [`s.t()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/t-method) y [`s.tl()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/tl-method), reemplazándolas por el comando [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview). Hay tres escenarios a considerar:

* **Seguimiento de vista de página**: reemplace la llamada de seguimiento de vista de página con el comando `sendEvent` del SDK web:

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Seguimiento automático de vínculos**: La propiedad de configuración [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) está habilitada de manera predeterminada. Establece automáticamente las variables de seguimiento de vínculos correctas para enviar datos al Audience Manager. Si desea deshabilitar el seguimiento automático de vínculos, establezca esta propiedad en `false` dentro del comando [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview).

* **Seguimiento manual de vínculos**: el SDK web no tiene comandos independientes entre las llamadas a pageview y a las que no son a pageview. Proporcione esa distinción dentro del objeto de carga útil.

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.audiencemanager.linkName = "Example custom link";
  dataObj.data.__adobe.audiencemanager.linkType = "o";
  dataObj.data.__adobe.audiencemanager.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6. Validar y publicar cambios**

Una vez que haya quitado todas las referencias al AppMeasurement y al objeto `s`, publique los cambios en su entorno de desarrollo para validar que la nueva implementación funciona. Una vez que haya validado que todo funciona correctamente, puede publicar las actualizaciones en producción.

Si se migra correctamente, `AppMeasurement.js` ya no será necesario en el sitio y se podrán eliminar todas las referencias a este script.

+++

En este punto, la implementación de Audience Manager se migra completamente al SDK web y está preparado para pasar a Real-Time CDP en el futuro.
