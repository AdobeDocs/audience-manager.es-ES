---
description: Las opciones del menú Administración permiten crear usuarios de Audience Manager y asignarlos a grupos. También puede establecer límites de vista (características, segmentos, destinos y modelos).
keywords: rbac;RBAC;basado en roles;basado en roles;controles de acceso basados en roles
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: Administración
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: c29e581c736e03066df7d0698d4ea384e14db467
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 2%

---

# [!UICONTROL Administration] (Controles RBAC) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> La administración de cuentas de usuario se está trasladando a [Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html). Para iniciar la migración de usuarios, pedimos a todos los clientes Audience Manager que tomen inmediatamente las medidas necesarias que se describen en este artículo: [Migración de usuarios de Audience Manager a Admin Console](admin-console-migration.md).
> 
> Cuando se hayan migrado todos los clientes, las secciones de administración de usuarios de este documento desaparecerán.

>[!IMPORTANT]
>
> Antes de usar [!DNL RBAC], esta función debe habilitarse mediante Adobe para su organización. Póngase en contacto con el equipo de su cuenta para solicitar [!DNL RBAC] o póngase en contacto con el Servicio de atención al cliente.


Las opciones de [!UICONTROL Administration] El menú permite crear usuarios de Audience Manager y asignarlos a grupos. También puede establecer límites de vista (características, segmentos, destinos y modelos).

