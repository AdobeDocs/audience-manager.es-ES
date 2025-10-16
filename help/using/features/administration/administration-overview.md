---
description: Las opciones del menú Administración permiten crear usuarios Audience Manager y asignarlos a grupos. También puede vista límites (características, segmentos, destinos y modelos).
keywords: RBAC; RBAC; función basado; basado en función; Controles de acceso basados en función
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: Administración
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: c29e581c736e03066df7d0698d4ea384e14db467
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 0%

---

# [!UICONTROL Administration] (Controles RBAC) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> El usuario administración de cuentas se mueve al [Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html). Para inicio usuario migración, requerimos que todos los clientes Audience Manager tomen inmediatamente las medidas necesarias descritas en este artículo: [Audience Manager usuario migración a Admin Console](admin-console-migration.md).
> 
> Cuando todos los clientes hayan migrado, las secciones de administración de usuario de este documento desaparecerán.

>[!IMPORTANT]
>
> Antes de poder utilizar [!DNL RBAC], esta función debe estar activada por Adobe Systems de su organización. Póngase en contacto con su equipo de cuenta para solicitud [!DNL RBAC] activación o póngase en contacto con el Servicio de atención al cliente.


Las opciones que hay bajo el [!UICONTROL Administration] menú permiten crear usuarios Audience Manager y asignarlos a grupos. También puede vista límites (características, segmentos, destinos y modelos).

Los clientes empresariales que utilizan [!DNL Audience Manager] necesitan una plataforma gestión de datos para todos sus datos, pero deben ser capaces de controlar la visibilidad de los diferentes elementos de datos para unidades de negocio específicas. Puede realizar esto mediante grupo permisos, también conocidos como [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] Utiliza grupos para asignar permisos. Los permisos no se asignan en el nivel usuario. Los permisos de grupo están ligados a objetos ([!UICONTROL traits], segmentos, etc.) y a acciones que se pueden realizar en dichos objetos (editar, vista, etc.). Estos controles también están disponibles a través de las API de REST Audience Manager. Consulte [User Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Administración de](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) grupos y [Métodos de API de administración de](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) permisos.

## Crear usuarios {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> El usuario administración de cuentas se mueve al [Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html). Para inicio usuario migración, requerimos que todos los clientes Audience Manager tomen inmediatamente las medidas necesarias descritas en este artículo: [Audience Manager usuario migración a Admin Console](admin-console-migration.md).
> 
> Cuando todos los clientes hayan migrado, la sección de administración de usuario de este documento desaparecerá.
> 
>Crear usuarios y [!DNL Audience Manager] especifique usuario detalles, inicio de sesión estado y asigne usuarios a grupos.

1. Haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Haga clic ![](assets/icon_add.png) para mostrar el [!UICONTROL Create New User] Página.
1. En **[!UICONTROL User Details]**, rellene los campos:
   * **[!UICONTROL Username]:** especifique un nombre de usuario único para Audience Manager.
   * **[!UICONTROL First Name]:** especifique el nombre del usuario.
   * **[!UICONTROL Last Name]:** Especifique los apellidos del usuario.
   * **[!UICONTROL Email Address]:** especifique la dirección correo electrónico del usuario. [!DNL Audience Manager] no envía notificación regulares a los usuarios. [!DNL Audience Manager] Los administradores tienen acceso a las direcciones correo electrónico de los usuarios y pueden correo electrónico manualmente a los usuarios según sea necesario. Por ejemplo, si un usuario olvida su contraseña, la dirección correo electrónico especificada en este campo se utiliza para enviar un contraseña temporal e instrucciones para restablecer el contraseña.
   * **[!UICONTROL Phone Number]:** Especifique el número de teléfono del usuario.
   * **[!UICONTROL Is Admin]:** especifique si este usuario es un [!DNL Audience Manager] administrador. Los usuarios administradores pueden administrar usuarios (crear, editar, etc.) y grupos (crear, asignar permisos, etc.). Los usuarios no administradores pueden controlar solo sus propios perfiles usuario, incluida la edición de sus direcciones correo electrónico y el restablecimiento de sus propias contraseñas. Para obtener más información, consulte [Editar su Configuración de la cuenta](../../features/administration/edit-account-settings.md).
