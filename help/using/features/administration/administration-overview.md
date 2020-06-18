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
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1068'
ht-degree: 1%

---


# Administración (controles RBAC) {#administration}

![](assets/rbac-controls.png)

Las opciones del [!UICONTROL Administration] menú permiten crear usuarios Audience Manager y asignarlos a grupos. También puede establecer límites de vista (características, segmentos, destinos y modelos).

Los clientes de la empresa que utilizan [!DNL Audience Manager] una plataforma de gestión de datos para todos sus datos, pero deben poder controlar la visibilidad de los diferentes elementos de datos en unidades de negocio específicas. Puede hacerlo mediante permisos de grupo, también denominados [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utiliza grupos para asignar permisos. Los permisos no se asignan a nivel de usuario. Los permisos de grupo están vinculados a objetos (características, segmentos, etc.) y a las acciones que puede realizar en esos objetos (edición, vista, etc.). Estos controles también están disponibles a través de las API de Audience Manager REST. Consulte Métodos [de Administración](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md)de usuarios, Administración [de grupos](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)y Administración de [permisos](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API.

## Create Users {#create-users}

<!-- t_create_users.xml -->

Cree usuarios en [!DNL Audience Manager] y especifique los detalles del usuario, el estado de inicio de sesión y asigne usuarios a los grupos.

1. Haga clic **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Haga clic en ![](assets/icon_add.png) para mostrar la [!UICONTROL Create New User] página.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **Nombre de usuario:** Especifique un nombre de usuario único para Audience Manager.
   * **Nombre:** Especifique el nombre del usuario.
   * **Apellido:** Especifique los apellidos del usuario.
   * **Dirección de correo electrónico:** Especifique la dirección de correo electrónico del usuario. [!DNL Audience Manager] no envía notificaciones regulares a los usuarios. [!DNL Audience Manager] los administradores tienen acceso a las direcciones de correo electrónico de los usuarios y pueden enviar mensajes manualmente a los usuarios según sea necesario. Por ejemplo, si un usuario olvida su contraseña, la dirección de correo electrónico especificada en este campo se utiliza para enviar una contraseña temporal e instrucciones para restablecer la contraseña.
   * **Número de teléfono:** Especifique el número de teléfono del usuario.
   * **Es administrador:** Especifique si este usuario es un [!DNL Audience Manager] administrador. Los usuarios administradores pueden administrar usuarios (crear, editar, etc.) y grupos (crear, asignar permisos, etc.). Los usuarios que no son administradores pueden controlar únicamente sus propios perfiles de usuario, incluida la edición de sus direcciones de correo electrónico y el restablecimiento de sus propias contraseñas. Para obtener más información, consulte [Editar la configuración](../../features/administration/edit-account-settings.md)de la cuenta.
1. En **[!UICONTROL Login]**, seleccione el estado que desee:
   * **Activo:**  Los usuarios activos pueden acceder [!DNL Audience Manager] y obtener los permisos por pertenencia a grupos.
   * **Desactivado:**  Los usuarios desactivados no pueden acceder [!DNL Audience Manager] y no tienen permisos. Si desactiva los usuarios, la información de los usuarios permanecerá activa [!DNL Audience Manager] y podrá reactivarla fácilmente si es necesario. Si elimina usuarios, debe volver a crearlos si necesitan usarlos [!DNL Audience Manager] nuevamente en el futuro.
   * **Caducado:** La contraseña de un usuario tiene más de 90 días.
   * **Pendiente:** El usuario tiene una contraseña temporal, ya sea después de restablecer la contraseña o como cuenta nueva, y aún no ha establecido una contraseña permanente.
   * **Bloqueado:** 5 intentos de inicio de sesión incorrectos bloquearán a un usuario.
1. En **[!UICONTROL Assigned Groups]**la lista desplegable, seleccione los grupos a los que desee asignar este usuario.
Para obtener más información sobre los grupos y permisos, consulte [Creación de un grupo](../../features/administration/administration-overview.md#create-group).
1. Haga clic **[!UICONTROL Save]**.

## Creación de grupos {#create-group}

Un *grupo* es una colección de usuarios que comparten derechos de acceso a objetos de destino, segmento y rasgo. Puede limitar los grupos a objetos únicos únicamente o darles un acceso amplio a combinaciones de objetos diferentes.

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

## Explicación de los permisos de comodines {#wild-card-permissions}

Simplifique la administración de derechos de grupo con [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] otorgue a los miembros del grupo acceso automático a cada origen de datos asociado a un segmento, destino o característica. En comparación, los permisos regulares solo permiten asignar fuentes de datos específicas a uno de estos objetos. Y, cuando agrega nuevas fuentes de datos, los miembros del grupo no tienen acceso a esas nuevas fuentes.

Debe abrir los permisos de grupo y asignar esas nuevas fuentes de datos al grupo. [!UICONTROL Wild Card Permissions] le permite evitar este proceso manual de actualización de fuentes de datos. Los grupos con [!UICONTROL Wild Card Permissions] acceso a nuevas fuentes de datos sin autorización explícita.

![](assets/wild-card.png)

Lea más abajo para ver una descripción de lo que significa cada permiso comodín:

**Rasgo**

* `MAP_ALL_TRAITS_TO_MODELS` - Los usuarios pueden seleccionar características como base para los modelos.
* `EDIT_ALL_TRAITS` - Los usuarios pueden editar todas las características configuradas en su cuenta de compañía.
* `VIEW_ALL_TRAITS` - Los usuarios pueden vista de todas las características configuradas en su cuenta de compañía.
* `DELETE_ALL_TRAITS` - Los usuarios pueden eliminar todas las características configuradas en su cuenta de compañía.
* `CREATE_ALL_ALGO_TRAITS` - Los usuarios pueden crear características algorítmicas.
* `MAP_ALL_TO_SEGMENTS` - Los usuarios pueden agregar cualquiera de las características que pertenecen a su compañía a los segmentos.
* `CREATE_ALL_TRAITS` - Los usuarios pueden crear características.

**Informes**

* `PTRREPORTS` - Este permiso comodín hace referencia a una funcionalidad obsoleta y se eliminará de la interfaz de usuario del Audience Manager en breve.

**Modelos**

* `VIEW_MODELS` - Los usuarios tienen permiso para vista de modelos que pertenecen a su compañía.

**Señales derivadas**

* `VIEW_DERIVED_SIGNALS` - Los usuarios pueden vista todas las señales derivadas que pertenezcan a su compañía.
* `CREATE_DERIVED_SIGNALS` - Los usuarios pueden crear señales derivadas.
* `EDIT_DERIVED_SIGNALS` - Los usuarios pueden editar todas las señales derivadas que pertenecen a su compañía.
* `DELETE_DERIVED_SIGNALS` - Los usuarios pueden borrar cualquiera de las señales derivadas que pertenezcan a su compañía.

**Destino**

* `EDIT_ALL_DESTINATIONS` - Los usuarios pueden editar toda la configuración de destino dentro de su cuenta de compañía.
* `CREATE_DESTINATIONS` - Los usuarios pueden crear destinos.
* `VIEW_ALL_DESTINATIONS` - Los usuarios pueden realizar la vista de todos los destinos configurados en su cuenta de compañía.
* `DELETE_ALL_DESTINATIONS` - Los usuarios pueden eliminar todos los destinos configurados en su cuenta de compañía.

**Etiquetas**

* `VIEW_TAGS` - Los usuarios pueden hacer todo (vista, creación, edición, eliminación) en sus Contenedores de etiquetas.

**Audiencia Lab**

* `MANAGE_SEGMENT_TEST_GROUPS` - Los usuarios pueden hacer todo (vista, creación, edición, eliminación) en los grupos de prueba del laboratorio de Audiencia.

**Segmento**

* `CREATE_ALL_SEGMENTS` - Los usuarios pueden crear segmentos.
* `DELETE_ALL_SEGMENTS` - Los usuarios pueden eliminar todos los segmentos configurados en su cuenta de compañía.
* `MAP_ALL_TO_DESTINATIONS` - Los usuarios pueden asignar cualquiera de los segmentos que pertenecen a su compañía a los destinos.
* `EDIT_ALL_SEGMENTS` - Los usuarios pueden editar todos los segmentos configurados en su cuenta de compañía.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Los usuarios pueden seleccionar segmentos como línea de base para los modelos.
* `VIEW_ALL_SEGMENTS` - Los usuarios pueden realizar la vista de todos los segmentos configurados en su cuenta de compañía.

**Señales**

* `VIEW_ALL_SIGNALS` - Los usuarios pueden vista todas las señales capturadas en el Explorador [de datos](/help/using/features/data-explorer/data-explorer-overview.md).

## Casos de uso {#use-cases}

### Supervisión del acceso de los usuarios {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] puede ayudarle a supervisar el estado de inicio de sesión del usuario, proporcionándole una imagen clara de quién puede acceder a la instancia de Audience Manager.

Según los requisitos comerciales, puede habilitar y deshabilitar las cuentas de usuario según sea necesario.

![monitor-user-access](assets/monitor-user-access.png)

### Garantizar la protección del acceso a las fuentes de datos confidenciales {#protect-sensitive-data-sources}

Puede configurar [!UICONTROL Role-Based Access Control] en el nivel de características, segmentos y destinos para cada grupo de usuarios.

Esta capacidad le ayuda a administrar la forma en que los usuarios vista, crean, leen, escriben y editan conjuntos de datos específicos, e incluso a restringir el acceso de los usuarios a conjuntos de datos que no deberían estar disponibles para ellos.

![access-protection](assets/access-protection.png)
