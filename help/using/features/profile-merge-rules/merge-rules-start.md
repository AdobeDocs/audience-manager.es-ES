---
description: Para crear reglas de combinación de Perfiles, revise y complete los pasos de cada uno de los procedimientos descritos en esta sección.
seo-description: Para crear reglas de combinación de Perfiles, revise y complete los pasos de cada uno de los procedimientos descritos en esta sección.
seo-title: Introducción a las reglas de combinación de Perfiles
solution: Audience Manager
title: Introducción a las reglas de combinación de Perfiles
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: dc22ed98b51b5633532bab45a79a14ee14dba5f5
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 4%

---


# Introducción a las reglas de combinación de Perfiles {#getting-started-with-profile-merge-rules}

Para crear [!UICONTROL Profile Merge Rules], revise y complete los pasos de cada uno de los procedimientos descritos en esta sección.

<!-- merge-rules-start.xml -->

## Crear una fuente de datos entre dispositivos {#create-data-source}

Para crear una fuente de datos entre dispositivos, vaya a **[!UICONTROL Audience Data > Data Sources > Add New]** y complete los pasos para cada sección que se describe aquí. Se necesitan permisos de administrador para crear o editar una fuente de datos entre dispositivos.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Consulte [Configuración de fuente de datos y Opciones de menú](../datasources-list-and-settings.md#settings-menu-options) para obtener descripciones de estos diferentes controles.

## Detalles de la fuente de datos {#details}

Para completar la sección [!UICONTROL Data Source Details]:

1. Asigne un nombre al origen de datos.
2. *(Opcional)* Describa la fuente de datos. Una descripción concisa le ayuda a definir la función o el propósito del origen de datos.
3. Proporcione un código de integración. Un código de integración es su propio ID exclusivo para esta fuente de datos.
4. En la lista **[!UICONTROL ID Type]**, seleccione **[!UICONTROL Cross Device]**.
5. En la lista **[!UICONTROL ID Definition]**, seleccione una opción que defina el tipo de fuente de datos. Las opciones incluyen:
   * **[!UICONTROL Person]**:: ID que define una sola persona. Este ID se puede asignar a varios [!DNL Audience Manager] ID.
   * **[!UICONTROL Household]**:: ID que define un grupo de personas. Este ID se puede asignar a varios [!DNL Audience Manager] ID.

## Controles de exportación de datos {#export-controls}

[Los ](../data-export-controls.md) controles de exportación de datos son reglas de clasificación opcionales que puede aplicar a un origen y destino de datos. Le impiden enviar datos a un destino cuando dicha acción infringe una privacidad de datos o un acuerdo de uso. Omita esta sección si no utiliza [!UICONTROL Data Export Controls].

## Configuración de fuentes de datos {#settings}

[!UICONTROL Data Source Settings] proporciona varias opciones, pero estas dos son importantes para crear una fuente de datos entre dispositivos:

* **[!UICONTROL Use as Authenticated Profile]**:: Seleccionado de forma predeterminada, esta opción le permite crear una  [!UICONTROL Profile Merge Rule] con sus propios datos autenticados.

* **[!UICONTROL Use as a Device Graph]**:: Este control solo está disponible para las cuentas enumeradas como proveedores de datos. Al seleccionar esta casilla de verificación, se crea el origen de datos como un gráfico del dispositivo y se permite compartirlo con otros [!DNL Audience Manager] clientes. Póngase en contacto con su [!DNL Audience Manager] consultor para configurarlo como proveedor de datos y especificar con qué clientes debe compartirse este [!UICONTROL Data Source]. El consultor le proporcionará el uso compartido de gráficos de cuentas y dispositivos a través de un proceso de aprovisionamiento interno.

* **[!UICONTROL Data retention for inactive Customer IDs]**:: Este control le permite establecer el período de retención de datos para los ID de cliente inactivos. Esto determina cuánto tiempo el Audience Manager mantiene los ID de cliente en nuestra base de datos después de que se vieron por última vez en la plataforma Audience Manager. El valor predeterminado es 24 meses (720 días). El valor mínimo que puede establecer es 1 mes y el valor máximo es 5 años. Tenga en cuenta que todos los meses se cuentan como 30 días. Audience Manager ejecuta un proceso que elimina los ID de cliente inactivos una vez a la semana, de acuerdo con la retención de datos que configuró para los ID de cliente inactivos.

Los campos de texto asociados a esta configuración permiten cambiar el nombre de [!UICONTROL Data Source] por un alias que aparece en las opciones [Regla de combinación de Perfiles](merge-rule-definitions.md). Por ejemplo, si agrega un alias a **[!UICONTROL Use as Authenticated Profile]**, ese nombre aparecerá en la lista [!UICONTROL Authenticated Profile Options]. Si agrega un alias a **[!UICONTROL Use as a Device Graph]**, ese nombre aparecerá en la lista [!UICONTROL Device Options].

## Crear una regla de combinación de Perfiles {#create-profile-merge-rule}

Para crear un [!UICONTROL Profile Merge Rule], vaya a **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** y complete los pasos para cada sección que se describe aquí.

Puede crear hasta 3 reglas de combinación después de configurar un origen de datos entre dispositivos. Puede obtener acceso a una cuarta regla de combinación de Perfiles ([!UICONTROL All Cross-Device Profiles]) si se registra para [Destinos basados en personas](../destinations/people-based-destinations-overview.md).

Se necesitan permisos de administrador para crear, editar o eliminar una regla. Todos los usuarios pueden realizar vistas y utilizar [!UICONTROL Profile Merge Rules] existentes.

<!-- create-profile-merge-rule.xml -->

**Requisitos previos:** Se requiere un origen de datos entre dispositivos para crear un  [!UICONTROL Profile Merge Rule]. Consulte [Creación de una fuente de datos](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Consulte [Opciones de regla de combinación de Perfiles Definidas](merge-rule-definitions.md) para obtener descripciones de estos diferentes controles.

## Información básica {#basic-info}

Para completar la sección [!UICONTROL Basic Information]:

1. Asigne un nombre a [!UICONTROL Profile Merge Rule].
2. *(Opcional)* Describa el  [!UICONTROL Profile Merge Rule]. Una descripción concisa le ayuda a definir la función o el propósito de la regla.
3. *(Opcional)* Seleccione  **[!UICONTROL Set as default]** si desea que sea el valor predeterminado  [!UICONTROL Profile Merge Rule]. Los nuevos segmentos se asocian automáticamente con la regla predeterminada.

## Controles de exportación de datos {#data-export-controls}

[Los ](../data-export-controls.md) controles de exportación de datos son reglas de clasificación opcionales que puede aplicar a su  [!UICONTROL Profile Merge Rule]. Le impiden enviar datos a un destino cuando dicha acción infringe una privacidad de datos o un acuerdo de uso. Omita esta sección si no utiliza [!UICONTROL Data Export Controls].

## Configuración de regla de combinación de perfiles {#profile-merge-rule-setup}

Para completar la sección [!UICONTROL Proflie Merge Rule Setup]:

1. Seleccione un **[!UICONTROL Authenticated Option]**. Las opciones incluyen:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Seleccione un **[!UICONTROL Authenticated Profile Option]** (hasta 3, máximo). Son las [fuentes de datos entre dispositivos](merge-rules-start.md) que creó anteriormente.
3. Seleccione una **[!UICONTROL Device Option]**. Las opciones incluyen:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Haga clic **[!UICONTROL Save]**.

### Consideraciones para destinos de Adobe Campaign que utilizan ID entre dispositivos como claves de ID de usuario {#considerations}

A finales de 2019, hemos lanzado una serie de mejoras en las reglas de combinación de Perfiles para mejorar la precisión de los archivos por lotes generados mediante ID entre dispositivos. Estas mejoras se respetarán estrictamente en la instancia de Audience Manager a partir del lunes 16 de marzo de 2020. Por lo tanto, los segmentos asignados a un destino mediante ID de varios dispositivos dejarán de producir exportaciones en algunas configuraciones de reglas de combinación de Perfil.

Para garantizar la integración correcta entre la instancia de Audience Manager y los destinos que utilizan ID entre dispositivos, como Adobe Campaign, asegúrese de cumplir los siguientes requisitos:

1. Revise la regla de combinación de Perfiles utilizada por los segmentos asignados a su destino de ID declarados de Adobe Campaign. La regla de combinación de Perfiles debe utilizar la opción [!UICONTROL Last Authenticated Profile], de modo que todos los perfiles autenticados se puedan incluir en las exportaciones. Si la regla de combinación de Perfiles utiliza una opción diferente, cambie a [!UICONTROL Last Authenticated Profile].
2. Seleccione el origen de datos de ID declarados de Adobe Campaign en la configuración de la regla de combinación de Perfiles.

>[!NOTE]
>
> Si ha alcanzado el número máximo de [!UICONTROL Profile Merge Rules] y necesita ayuda para configurarlas según las instrucciones anteriores, póngase en contacto con el Servicio de atención al cliente.

## Configurar el código de regla de combinación {#configure-merge-rule-code}

Siga estas instrucciones para configurar el código [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL] y [!DNL SDK] móvil para trabajar con las reglas de combinación.

<!-- merge-rules-configure-code.xml -->

### Requisitos previos

Debe configurar una [fuente de datos entre dispositivos](#create-data-source) y [reglas de combinación de perfiles](#create-profile-merge-rule) *antes de* completar estos procedimientos.

## Para clientes de Adobe Experience Platform Identity Service {#id-service-customers}

Se recomienda el [!UICONTROL Adobe Experience Platform Identity Service] y la última versión de [DIL](../../dil/dil-overview.md) al trabajar con [!UICONTROL Profile Merge Rules]. Sin embargo, no es necesario utilizar [!UICONTROL Adobe Experience Platform Identity Service] para trabajar con esta función. Si solo utiliza [!UICONTROL DIL], consulte la sección [DIL heredado](#legacy-dil) a continuación.

### Configuración de la función Definir ID de cliente

Al trabajar con [!UICONTROL Adobe Experience Platform Identity Service], la función `setCustomerIDs` pasa los ID declarados a [!DNL Audience Manager]. Para utilizar una regla de combinación de perfiles, debe modificar `setCustomerIDs` para utilizar el código de integración especificado al crear una fuente de datos entre dispositivos. Por ejemplo, supongamos que ha creado una fuente de datos entre dispositivos con el código de integración `my_datasource_ic`. Para pasar un ID declarado, debe agregar el código de integración a la función de ID de visitante como se muestra en el ejemplo de código modificado que se muestra a continuación.

#### Ejemplo de código genérico

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### Ejemplo de código modificado

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

Para obtener más información, consulte [Creación de una fuente de datos entre dispositivos](#create-data-source) y [ID de clientes y estados de autenticación](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html).

### Configurar la función `DIL.create`

Las últimas versiones de [!UICONTROL DIL] ahora recogen automáticamente el [!UICONTROL declared ID] de la función `visitorService` en `DIL.create` (consulte [Variables de ID declaradas](../declared-ids.md#declared-id-variables)). Compruebe la función `DIL.create` para asegurarse de que está configurada correctamente, como se muestra en el ejemplo de código siguiente.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

En el par clave-valor de Área de nombres, la variable `*`MCORG`*` es su identificador de organización [!DNL Experience Cloud]. Si no tiene este ID, puede encontrarlo en la sección [!UICONTROL Administration] del panel [!DNL Experience Cloud]. Necesita permisos de administrador para vista de este panel. Consulte [Administración: Servicios principales](https://docs.adobe.com/content/help/es-ES/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Configuración de SDK

Consulte la sección [Configurar SDK](#configure-sdks-legacy-dil) a continuación.

## DIL heredado {#legacy-dil}

Si todavía no está usando [!DNL Adobe Experience Platform Identity Service], realmente debe hacerlo. Pero, entendemos que el cambio a un nuevo código requiere de una cuidadosa reflexión y prueba. En estos casos, compruebe la función `DIL.create` para asegurarse de que está configurada correctamente, como se muestra en el ejemplo de código siguiente.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Para obtener más información, consulte la sección [!UICONTROL DIL] heredada en [Variables de ID declaradas](../declared-ids.md#declared-id-variables).

### Configurar SDK {#configure-sdks-legacy-dil}

Compruebe los métodos del código [!DNL SDK] que le permiten pasar [!UICONTROL declared IDs] desde [!DNL Android] y [!DNL iOS] dispositivos móviles. Los nombres de las bibliotecas de códigos [!DNL Android] y [!DNL iOS] son los mismos:

* `dpid`:: ID de origen de datos entre dispositivos.
* `dpuuid`:: El  [!UICONTROL declared ID] (es decir, el ID de usuario).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de dispositivo </th> 
   <th colname="col2" class="entry"> Método </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android  </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Sintaxis:</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>Ejemplo:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS  </b> </p> </td> 
   <td colname="col2"> <p> <code> audienceSetDpid:dpuuid </code> </p> <p> <b>Sintaxis:</b> </p><p>
    <code class="javascript">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </code></p>
    <p> <b>Ejemplo:</b> </p><p>
    <code class="javascript">
      [ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"];
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

Consulte también [Métodos de Audience Manager para Android](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) y [Métodos de Audience Manager para iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Crear una fuente de datos](../manage-datasources.md#create-data-source)