Clientes empresariales que utilizan [!DNL Audience Manager] necesitan una plataforma de gestión de datos para todos sus datos, pero deben poder controlar la visibilidad de los diferentes elementos de datos para unidades empresariales específicas. Puede realizar esto mediante permisos de grupo, también denominados [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utiliza grupos para asignar permisos. Los permisos no se asignan al nivel de usuario. Los permisos de grupo están vinculados a objetos ([!UICONTROL traits], segmentos, etc.) y a acciones que se pueden realizar en esos objetos (editar, ver, etc.). Estos controles también están disponibles a través de las API de REST de Audience Manager. Consulte [Administración de usuarios](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Administración de grupos](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md), y [Administración de permisos](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) Métodos de API.

## Crear usuarios {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> La administración de cuentas de usuario se está trasladando a [Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html). Para iniciar la migración de usuarios, pedimos a todos los clientes Audience Manager que tomen inmediatamente las medidas necesarias que se describen en este artículo: [Migración de usuarios de Audience Manager a Admin Console](admin-console-migration.md).
> 
> Una vez migrados todos los clientes, la sección de administración de usuarios de este documento desaparecerá.
> 
Creación de usuarios en [!DNL Audience Manager] y especifique los detalles del usuario, el estado de inicio de sesión y asigne usuarios a grupos.

1. Haga clic **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Clic ![](assets/icon_add.png) para mostrar el [!UICONTROL Create New User] página.
1. En **[!UICONTROL User Details]**, rellene los campos:
   * **[!UICONTROL Username]:** Especifique un nombre de usuario único para el Audience Manager.
   * **[!UICONTROL First Name]:** Especifique el nombre del usuario.
   * **[!UICONTROL Last Name]:** Especifique el apellido del usuario.
   * **[!UICONTROL Email Address]:** Especifique la dirección de correo electrónico del usuario. [!DNL Audience Manager] no envía notificaciones regulares a los usuarios. [!DNL Audience Manager] los administradores tienen acceso a las direcciones de correo electrónico de los usuarios y pueden enviarlos manualmente según sea necesario. Por ejemplo, si un usuario olvida su contraseña, la dirección de correo electrónico especificada en este campo se utiliza para enviar una contraseña temporal e instrucciones para restablecerla.
   * **[!UICONTROL Phone Number]:** Especifique el número de teléfono del usuario.
   * **[!UICONTROL Is Admin]:** Especifique si este usuario es un [!DNL Audience Manager] administrador. Los usuarios administradores pueden administrar usuarios (crear, editar, etc.) y grupos (crear, asignar permisos, etc.). Los usuarios no administradores solo pueden controlar sus propios perfiles de usuario, incluida la edición de sus direcciones de correo electrónico y el restablecimiento de sus propias contraseñas. Para obtener más información, consulte [Editar la configuración de la cuenta](../../features/administration/edit-account-settings.md).
1. En **[!UICONTROL Login]**, seleccione el estado deseado:
   * **[!UICONTROL Active]:**  Los usuarios activos pueden acceder a [!DNL Audience Manager] y tienen los permisos otorgados por la pertenencia al grupo.
   * **[!UICONTROL Deactivated]:**  Los usuarios desactivados no pueden acceder [!DNL Audience Manager] y no tienen ningún permiso. Si desactiva usuarios, su información de usuario permanece en [!DNL Audience Manager] y puede reactivarlos fácilmente, si es necesario. Si elimina usuarios, debe volver a crearlos si necesitan utilizar [!DNL Audience Manager] otra vez en el futuro.
   * **[!UICONTROL Expired]:** La contraseña de un usuario tiene más de 90 días.
   * **[!UICONTROL Pending]:** El usuario tiene una contraseña temporal, ya sea como tras un restablecimiento de contraseña o como una cuenta completamente nueva, y aún no ha establecido una contraseña permanente.
   * **[!UICONTROL Locked Out]:** 5 intentos de inicio de sesión incorrectos bloquearán al usuario.
1. En **[!UICONTROL Assigned Groups]**, en la lista desplegable, seleccione los grupos a los que desee asignar este usuario.
Para obtener más información sobre los grupos y los permisos, consulte [Crear un grupo](../../features/administration/administration-overview.md#create-group).
1. Haga clic **[!UICONTROL Save]**.

## Cree un [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> La administración de cuentas de usuario se está trasladando a [Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html). Para iniciar la migración de usuarios, recomendamos a todos los clientes Audience Manager que tomen inmediatamente las medidas necesarias que se describen en este artículo: [Migración de usuarios de Audience Manager a Admin Console](admin-console-migration.md).
> 
> Cuando se hayan migrado todos los clientes, esta sección desaparecerá.

A *grupo* es una colección de usuarios que comparten derechos de acceso con [!UICONTROL destination], [!UICONTROL segment], y [!UICONTROL trait] objetos. Puede limitar los grupos a objetos únicos o darles un amplio acceso a combinaciones de objetos diferentes.

<!-- t_create_groups.xml -->

Para crear un grupo:

1. Haga clic **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Clic  ![](assets/icon_add.png) para abrir [!UICONTROL Group Settings] página.
3. En [!UICONTROL Group Details]:
   * Nombre el grupo.
   * Proporcione una breve descripción del grupo.
4. Entrada [!UICONTROL Group Members], haga clic en un usuario desde **[!UICONTROL Add Users]** opciones para agregarlas al grupo.
5. Entrada [!UICONTROL Group Permissions], seleccione una [rasgo](../../features/traits/trait-details-page.md), [segmento](../../features/segments/segments-purpose.md), o [destino](../../features/destinations/destinations.md) de **[!UICONTROL Add Object]**.
Se abrirá una ventana de permisos para el objeto seleccionado.
6. Active la casilla de verificación de los permisos que desea que tengan los miembros del grupo.
7. *(Opcional)* Asignar [Permisos de comodines](../../features/administration/administration-overview.md#wild-card-permissions) al grupo.
8. Haga clic **[!UICONTROL Save Group]**.

## Comprensión [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> La administración de cuentas de usuario se está trasladando a [Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html). Para iniciar la migración de usuarios, recomendamos a todos los clientes Audience Manager que tomen inmediatamente las medidas necesarias que se describen en este artículo: [Migración de usuarios de Audience Manager a Admin Console](admin-console-migration.md).
> 
> Cuando se hayan migrado todos los clientes, esta sección desaparecerá.

Simplifique la administración de derechos de grupo con [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] dar a los miembros del grupo acceso automático a cada fuente de datos asociada a un [!UICONTROL segment], [!UICONTROL destination], o [!UICONTROL trait]. Por comparación, los permisos regulares solo le permiten asignar permisos específicos [!UICONTROL data sources] a uno de estos objetos. Y, cuando agregue un nuevo [!UICONTROL data sources]Sin embargo, los miembros del grupo no tienen acceso a esas nuevas fuentes.

Debe abrir los permisos de grupo y asignar los nuevos [!UICONTROL data sources] al grupo. [!UICONTROL Wild Card Permissions] le permite evitar este manual [!UICONTROL data source] proceso de actualización. Grupos con [!UICONTROL Wild Card Permissions] obtenga acceso a nuevos [!UICONTROL data sources] sin autorización explícita.

![](assets/wild-card.png)

Lea a continuación una descripción de lo que cada [!UICONTROL wildcard permission] significa:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Los usuarios pueden seleccionar [!UICONTROL traits] como línea de base para [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Los usuarios pueden editar todo [!UICONTROL traits] configuradas en su cuenta de compañía.
* `VIEW_ALL_TRAITS` - Los usuarios pueden ver todo [!UICONTROL traits] configuradas en su cuenta de compañía.
* `DELETE_ALL_TRAITS` - Los usuarios pueden eliminar todo [!UICONTROL traits] configuradas en su cuenta de compañía.
* `CREATE_ALL_ALGO_TRAITS` - Los usuarios pueden crear [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Los usuarios pueden agregar cualquiera de las [!UICONTROL traits] que pertenecen a su compañía a [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Los usuarios pueden crear [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS` - Los usuarios tienen permiso para ver [!UICONTROL models] que pertenecen a su compañía.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Los usuarios pueden ver todas las [!UICONTROL derived signals] que pertenecen a su compañía.
* `CREATE_DERIVED_SIGNALS` - Los usuarios pueden crear [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Los usuarios pueden editar todos los [!UICONTROL derived signals] que pertenecen a su compañía.
* `DELETE_DERIVED_SIGNALS` - Los usuarios pueden eliminar cualquiera de las [!UICONTROL derived signals] que pertenecen a su compañía.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Los usuarios pueden editar todos los [!UICONTROL destinations] configuradas en su cuenta de compañía.
* `CREATE_DESTINATIONS` - Los usuarios pueden crear [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Los usuarios pueden ver todas las [!UICONTROL destinations] configuradas en su cuenta de compañía.
* `DELETE_ALL_DESTINATIONS` - Los usuarios pueden eliminar todos los [!UICONTROL destinations] configuradas en su cuenta de compañía.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Los usuarios pueden hacer de todo (ver, crear, editar, eliminar) en su [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Los usuarios pueden hacer de todo (ver, crear, editar, eliminar) en su [!UICONTROL Audience Lab] grupos de prueba.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Los usuarios pueden crear segmentos.
* `DELETE_ALL_SEGMENTS` : Los usuarios pueden eliminar todos los segmentos configurados en su cuenta de compañía.
* `MAP_ALL_TO_DESTINATIONS` : Los usuarios pueden asignar cualquiera de los segmentos que pertenecen a su compañía a destinos.
* `EDIT_ALL_SEGMENTS` : Los usuarios pueden editar todos los segmentos configurados en su cuenta de empresa.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Los usuarios pueden seleccionar segmentos como línea de base para los modelos.
* `VIEW_ALL_SEGMENTS` : Los usuarios pueden ver todos los segmentos configurados en su cuenta de compañía.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Los usuarios pueden ver todas las señales captadas en [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Casos de uso {#use-cases}

### Supervisión del acceso de los usuarios {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] puede ayudarle a monitorizar el estado de inicio de sesión del usuario, lo que le ofrece una imagen clara de quién puede acceder a la instancia de Audience Manager.

Según los requisitos de su empresa, puede habilitar y deshabilitar cuentas de usuario según sea necesario.

![monitor-user-access](assets/monitor-user-access.png)

### Garantizar la protección de acceso para los [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

Puede configurar [!UICONTROL Role-Based Access Control] en [!UICONTROL trait], segmento y [!UICONTROL destination] nivel, para cada grupo de usuarios.

Esta capacidad le ayuda a administrar la forma en que los usuarios ven, crean, leen, escriben y editan conjuntos de datos específicos, e incluso a restringir el acceso de los usuarios a conjuntos de datos que no deberían estar disponibles para ellos.

![protección de acceso](assets/access-protection.png)
