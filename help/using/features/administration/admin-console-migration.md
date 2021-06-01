---
description: La administración de usuarios Audience Manager se está trasladando a Adobe Admin Console. En este artículo se explica lo que debe hacer para prepararse para la migración de usuarios y lo que cambiará una vez completada la migración.
keywords: rbac;RBAC;basados en funciones;basados en roles;controles de acceso basados en roles
seo-description: La administración de usuarios Audience Manager se está trasladando a Adobe Admin Console. En este artículo se explica lo que debe hacer para prepararse para la migración de usuarios y lo que cambiará una vez completada la migración.
seo-title: Migración de usuarios Audience Manager a Admin Console
solution: Audience Manager
title: Migración de usuarios Audience Manager a Admin Console
feature: Administración
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 3%

---

# [!DNL Audience Manager] migración de usuarios a  [!DNL Admin Console] {#user-migration}

## Información general {#overview}

[!DNL Audience Manager] la administración de cuentas de usuario se está trasladando a  [Adobe Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html) para obtener una experiencia más optimizada en las soluciones de Adobe.

Los beneficios de utilizar [!DNL Admin Console] incluyen:

| Ventaja | Descripción |
|---|---|
| Inicio de sesión único entre soluciones | [!DNL Audience Manager] los usuarios pueden iniciar sesión en  [!DNL Experience Cloud] y en todas las demás soluciones con su  [!DNL Adobe ID] o  [!DNL Enterprise ID]. Este inicio de sesión permite el acceso a soluciones integradas y servicios principales en [!DNL Experience Cloud]. Después de la migración, los usuarios que intenten iniciar sesión con los accesos heredados (`bank.demdex.com`) se redirigirán a `experiencecloud.adobe.com`. |
| Administración de usuarios y grupos | Una vez completada la migración, los [!DNL Audience Manager] administradores administrarán usuarios y grupos exclusivamente en [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/). |
| Administración de productos y servicios | Desde [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/), los administradores pueden: <ul><li>Crear, actualizar y eliminar usuarios</li><li>Concesión de acceso a soluciones y servicios</li></ul> |

Para facilitar la migración de usuarios, pedimos a todos los administradores de [!DNL Audience Manager] que empiecen a migrar sus cuentas de usuario a [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) lo antes posible, siguiendo los pasos descritos en este artículo.

## Qué necesitan hacer los usuarios {#what-to-do-users}

Como usuario Audience Manager, todo lo que debe hacer es ponerse en contacto con su [!DNL Audience Manager] administrador y pedirle que cree una nueva cuenta de usuario en [!DNL Admin Console].

## Qué necesitan hacer los administradores {#what-to-do-admins}

Los administradores de Audience Manager deben seguir los pasos a continuación para migrar usuarios a [!DNL Admin Console].

1. Vaya a [https://adminconsole.adobe.com](https://adminconsole.adobe.com) e inicie sesión con su Adobe ID o Enterprise ID. Si no tiene acceso a [!DNL Admin Console], póngase en contacto con el Servicio de atención al cliente o con su asesor de Adobe.
2. Consulte la [!DNL Adobe Admin Console] [guía de ayuda](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html) para obtener instrucciones detalladas sobre cómo crear y administrar cuentas de usuario.
3. Cree nuevas cuentas de usuario para todos los usuarios de Audience Manager existentes.
4. Informe a los usuarios de las cuentas de usuario recién creadas. Una vez que los usuarios se migran a [!DNL Admin Console], deben dejar de utilizar inicios de sesión heredados.

## Consideraciones sobre la migración de usuarios {#considerations}

Tanto los usuarios como los administradores deben tener en cuenta las siguientes consideraciones para la migración de usuarios Audience Manager:

* Una vez que se creen nuevas cuentas de usuario en Admin Console, se aplicarán los permisos existentes de sus cuentas de usuario heredadas.
* Las actualizaciones de los permisos de usuario se administrarán desde [!DNL Audience Manager]. El [!DNL Admin Console] solo cubre la administración de usuarios y grupos.
* Los administradores no necesitan deshabilitar las cuentas de usuario heredadas. Las cuentas de usuario antiguas se combinarán automáticamente en las migradas.
