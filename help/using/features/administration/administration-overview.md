---
description: Las opciones del menú Administración permiten crear usuarios Audience Manager y asignarlos a grupos. También puede establecer límites de vista (características, segmentos, destinos y modelos).
keywords: rbac;RBAC;basado en roles;basado en roles;controles de acceso basados en roles
seo-description: Las opciones del menú Administración permiten crear usuarios Audience Manager y asignarlos a grupos. También puede establecer límites de vista (características, segmentos, destinos y modelos).
seo-title: Administración
solution: Audience Manager
title: Administración
topic: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
translation-type: tm+mt
source-git-commit: 55cb69bad1f369ed3b58bece54aebdca4b14f7a7
workflow-type: tm+mt
source-wordcount: '1203'
ht-degree: 2%

---


# [!UICONTROL Administration] (Controles RBAC)  {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> La administración de cuentas de usuario se está trasladando al [Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html). Para la migración de usuarios de inicio, se requiere que todos los clientes Audience Manager tomen inmediatamente las medidas necesarias descritas en este artículo: [Migración de usuarios Audience Manager a Admin Console](admin-console-migration.md).
> 
> Una vez que todos los clientes hayan migrado, las secciones de administración de usuarios de este documento desaparecerán.


Las opciones del menú [!UICONTROL Administration] le permiten crear usuarios Audience Manager y asignarlos a grupos. También puede establecer límites de vista (características, segmentos, destinos y modelos).

