---
title: Actualice la biblioteca de recopilación de datos para el Audience Manager de la biblioteca JavaScript de AppMeasurement a la biblioteca JavaScript del SDK web.
description: Conozca los pasos para actualizar la biblioteca de recopilación de datos para Audience Manager de la biblioteca JavaScript de AppMeasurement a la biblioteca JavaScript del SDK web.
source-git-commit: b0c35d79a07b481e332ddf8f4aedab5484416a51
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---


# Actualice la biblioteca de recopilación de datos para Audience Manager de la biblioteca JavaScript de AppMeasurement a la biblioteca JavaScript del SDK web

## Destinatarios previstos {#intended-audience}

Esta página está destinada a los clientes de Audience Manager que utilizan el AppMeasurement para introducir datos de recopilación web en Audience Manager. Para clientes que utilizan [Extensión de etiquetas de Audience Manager](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview), lea la guía sobre cómo actualizar la biblioteca de recopilación de datos para Audience Manager [de la extensión de etiqueta Audience Manager a la extensión de etiqueta SDK web](dil-extension-to-web-sdk.md).

## Ventajas y desventajas de esta ruta de implementación

El uso de este enfoque de migración tiene ventajas y desventajas. Valore cuidadosamente cada opción para decidir qué enfoque es el mejor para su organización.

| Ventajas | Desventajas |
| --- | --- |
| <ul><li>**Utiliza la implementación existente**: Aunque este enfoque requiere algunos cambios de implementación, no requiere una implementación completamente nueva desde cero. Puede utilizar la capa de datos y el código existentes con cambios mínimos en la lógica de implementación.</li><li>**No requiere un esquema**: para esta fase de migración al SDK web, no necesita un esquema XDM. En su lugar, puede rellenar la variable `data` , que envía los datos directamente al Audience Manager. Una vez completada la migración al SDK web, puede crear un esquema para su organización y utilizar la asignación de flujos de datos para rellenar los campos XDM aplicables. Si se requiere un esquema en esta fase del proceso de migración, su organización se vería obligada a utilizar un esquema XDM de Audience Manager. El uso de este esquema dificulta que su organización utilice su propio esquema en el futuro.</li></ul> | <ul><li>**Deuda técnica de ejecución**: Dado que este método utiliza una forma modificada de la implementación existente, puede resultar más difícil rastrear la lógica de implementación y realizar cambios en el futuro cuando sea necesario.</li><li>**Requiere asignación para enviar datos a Platform**: Cuando su organización esté lista para utilizar Real-Time CDP, debe enviar datos a un conjunto de datos en Adobe Experience Platform. Esta acción requiere que todos los campos del `data` El objeto debe ser una entrada en la herramienta de asignación de flujos de datos que lo asigne a un campo de esquema XDM. La asignación solo debe realizarse una vez para este flujo de trabajo y no implica realizar cambios de implementación. Sin embargo, es un paso adicional que no es necesario al enviar datos en un objeto XDM.</li></ul> |

El Adobe recomienda seguir esta ruta de implementación en los siguientes casos:

* Tiene una implementación existente de mediante la biblioteca JavaScript del AppMeasurement de Adobe Analytics. Si tiene una implementación con la extensión de etiquetas Audience Manager, siga [Migrar de la extensión de etiqueta de Audience Manager a la extensión de etiqueta del SDK web](dil-extension-to-web-sdk.md) en su lugar.
* Tiene intención de utilizar Real-Time CDP en el futuro, pero no desea reemplazar la implementación de Audience Manager con una implementación de SDK web desde cero. Reemplazar la implementación desde cero en el SDK web requiere el mayor esfuerzo, pero también ofrece la arquitectura de implementación a largo plazo más viable. Si su organización está dispuesta a realizar el esfuerzo de una implementación limpia del SDK web, consulte la [Documentación del SDK web](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) para obtener más información.

## Pasos necesarios para migrar al SDK web

Las siguientes medidas contienen objetivos concretos para alcanzar. Haga clic en cada paso para obtener instrucciones detalladas sobre cómo hacerlo.

+++**1. Creación y configuración de una secuencia de datos**

Cree una secuencia de datos en la recopilación de datos de Adobe Experience Platform. Al enviar datos a este conjunto de datos, se reenvían datos al Audience Manager. En el futuro, este mismo conjunto de datos reenviará datos a Real-Time CDP.

