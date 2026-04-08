---
description: La administración de usuarios de Audience Manager se está trasladando a Adobe Admin Console. Este artículo explica lo que necesita hacer para prepararse para la migración de usuarios y qué cambiará una vez que se complete la migración.
keywords: rbac;RBAC;basado en roles;basado en roles;controles de acceso basados en roles
seo-description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
seo-title: Audience Manager User Migration to Admin Console
solution: Audience Manager
title: Migración de usuarios de Audience Manager a Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
TQID: https://experienceleague.adobe.com/CE7RomA3PrbV9wwVnwehnZLdP-L73QzOyOlOGSQ0rSs
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 391
ht-degree: 1%

---

# Migración de usuarios de [!DNL Audience Manager] a [!DNL Admin Console] {#user-migration}

## Información general {#overview}

La administración de cuentas de usuario de [!DNL Audience Manager] se está trasladando a [Adobe Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html) para disfrutar de una mejor experiencia en las soluciones de Adobe.

Los beneficios de usar [!DNL Admin Console] incluyen:

| Ventaja | Descripción |
|---|---|
| Inicio de sesión único en todas las soluciones | [!DNL Audience Manager] usuarios pueden iniciar sesión en [!DNL Experience Cloud] y en todas las demás soluciones usando sus [!DNL Adobe ID] o [!DNL Enterprise ID]. Este inicio de sesión permite acceder a las soluciones integradas y a los servicios principales de [!DNL Experience Cloud]. Después de la migración, los usuarios que intenten iniciar sesión con los inicios de sesión heredados (`bank.demdex.com`) se redirigirán a `experiencecloud.adobe.com`. |
| Administrar usuarios y grupos | Una vez completada la migración, [!DNL Audience Manager] administradores administrarán usuarios y grupos exclusivamente en [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/). |
| Administración de productos y servicios | Desde [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/), los administradores pueden: <ul><li>Crear, actualizar y eliminar usuarios</li><li>Concesión de acceso a soluciones y servicios</li></ul> |

Para facilitar la migración de usuarios, pedimos a todos los administradores de [!DNL Audience Manager] que comiencen a migrar sus cuentas de usuario a [Adobe Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html) lo antes posible, siguiendo los pasos descritos en este artículo.

## Qué deben hacer los usuarios {#what-to-do-users}

Como usuario de Audience Manager, todo lo que debe hacer es ponerse en contacto con el administrador de [!DNL Audience Manager] y pedirle que cree una nueva cuenta de usuario en [!DNL Admin Console].

## Qué deben hacer los administradores {#what-to-do-admins}

Los administradores de Audience Manager deben seguir los pasos a continuación para migrar usuarios a [!DNL Admin Console].

1. Vaya a [https://adminconsole.adobe.com](https://adminconsole.adobe.com) e inicie sesión con su Adobe ID o Enterprise ID. Si no tiene acceso a [!DNL Admin Console], póngase en contacto con el Servicio de atención al cliente o con su consultor de Adobe.
2. Consulte la [!DNL Adobe Admin Console] [guía de ayuda](https://helpx.adobe.com/es/enterprise/admin-guide.html/enterprise/using/users.ug.html) para obtener instrucciones detalladas sobre cómo crear y administrar cuentas de usuario.
3. Cree nuevas cuentas de usuario para todos los usuarios de Audience Manager existentes.
4. Informe a los usuarios de las cuentas de usuario recién creadas. Una vez migrados los usuarios a [!DNL Admin Console], deberían dejar de usar los inicios de sesión heredados.

## Consideraciones sobre migración de usuarios {#considerations}

Tanto los usuarios como los administradores deben tener en cuenta las siguientes consideraciones para la migración de usuarios de Audience Manager:

* Una vez que se creen nuevas cuentas de usuario en Admin Console, los permisos existentes de las cuentas de usuario heredadas seguirán aplicándose.
* Las actualizaciones de los permisos de usuario se seguirán administrando desde [!DNL Audience Manager]. [!DNL Admin Console] solo cubre la administración de usuarios y grupos.
* Los administradores no necesitan deshabilitar las cuentas de usuario heredadas. Las cuentas de usuario antiguas se combinarán automáticamente con las migradas.
