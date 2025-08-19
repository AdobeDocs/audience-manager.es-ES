---
description: Audience Manager usuario gestión se está trasladando a Adobe Admin Console. En este artículo se explica lo que debe hacer para prepararse para usuario migración y lo que cambiará una vez que se complete la migración.
keywords: RBAC; RBAC; función basado; basado en función; Controles de acceso basados en función
seo-description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
seo-title: Audience Manager User Migration to Admin Console
solution: Audience Manager
title: Audience Manager de la migración de usuarios a Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 1%

---

# [!DNL Audience Manager] usuario migrar a [!DNL Admin Console] {#user-migration}

## Información general {#overview}

[!DNL Audience Manager] usuario administración de cuentas se traslada al [Adobe Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html) para lograr una experiencia más ágil en sus soluciones Adobe Systems.

Entre las ventajas de usar la [!DNL Admin Console] se incluyen:

| Ventaja | Descripción |
|---|---|
| Inicio de sesión único en todas las soluciones | [!DNL Audience Manager] Los usuarios pueden iniciar sesión en [!DNL Experience Cloud] y en todas las demás soluciones mediante su [!DNL Adobe ID] o [!DNL Enterprise ID]. Este inicio de sesión permite acceder a soluciones integradas y servicios principales a través [!DNL Experience Cloud]de . Tras la migración, se redirigirá a `bank.demdex.com`los usuarios que intenten iniciar sesión mediante inicios de sesión heredados (`experiencecloud.adobe.com`). |
| Administrar usuarios y grupos | Una vez completada la migración, [!DNL Audience Manager] los administradores administrar usuarios y grupos exclusivamente en el [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/)archivo . |
| Administrar productos y servicios | Desde , [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/)los administradores pueden: <ul><li>Crear, actualizar y eliminar usuarios</li><li>Conceder acceso a soluciones y servicios</li></ul> |

Para facilitar usuario migración, pedimos a todos los [!DNL Audience Manager] administradores que inicio migrar sus cuentas usuario a [Adobe Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html) lo antes posible, siguiendo los pasos descritos en este artículo.

## Qué deben hacer los usuarios {#what-to-do-users}

Como Audience Manager usuario, todo lo que necesita hacer es ponerse en contacto con su [!DNL Audience Manager] administrador y pedirle que cree un nuevo cuenta de usuario para usted en [!DNL Admin Console].

## Qué deben hacer los administradores {#what-to-do-admins}

Audience Manager administradores deben seguir los pasos siguientes para migrar usuarios a [!DNL Admin Console].

1. Vaya a [https://adminconsole.adobe.com](https://adminconsole.adobe.com) e inicie sesión con su Adobe ID o Enterprise ID. Si no tiene acceso al , póngase en contacto con el [!DNL Admin Console]Servicio de atención al cliente o con su Adobe Systems asesor.
2. Consulte el guía[!DNL Adobe Admin Console] de [&#128279;](https://helpx.adobe.com/es/enterprise/admin-guide.html/enterprise/using/users.ug.html)ayuda para obtener instrucciones detalladas sobre cómo crear y administrar usuario cuentas.
3. Crear nuevo usuario contabiliza a todos los usuarios de Audience Manager existentes.
4. Informe a los usuarios sobre las cuentas usuario recientemente creadas. Una vez migrados los usuarios a [!DNL Admin Console], deben dejar de usar inicios de sesión heredados.

## Consideraciones sobre la migración de usuarios {#considerations}

Tanto los usuarios como los administradores deben tener en cuenta las siguientes consideraciones para Audience Manager usuario migración:

* Una vez que se hayan creado nuevas cuentas usuario en Admin Console, se seguirán aplicando los permisos existentes de sus cuentas de usuario heredadas.
* Las actualizaciones de usuario permisos se seguirán gestionando desde [!DNL Audience Manager]. El [!DNL Admin Console] único cubre usuario y administración de grupos.
* Los administradores no necesitan desactivar las cuentas usuario heredadas. Las cuentas usuario antiguas se fusionarán automáticamente con las migradas.
