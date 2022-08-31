---
description: Para crear reglas de combinación de perfiles , revise y complete los pasos de cada uno de los procedimientos descritos en esta sección.
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: Introducción a las reglas de combinación de Perfiles
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 3%

---

# Introducción a las reglas de combinación de Perfiles {#getting-started-with-profile-merge-rules}

Para crear [!UICONTROL Profile Merge Rules], revise y complete los pasos de cada uno de los procedimientos descritos en esta sección.

<!-- merge-rules-start.xml -->

## Crear una fuente de datos entre dispositivos {#create-data-source}

Para crear una fuente de datos entre dispositivos, vaya a **[!UICONTROL Audience Data > Data Sources > Add New]** y complete los pasos para cada sección descrita aquí. Se necesitan permisos de administrador para crear o editar una fuente de datos entre dispositivos.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Consulte [Configuración y opciones de menú de fuentes de datos](../datasources-list-and-settings.md#settings-menu-options) para obtener descripciones de estos diferentes controles.

## Detalles de la fuente de datos {#details}

Para completar la [!UICONTROL Data Source Details] sección:

1. Asigne un nombre al origen de datos.
2. *(Opcional)* Describa la fuente de datos. Una descripción concisa ayuda a definir la función o el propósito del origen de datos.
3. Proporcione un código de integración. Un código de integración es su propio ID único para esta fuente de datos.
4. En el **[!UICONTROL ID Type]** lista, seleccionar **[!UICONTROL Cross Device]**.
5. En el **[!UICONTROL ID Definition]** seleccione una opción que defina el tipo de fuente de datos. Las opciones incluyen:
   * **[!UICONTROL Person]**: Un ID que define una sola persona. Este ID se puede asignar a varios [!DNL Audience Manager] ID.
   * **[!UICONTROL Household]**: ID que define un grupo de personas. Este ID se puede asignar a varios [!DNL Audience Manager] ID.

## Controles de exportación de datos {#export-controls}

[Controles de exportación de datos](../data-export-controls.md) son reglas de clasificación opcionales que puede aplicar a una fuente de datos y a un destino. Evitan que envíe datos a un destino cuando esa acción infringe una privacidad de datos o un acuerdo de uso. Omita esta sección si no utiliza [!UICONTROL Data Export Controls].

## Configuración de fuentes de datos {#settings}

[!UICONTROL Data Source Settings] proporciona varias opciones, pero estas dos son importantes para crear una fuente de datos entre dispositivos:

* **[!UICONTROL Use as Authenticated Profile]**: Seleccionado de forma predeterminada, esta configuración le permite generar un [!UICONTROL Profile Merge Rule] con sus propios datos autenticados.

* **[!UICONTROL Use as a Device Graph]**: Este control solo está disponible para cuentas que aparecen como proveedores de datos. Al seleccionar esta casilla de verificación, se crea la fuente de datos como un gráfico de dispositivos y se permite compartirla con otros [!DNL Audience Manager] clientes. Trabaje con su [!DNL Audience Manager] consultor para configurarlo como proveedor de datos y especificar qué clientes [!UICONTROL Data Source] debe compartirse con . El consultor hará uso compartido del gráfico de dispositivos y cuentas a través de procesos de aprovisionamiento internos.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Este control le permite establecer el periodo de retención de datos para los ID de cliente inactivos. Esto determina cuánto tiempo el Audience Manager mantiene los ID de cliente en nuestra base de datos después de haberlos visto por última vez en la plataforma de Audience Manager. El valor predeterminado es 24 meses (720 días). El valor mínimo que puede establecer es 1 mes y el valor máximo es 5 años. Tenga en cuenta que todos los meses se cuentan como 30 días. Audience Manager ejecuta un proceso que elimina los ID de cliente inactivos una vez a la semana, de acuerdo con la retención de datos que configure para los ID de cliente inactivos.

Los campos de texto asociados a esta configuración le permiten cambiar el nombre del [!UICONTROL Data Source] con un alias que aparece en la variable [Opciones de reglas de combinación de perfiles](merge-rule-definitions.md). Por ejemplo, si agrega un alias a **[!UICONTROL Use as Authenticated Profile]**, ese nombre aparece en el [!UICONTROL Authenticated Profile Options] lista. Si agrega un alias a **[!UICONTROL Use as a Device Graph]**, ese nombre aparece en el [!UICONTROL Device Options] lista.

## Crear una regla de combinación de perfiles {#create-profile-merge-rule}

Para crear un [!UICONTROL Profile Merge Rule], vaya a **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** y complete los pasos para cada sección descrita aquí.

Puede crear hasta 3 reglas de combinación después de configurar un origen de datos entre dispositivos. Puede acceder a una cuarta regla de combinación de perfiles ([!UICONTROL All Cross-Device Profiles]) si se inscribe para [Destinos basados en personas](../destinations/people-based-destinations-overview.md).

Se necesitan permisos de administrador para crear, editar o eliminar una regla. Todos los usuarios pueden ver y utilizar la [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**Requisitos previos:** Se requiere una fuente de datos entre dispositivos para crear un [!UICONTROL Profile Merge Rule]. Consulte [Crear una fuente de datos](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Consulte [Definición de las opciones de las reglas de combinación de perfiles](merge-rule-definitions.md) para obtener descripciones de estos diferentes controles.

## Información básica {#basic-info}

Para completar la [!UICONTROL Basic Information] sección:

1. Asigne un nombre a la variable [!UICONTROL Profile Merge Rule].
2. *(Opcional)* Describa el [!UICONTROL Profile Merge Rule]. Una descripción concisa le ayuda a definir la función o el propósito de la regla.
3. *(Opcional)* Select **[!UICONTROL Set as default]** si desea que este sea el valor predeterminado [!UICONTROL Profile Merge Rule]. Los nuevos segmentos se asocian automáticamente a la regla predeterminada.

## Controles de exportación de datos {#data-export-controls}

[Controles de exportación de datos](../data-export-controls.md) son reglas de clasificación opcionales que puede aplicar a su [!UICONTROL Profile Merge Rule]. Evitan que envíe datos a un destino cuando esa acción infringe una privacidad de datos o un acuerdo de uso. Omita esta sección si no utiliza [!UICONTROL Data Export Controls].

## Configuración de reglas de combinación de perfiles {#profile-merge-rule-setup}

Para completar la [!UICONTROL Proflie Merge Rule Setup] sección:

1. Seleccione un **[!UICONTROL Authenticated Option]**. Las opciones incluyen:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Seleccione un **[!UICONTROL Authenticated Profile Option]** (hasta 3, máximo). Estos son los [fuentes de datos entre dispositivos](merge-rules-start.md) ha creado anteriormente.
3. Seleccione una **[!UICONTROL Device Option]**. Las opciones incluyen:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. Haga clic **[!UICONTROL Save]**.

### Consideraciones para destinos de Adobe Campaign que utilizan ID entre dispositivos como claves de ID de usuario {#considerations}

A finales de 2019, publicamos una serie de mejoras en las reglas de combinación de perfiles para mejorar la precisión de los archivos por lotes generados mediante ID entre dispositivos. Estas mejoras se respetarán estrictamente en la instancia de Audience Manager a partir del lunes 16 de marzo de 2020. Por lo tanto, los segmentos asignados a un destino mediante un ID entre dispositivos dejarán de producir exportaciones en algunas configuraciones de reglas de combinación de perfiles.

Para garantizar la integración correcta entre la instancia de Audience Manager y los destinos que utilizan ID entre dispositivos, como Adobe Campaign, asegúrese de cumplir los siguientes requisitos:

1. Revise la regla de combinación de perfiles utilizada por los segmentos asignados a su destino de ID declarado de Adobe Campaign . La regla de combinación de perfiles debe utilizar la variable [!UICONTROL Last Authenticated Profile] , de modo que todos los perfiles autenticados se puedan incluir en las exportaciones. Si la regla de combinación de perfiles utiliza una opción distinta, cambie a [!UICONTROL Last Authenticated Profile].
2. Seleccione la fuente de datos de ID declarados de Adobe Campaign en la configuración de la regla de combinación de perfiles .

>[!NOTE]
>
> Si ha alcanzado el número máximo de [!UICONTROL Profile Merge Rules] y necesita ayuda para configurarlas según las instrucciones anteriores, póngase en contacto con el Servicio de atención al cliente.

## Configurar código de regla de combinación {#configure-merge-rule-code}

Siga estas instrucciones para configurar la variable [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL]y móvil [!DNL SDK] para trabajar con las reglas de combinación.

<!-- merge-rules-configure-code.xml -->

### Requisitos previos

Debe configurar un [fuente de datos entre dispositivos](#create-data-source) y [reglas de combinación de perfiles](#create-profile-merge-rule) *before* completar estos procedimientos.

## Para clientes del servicio de Adobe Experience Platform ID {#id-service-customers}

La variable [!UICONTROL Adobe Experience Platform Identity Service] y la última versión de [DIL](../../dil/dil-overview.md) se recomienda cuando se trabaja con [!UICONTROL Profile Merge Rules]. Sin embargo, no es necesario usar la variable [!UICONTROL Adobe Experience Platform Identity Service] para trabajar con esta función. Si solo está utilizando [!UICONTROL DIL], consulte la [sección DIL heredado](#legacy-dil) más abajo.

### Configuración de la función Set Customer ID

Al trabajar con la variable [!UICONTROL Adobe Experience Platform Identity Service], el `setCustomerIDs` pasa los ID declarados a [!DNL Audience Manager]. Para utilizar una regla de combinación de perfiles, debe modificar `setCustomerIDs` para utilizar el código de integración especificado al crear una fuente de datos entre dispositivos. Por ejemplo, supongamos que ha creado una fuente de datos entre dispositivos con el código de integración `my_datasource_ic`. Para pasar un ID declarado, agregaría el código de integración a la función de ID de visitante como se muestra en el ejemplo de código modificado que aparece a continuación.

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

Para obtener más información, consulte [Crear una fuente de datos entre dispositivos](#create-data-source) y [ID de cliente y estados de autenticación](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html).

### Configurar `DIL.create` function

Las últimas versiones de [!UICONTROL DIL] ahora recoge automáticamente el [!UICONTROL declared ID] de la variable `visitorService` en `DIL.create` (consulte [Variables de ID declaradas](../declared-ids.md#declared-id-variables)). Compruebe su `DIL.create` para asegurarse de que se ha configurado correctamente, como se muestra en el ejemplo de código siguiente.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

En el par clave-valor del área de nombres, la variable `*`MCORG`*` es su [!DNL Experience Cloud] ID de organización. Si no tiene este ID, puede encontrarlo en el [!UICONTROL Administration] de la sección [!DNL Experience Cloud] tablero. Necesita permisos de administrador para ver este tablero. Consulte [Administración: Servicios principales](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

### Configuración de SDK

Consulte la [Configuración de SDK](#configure-sdks-legacy-dil) a continuación.

## DIL heredado {#legacy-dil}

Si no utiliza [!DNL Adobe Experience Platform Identity Service] sin embargo, realmente deberías hacerlo. Sin embargo, entendemos que el paso a un nuevo código requiere de una cuidadosa reflexión y prueba. En estos casos, consulte a su `DIL.create` para asegurarse de que se ha configurado correctamente, como se muestra en el ejemplo de código siguiente.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Para obtener más información, consulte la [!UICONTROL DIL] en [Variables de ID declaradas](../declared-ids.md#declared-id-variables).

### Configuración de SDK {#configure-sdks-legacy-dil}

Compruebe los métodos de [!DNL SDK] código que le permite pasar [!UICONTROL declared IDs] from [!DNL Android] y [!DNL iOS] dispositivos móviles. Los nombres de variables para la variable [!DNL Android] y [!DNL iOS] las bibliotecas de código son las mismas:

* `dpid`: El ID de fuente de datos entre dispositivos.
* `dpuuid`: La variable [!UICONTROL declared ID] (es decir, el ID de usuario).

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

Consulte también [Métodos de Audience Manager para Android](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) y [Métodos de Audience Manager para iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Crear una fuente de datos](../manage-datasources.md#create-data-source)