1. En **[!UICONTROL Login]**, seleccione el estado deseado:
   * **[!UICONTROL Active]: Los**  usuarios activos pueden acceder a [!DNL Audience Manager] los permisos concedidos por miembros del grupo y disponer de ellos.
   * **[!UICONTROL Deactivated]:**  los usuarios desactivados no pueden acceder [!DNL Audience Manager] a ellos y no tienen ningún permiso. Si desactiva a los usuarios, su usuario información permanece y [!DNL Audience Manager] puede simplemente reactivarlos, si es necesario. Si elimina usuarios, debe volver a crearlos si necesitan volver a usarlos [!DNL Audience Manager] en el futuro.
   * **[!UICONTROL Expired]:** El contraseña de un usuario tiene más de 90 días.
   * **[!UICONTROL Pending]:** el usuario tiene un contraseña temporal, ya sea después de un restablecimiento del contraseña o como un marca nuevo cuenta, y aún no ha establecido un contraseña permanente.
   * **[!UICONTROL Locked Out]:** 5 intentos de inicio de sesión incorrectos bloquean un usuario.
1. En **[!UICONTROL Assigned Groups]**, en el lista desplegable, seleccione los grupos a los que desee asignar este usuario.
Para obtener más información sobre los grupos y los permisos, consulte [Crear un grupo](../../features/administration/administration-overview.md#create-group).
1. Haga clic en **[!UICONTROL Save]**.

## Crear un [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> El usuario administración de cuentas se mueve al [Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html). Para inicio usuario migración, aconsejamos a todos los clientes Audience Manager que tomen inmediatamente las medidas necesarias descritas en este artículo: [Audience Manager usuario migración a Admin Console](admin-console-migration.md).
> 
> Cuando todos los clientes hayan migrado, esta sección desaparecerá.

Un *grupo* es un colección de usuarios que comparten derechos de acceso a [!UICONTROL destination], [!UICONTROL segment], y [!UICONTROL trait] objetos. Puede limitar grupos a objetos individuales o concederles amplio acceso a combinaciones de objetos diferentes.

<!-- t_create_groups.xml -->

Para crear una grupo:

1. Haga clic en **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Haga clic  ![](assets/icon_add.png) para abrir el [!UICONTROL Group Settings] Página.
3. En [!UICONTROL Group Details]:
   * Asigne un nombre al grupo.
   * Proporcione una breve descripción grupo.
4. En , haga clic en [!UICONTROL Group Members]un usuario de opciones para **[!UICONTROL Add Users]** agregarlas al grupo.
5. En [!UICONTROL Group Permissions], seleccione una [característica](../../features/traits/trait-details-page.md), [segmento](../../features/segments/segments-purpose.md) o [destino](../../features/destinations/destinations.md) de **[!UICONTROL Add Object]**.
Se abre una ventana de permisos para el objeto seleccionado.
6. Active la casilla de verificación de los permisos que desea que tengan grupo miembros.
7. *(Opcional)* Asigne [permisos](../../features/administration/administration-overview.md#wild-card-permissions) de comodín al grupo.
8. Haga clic en **[!UICONTROL Save Group]**.

## Comprensión [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> El usuario administración de cuentas se mueve al [Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html). Para inicio usuario migración, aconsejamos a todos los clientes Audience Manager que tomen inmediatamente las medidas necesarias descritas en este artículo: [Audience Manager usuario migración a Admin Console](admin-console-migration.md).
> 
> Cuando todos los clientes hayan migrado, esta sección desaparecerá.

Simplifique la gestión de derechos de grupo con [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions]Conceder a grupo miembros acceso automático a cada fuente de datos asociado a , [!UICONTROL segment]&#x200B;[!UICONTROL destination], o [!UICONTROL trait]. En comparación, los permisos regulares sólo permiten asignar elementos específicos [!UICONTROL data sources] a uno de estos objetos. Y, cuando agrega nuevos [!UICONTROL data sources], grupo miembros no tienen acceso a esas nuevas fuentes.

Debe abrir los permisos grupo y asignar los nuevos [!UICONTROL data sources] al grupo. [!UICONTROL Wild Card Permissions] permite evitar este proceso de actualización manual [!UICONTROL data source] . Los grupos con [!UICONTROL Wild Card Permissions] obtienen acceso a nuevos [!UICONTROL data sources] sin autorización explícita.

![](assets/wild-card.png)

Lea a continuación para obtener una descripción de lo que significa cada uno [!UICONTROL wildcard permission] :

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Los usuarios pueden seleccionar [!UICONTROL traits] como línea de base para [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Los usuarios pueden editar todas las [!UICONTROL traits] configuraciones dentro de su compañía cuenta.
* `VIEW_ALL_TRAITS` - Los usuarios pueden vista todo [!UICONTROL traits] configurado dentro de su cuenta compañía.
* `DELETE_ALL_TRAITS` - Los usuarios pueden eliminar todas las [!UICONTROL traits] configuraciones dentro de su compañía cuenta.
* `CREATE_ALL_ALGO_TRAITS` - Los usuarios pueden crear [!UICONTROL algorithmic traits]archivos .
* `MAP_ALL_TO_SEGMENTS` - Los usuarios pueden añadir cualquiera de las [!UICONTROL traits] pertenencias a su compañía a [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Los usuarios pueden crear [!UICONTROL traits]archivos .

**[!UICONTROL Models]**

* `VIEW_MODELS` - Los usuarios tienen permiso a vista [!UICONTROL models] pertenecientes a su compañía.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Los usuarios pueden vista todas las [!UICONTROL derived signals] pertenencias a su compañía.
* `CREATE_DERIVED_SIGNALS` - Los usuarios pueden crear [!UICONTROL derived signals]archivos .
* `EDIT_DERIVED_SIGNALS` - Los usuarios pueden editar todas las [!UICONTROL derived signals] pertenencias a su compañía.
* `DELETE_DERIVED_SIGNALS` - Los usuarios pueden eliminar cualquiera de las [!UICONTROL derived signals] pertenencias a su compañía.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Los usuarios pueden editar toda la [!UICONTROL destinations] configuración dentro de su compañía cuenta.
* `CREATE_DESTINATIONS` - Los usuarios pueden crear [!UICONTROL destinations]archivos .
* `VIEW_ALL_DESTINATIONS` - Los usuarios pueden vista toda la [!UICONTROL destinations] configuración dentro de su cuenta compañía.
* `DELETE_ALL_DESTINATIONS` - Los usuarios pueden eliminar toda la [!UICONTROL destinations] configuración dentro de su cuenta compañía.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Los usuarios pueden hacer todo (vista, crear, editar, eliminar) en su [!UICONTROL Tag Containers]archivo .

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Los usuarios pueden hacer todo (vista, crear, editar, eliminar) en sus [!UICONTROL Audience Lab] grupos prueba.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Los usuarios pueden crear segmentos.
* `DELETE_ALL_SEGMENTS` - Los usuarios pueden eliminar todos los segmentos configurados dentro de su compañía cuenta.
* `MAP_ALL_TO_DESTINATIONS` - Los usuarios pueden mapear cualquiera de los segmentos pertenecientes a su compañía a destinos.
* `EDIT_ALL_SEGMENTS` - Los usuarios pueden editar todos los segmentos configurados dentro de su compañía cuenta.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Los usuarios pueden seleccionar segmentos como línea de base para los modelos.
* `VIEW_ALL_SEGMENTS` - Los usuarios pueden vista todos los segmentos configurados dentro de su compañía cuenta.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Los usuarios pueden vista todas las señales capturadas en [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Casos de uso {#use-cases}

### Supervisión del acceso de los usuarios {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] puede ayudarlo a monitor usuario inicio de sesión estado, dándole una idea clara de quién puede acceder a su Audience Manager instancia.

Según los requisitos de su empresa, puede habilitar y deshabilitar usuario cuentas según sea necesario.

![monitor-usuario-acceso](assets/monitor-user-access.png)

### Garantice la protección del acceso en casos sensibles [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

Se pueden configurar [!UICONTROL Role-Based Access Control] en [!UICONTROL trait], segmento y [!UICONTROL destination] nivel para cada grupo de usuarios.

Esta capacidad le ayuda a administrar cómo los usuarios vista, crean, leen, escriben y editan conjuntos de datos específicos, y igualado restringen el acceso de los usuarios a conjuntos de datos que no deberían estar disponibles para ellos.

![protección de acceso](assets/access-protection.png)
