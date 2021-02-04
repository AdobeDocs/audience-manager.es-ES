---
description: La administración de usuarios de Audience Manager se está trasladando a Adobe Admin Console. En este artículo se explica qué debe hacer para prepararse para la migración de usuarios y qué cambiará una vez que se complete la migración.
keywords: rbac;RBAC;basado en roles;basado en roles;controles de acceso basados en roles
seo-description: La administración de usuarios de Audience Manager se está trasladando a Adobe Admin Console. En este artículo se explica qué debe hacer para prepararse para la migración de usuarios y qué cambiará una vez que se complete la migración.
seo-title: Migración de usuarios Audience Manager a Admin Console
solution: Audience Manager
title: Migración de usuarios Audience Manager a Admin Console
feature: Administration
translation-type: tm+mt
source-git-commit: e4a9ae06a1283870613d2751b171fc443b8701d8
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 3%

---


# [!DNL Audience Manager] migración de usuarios a  [!DNL Admin Console] {#user-migration}

## Información general {#overview}

[!DNL Audience Manager] la administración de cuentas de usuario se está trasladando a  [Adobe Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html) para disfrutar de una experiencia más optimizada en las soluciones de Adobe.

Los beneficios de utilizar [!DNL Admin Console] incluyen:

| Ventaja | Descripción |
|---|---|
| Inicio de sesión único en varias soluciones | [!DNL Audience Manager] los usuarios pueden iniciar sesión en  [!DNL Experience Cloud] y en todas las demás soluciones con sus  [!DNL Adobe ID] o  [!DNL Enterprise ID]. Este inicio de sesión permite el acceso a soluciones integradas y servicios principales en [!DNL Experience Cloud]. Después de la migración, los usuarios que intenten iniciar sesión mediante inicios de sesión heredados (`bank.demdex.com`) se redirigirán a `experiencecloud.adobe.com`. |
| Administrar usuarios y grupos | Una vez completada la migración, [!DNL Audience Manager] los administradores administrarán usuarios y grupos exclusivamente en [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/). |
| Administrar productos y servicios | Desde [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/), los administradores pueden: <ul><li>Crear, actualizar y eliminar usuarios</li><li>Conceder acceso a soluciones y servicios</li><li>Conceder permisos de usuario</li></ul> |

Para facilitar la migración de usuarios, pedimos a todos los [!DNL Audience Manager] administradores que tengan el inicio de migrar sus cuentas de usuario a [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) lo antes posible, siguiendo los pasos descritos en este artículo.

## Qué deben hacer los usuarios {#what-to-do-users}

Como usuario Audience Manager, todo lo que necesita hacer es ponerse en contacto con su [!DNL Audience Manager] administrador y pedirle que cree una nueva cuenta de usuario en [!DNL Admin Console].

## Qué deben hacer los administradores {#what-to-do-admins}

Los administradores de Audience Manager deben seguir los pasos a continuación para migrar los usuarios a [!DNL Admin Console].

1. Vaya a [https://adminconsole.adobe.com](https://adminconsole.adobe.com) e inicie sesión con su Adobe ID o Enterprise ID. Si no tiene acceso a [!DNL Admin Console], póngase en contacto con el Servicio de atención al cliente o con el consultor de Adobe.
2. Consulte la [!DNL Adobe Admin Console] [guía de ayuda](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html) para obtener instrucciones detalladas sobre cómo crear y administrar cuentas de usuario.
3. Cree nuevas cuentas de usuario para todos los usuarios Audience Manager existentes.
4. Informar a los usuarios sobre las cuentas de usuario recién creadas. Una vez que los usuarios se migran a [!DNL Admin Console], deben dejar de utilizar inicios de sesión heredados.

## Consideraciones de migración de usuarios {#considerations}

Tanto los usuarios como los administradores deben tener en cuenta las siguientes consideraciones para la migración de usuarios Audience Manager:

* Una vez creadas las cuentas de usuario nuevas en Admin Console, los permisos existentes de sus cuentas de usuario heredadas se transferirán automáticamente. No es necesario que los administradores asignen nuevos permisos en [!DNL Admin Console].
* Los administradores no necesitan deshabilitar las cuentas de usuario heredadas. Las cuentas de usuario antiguas se combinarán automáticamente en las migradas.
* Las actualizaciones de los permisos de usuario se seguirán administrando desde [!DNL Audience Manager]. El [!DNL Admin Console] sólo cubre la administración de usuarios y grupos.