1. Vaya a [experience.adobe.com](https://experience.adobe.com) e inicie sesión con sus credenciales.
1. Utilice la página de inicio o el selector de productos en la parte superior derecha para desplazarse a **[!UICONTROL Data Collection]**.
1. En el panel de navegación izquierdo, seleccione **[!UICONTROL Datastreams]**.
1. Seleccionar **[!UICONTROL New Datastream]**.
1. Introduzca el nombre que desee y seleccione **[!UICONTROL Save]**.
1. Una vez creada la secuencia de datos, seleccione **[!UICONTROL Add Service]**.
1. En el menú desplegable del servicio, seleccione **[!UICONTROL Audience Manager]**.

   ![Añadir servicio de Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

El conjunto de datos está listo para recibir y pasar datos al Audience Manager. Tenga en cuenta el ID de la secuencia de datos, ya que este ID es necesario al configurar el SDK web en código.

+++

+++**2. Instalación de la biblioteca JavaScript del SDK web**

Consulte [Instalación del SDK web mediante la biblioteca JavaScript de](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) para obtener detalles y bloques de código que utilizar. Consulte la última versión de `alloy.js` por lo tanto, se pueden utilizar sus llamadas al método.

+++

+++**3. Configuración del SDK web**

Configure la implementación para que apunte al conjunto de datos creado en el paso 1 mediante el SDK web [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) comando. El `configure` El comando debe configurarse en cada página para que pueda incluirse junto con el código de instalación de la biblioteca.

Utilice el [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) y [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) propiedades dentro del SDK web `configure` comando:

* Configure las variables `edgeConfigId` al ID de la secuencia de datos recuperado del paso anterior.
* Configure las variables `orgId` al ID de organización de IMS de su organización.

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Si lo desea, puede definir otras propiedades en la variable [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) en función de los requisitos de implementación de su organización.

+++

+++**4. Actualizar la lógica de código para utilizar una carga útil JSON**

Cambie la implementación de Audience Manager para que no dependa de lo siguiente `AppMeasurement.js` o el `s` objeto. En su lugar, establezca variables en un objeto JavaScript con formato correcto, que se convierte en un objeto JSON cuando se envía al Adobe. Tener un [capa de datos](https://experienceleague.adobe.com/en/docs/analytics/implementation/prepare/data-layer) en su sitio ayuda enormemente a la hora de configurar valores, ya que puede seguir haciendo referencia a esos mismos valores.

Para enviar datos al Audience Manager, la carga útil del SDK web debe utilizar `data.__adobe.audiencemanager` con todas las variables de analytics establecidas dentro de este objeto. Las variables de este objeto comparten nombres y formatos idénticos a los de sus equivalentes de variables de AppMeasurement. Por ejemplo, si establece la variable `products` , no lo divida en objetos individuales como lo haría con XDM. En su lugar, inclúyala como una cadena exactamente como es si establece el valor `s.products` variable:

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

En última instancia, esta carga útil contiene todos los valores deseados y todas las referencias a `s` en la implementación se han eliminado. Puede utilizar cualquiera de los recursos que proporciona JavaScript para establecer este objeto de carga útil, incluida la notación de puntos para establecer valores individuales.

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

Actualice todas las instancias en las que llame a [`s.t()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/t-method) y [`s.tl()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/tl-method), sustituyéndolos por el [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) comando. Hay tres escenarios a considerar:

* **Seguimiento de vista de página**: Reemplace la llamada de seguimiento de vista de página con el SDK web `sendEvent` comando:

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Seguimiento automático de vínculos**: La [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) La propiedad de configuración de está habilitada de forma predeterminada. Establece automáticamente las variables de seguimiento de vínculos correctas para enviar datos al Audience Manager. Si desea deshabilitar el seguimiento automático de vínculos, establezca esta propiedad como `false` dentro de [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) comando.

* **Seguimiento manual de vínculos**: el SDK web no tiene comandos independientes entre las llamadas a la vista de página y a las que no son de vista de página. Proporcione esa distinción dentro del objeto de carga útil.

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

+++**6. Validación y publicación de cambios**

Una vez que haya eliminado todas las referencias a AppMeasurement y a `s` , publique los cambios en el entorno de desarrollo para validar que la nueva implementación funciona. Una vez que haya validado que todo funciona correctamente, puede publicar las actualizaciones en producción.

Si se migra correctamente, `AppMeasurement.js` ya no es necesaria en el sitio y se pueden eliminar todas las referencias a esta secuencia de comandos.

+++

En este punto, la implementación de Audience Manager se migra completamente al SDK web y está preparado para pasar a Real-Time CDP en el futuro.
