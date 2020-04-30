---
description: Para crear reglas de combinación de Perfiles, revise y complete los pasos de cada uno de los procedimientos descritos en esta sección.
seo-description: Para crear reglas de combinación de Perfiles, revise y complete los pasos de cada uno de los procedimientos descritos en esta sección.
seo-title: Introducción a las reglas de combinación de Perfiles
solution: Audience Manager
title: Introducción a las reglas de combinación de Perfiles
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Introducción a las reglas de combinación de Perfiles {#getting-started-with-profile-merge-rules}

Para crear [!UICONTROL Profile Merge Rules], revise y complete los pasos de cada uno de los procedimientos descritos en esta sección.

<!-- merge-rules-start.xml -->

## Creación de una fuente de datos entre dispositivos {#create-data-source}

Para crear una fuente de datos entre dispositivos, vaya a **[!UICONTROL Audience Data > Data Sources > Add New]** y complete los pasos de cada sección que se describe aquí. Se necesitan permisos de administrador para crear o editar una fuente de datos entre dispositivos.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Consulte Configuración [de fuente de datos y Opciones](../datasources-list-and-settings.md#settings-menu-options) de menú para obtener descripciones de estos diferentes controles.

## Detalles de la fuente de datos {#details}

Para completar la [!UICONTROL Data Source Details] sección:

1. Asigne un nombre al origen de datos.
2. *(Opcional)* Describa la fuente de datos. Una descripción concisa le ayuda a definir la función o el propósito del origen de datos.
3. Proporcione un código de integración. Un código de integración es su propio ID exclusivo para esta fuente de datos.
4. En la **[!UICONTROL ID Type]** lista, seleccione **[!UICONTROL Cross Device]**.
5. En la **[!UICONTROL ID Definition]** lista, seleccione una opción que defina el tipo de fuente de datos. Las opciones incluyen:
   * **[!UICONTROL Person]**:: ID que define una sola persona. Este ID se puede asignar a varios [!DNL Audience Manager] ID.
   * **[!UICONTROL Household]**:: ID que define un grupo de personas. Este ID se puede asignar a varios [!DNL Audience Manager] ID.

## Controles de exportación de datos {#export-controls}

[Los controles](../data-export-controls.md) de exportación de datos son reglas de clasificación opcionales que se pueden aplicar a un origen y destino de datos. Le impiden enviar datos a un destino cuando dicha acción infringe una privacidad de datos o un acuerdo de uso. Omita esta sección si no utiliza [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

[!UICONTROL Data Source Settings] proporciona varias opciones, pero estas dos son importantes para crear una fuente de datos entre dispositivos:

* **[!UICONTROL Use as Authenticated Profile]**:: Seleccionado de forma predeterminada, esta opción le permite crear un [!UICONTROL Profile Merge Rule] con sus propios datos autenticados.

* **[!UICONTROL Use as a Device Graph]**:: Este control solo está disponible para las cuentas enumeradas como proveedores de datos. Al seleccionar esta casilla de verificación, se crea el origen de datos como un gráfico del dispositivo y se permite compartirlo con otros [!DNL Audience Manager] clientes. Póngase en contacto con su [!DNL Audience Manager] consultor para configurarlo como proveedor de datos y especificar con qué clientes se debe compartir esta información [!UICONTROL Data Source] . El consultor le proporcionará el uso compartido de gráficos de cuentas y dispositivos a través de un proceso de aprovisionamiento interno.

* **[!UICONTROL Data retention for inactive Customer IDs]**:: Este control le permite establecer el período de retención de datos para los ID de cliente inactivos. Esto determina durante cuánto tiempo el Administrador de Audiencias mantiene los ID de cliente en nuestra base de datos después de la última vez que se vieron en la plataforma del Administrador de Audiencias. El valor predeterminado es 24 meses (720 días). El valor mínimo que puede establecer es 1 mes y el valor máximo es 5 años. Tenga en cuenta que todos los meses se cuentan como 30 días. El Administrador de Audiencias ejecuta un proceso que elimina los ID de cliente inactivos una vez a la semana, de acuerdo con la retención de datos configurada para los ID de cliente inactivos.

Los campos de texto asociados a esta configuración permiten cambiar el nombre del [!UICONTROL Data Source] objeto por un alias que aparece en las opciones [Regla de combinación de](merge-rule-definitions.md)Perfiles. Por ejemplo, si agrega un alias a **[!UICONTROL Use as Authenticated Profile]**, ese nombre aparecerá en la [!UICONTROL Authenticated Profile Options] lista. Si agrega un alias a **[!UICONTROL Use as a Device Graph]**, ese nombre aparecerá en la [!UICONTROL Device Options] lista.

## Creación de una regla de combinación de Perfiles {#create-profile-merge-rule}

Para crear un [!UICONTROL Profile Merge Rule], vaya a **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** y complete los pasos de cada sección que se describe aquí.

Puede crear hasta 3 reglas de combinación después de configurar un origen de datos entre dispositivos. Puede acceder a una cuarta regla de combinación de Perfiles ([!UICONTROL All Cross-Device Profiles]) si se registra en Destinos [basados en](../destinations/people-based-destinations-overview.md)personas.

Se necesitan permisos de administrador para crear, editar o eliminar una regla. Todos los usuarios pueden realizar vistas y utilizar los datos existentes [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**Requisitos previos:** Se requiere un origen de datos entre dispositivos para crear un [!UICONTROL Profile Merge Rule]. Consulte [Creación de una fuente](../manage-datasources.md#create-data-source)de datos.

>[!TIP]
>
>Consulte Opciones de regla de combinación de [Perfiles Definidas](merge-rule-definitions.md) para obtener descripciones de estos diferentes controles.

## Información básica {#basic-info}

Para completar la [!UICONTROL Basic Information] sección:

1. Asigne un nombre al [!UICONTROL Profile Merge Rule].
2. *(Opcional)* Describa el [!UICONTROL Profile Merge Rule]. Una descripción concisa le ayuda a definir la función o el propósito de la regla.
3. *(Opcional)* Seleccione **[!UICONTROL Set as default]** si desea que sea el valor predeterminado [!UICONTROL Profile Merge Rule]. Los nuevos segmentos se asocian automáticamente con la regla predeterminada.

## Controles de exportación de datos {#data-export-controls}

[Los controles](../data-export-controls.md) de exportación de datos son reglas de clasificación opcionales que puede aplicar a su [!UICONTROL Profile Merge Rule]. Le impiden enviar datos a un destino cuando dicha acción infringe una privacidad de datos o un acuerdo de uso. Omita esta sección si no utiliza [!UICONTROL Data Export Controls].

## Configuración de regla de combinación de Perfiles {#profile-merge-rule-setup}

Para completar la [!UICONTROL Proflie Merge Rule Setup] sección:

1. Seleccione un **[!UICONTROL Authenticated Option]**. Las opciones incluyen:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Seleccione un **[!UICONTROL Authenticated Profile Option]** (hasta 3, máximo). Son las fuentes [](merge-rules-start.md) de datos entre dispositivos que ha creado anteriormente.
3. Seleccione una **[!UICONTROL Device Option]**. Las opciones incluyen:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Haga clic **[!UICONTROL Save]**.

## Configurar código de regla de combinación {#configure-merge-rule-code}

Siga estas instrucciones para configurar el código [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL]y [!DNL SDK] móvil para que funcione con las reglas de combinación.

<!-- merge-rules-configure-code.xml -->

### Requisitos previos

Debe configurar un origen [de datos](#create-data-source) entre dispositivos y reglas [de combinación de](#create-profile-merge-rule) perfiles *antes* de completar estos procedimientos.

## Para clientes del servicio de identidad de Adobe Experience Platform {#id-service-customers}

Se recomiendan la versión [!UICONTROL Adobe Experience Platform Identity Service] y la última versión de [DIL](../../dil/dil-overview.md) al trabajar con [!UICONTROL Profile Merge Rules]. Sin embargo, no es necesario usar el [!UICONTROL Adobe Experience Platform Identity Service] para trabajar con esta función. Si solo utiliza [!UICONTROL DIL], consulte la sección [DIL](#legacy-dil) heredada a continuación.

### Configuración de la función Definir ID de cliente

Al trabajar con el [!UICONTROL Adobe Experience Platform Identity Service], la `setCustomerIDs` función pasa los ID declarados a [!DNL Audience Manager]. Para utilizar una regla de combinación de perfiles, debe modificarla `setCustomerIDs` para utilizar el código de integración especificado al crear un origen de datos entre dispositivos. Por ejemplo, supongamos que ha creado una fuente de datos entre dispositivos con el código de integración `my_datasource_ic`. Para pasar un ID declarado, debe agregar el código de integración a la función de ID de visitante como se muestra en el ejemplo de código modificado que se muestra a continuación.

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

Para obtener más información, consulte [Creación de una fuente](#create-data-source) de datos entre dispositivos, ID de [cliente y estados](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)de autenticación.

### Configurar `DIL.create` función

Las últimas versiones de [!UICONTROL DIL] ahora recogen automáticamente la [!UICONTROL declared ID] función de la `visitorService` en `DIL.create` (consulte Variables [de ID](../declared-ids.md#declared-id-variables)declaradas). Compruebe su `DIL.create` función para asegurarse de que está correctamente configurada, como se muestra en el ejemplo de código siguiente.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

En el par clave-valor de la Área de nombres, la variable `*`MCORG`*` es su ID [!DNL Experience Cloud] de organización. Si no tiene este ID, puede encontrarlo en la [!UICONTROL Administration] sección del [!DNL Experience Cloud] panel. Necesita permisos de administrador para vista de este panel. See [Administration: Core Services](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Configuración de SDK

Consulte la sección [Configurar SDK](#configure-sdks-legacy-dil) más abajo.

## DIL heredado {#legacy-dil}

Si no estás usando [!DNL Adobe Experience Platform Identity Service] todavía, realmente deberías hacerlo. Pero, entendemos que el cambio a un nuevo código requiere de una cuidadosa reflexión y prueba. En estos casos, compruebe su `DIL.create` función para asegurarse de que está configurada correctamente, como se muestra en el ejemplo de código siguiente.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Para obtener más información, consulte la sección heredada [!UICONTROL DIL] de Variables [de ID](../declared-ids.md#declared-id-variables)declaradas.

### Configuración de SDK {#configure-sdks-legacy-dil}

Compruebe los métodos del [!DNL SDK] código que le permiten pasar [!UICONTROL declared IDs] desde [!DNL Android] dispositivos móviles y [!DNL iOS] móviles. Los nombres de las bibliotecas de códigos [!DNL Android] y [!DNL iOS] son los mismos:

* `dpid`:: ID de origen de datos entre dispositivos.
* `dpuuid`:: El [!UICONTROL declared ID] (es decir, el ID de usuario).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de dispositivo </th> 
   <th colname="col2" class="entry"> Método </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Sintaxis:</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>Ejemplo:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
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

Consulte también Métodos del Administrador de [Audiencias para Android](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) y Métodos del Administrador de [Audiencias para iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Crear una fuente de datos](../manage-datasources.md#create-data-source)

