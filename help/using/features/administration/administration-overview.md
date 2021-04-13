---
description: Las opciones del menú Administración permiten crear usuarios Audience Manager y asignarlos a grupos. También puede ver límites (características, segmentos, destinos y modelos).
keywords: rbac;RBAC;basados en funciones;basados en roles;controles de acceso basados en roles
seo-description: Las opciones del menú Administración permiten crear usuarios Audience Manager y asignarlos a grupos. También puede ver límites (características, segmentos, destinos y modelos).
seo-title: Administración
solution: Audience Manager
title: Administración
topic-edit: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administración
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1204'
ht-degree: 2%

---

# [!UICONTROL Administration] (Controles RBAC)  {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> La administración de cuentas de usuario se está trasladando al [Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html). Para iniciar la migración de usuarios, se requiere que todos los clientes Audience Manager tomen inmediatamente las medidas necesarias que se describen en este artículo: [migración de usuarios Audience Manager al Admin Console](admin-console-migration.md).
> 
> Una vez que todos los clientes hayan migrado, las secciones de administración de usuarios de este documento desaparecerán.


Las opciones del menú [!UICONTROL Administration] permiten crear usuarios Audience Manager y asignarlos a grupos. También puede ver límites (características, segmentos, destinos y modelos).

Los clientes empresariales que utilizan [!DNL Audience Manager] necesitan una plataforma de administración de datos para todos sus datos, pero deben poder controlar la visibilidad de los diferentes elementos de datos en unidades de negocio específicas. Puede hacerlo mediante permisos de grupo, también denominados [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utiliza grupos para asignar permisos. Los permisos no se asignan en el nivel de usuario. Los permisos de grupo están vinculados a objetos ([!UICONTROL traits], segmentos, etc.) y a las acciones que se pueden realizar en esos objetos (edición, vista, etc.). Estos controles también están disponibles a través de las API de REST del Audience Manager. Consulte los métodos de API [Administración de usuarios](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Administración de grupos](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) y [Administración de permisos](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md).

## Crear usuarios {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> La administración de cuentas de usuario se está trasladando al [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Para iniciar la migración de usuarios, se requiere que todos los clientes Audience Manager tomen inmediatamente las medidas necesarias que se describen en este artículo: [migración de usuarios Audience Manager al Admin Console](admin-console-migration.md).
> 
> Una vez que todos los clientes hayan migrado, la sección de administración de usuarios de este documento desaparecerá.

Cree usuarios en [!DNL Audience Manager] y especifique los detalles del usuario, el estado de inicio de sesión y asigne usuarios a grupos.

1. Haga clic **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Haga clic en ![](assets/icon_add.png) para mostrar la página [!UICONTROL Create New User].
1. En **[!UICONTROL User Details]**, rellene los campos:
   * **[!UICONTROL Username]:** especifique un nombre de usuario único para el Audience Manager.
   * **[!UICONTROL First Name]:** especifique el nombre del usuario.
   * **[!UICONTROL Last Name]:** especifique los apellidos del usuario.
   * **[!UICONTROL Email Address]:** especifique la dirección de correo electrónico del usuario. [!DNL Audience Manager] no envía notificaciones regulares a los usuarios. [!DNL Audience Manager] los administradores tienen acceso a las direcciones de correo electrónico de los usuarios y pueden enviar manualmente los mensajes de correo electrónico que necesiten. Por ejemplo, si un usuario olvida su contraseña, se utiliza la dirección de correo electrónico especificada en este campo para enviar una contraseña temporal e instrucciones para restablecer la contraseña.
   * **[!UICONTROL Phone Number]:** especifique el número de teléfono del usuario.
   * **[!UICONTROL Is Admin]:** especifique si este usuario es  [!DNL Audience Manager] administrador. Los usuarios administradores pueden administrar usuarios (crear, editar, etc.) y grupos (crear, asignar permisos, etc.). Los usuarios no administradores solo pueden controlar sus propios perfiles de usuario, como editar sus direcciones de correo electrónico y restablecer sus propias contraseñas. Para obtener más información, consulte [Editar la configuración de la cuenta](../../features/administration/edit-account-settings.md).
1. En **[!UICONTROL Login]**, seleccione el estado deseado:
   * **[!UICONTROL Active]:**  Los usuarios activos pueden acceder  [!DNL Audience Manager] y obtener los permisos otorgados por la pertenencia a un grupo.
   * **[!UICONTROL Deactivated]:**  Los usuarios desactivados no pueden acceder a  [!DNL Audience Manager] y no tienen permisos. Si desactiva usuarios, su información de usuario permanece en [!DNL Audience Manager] y puede reactivarlos fácilmente si es necesario. Si elimina usuarios, debe volver a crearlos si necesitan usar [!DNL Audience Manager] de nuevo en el futuro.
   * **[!UICONTROL Expired]:** La contraseña de un usuario tiene más de 90 días.
   * **[!UICONTROL Pending]:** El usuario tiene una contraseña temporal, ya sea después de restablecer una contraseña o como cuenta nueva, y aún no ha establecido una contraseña permanente.
   * **[!UICONTROL Locked Out]:** 5 intentos de inicio de sesión incorrectos bloquearán a un usuario.
1. En **[!UICONTROL Assigned Groups]**, en la lista desplegable, seleccione los grupos a los que desee asignar a este usuario.
Para obtener más información sobre los grupos y permisos, consulte [Crear un grupo](../../features/administration/administration-overview.md#create-group).
1. Haga clic **[!UICONTROL Save]**.

## Cree un [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> La administración de cuentas de usuario se está trasladando al [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Para iniciar la migración de usuarios, recomendamos a todos los clientes Audience Manager que tomen inmediatamente las medidas necesarias que se describen en este artículo: [migración de usuarios Audience Manager al Admin Console](admin-console-migration.md).
> 
> Una vez que todos los clientes hayan migrado, esta sección desaparecerá.

Un *grupo* es una colección de usuarios que comparten derechos de acceso a los objetos [!UICONTROL destination], [!UICONTROL segment] y [!UICONTROL trait]. Puede limitar los grupos a objetos únicos únicamente o darles un acceso amplio a combinaciones de objetos diferentes.

<!-- t_create_groups.xml -->

Para crear un grupo:

1. Haga clic **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Haga clic en ![](assets/icon_add.png) para abrir la página [!UICONTROL Group Settings].
3. En [!UICONTROL Group Details]:
   * Asigne un nombre al grupo.
   * Proporcione una breve descripción del grupo.
4. En [!UICONTROL Group Members], haga clic en un usuario desde las opciones **[!UICONTROL Add Users]** para agregarlo al grupo.
5. En [!UICONTROL Group Permissions], seleccione un [rasgo](../../features/traits/trait-details-page.md), [segmento](../../features/segments/segments-purpose.md) o [destino](../../features/destinations/destinations.md) en **[!UICONTROL Add Object]**.
Se abrirá una ventana de permisos para el objeto seleccionado.
6. Seleccione la casilla de los permisos que desea que tengan los miembros del grupo.
7. *(Opcional)* Asigne  [permisos de ](../../features/administration/administration-overview.md#wild-card-permissions) comodines al grupo.
8. Haga clic **[!UICONTROL Save Group]**.

## Explicación de [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> La administración de cuentas de usuario se está trasladando al [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Para iniciar la migración de usuarios, recomendamos a todos los clientes Audience Manager que tomen inmediatamente las medidas necesarias que se describen en este artículo: [migración de usuarios Audience Manager al Admin Console](admin-console-migration.md).
> 
> Una vez que todos los clientes hayan migrado, esta sección desaparecerá.

Simplifique la administración de derechos de grupo con [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] otorgue a los miembros del grupo acceso automático a cada fuente de datos asociada a un  [!UICONTROL segment],  [!UICONTROL destination] o  [!UICONTROL trait]. En comparación, los permisos regulares solo permiten asignar [!UICONTROL data sources] específicos a uno de estos objetos. Y, cuando agrega [!UICONTROL data sources] nuevos, los miembros del grupo no tienen acceso a esas nuevas fuentes.

Debe abrir los permisos de grupo y asignar los nuevos [!UICONTROL data sources] al grupo. [!UICONTROL Wild Card Permissions] le permite evitar este proceso de  [!UICONTROL data source] actualización manual. Los grupos con [!UICONTROL Wild Card Permissions] obtienen acceso a [!UICONTROL data sources] nuevos sin autorización explícita.

![](assets/wild-card.png)

Lea a continuación para ver una descripción de lo que significa cada [!UICONTROL wildcard permission]:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Los usuarios pueden seleccionar  [!UICONTROL traits] como línea de base para  [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Los usuarios pueden editar todas las  [!UICONTROL traits] configuraciones de su cuenta de empresa.
* `VIEW_ALL_TRAITS` - Los usuarios pueden ver toda la  [!UICONTROL traits] configuración de su cuenta de empresa.
* `DELETE_ALL_TRAITS` - Los usuarios pueden eliminar toda la  [!UICONTROL traits] configuración de su cuenta de empresa.
* `CREATE_ALL_ALGO_TRAITS` - Los usuarios pueden crear  [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Los usuarios pueden agregar cualquiera de los  [!UICONTROL traits] miembros de su empresa a  [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Los usuarios pueden crear  [!UICONTROL traits].

**[!UICONTROL Reports]**

* `PTRREPORTS` : hace  [!UICONTROL wildcard permission] referencia a una funcionalidad obsoleta y se eliminará de la interfaz de usuario del Audience Manager en breve.

**[!UICONTROL Models]**

* `VIEW_MODELS` - Los usuarios tienen permiso para ver si  [!UICONTROL models] pertenecen a su empresa.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Los usuarios pueden ver todas las  [!UICONTROL derived signals] pertenencias a su empresa.
* `CREATE_DERIVED_SIGNALS` - Los usuarios pueden crear  [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Los usuarios pueden editar todas las  [!UICONTROL derived signals] pertenencias a su empresa.
* `DELETE_DERIVED_SIGNALS` - Los usuarios pueden eliminar cualquiera de los  [!UICONTROL derived signals] miembros de su empresa.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Los usuarios pueden editar toda la  [!UICONTROL destinations] configuración de su cuenta de empresa.
* `CREATE_DESTINATIONS` - Los usuarios pueden crear  [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Los usuarios pueden ver toda la  [!UICONTROL destinations] configuración de su cuenta de empresa.
* `DELETE_ALL_DESTINATIONS` - Los usuarios pueden eliminar toda la  [!UICONTROL destinations] configuración de su cuenta de empresa.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Los usuarios pueden hacer todo (ver, crear, editar, eliminar) en su  [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Los usuarios pueden hacer todo (ver, crear, editar o eliminar) en sus grupos de  [!UICONTROL Audience Lab] prueba.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Los usuarios pueden crear segmentos.
* `DELETE_ALL_SEGMENTS` - Los usuarios pueden eliminar todos los segmentos configurados en su cuenta de empresa.
* `MAP_ALL_TO_DESTINATIONS` : los usuarios pueden asignar cualquiera de los segmentos que pertenecen a su empresa a destinos.
* `EDIT_ALL_SEGMENTS` - Los usuarios pueden editar todos los segmentos configurados en su cuenta de empresa.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Los usuarios pueden seleccionar segmentos como línea de base para los modelos.
* `VIEW_ALL_SEGMENTS` - Los usuarios pueden ver todos los segmentos configurados en su cuenta de empresa.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Los usuarios pueden ver todas las señales capturadas en la  [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Casos de uso {#use-cases}

### Monitorización del acceso de usuario {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] puede ayudarle a supervisar el estado de inicio de sesión del usuario, lo que le ofrece una imagen clara de quién puede acceder a la instancia de Audience Manager.

Según sus necesidades comerciales, puede habilitar y deshabilitar las cuentas de usuario según sea necesario.

![monitor-user-access](assets/monitor-user-access.png)

### Garantizar la protección de acceso para [!UICONTROL Data Sources] {#protect-sensitive-data-sources} confidenciales

Puede configurar [!UICONTROL Role-Based Access Control] en el nivel [!UICONTROL trait], segmento y [!UICONTROL destination] para cada grupo de usuarios.

Esta capacidad le ayuda a administrar la forma en que los usuarios ven, crean, leen, escriben y editan conjuntos de datos específicos, e incluso a restringir el acceso de los usuarios a conjuntos de datos que no deberían estar disponibles para ellos.

![protección de acceso](assets/access-protection.png)
