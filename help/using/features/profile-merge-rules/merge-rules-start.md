---
description: Para crear reglas de combinación de perfiles, revise y complete los pasos de cada uno de los procedimientos descritos en esta sección.
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: Introducción a las reglas de combinación de perfiles
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1263'
ht-degree: 1%

---

# Introducción a las reglas de combinación de perfiles {#getting-started-with-profile-merge-rules}

Para crear [!UICONTROL Profile Merge Rules], revise y complete los pasos de cada uno de los procedimientos descritos en esta sección.

<!-- merge-rules-start.xml -->

## Creación de un Source de datos entre dispositivos {#create-data-source}

Para crear una fuente de datos entre dispositivos, vaya a **[!UICONTROL Audience Data > Data Sources > Add New]** y complete los pasos para cada sección que se describe aquí. Se requieren permisos de administrador para crear o editar una fuente de datos entre dispositivos.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Consulte [Configuración de Data Source y Opciones de menú](../datasources-list-and-settings.md#settings-menu-options) para obtener descripciones de estos controles diferentes.

## Detalles de Data Source {#details}

Para completar la sección [!UICONTROL Data Source Details]:

1. Asigne un nombre a la fuente de datos.
2. *(Opcional)* Describa el origen de datos. Una descripción concisa le ayuda a definir la función o el propósito de la fuente de datos.
3. Proporcione un código de integración. Un código de integración es su propio ID único para esta fuente de datos.
4. En la lista **[!UICONTROL ID Type]**, seleccione **[!UICONTROL Cross Device]**.
5. En la lista **[!UICONTROL ID Definition]**, seleccione una opción que defina el tipo de origen de datos. Las opciones incluyen:
   * **[!UICONTROL Person]**: ID que define a una sola persona. Este identificador se puede asignar a varios [!DNL Audience Manager] identificadores.
   * **[!UICONTROL Household]**: ID. que define un grupo de personas. Este identificador se puede asignar a varios [!DNL Audience Manager] identificadores.

## Controles de exportación de datos {#export-controls}

[Controles de exportación de datos](../data-export-controls.md) son reglas de clasificación opcionales que puede aplicar a un origen y destino de datos. Evitan que envíe datos a un destino cuando esa acción infringe un acuerdo de uso o privacidad de datos. Omita esta sección si no usa [!UICONTROL Data Export Controls].

## Configuración de Data Source {#settings}

La sección [!UICONTROL Data Source Settings] proporciona varias opciones, pero estas dos son importantes para crear un origen de datos entre dispositivos:

* **[!UICONTROL Use as Authenticated Profile]**: seleccionada de forma predeterminada, esta configuración le permite generar un [!UICONTROL Profile Merge Rule] con sus propios datos autenticados.

* **[!UICONTROL Use as a Device Graph]**: este control solo está disponible para las cuentas enumeradas como proveedor de datos. Al seleccionar esta casilla de verificación, se crea la fuente de datos como un gráfico de dispositivo y se le permite compartirlo con otros [!DNL Audience Manager] clientes. Póngase en contacto con el consultor de [!DNL Audience Manager] para configurarse como proveedor de datos y especificar con qué clientes se debe compartir este(a) [!UICONTROL Data Source]. El consultor proporcionará el uso compartido de la cuenta y el gráfico del dispositivo a través de procesos de aprovisionamiento internos.

* **[!UICONTROL Data retention for inactive Customer IDs]**: este control le permite establecer el período de retención de datos para los ID de cliente inactivos. Esto determina cuánto tiempo mantiene el Audience Manager los ID de cliente en nuestra base de datos después de que se hayan visto por última vez en la plataforma de Audience Manager. El valor predeterminado es 24 meses (720 días). El valor mínimo que puede establecer es 1 mes y el valor máximo es 5 años. Tenga en cuenta que contamos todos los meses como 30 días. Audience Manager ejecuta un proceso que elimina los ID de cliente inactivos una vez a la semana, de acuerdo con la retención de datos establecida para los ID de cliente inactivos.

Los campos de texto asociados con esta configuración le permiten cambiar el nombre de [!UICONTROL Data Source] por un alias que aparezca en las [opciones de regla de combinación de perfiles](merge-rule-definitions.md). Por ejemplo, si agrega un alias a **[!UICONTROL Use as Authenticated Profile]**, ese nombre aparecerá en la lista [!UICONTROL Authenticated Profile Options]. Si agrega un alias a **[!UICONTROL Use as a Device Graph]**, ese nombre aparecerá en la lista [!UICONTROL Device Options].

## Crear una regla de combinación de perfiles {#create-profile-merge-rule}

Para crear un(a) [!UICONTROL Profile Merge Rule], vaya a **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** y complete los pasos para cada sección que se describe aquí.

Puede crear hasta tres reglas de combinación después de configurar una fuente de datos entre dispositivos. Obtendrá acceso a una cuarta regla de combinación de perfiles ([!UICONTROL All Cross-Device Profiles]) si se inscribe en [Destinos basados en personas](../destinations/people-based-destinations-overview.md).

Se requieren permisos de administrador para crear, editar o eliminar una regla. Todos los usuarios pueden ver y utilizar los(as) [!UICONTROL Profile Merge Rules] existentes.

<!-- create-profile-merge-rule.xml -->

**Requisitos previos:** Se requiere un origen de datos entre dispositivos para generar [!UICONTROL Profile Merge Rule]. Ver [Crear un Source de datos](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Consulte [Opciones definidas de reglas de combinación de perfiles](merge-rule-definitions.md) para obtener descripciones de estos controles diferentes.

## Información básica {#basic-info}

Para completar la sección [!UICONTROL Basic Information]:

1. Asigne un nombre a [!UICONTROL Profile Merge Rule].
2. *(Opcional)* Describa a [!UICONTROL Profile Merge Rule]. Una descripción concisa le ayuda a definir la función o el propósito de la regla.
3. *(Opcional)* Seleccione **[!UICONTROL Set as default]** si desea que este sea el valor predeterminado [!UICONTROL Profile Merge Rule]. Los nuevos segmentos se asocian automáticamente con la regla predeterminada.

## Controles de exportación de datos {#data-export-controls}

[Controles de exportación de datos](../data-export-controls.md) son reglas de clasificación opcionales que puede aplicar a su [!UICONTROL Profile Merge Rule]. Evitan que envíe datos a un destino cuando esa acción infringe un acuerdo de uso o privacidad de datos. Omita esta sección si no usa [!UICONTROL Data Export Controls].

## Configuración de reglas de combinación de perfiles {#profile-merge-rule-setup}

Para completar la sección [!UICONTROL Proflie Merge Rule Setup]:

1. Seleccione un(a) **[!UICONTROL Authenticated Option]**. Las opciones incluyen:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Seleccione un(a) **[!UICONTROL Authenticated Profile Option]** (máximo 3). Estas son las [fuentes de datos entre dispositivos](merge-rules-start.md) que creó anteriormente.
3. Seleccione un(a) **[!UICONTROL Device Option]**. Las opciones incluyen:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. Haga clic en **[!UICONTROL Save]**.

### Consideraciones para destinos de Adobe Campaign que usan ID entre dispositivos como claves de ID de usuario {#considerations}

A finales de 2019, publicamos una serie de mejoras en las reglas de combinación de perfiles para mejorar la precisión de los archivos por lotes generados mediante ID entre dispositivos. Estas mejoras se respetarán estrictamente en la instancia de Audience Manager a partir del lunes, 16 de marzo de 2020. Por lo tanto, los segmentos asignados a un destino mediante ID entre dispositivos dejarán de producir exportaciones en algunas configuraciones de reglas de combinación de perfiles.

Para garantizar la correcta integración entre la instancia de Audience Manager y los destinos que utilizan ID entre dispositivos, como Adobe Campaign, asegúrese de cumplir los siguientes requisitos:

1. Revise la regla de combinación de perfiles utilizada por los segmentos asignados a su destino de ID declarados de Adobe Campaign. La regla de combinación de perfiles debe utilizar la opción [!UICONTROL Last Authenticated Profile], de modo que todos los perfiles autenticados se puedan incluir en las exportaciones. Si la regla de combinación de perfiles usa una opción diferente, cambie a [!UICONTROL Last Authenticated Profile].
2. Seleccione la fuente de datos de ID declarado de Adobe Campaign en la configuración de la regla de combinación de perfiles.

>[!NOTE]
>
> Si ha alcanzado el número máximo de [!UICONTROL Profile Merge Rules] y necesita ayuda para configurarlos según las instrucciones anteriores, póngase en contacto con el Servicio de atención al cliente.

## Configurar código de regla de combinación {#configure-merge-rule-code}

Siga estas instrucciones para configurar el código [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL] y el móvil [!DNL SDK] de modo que funcione con las reglas de combinación.

<!-- merge-rules-configure-code.xml -->

### Requisitos previos

Debe configurar una [fuente de datos entre dispositivos](#create-data-source) y [reglas de combinación de perfiles](#create-profile-merge-rule) *antes de que* complete estos procedimientos.

## Para clientes del servicio de identidad de Adobe Experience Platform {#id-service-customers}

Se recomienda [!UICONTROL Adobe Experience Platform Identity Service] y la última versión de [DIL](../../dil/dil-overview.md) al trabajar con [!UICONTROL Profile Merge Rules]. Sin embargo, no tiene que usar [!UICONTROL Adobe Experience Platform Identity Service] para trabajar con esta característica. Si solo usa [!UICONTROL DIL], consulte la [sección de DIL heredados](#legacy-dil) a continuación.

### Configuración de la función Set Customer ID

Al trabajar con [!UICONTROL Adobe Experience Platform Identity Service], la función `setCustomerIDs` pasa los identificadores declarados a [!DNL Audience Manager]. Para usar una regla de combinación de perfiles, debe modificar `setCustomerIDs` para que utilice el código de integración especificado al crear un origen de datos entre dispositivos. Por ejemplo, supongamos que ha creado una fuente de datos entre dispositivos con el código de integración `my_datasource_ic`. Para pasar un ID declarado, agregaría el código de integración a la función de ID de visitante como se muestra en el ejemplo de código modificado que aparece a continuación.

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

Para obtener más información, consulte [Crear un Source de datos entre dispositivos](#create-data-source) y [ID de cliente y estados de autenticación](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=es).

### Configurar la función `DIL.create`

Las últimas versiones de [!UICONTROL DIL] ahora toman automáticamente [!UICONTROL declared ID] de la función `visitorService` en `DIL.create` (vea [Variables de ID declaradas](../declared-ids.md#declared-id-variables)). Compruebe la función `DIL.create` para asegurarse de que está correctamente configurada, como se muestra en el ejemplo de código siguiente.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

En el par clave-valor del área de nombres, la variable `*`MCORG`*` es su ID de organización [!DNL Experience Cloud]. Si no tiene este identificador, puede encontrarlo en la sección [!UICONTROL Administration] del panel [!DNL Experience Cloud]. Necesita permisos de administrador para ver este tablero. Consulte [Administración: servicios principales](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=es).

### Configuración de SDK

Consulte la sección [Configurar SDK](#configure-sdks-legacy-dil) a continuación.

## DIL heredado {#legacy-dil}

Si todavía no usa [!DNL Adobe Experience Platform Identity Service], en realidad debería hacerlo. Sin embargo, entendemos que pasar a un nuevo código requiere una cuidadosa reflexión y pruebas. En estos casos, compruebe su función `DIL.create` para asegurarse de que está correctamente configurada, como se muestra en el ejemplo de código siguiente.

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

### Configuración de SDK {#configure-sdks-legacy-dil}

Compruebe los métodos en su código de [!DNL SDK] que le permiten pasar [!UICONTROL declared IDs] desde [!DNL Android] y [!DNL iOS] dispositivos móviles. Los nombres de las variables para las bibliotecas de código [!DNL Android] y [!DNL iOS] son los mismos:

* `dpid`: ID de origen de datos entre dispositivos.
* `dpuuid`: el [!UICONTROL declared ID] (es decir, el identificador de usuario).

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
      &lbrack;ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"&rbrack;;
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

Vea también [Métodos Audience Manager para Android](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html?lang=es) y [Métodos Audience Manager para iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html?lang=es).

>[!MORELIKETHIS]
>
>* [Crear una fuente de datos](../manage-datasources.md#create-data-source)