Los clientes empresariales que utilizan [!DNL Audience Manager] necesitan una plataforma de gestión de datos para todos sus datos, pero deben poder controlar la visibilidad de los diferentes elementos de datos en unidades de negocios específicas. Puede hacerlo mediante permisos de grupo, también denominados [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utiliza grupos para asignar permisos. Los permisos no se asignan a nivel de usuario. Los permisos de grupo están ligados a objetos ([!UICONTROL traits], segmentos, etc.) y a las acciones que puede realizar en esos objetos (edición, vista, etc.). Estos controles también están disponibles a través de las API de Audience Manager REST. Consulte [Administración de usuarios](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Administración de grupos](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) y [Administración de permisos](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) métodos de API.

## Crear usuarios {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> La administración de cuentas de usuario se está trasladando al [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Para la migración de usuarios de inicio, se requiere que todos los clientes Audience Manager tomen inmediatamente las medidas necesarias descritas en este artículo: [Migración de usuarios Audience Manager a Admin Console](admin-console-migration.md).
> 
> Una vez que todos los clientes hayan migrado, la sección de administración de usuarios de este documento desaparecerá.

Cree usuarios en [!DNL Audience Manager] y especifique los detalles del usuario, el estado de inicio de sesión y asigne usuarios a los grupos.

1. Haga clic **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Haga clic en ![](assets/icon_add.png) para mostrar la página [!UICONTROL Create New User].
1. En **[!UICONTROL User Details]**, rellene los campos:
   * **[!UICONTROL Username]:** Especifique un nombre de usuario único para Audience Manager.
   * **[!UICONTROL First Name]:** Especifique el nombre del usuario.
   * **[!UICONTROL Last Name]:** Especifique los apellidos del usuario.
   * **[!UICONTROL Email Address]:** Especifique la dirección de correo electrónico del usuario. [!DNL Audience Manager] no envía notificaciones regulares a los usuarios. [!DNL Audience Manager] los administradores tienen acceso a las direcciones de correo electrónico de los usuarios y pueden enviar mensajes manualmente a los usuarios según sea necesario. Por ejemplo, si un usuario olvida su contraseña, se utiliza la dirección de correo electrónico especificada en este campo para enviar una contraseña temporal e instrucciones para restablecer la contraseña.
   * **[!UICONTROL Phone Number]:** Especifique el número de teléfono del usuario.
   * **[!UICONTROL Is Admin]:** Especifique si este usuario es un  [!DNL Audience Manager] administrador. Los usuarios administradores pueden administrar usuarios (crear, editar, etc.) y grupos (crear, asignar permisos, etc.). Los usuarios que no son administradores pueden controlar únicamente sus propios perfiles de usuario, incluida la edición de sus direcciones de correo electrónico y el restablecimiento de sus propias contraseñas. Para obtener más información, consulte [Editar la configuración de su cuenta](../../features/administration/edit-account-settings.md).
1. En **[!UICONTROL Login]**, seleccione el estado que desee:
   * **[!UICONTROL Active]:Los usuarios**  activos pueden acceder  [!DNL Audience Manager] y obtener los permisos por pertenencia a grupos.
   * **[!UICONTROL Deactivated]:**  Los usuarios desactivados no pueden acceder  [!DNL Audience Manager] y no tienen permisos. Si desactiva los usuarios, su información de usuario permanecerá en [!DNL Audience Manager] y podrá reactivarla fácilmente, si es necesario. Si elimina usuarios, debe volver a crearlos si necesitan usar [!DNL Audience Manager] nuevamente en el futuro.
   * **[!UICONTROL Expired]:** La contraseña de un usuario tiene más de 90 días.
   * **[!UICONTROL Pending]:** El usuario tiene una contraseña temporal, ya sea después de restablecer una contraseña o como cuenta nueva, y aún no ha establecido una contraseña permanente.
   * **[!UICONTROL Locked Out]:** 5 intentos de inicio de sesión incorrectos bloquearán a un usuario.
1. En **[!UICONTROL Assigned Groups]**, en la lista desplegable, seleccione los grupos que desee asignar a este usuario.
Para obtener más información acerca de los grupos y permisos, consulte [Crear un grupo](../../features/administration/administration-overview.md#create-group).
1. Haga clic **[!UICONTROL Save]**.

## Cree un [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> La administración de cuentas de usuario se está trasladando al [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Para la migración de usuarios de inicio, recomendamos a todos los clientes Audience Manager que tomen inmediatamente las medidas necesarias descritas en este artículo: [Migración de usuarios Audience Manager a Admin Console](admin-console-migration.md).
> 
> Después de que todos los clientes hayan migrado, esta sección desaparecerá.

Un *grupo* es una colección de usuarios que comparten derechos de acceso a objetos [!UICONTROL destination], [!UICONTROL segment] y [!UICONTROL trait]. Puede limitar los grupos a objetos únicos únicamente o darles un acceso amplio a combinaciones de objetos diferentes.

<!-- t_create_groups.xml -->

Para crear un grupo:

1. Haga clic **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Haga clic ![](assets/icon_add.png) para abrir la página [!UICONTROL Group Settings].
3. En [!UICONTROL Group Details]:
   * Asigne un nombre al grupo.
   * Proporcione una breve descripción del grupo.
4. En [!UICONTROL Group Members], haga clic en un usuario de las opciones **[!UICONTROL Add Users]** para agregarlo al grupo.
5. En [!UICONTROL Group Permissions], seleccione una [característica](../../features/traits/trait-details-page.md), [segmento](../../features/segments/segments-purpose.md) o [destino](../../features/destinations/destinations.md) en **[!UICONTROL Add Object]**.
Se abre una ventana de permisos para el objeto seleccionado.
6. Seleccione la casilla de verificación de los permisos que desea que tengan los miembros del grupo.
7. *(Opcional)* Asigne  [permisos de comodines ](../../features/administration/administration-overview.md#wild-card-permissions) al grupo.
8. Haga clic **[!UICONTROL Save Group]**.

## Explicación de [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> La administración de cuentas de usuario se está trasladando al [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Para la migración de usuarios de inicio, recomendamos a todos los clientes Audience Manager que tomen inmediatamente las medidas necesarias descritas en este artículo: [Migración de usuarios Audience Manager a Admin Console](admin-console-migration.md).
> 
> Después de que todos los clientes hayan migrado, esta sección desaparecerá.

Simplifique la administración de derechos de grupo con [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] otorgue a los miembros del grupo acceso automático a cada origen de datos asociado a un  [!UICONTROL segment],  [!UICONTROL destination]o  [!UICONTROL trait]. En comparación, los permisos regulares sólo permiten asignar [!UICONTROL data sources] específicos a uno de estos objetos. Y, cuando agrega [!UICONTROL data sources] nuevos, los miembros del grupo no tienen acceso a esas nuevas fuentes.

Debe abrir los permisos de grupo y asignar los nuevos [!UICONTROL data sources] al grupo. [!UICONTROL Wild Card Permissions] le permite evitar este proceso de  [!UICONTROL data source] actualización manual. Los grupos con [!UICONTROL Wild Card Permissions] obtienen acceso a [!UICONTROL data sources] nuevos sin autorización explícita.

![](assets/wild-card.png)

Lea a continuación para ver una descripción de lo que significa cada [!UICONTROL wildcard permission]:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Los usuarios pueden seleccionar  [!UICONTROL traits] como línea de base para  [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Los usuarios pueden editar toda la  [!UICONTROL traits] configuración de su cuenta de compañía.
* `VIEW_ALL_TRAITS` - Los usuarios pueden realizar la vista de todas las  [!UICONTROL traits] configuraciones dentro de su cuenta de compañía.
* `DELETE_ALL_TRAITS` - Los usuarios pueden eliminar toda la  [!UICONTROL traits] configuración de su cuenta de compañía.
* `CREATE_ALL_ALGO_TRAITS` - Los usuarios pueden crear  [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Los usuarios pueden agregar cualquiera de los  [!UICONTROL traits] miembros de su compañía a  [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Los usuarios pueden crear  [!UICONTROL traits].

**[!UICONTROL Reports]**

* `PTRREPORTS` - Esto  [!UICONTROL wildcard permission] se refiere a la funcionalidad obsoleta y se eliminará de la interfaz de usuario del Audience Manager en breve.

**[!UICONTROL Models]**

* `VIEW_MODELS` - Los usuarios tienen permiso para  [!UICONTROL models] pertenecer a su compañía.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Los usuarios pueden vista de todos los  [!UICONTROL derived signals] miembros de su compañía.
* `CREATE_DERIVED_SIGNALS` - Los usuarios pueden crear  [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Los usuarios pueden editar toda la  [!UICONTROL derived signals] pertenencia a su compañía.
* `DELETE_DERIVED_SIGNALS` - Los usuarios pueden eliminar cualquier  [!UICONTROL derived signals] pertenencia a su compañía.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Los usuarios pueden editar toda la  [!UICONTROL destinations] configuración de su cuenta de compañía.
* `CREATE_DESTINATIONS` - Los usuarios pueden crear  [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Los usuarios pueden realizar la vista de toda la  [!UICONTROL destinations] configuración dentro de su cuenta de compañía.
* `DELETE_ALL_DESTINATIONS` - Los usuarios pueden eliminar toda la  [!UICONTROL destinations] configuración de su cuenta de compañía.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Los usuarios pueden hacer todo (vista, creación, edición, eliminación) en su  [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Los usuarios pueden hacer todo (vista, creación, edición, eliminación) en los grupos de  [!UICONTROL Audience Lab] prueba.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Los usuarios pueden crear segmentos.
* `DELETE_ALL_SEGMENTS` - Los usuarios pueden eliminar todos los segmentos configurados en su cuenta de compañía.
* `MAP_ALL_TO_DESTINATIONS` - Los usuarios pueden asignar cualquiera de los segmentos que pertenecen a su compañía a los destinos.
* `EDIT_ALL_SEGMENTS` - Los usuarios pueden editar todos los segmentos configurados en su cuenta de compañía.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Los usuarios pueden seleccionar segmentos como línea de base para los modelos.
* `VIEW_ALL_SEGMENTS` - Los usuarios pueden realizar la vista de todos los segmentos configurados en su cuenta de compañía.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Los usuarios pueden vista todas las señales capturadas en la  [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Casos de uso {#use-cases}

### Monitoreo del acceso del usuario {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] puede ayudarle a supervisar el estado de inicio de sesión del usuario, proporcionándole una imagen clara de quién puede acceder a la instancia de Audience Manager.

Según los requisitos comerciales, puede habilitar y deshabilitar las cuentas de usuario según sea necesario.

![monitor-user-access](assets/monitor-user-access.png)

### Garantizar la protección de acceso para [!UICONTROL Data Sources] {#protect-sensitive-data-sources} sensibles

Puede configurar [!UICONTROL Role-Based Access Control] en [!UICONTROL trait], segmento y [!UICONTROL destination] nivel para cada grupo de usuarios.

Esta capacidad le ayuda a administrar la forma en que los usuarios vista, crean, leen, escriben y editan conjuntos de datos específicos, e incluso a restringir el acceso de los usuarios a conjuntos de datos que no deberían estar disponibles para ellos.

![access-protection](assets/access-protection.png)
