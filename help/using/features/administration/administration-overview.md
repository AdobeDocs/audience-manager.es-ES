---
description: Las opciones del menú Administración permiten crear usuarios de Audience Manager y asignarlos a grupos. También puede ver los límites (características, segmentos, destinos y modelos).
keywords: rbac; RBAC; función basada en; basado en roles; controles de acceso basados en roles
seo-description: Las opciones del menú Administración permiten crear usuarios de Audience Manager y asignarlos a grupos. También puede ver los límites (características, segmentos, destinos y modelos).
seo-title: Administración
solution: Audience Manager
title: Administración
topic: API DIL
uuid: 498 e 0316-cf 1 b -43 e 9-88 ba -338 ee 0 daf 225
translation-type: tm+mt
source-git-commit: 5d66c44a9072129de9da69918e9eeda2e18ccb22

---


# Administration (RBAC Controls) {#administration}

![](assets/rbac-controls.png)

The options under the [!UICONTROL Administration] menu let you create Audience Manager users and assign them to groups. También puede ver los límites (características, segmentos, destinos y modelos).

Enterprise customers using [!DNL Audience Manager] need one data management platform for all of their data, but must be able to control the visibility of the different data elements to specific business units. You can accomplish this using group permissions, also referred to as [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utiliza grupos para asignar permisos. Los permisos no se asignan a nivel de usuario. Los permisos de grupo están vinculados a objetos (características, segmentos, etc.) y acciones que puede realizar en estos objetos (editar, ver, etc.). Estos controles también están disponibles a través de las API REST de Audience Manager. See [User Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Group Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md), and [Permissions Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API methods.

## Create Users {#create-users}

<!-- t_create_users.xml -->

Create users in [!DNL Audience Manager] and specify user details, login status, and assign users to groups.

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Users]**.
1. Click ![](assets/icon_add.png) to display the [!UICONTROL Create New User] page.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **Nombre de usuario:** Especifique un nombre de usuario exclusivo para Audience Manager.
   * **Nombre:** Especifique el nombre del usuario.
   * **Apellidos:** Especifique el apellido del usuario.
   * **Dirección de correo electrónico:** Especifique la dirección de correo electrónico del usuario. [!DNL Audience Manager] no envía notificación regular a los usuarios. [!DNL Audience Manager] los administradores tienen acceso a las direcciones de correo electrónico de los usuarios y pueden enviar por correo electrónico manualmente a los usuarios según sea necesario. Por ejemplo, si un usuario olvida su contraseña, la dirección de correo electrónico especificada en este campo se utiliza para enviar una contraseña temporal e instrucciones para restablecer la contraseña.
   * **Número de teléfono:** Especifique el número de teléfono del usuario.
   * **Es administrador:** Especifique si este usuario es [!DNL Audience Manager] administrador. Los usuarios administradores pueden administrar usuarios (crear, editar, etc.) y grupos (crear, asignar permisos, etc.). Los usuarios no administradores solo pueden controlar sus propios perfiles de usuario, como editar sus direcciones de correo electrónico y restablecer sus propias contraseñas. For more information, see [Edit Your Account Settings](../../features/administration/edit-account-settings.md).
1. Under **[!UICONTROL Login]**, select the desired status:
   * **Activo:** Los usuarios activos pueden acceder [!DNL Audience Manager] y tener los permisos concedidos por la pertenencia a grupos.
   * **Desactivado:** Los usuarios desactivados no tienen acceso [!DNL Audience Manager] y no tienen permisos. If you deactivate users, their user information remains in [!DNL Audience Manager] and you can simple reactivate them, if necessary. If you remove users, you must re-create them if they need to use [!DNL Audience Manager] again in the future.
   * **Caducado:** La contraseña de un usuario tiene más de 90 días.
   * **Pendiente:** El usuario tiene una contraseña temporal, ya sea como una contraseña o como una cuenta nueva, y todavía no ha establecido una contraseña permanente.
   * **Bloqueado:** 5 intentos de inicio de sesión incorrectos bloquearán a un usuario.
1. Under **[!UICONTROL Assigned Groups]**, from the drop-down list, select the desired groups to which you want to assign this user.
For more information about groups and permissions, see [Create a Group](../../features/administration/administration-overview.md#create-group).
1. Haga clic en **[!UICONTROL Save]**.

## Creación de grupos {#create-group}

*Un grupo* es una colección de usuarios que comparten derechos de acceso a objetos de destino, segmentos y características. Solo puede limitar grupos a objetos individuales o proporcionarles acceso amplio a combinaciones de diferentes objetos.

<!-- t_create_groups.xml -->

Para crear un grupo:

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Groups]**.
1. Click  ![](assets/icon_add.png) to open the [!UICONTROL Group Settings] page.
1. En [!UICONTROL Group Details]:
   * Asigne un nombre al grupo.
   * Proporcione una breve descripción del grupo.
1. In [!UICONTROL Group Members], click a user from **[!UICONTROL Add Users]** options to add them to the group.
1. In [!UICONTROL Group Permissions], select a [trait](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md), or [destination](../../features/destinations/destinations.md) from **[!UICONTROL Add Object]**.
Se abre una ventana de permisos para el objeto seleccionado.
1. Seleccione la casilla de verificación de los permisos que desea que tengan los miembros del grupo.
1. *(Opcional)* Asigne [permisos de comodines](../../features/administration/administration-overview.md#wild-card-permissions) al grupo.
1. Haga clic en **[!UICONTROL Save Group]**.

## Understanding Wild Card Permissions {#wild-card-permissions}

Simplify group rights management with [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] dar a los miembros del grupo acceso automático a cada fuente de datos asociada a un segmento, destino o característica. Por comparación, los permisos normales sólo permiten asignar fuentes de datos específicas a uno de estos objetos. Y, cuando agrega nuevas fuentes de datos, los miembros del grupo no obtienen acceso a esas nuevas fuentes.

Debe abrir los permisos de grupo y asignar esas nuevas fuentes de datos al grupo. [!UICONTROL Wild Card Permissions] permite evitar este proceso de actualización manual de fuentes de datos. Groups with [!UICONTROL Wild Card Permissions] get access to new data sources without explicit authorization.

![](assets/wild-card.png)

Lea más abajo para obtener una descripción del significado de cada comodín:

**Rasgo**

* `MAP_ALL_TRAITS_TO_MODELS` - Los usuarios pueden seleccionar características como punto de referencia para los modelos.
* `EDIT_ALL_TRAITS` - Los usuarios pueden editar todas las características pertenecientes a su empresa (PID).
* `VIEW_ALL_TRAITS` - Los usuarios pueden ver todas las características pertenecientes a su empresa (PID).
* `DELETE_ALL_TRAITS` - Los usuarios pueden eliminar todas las características que pertenecen a su empresa (PID).
* `CREATE_ALL_ALGO_TRAITS` - Los usuarios pueden crear características algorítmicas.
* `MAP_ALL_TO_SEGMENTS` - Los usuarios pueden agregar cualquiera de las características pertenecientes a su empresa a segmentos.
* `CREATE_ALL_TRAITS` - Los usuarios pueden crear características.

**Informes**

* `PTRREPORTS` - Este permiso comodín se refiere a la funcionalidad obsoleta y se eliminará de la interfaz de usuario de Audience Manager en breve.

**Modelos**

* `VIEW_MODELS` - Los usuarios tienen permiso para ver modelos pertenecientes a su empresa.

**Señales derivadas**

* `VIEW_DERIVED_SIGNALS` - Los usuarios pueden ver todas las señales derivadas pertenecientes a su empresa.
* `CREATE_DERIVED_SIGNALS` - Los usuarios pueden crear señales derivadas.
* `EDIT_DERIVED_SIGNALS` - Los usuarios pueden editar todas las señales derivadas pertenecientes a su empresa.
* `DELETE_DERIVED_SIGNALS` - Los usuarios pueden eliminar cualquiera de las señales derivadas que pertenecen a su empresa.

**Destino**

* `EDIT_ALL_DESTINATIONS` - Los usuarios pueden editar todo el destino de la cuenta de la empresa.
* `CREATE_DESTINATIONS` - Los usuarios pueden crear destinos.
* `VIEW_ALL_DESTINATIONS` - Los usuarios pueden ver todos los destinos configurados dentro de su cuenta de empresa.
* `DELETE_ALL_DESTINATIONS` - Los usuarios pueden eliminar todos los destinos configurados dentro de su cuenta de empresa.

**Etiquetas**

* `VIEW_TAGS` - Los usuarios pueden hacer todo (ver, crear, editar, eliminar) en sus contenedores de etiquetas.

**Audience Lab**

* `MANAGE_SEGMENT_TEST_GROUPS` - Los usuarios pueden hacer todo (ver, crear, editar, eliminar) en los grupos de prueba de Audience Lab.

**Segmento**

* `CREATE_ALL_SEGMENTS` - Los usuarios pueden crear segmentos.
* `DELETE_ALL_SEGMENTS` - Los usuarios pueden eliminar todos los segmentos configurados dentro de su cuenta de empresa.
* `MAP_ALL_TO_DESTINATIONS` - Los usuarios pueden asignar cualquiera de los segmentos pertenecientes a su empresa a destinos.
* `EDIT_ALL_SEGMENTS` - Los usuarios pueden editar todos los segmentos configurados en su cuenta de empresa.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Los usuarios pueden seleccionar segmentos como punto de referencia para los modelos.
* `VIEW_ALL_SEGMENTS` - Los usuarios pueden ver todos los segmentos configurados dentro de su cuenta de empresa.

**Señales**

* `VIEW_ALL_SIGNALS` - Los usuarios pueden ver todas las señales capturadas en [el Explorador de datos](/help/using/features/data-explorer/data-explorer-overview.md).