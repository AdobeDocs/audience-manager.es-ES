---
description: Para crear reglas de combinación de perfiles revise y complete los pasos de cada uno de los procedimientos descritos en esta sección.
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: Introducción con reglas de combinación de perfiles
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1263'
ht-degree: 1%

---

# Introducción con reglas de combinación de perfiles {#getting-started-with-profile-merge-rules}

Para crear [!UICONTROL Profile Merge Rules], revisar y completar los pasos de cada uno de los procedimientos descritos en esta sección.

<!-- merge-rules-start.xml -->

## Crear un Origen de datos entre dispositivos {#create-data-source}

Para crear un fuente de datos dispositivos cruzado, vaya a **[!UICONTROL Audience Data > Data Sources > Add New]** y complete los pasos para cada sección descrita aquí. Se requieren permisos de administrador para crear o editar un fuente de datos entre dispositivos.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Consulte [Configuración Origen datos y Opciones](../datasources-list-and-settings.md#settings-menu-options) menú para obtener descripciones de estos diferentes controles.

## Detalles Origen de datos {#details}

Para completar la [!UICONTROL Data Source Details] sección:

1. Asigne un nombre al fuente de datos.
2. *(Opcional)* Describa el fuente de datos. Una descripción concisa ayuda a definir la función o el propósito del fuente de datos.
3. Proporcione un código de integración. Un código de integración es su propio ID único para este fuente de datos.
4. En la **[!UICONTROL ID Type]** lista, seleccione **[!UICONTROL Cross Device]**.
5. En la **[!UICONTROL ID Definition]** lista, seleccione una opción que defina el tipo de fuente de datos. Las opciones incluyen:
   * **[!UICONTROL Person]**: un ID que define a una sola persona. Este ID se puede asignar a varios [!DNL Audience Manager] ID.
   * **[!UICONTROL Household]**: un ID que define un grupo de personas. Este ID se puede asignar a varios [!DNL Audience Manager] ID.

## Controles de exportación de datos {#export-controls}

[Los controles](../data-export-controls.md) de exportación de datos son reglas opcionales clasificación se pueden aplicar a un fuente de datos y a un destino. Impiden que envíe datos a un destino cuando esa acción infringe un acuerdo de privacidad o uso de datos. Omita esta sección si no utiliza [!UICONTROL Data Export Controls].

## Configuración de Origen de datos {#settings}

[!UICONTROL Data Source Settings] ofrece varias opciones, pero estas dos son importantes para crear una fuente de datos dispositivos cruzada:

* **[!UICONTROL Use as Authenticated Profile]**: está seleccionada de forma predeterminada, este ajuste le permite versión con sus [!UICONTROL Profile Merge Rule] propios datos autenticados.

* **[!UICONTROL Use as a Device Graph]**: Este control solo está disponible para las cuentas que figuran como proveedores de datos. Al seleccionar esta casilla de verificación, se crea la fuente de datos como un gráfico de dispositivos y se puede compartir con otros [!DNL Audience Manager] clientes. Trabaje con su [!DNL Audience Manager] consultor para configurarse como proveedor de datos y especificar con qué clientes [!UICONTROL Data Source] debe compartirse. El consultor aprovisionará el uso compartido de cuenta y dispositivos gráficos mediante procesos de aprovisionamiento interno.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Este control permite establecer el periodo de retención de datos para los ID de cliente inactivos. Esto determina cuánto tiempo Audience Manager mantiene los ID de cliente en nuestra base de datos después de que se vieron por última vez en la plataforma Audience Manager. El valor predeterminado es 24 meses (720 días). El valor mínimo que puede establecer es de 1 mes y el valor máximo es de 5 años. Tenga en cuenta que contamos todos los meses como 30 días. Audience Manager ejecuta un proceso que elimina los ID de cliente inactivos una vez por semana, de acuerdo con la retención de datos que estableció para los ID de cliente inactivos.

Los campos de texto asociados a esta configuración le permiten cambiar el nombre [!UICONTROL Data Source] con un alias que aparece en las opciones[ de Regla de ](merge-rule-definitions.md)combinación de perfiles. Por ejemplo, si añade un alias a **[!UICONTROL Use as Authenticated Profile]**, ese nombre aparecerá en el [!UICONTROL Authenticated Profile Options] lista. Si añade un alias a **[!UICONTROL Use as a Device Graph]**, ese nombre aparecerá en el [!UICONTROL Device Options] lista.

## Crear una regla de combinación de perfiles {#create-profile-merge-rule}

Para crear un [!UICONTROL Profile Merge Rule], vaya a **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** y complete los pasos de cada una de las secciones aquí descritas.

Puede crear hasta 3 reglas de combinación después de configurar una fuente de datos dispositivos cruzada. Obtienes acceso a una 4ª regla de combinación de perfiles ([!UICONTROL All Cross-Device Profiles]) si te registras en [destinos](../destinations/people-based-destinations-overview.md) basados en personas.

Se requieren permisos de administrador para crear, editar o eliminar un regla. Todos los usuarios pueden vista y utilizar los archivos .[!UICONTROL Profile Merge Rules]

<!-- create-profile-merge-rule.xml -->

**Requisitos previos:** Se requiere un fuente de datos dispositivos cruzado para versión un [!UICONTROL Profile Merge Rule]archivo . Consulte [Crear un Origen](../manage-datasources.md#create-data-source) de datos.

>[!TIP]
>
>Consulte [Regla de combinación de perfiles Opciones Definido](merge-rule-definitions.md) para obtener descripciones de estos diferentes controles.

## Información básica {#basic-info}

Para completar la [!UICONTROL Basic Information] sección:

1. Asigne el siguiente nombre al [!UICONTROL Profile Merge Rule]archivo .
2. *(Opcional)* Describa el [!UICONTROL Profile Merge Rule]archivo . Una descripción concisa le ayuda a definir la función o el propósito de su regla.
3. *(Opcional)* Seleccione **[!UICONTROL Set as default]** si desea que este sea el valor predeterminado [!UICONTROL Profile Merge Rule]. Nuevo segmentos se asocian automáticamente al regla predeterminado.

## Controles de exportación de datos {#data-export-controls}

[Los controles](../data-export-controls.md) de exportación de datos son reglas opcionales clasificación se pueden aplicar a sus [!UICONTROL Profile Merge Rule]. Impiden que envíe datos a un destino cuando esa acción infringe un acuerdo de privacidad o uso de datos. Omita esta sección si no utiliza [!UICONTROL Data Export Controls].

## Configuración de reglas de combinación de perfiles {#profile-merge-rule-setup}

Para completar la [!UICONTROL Proflie Merge Rule Setup] sección:

1. Seleccione un **[!UICONTROL Authenticated Option]** archivo . Las opciones incluyen:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Seleccione un **[!UICONTROL Authenticated Profile Option]** (hasta 3, máximo). Éstas son las [fuentes](merge-rules-start.md) de datos dispositivos cruzadas que creó anteriormente.
3. Seleccione un **[!UICONTROL Device Option]** archivo . Las opciones incluyen:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. Haga clic en **[!UICONTROL Save]**.

### Consideraciones para destinos Adobe Campaign que usan ID entre dispositivos como claves de ID de usuario {#considerations}

A finales de 2019, publicamos una serie de mejoras en las reglas de combinación de perfiles para mejorar la precisión de los archivos por lotes generados mediante ID dispositivos cruzados. Estas mejoras se respetarán estrictamente en su instancia de Audience Manager a partir del lunes 16 de marzo de 2020. En consecuencia, los segmentos asignados a un destino mediante ID dispositivos cruzados dejarán de producir exportaciones en algunas configuraciones de reglas de combinación de perfiles.

Para garantizar la correcta integración entre el instancia Audience Manager y los destinos que usan ID dispositivos cruzados, como Adobe Campaign, asegúrese de cumplir los siguientes requisitos:

1. Revise la regla de combinación de perfiles utilizada por los segmentos asignados a su Adobe Campaign destino de ID declarado. La regla de combinación de perfiles debe utilizar esta [!UICONTROL Last Authenticated Profile] opción, de modo que todos los perfiles autenticados se pueden incluir en las exportaciones. Si la regla de combinación de perfiles utiliza una opción diferente, cámbiela a [!UICONTROL Last Authenticated Profile].
2. Seleccione el fuente de datos ID declarado Adobe Campaign en la configuración de las reglas de combinación de perfiles.

>[!NOTE]
>
> Si ha alcanzado el número máximo de ellos y necesita ayuda para configurarlos según las instrucciones anteriores, póngase en contacto con el Servicio de [!UICONTROL Profile Merge Rules] atención al cliente.

## Configurar regla de combinación Code {#configure-merge-rule-code}

Siga estas instrucciones para configurar el código , [!UICONTROL Adobe Experience Platform Identity Service], y el [!UICONTROL DIL]código móvil [!DNL SDK] para trabajar con sus reglas de combinación.

<!-- merge-rules-configure-code.xml -->

### Requisitos previos

Debe configurar una [fuente de datos dispositivos](#create-data-source) cruzada y [perfil reglas ](#create-profile-merge-rule)*de combinación antes* de completar estos procedimientos.

## Para clientes del servicio de identidad Adobe Experience Platform {#id-service-customers}

Se recomienda la [!UICONTROL Adobe Experience Platform Identity Service] versión más reciente de [DIL](../../dil/dil-overview.md) si se trabaja con [!UICONTROL Profile Merge Rules]. Sin embargo, no tiene que usar el [!UICONTROL Adobe Experience Platform Identity Service] para trabajar con esta función. Si solo está utilizando [!UICONTROL DIL], consulte la [sección](#legacy-dil) DIL heredada a continuación.

### Configuración de la función Establecer ID de cliente

Cuando se trabaja con [!UICONTROL Adobe Experience Platform Identity Service], la función pasa los `setCustomerIDs` ID declarados a [!DNL Audience Manager]. Para utilizar un regla de combinación de perfil, debe modificarlo `setCustomerIDs` para que utilice el código de integración especificado al crear un fuente de datos dispositivos cruzado. Por ejemplo, supongamos que ha creado una fuente de datos dispositivos cruzada con el código `my_datasource_ic`de integración. Para pasar un ID declarado, debe agregar el código de integración a la función ID de visitante, tal como se muestra en el ejemplo de código modificado que se muestra a continuación.

#### Ejemplo de código genérico

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### Muestra de código modificado

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

Para obtener más información, consulte [Crear una Origen](#create-data-source) de datos entre dispositivos e [ID de cliente y Estados](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=es) Authentication.

### Configurar `DIL.create` función

Las versiones más recientes de [!UICONTROL DIL] ahora recogen automáticamente la [!UICONTROL declared ID] `visitorService` función `DIL.create` de (consulte [Variables](../declared-ids.md#declared-id-variables) de ID declaradas). Compruebe su `DIL.create` función para asegurarse de que está configurada correctamente, tal y como se muestra en el ejemplo de código siguiente.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

En el par clave-valor del espacio de nombres, el `*`variable MCORG`*` es su [!DNL Experience Cloud] ID de organización. Si no dispone de este ID, puede encontrarlo en la [!UICONTROL Administration] sección del [!DNL Experience Cloud] panel. Se necesitan permisos de administrador para vista este panel. Consulte [Administración: Servicios](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=es) principales.

### Configurar SDK

Consulte la [sección Configuración de](#configure-sdks-legacy-dil) SDK más abajo.

## DIL heredado {#legacy-dil}

Si aún no lo está usando [!DNL Adobe Experience Platform Identity Service] , realmente debería hacerlo. Sin embargo, entendemos que pasar a un nuevo código requiere una cuidadosa reflexión y pruebas. En estos casos, compruebe su `DIL.create` función para asegurarse de que está configurada correctamente, tal y como se muestra en el ejemplo de código siguiente.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Para obtener más información, consulte la sección heredada [!UICONTROL DIL] de [Variables de ID declaradas](../declared-ids.md#declared-id-variables).

### Configurar SDK {#configure-sdks-legacy-dil}

Compruebe en su código los métodos [!DNL SDK] que le permiten pasar [!UICONTROL declared IDs] desde [!DNL Android] un [!DNL iOS] dispositivos móvil. Los nombres de variable para los [!DNL Android] bibliotecas y [!DNL iOS] código son los mismos:

* `dpid`: ID del fuente de datos dispositivos cruzado.
* `dpuuid`: El [!UICONTROL declared ID] (es decir, el ID usuario).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de dispositivo </th> 
   <th colname="col2" class="entry"> Método </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Androide </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Sintaxis:</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>Ejemplo:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Ios </b> </p> </td> 
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

Consulte también Métodos [Audience Manager para Android](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html?lang=es) y [Métodos Audience Manager para iOS.](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html?lang=es)

>[!MORELIKETHIS]
>
>* [Crear una fuente de datos](../manage-datasources.md#create-data-source)
