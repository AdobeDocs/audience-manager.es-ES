---
description: Las opciones del menú Administración permiten crear usuarios Audience Manager y asignarlos a grupos. También puede establecer límites de vista (características, segmentos, destinos y modelos).
keywords: rbac;RBAC;role based;role-based;role-based access controls
seo-description: Las opciones del menú Administración permiten crear usuarios Audience Manager y asignarlos a grupos. También puede establecer límites de vista (características, segmentos, destinos y modelos).
seo-title: Administration
solution: Audience Manager
title: Administration
topic: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 002429c74298ac34533225c105d5d71761ebf9c0
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 1%

---


# [!UICONTROL Administration] (Controles RBAC) {#administration}

![](assets/rbac-controls.png)

Las opciones del [!UICONTROL Administration] menú permiten crear usuarios Audience Manager y asignarlos a grupos. También puede establecer límites de vista (características, segmentos, destinos y modelos).

Los clientes de la empresa que utilizan [!DNL Audience Manager] una plataforma de gestión de datos para todos sus datos, pero deben poder controlar la visibilidad de los diferentes elementos de datos en unidades de negocio específicas. Puede hacerlo mediante permisos de grupo, también denominados [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utiliza grupos para asignar permisos. Los permisos no se asignan a nivel de usuario. Los permisos de grupo están ligados a objetos ([!UICONTROL traits], segmentos, etc.) y a las acciones que puede realizar en esos objetos (edición, vista, etc.). Estos controles también están disponibles a través de las API de Audience Manager REST. Consulte Métodos [de Administración](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md)de usuarios, Administración [de grupos](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)y Administración de [permisos](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API.

## Create Users {#create-users}

<!-- t_create_users.xml -->

Cree usuarios en [!DNL Audience Manager] y especifique los detalles del usuario, el estado de inicio de sesión y asigne usuarios a los grupos.

1. Haga clic **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Haga clic en ![](assets/icon_add.png) para mostrar la [!UICONTROL Create New User] página.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **[!UICONTROL Username]::**Especifique un nombre de usuario único para Audience Manager.
   * **[!UICONTROL First Name]::**Especifique el nombre del usuario.
   * **[!UICONTROL Last Name]::**Especifique los apellidos del usuario.
   * **[!UICONTROL Email Address]::**Especifique la dirección de correo electrónico del usuario.[!DNL Audience Manager]no envía notificaciones regulares a los usuarios.[!DNL Audience Manager]los administradores tienen acceso a las direcciones de correo electrónico de los usuarios y pueden enviar mensajes manualmente a los usuarios según sea necesario. Por ejemplo, si un usuario olvida su contraseña, se utiliza la dirección de correo electrónico especificada en este campo para enviar una contraseña temporal e instrucciones para restablecer la contraseña.
   * **[!UICONTROL Phone Number]::**Especifique el número de teléfono del usuario.
   * **[!UICONTROL Is Admin]::**Especifique si este usuario es un[!DNL Audience Manager]administrador. Los usuarios administradores pueden administrar usuarios (crear, editar, etc.) y grupos (crear, asignar permisos, etc.). Los usuarios que no son administradores pueden controlar únicamente sus propios perfiles de usuario, incluida la edición de sus direcciones de correo electrónico y el restablecimiento de sus propias contraseñas. Para obtener más información, consulte[Editar la configuración](../../features/administration/edit-account-settings.md)de la cuenta.
1. En **[!UICONTROL Login]**, seleccione el estado que desee:
   * **[!UICONTROL Active]::**Los usuarios activos pueden acceder[!DNL Audience Manager]y obtener los permisos por pertenencia a grupos.
   * **[!UICONTROL Deactivated]::**Los usuarios desactivados no pueden acceder[!DNL Audience Manager]y no tienen permisos. Si desactiva los usuarios, la información de los usuarios permanecerá activa[!DNL Audience Manager]y podrá reactivarla fácilmente si es necesario. Si elimina usuarios, debe volver a crearlos si necesitan usarlos[!DNL Audience Manager]nuevamente en el futuro.
   * **[!UICONTROL Expired]::**La contraseña de un usuario tiene más de 90 días.
   * **[!UICONTROL Pending]::**El usuario tiene una contraseña temporal, ya sea después de restablecer la contraseña o como cuenta nueva, y aún no ha establecido una contraseña permanente.
   * **[!UICONTROL Locked Out]::**5 intentos de inicio de sesión incorrectos bloquearán a un usuario.
1. En **[!UICONTROL Assigned Groups]**la lista desplegable, seleccione los grupos a los que desee asignar este usuario.
Para obtener más información sobre los grupos y permisos, consulte [Creación de un grupo](../../features/administration/administration-overview.md#create-group).
1. Haga clic **[!UICONTROL Save]**.

## Cree un [!UICONTROL Group] {#create-group}

Un *grupo* es una colección de usuarios que comparten derechos de acceso a [!UICONTROL destination], [!UICONTROL segment]y [!UICONTROL trait] objetos. Puede limitar los grupos a objetos únicos únicamente o darles un acceso amplio a combinaciones de objetos diferentes.

<!-- t_create_groups.xml -->

Para crear un grupo:

1. Haga clic **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
1. Haga clic ![](assets/icon_add.png) para abrir la [!UICONTROL Group Settings] página.
1. En [!UICONTROL Group Details]:
   * Asigne un nombre al grupo.
   * Proporcione una breve descripción del grupo.
1. En [!UICONTROL Group Members], haga clic en un usuario de **[!UICONTROL Add Users]** las opciones para agregarlo al grupo.
1. En [!UICONTROL Group Permissions], seleccione un [rasgo](../../features/traits/trait-details-page.md), [segmento](../../features/segments/segments-purpose.md)o [destino](../../features/destinations/destinations.md) desde **[!UICONTROL Add Object]**.
Se abre una ventana de permisos para el objeto seleccionado.
1. Seleccione la casilla de verificación de los permisos que desea que tengan los miembros del grupo.
1. *(Opcional)* Asigne permisos [de](../../features/administration/administration-overview.md#wild-card-permissions) comodines al grupo.
1. Haga clic **[!UICONTROL Save Group]**.

## Explicación [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

Simplifique la administración de derechos de grupo con [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] otorgue a los miembros del grupo acceso automático a cada origen de datos asociado a un [!UICONTROL segment], [!UICONTROL destination]o [!UICONTROL trait]. En comparación, los permisos regulares solo permiten asignar elementos específicos [!UICONTROL data sources] a uno de estos objetos. Y, cuando agrega nuevos [!UICONTROL data sources]miembros del grupo, no obtiene acceso a esas nuevas fuentes.

Debe abrir los permisos de grupo y asignar los nuevos [!UICONTROL data sources] al grupo. [!UICONTROL Wild Card Permissions] le permite evitar este proceso de [!UICONTROL data source] actualización manual. Los grupos con [!UICONTROL Wild Card Permissions] acceso a nuevos grupos [!UICONTROL data sources] sin autorización explícita.

![](assets/wild-card.png)

Lea a continuación para ver una descripción de lo que significa cada [!UICONTROL wildcard permission] :

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Los usuarios pueden seleccionar [!UICONTROL traits] como línea de base para [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Los usuarios pueden editar toda la [!UICONTROL traits] configuración de su cuenta de compañía.
* `VIEW_ALL_TRAITS` - Los usuarios pueden realizar la vista de todas las [!UICONTROL traits] configuraciones dentro de su cuenta de compañía.
* `DELETE_ALL_TRAITS` - Los usuarios pueden eliminar toda la [!UICONTROL traits] configuración de su cuenta de compañía.
* `CREATE_ALL_ALGO_TRAITS` - Los usuarios pueden crear [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Los usuarios pueden agregar cualquiera de los elementos [!UICONTROL traits] pertenecientes a su compañía a [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Los usuarios pueden crear [!UICONTROL traits].

**[!UICONTROL Reports]**

* `PTRREPORTS` - Esto [!UICONTROL wildcard permission] se refiere a la funcionalidad obsoleta y se eliminará de la interfaz de usuario del Audience Manager en breve.

**[!UICONTROL Models]**

* `VIEW_MODELS` - Los usuarios tienen permiso para pertenecer a la vista [!UICONTROL models] de su compañía.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Los usuarios pueden realizar la vista de todos los [!UICONTROL derived signals] miembros de su compañía.
* `CREATE_DERIVED_SIGNALS` - Los usuarios pueden crear [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Los usuarios pueden editar toda la [!UICONTROL derived signals] pertenencia a su compañía.
* `DELETE_DERIVED_SIGNALS` - Los usuarios pueden eliminar cualquiera de los [!UICONTROL derived signals] que pertenezcan a su compañía.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Los usuarios pueden editar toda la [!UICONTROL destinations] configuración de su cuenta de compañía.
* `CREATE_DESTINATIONS` - Los usuarios pueden crear [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Los usuarios pueden realizar la vista de todas las [!UICONTROL destinations] configuraciones dentro de su cuenta de compañía.
* `DELETE_ALL_DESTINATIONS` - Los usuarios pueden eliminar toda la [!UICONTROL destinations] configuración de su cuenta de compañía.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Los usuarios pueden hacer todo (vista, creación, edición, eliminación) en su [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Los usuarios pueden hacer todo (vista, creación, edición y eliminación) en sus grupos [!UICONTROL Audience Lab] de prueba.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Los usuarios pueden crear segmentos.
* `DELETE_ALL_SEGMENTS` - Los usuarios pueden eliminar todos los segmentos configurados en su cuenta de compañía.
* `MAP_ALL_TO_DESTINATIONS` - Los usuarios pueden asignar cualquiera de los segmentos que pertenecen a su compañía a los destinos.
* `EDIT_ALL_SEGMENTS` - Los usuarios pueden editar todos los segmentos configurados en su cuenta de compañía.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Los usuarios pueden seleccionar segmentos como línea de base para los modelos.
* `VIEW_ALL_SEGMENTS` - Los usuarios pueden realizar la vista de todos los segmentos configurados en su cuenta de compañía.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Los usuarios pueden vista todas las señales capturadas en el Explorador [de datos](/help/using/features/data-explorer/data-explorer-overview.md).

## Casos de uso {#use-cases}

### Supervisión del acceso de los usuarios {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] puede ayudarle a supervisar el estado de inicio de sesión del usuario, proporcionándole una imagen clara de quién puede acceder a la instancia de Audience Manager.

Según los requisitos comerciales, puede habilitar y deshabilitar las cuentas de usuario según sea necesario.

![monitor-user-access](assets/monitor-user-access.png)

### Garantizar la protección de acceso para usuarios sensibles [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

Puede configurar [!UICONTROL Role-Based Access Control] en [!UICONTROL trait], segmentos y [!UICONTROL destination] niveles para cada grupo de usuarios.

Esta capacidad le ayuda a administrar la forma en que los usuarios vista, crean, leen, escriben y editan conjuntos de datos específicos, e incluso a restringir el acceso de los usuarios a conjuntos de datos que no deberían estar disponibles para ellos.

![access-protection](assets/access-protection.png)
