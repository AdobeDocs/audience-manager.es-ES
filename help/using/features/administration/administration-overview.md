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
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Administración (Controles RBAC) {#administration}

![](assets/rbac-controls.png)

Las opciones del [!UICONTROL Administration] menú permiten crear usuarios de Audience Manager y asignarlos a grupos. También puede ver los límites (características, segmentos, destinos y modelos).

Los clientes de Enterprise que utilizan [!DNL Audience Manager] una plataforma de administración de datos para todos sus datos, pero deben poder controlar la visibilidad de los distintos elementos de datos en unidades comerciales específicas. Puede hacerlo utilizando permisos de grupo, también denominado [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utiliza grupos para asignar permisos. Los permisos no se asignan a nivel de usuario. Los permisos de grupo están vinculados a objetos (características, segmentos, etc.) y acciones que puede realizar en estos objetos (editar, ver, etc.). Estos controles también están disponibles a través de las API REST de Audience Manager. Consulte [Métodos API de administración de usuarios](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [administración](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)[de grupos y](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) administración de permisos.

## Create Users {#create-users}

<!-- t_create_users.xml -->

Cree usuarios en [!DNL Audience Manager] y especifique detalles del usuario, estado de inicio de sesión y asigne usuarios a grupos.

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Users]**.
1. Haga clic para ![](assets/icon_add.png) mostrar la [!UICONTROL Create New User] página.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **Nombre de usuario:** Especifique un nombre de usuario exclusivo para Audience Manager.
   * **Nombre:** Especifique el nombre del usuario.
   * **Apellidos:** Especifique el apellido del usuario.
   * **Dirección de correo electrónico:** Especifique la dirección de correo electrónico del usuario. [!DNL Audience Manager] no envía notificación regular a los usuarios. [!DNL Audience Manager] los administradores tienen acceso a las direcciones de correo electrónico de los usuarios y pueden enviar por correo electrónico manualmente a los usuarios según sea necesario. Por ejemplo, si un usuario olvida su contraseña, la dirección de correo electrónico especificada en este campo se utiliza para enviar una contraseña temporal e instrucciones para restablecer la contraseña.
   * **Número de teléfono:** Especifique el número de teléfono del usuario.
   * **Es administrador:** Especifique si este usuario es [!DNL Audience Manager] administrador. Los usuarios administradores pueden administrar usuarios (crear, editar, etc.) y grupos (crear, asignar permisos, etc.). Los usuarios no administradores solo pueden controlar sus propios perfiles de usuario, como editar sus direcciones de correo electrónico y restablecer sus propias contraseñas. Para obtener más información, consulte [Editar la configuración de la cuenta](../../features/administration/edit-account-settings.md).
1. En, **[!UICONTROL Login]** seleccione el estado que desee:
   * **Activo:** Los usuarios activos pueden acceder [!DNL Audience Manager] y tener los permisos concedidos por la pertenencia a grupos.
   * **Desactivado:** Los usuarios desactivados no tienen acceso [!DNL Audience Manager] y no tienen permisos. Si desactiva usuarios, su información de usuario permanece en [!DNL Audience Manager] y puede reactivarlos, si es necesario. Si elimina usuarios, debe volver a crearlos si necesita volver a utilizarlos [!DNL Audience Manager] en el futuro.
   * **Caducado:** La contraseña de un usuario tiene más de 90 días.
   * **Pendiente:** El usuario tiene una contraseña temporal, ya sea como una contraseña o como una cuenta nueva, y todavía no ha establecido una contraseña permanente.
   * **Bloqueado:** 5 intentos de inicio de sesión incorrectos bloquearán a un usuario.
1. En **[!UICONTROL Assigned Groups]**la lista desplegable, seleccione los grupos que desee asignar a este usuario.
Para obtener más información sobre los grupos y permisos, consulte [Crear un grupo](../../features/administration/administration-overview.md#create-group).
1. Haga clic en **[!UICONTROL Save]**.

## Creación de grupos {#create-group}

*Un grupo* es una colección de usuarios que comparten derechos de acceso a objetos de destino, segmentos y características. Solo puede limitar grupos a objetos individuales o proporcionarles acceso amplio a combinaciones de diferentes objetos.

<!-- t_create_groups.xml -->

Para crear un grupo:

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Groups]**.
1. Haga clic en ![](assets/icon_add.png) para abrir [!UICONTROL Group Settings] la página.
1. En [!UICONTROL Group Details]:
   * Asigne un nombre al grupo.
   * Proporcione una breve descripción del grupo.
1. En [!UICONTROL Group Members], haga clic en un usuario desde **[!UICONTROL Add Users]** las opciones para agregarlas al grupo.
1. En [!UICONTROL Group Permissions], seleccione [un rasgo](../../features/traits/trait-details-page.md), [un segmento](../../features/segments/segments-purpose.md)o [un destino](../../features/destinations/destinations.md) .
**[!UICONTROL Add Object]**
Se abre una ventana de permisos para el objeto seleccionado.
1. Seleccione la casilla de verificación de los permisos que desea que tengan los miembros del grupo.
1. *(Opcional)* Asigne [permisos de comodines](../../features/administration/administration-overview.md#wild-card-permissions) al grupo.
1. Haga clic en **[!UICONTROL Save Group]**.

## Explicación de los permisos de comodines {#wild-card-permissions}

Simplifique la administración de derechos de grupo con [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] dar a los miembros del grupo acceso automático a cada fuente de datos asociada a un segmento, destino o característica. Por comparación, los permisos normales sólo permiten asignar fuentes de datos específicas a uno de estos objetos. Y, cuando agrega nuevas fuentes de datos, los miembros del grupo no obtienen acceso a esas nuevas fuentes.

Debe abrir los permisos de grupo y asignar esas nuevas fuentes de datos al grupo. [!UICONTROL Wild Card Permissions] permite evitar este proceso de actualización manual de fuentes de datos. Los grupos tienen [!UICONTROL Wild Card Permissions] acceso a nuevas fuentes de datos sin autorización explícita.

![](assets/wild-card.png)

Lea más abajo para obtener una descripción del significado de cada comodín:

**Rasgo**

* `MAP_ALL_TRAITS_TO_MODELS` - Los usuarios pueden seleccionar características como punto de referencia para los modelos.
* `EDIT_ALL_TRAITS` - Los usuarios pueden editar todas las características configuradas dentro de su cuenta de empresa.
* `VIEW_ALL_TRAITS` - Los usuarios pueden ver todas las características configuradas dentro de su cuenta de empresa.
* `DELETE_ALL_TRAITS` - Los usuarios pueden eliminar todas las características configuradas dentro de su cuenta de empresa.
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