---
description: Añada el módulo de administración de Audiencias a Adobe Analytics AppMeasurement para reenviar los datos de Analytics al Audience Manager en lugar de hacer que el código de la biblioteca de integración de datos del Audience Manager (DIL) envíe un píxel desde la página.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Añada el módulo de administración de Audiencias a Adobe Analytics AppMeasurement para reenviar los datos de Analytics al Audience Manager en lugar de hacer que el código de la biblioteca de integración de datos del Audience Manager (DIL) envíe un píxel desde la página.
seo-title: Implementar el módulo de administración de Audiencias
solution: Audience Manager
title: Implementar el módulo de administración de Audiencias
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 1%

---


# Cómo reenviar datos de [!DNL Adobe Analytics] a [!DNL Audience Manager] {#implement-the-audience-management-module}

Siga los pasos de este tutorial para reenviar [!DNL Analytics] datos a [!DNL Audience Manager] la página en lugar de hacer que el código [!DNL Audience Manager] ( [!UICONTROL Data Integration Library][!DNL DIL]) envíe un píxel desde la página.

>[!TIP]
>
>Le recomendamos que utilice [!DNL Adobe Experience Platform Launch] para reenviar [!UICONTROL Analytics] datos a [!DNL Audience Manager]. Al usar [!UICONTROL Launch], no es necesario copiar el código manualmente en [!DNL AppMeasurement], como se muestra en esta página.

## Requisitos previos {#prereqs}

Además de habilitar las extensiones o implementar el código descrito en este documento, también debe:

* Implementar el servicio [de identidad de](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform.
* Habilite el reenvío [del lado del](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) servidor para los grupos de informes en la [!UICONTROL Adobe Analytics Admin Console].

## Implementación {#implementation}

Existen dos métodos para implementar el reenvío de datos de [!DNL Adobe Analytics] a [!DNL Audience Manager], según la solución de administración de etiquetas que utilice.

### Implementación mediante [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] recomienda utilizar la extensión [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) para instrumentar [!DNL Adobe Analytics] y [!DNL Audience Manager] en sus propiedades. En este caso, no es necesario copiar manualmente ningún código. En su lugar, debe habilitar el uso compartido de datos en la [!DNL Analytics Launch] extensión, como se muestra en la siguiente imagen. Consulte también la documentación de [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Si instala la [!DNL Adobe Analytics] extensión, *no* instale también la [!DNL Audience Manager] extensión. El reenvío de datos desde la [!DNL Analytics] extensión reemplaza la funcionalidad de la [!DNL Audience Manager] extensión.

![Cómo habilitar el uso compartido de datos desde la extensión Adobe Analytics al Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Implementación mediante [!DNL Adobe Digital Tag Management (DTM)] o cualquier otra solución de administración de etiquetas

>[!WARNING]
>
>[!DNL Adobe] ha lanzado los planes de extinción [!DNL DTM] para finales de 2020. Para obtener más información y programar, consulte [!DNL DTM] Planes para un atardecer en los foros [de la comunidad de](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)Adobe.

Para implementar el [!UICONTROL Audience Management Module] uso de [Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) u otra solución de administración de etiquetas:

1. Descargue [!UICONTROL AppMeasurement] mediante el Administrador [de códigos de](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html) Analytics (requiere la versión 1.5 o posterior).
1. Actualice su [!UICONTROL AppMeasurement] código a la versión incluida en el archivo zip descargado.
1. Copie todo el código desde `AppMeasurement_Module_AudienceManagement.js` el archivo zip. Pegue el archivo en el `appMeasurement.js` archivo justo encima del texto, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Añada el código, `s.loadModule("AudienceManagement");`, justo encima del `AppMeasurement_Module_AudienceManagement.js` código que acaba de agregar en el paso anterior.
1. Actualice y copie el código siguiente y agréguelo a la `doPlugins` función del `AppMeasurement.js` archivo.

```js
s.AudienceManagement.setup({ 
     "partner":"INSERT-YOUR-PARTNER-NAME-HERE", 
     "containerNSID":0, 
     "uuidCookie": { 
          "name":"aam_uuid", 
          "days":30
     },
     "visitorService": {
          "namespace": "INSERT-EXPERIENCE-CLOUD-ORGID-HERE" 
     } 
});
```

>[!TIP]
>
>La `audienceManagement.setup` función comparte parámetros con la [!DNL Audience Manager] función `DIL.create` , que puede configurar en este código. Para obtener más información sobre estos parámetros, consulte [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Elementos de código definidos {#code-elements-defined}

La siguiente tabla define variables importantes en el ejemplo de código.

| Parámetro | Descripción |
|--- |--- |
| `partner` | Requerido. Es un nombre de socio que le ha asignado [!DNL Adobe]. A veces se le denomina subdominio de socio [!UICONTROL partner ID] o subdominio de socio.  Póngase en contacto con su [!DNL Adobe] asesor o con el Servicio de atención [al cliente](https://helpx.adobe.com/marketing-cloud/contact-support.html) si no conoce el nombre de su socio. |
| `containerNSID` | Requerido. La mayoría de los clientes pueden establecer `"containerNSID":0` . Sin embargo, si la compañía necesita personalizar la sincronización de ID con un contenedor diferente, puede especificar ese ID de contenedor aquí. |
| `uuidCookie` | Opcional. Esta configuración le permite establecer una [!DNL Adobe] cookie en el dominio de origen. Esto [!DNL cookie] contiene el [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Requerido. El `namespace` parámetro es obligatorio si utiliza el [!DNL AudienceManagement] módulo incluido con [!UICONTROL AppMeasurement] la versión 2.10 o posterior. Este [!UICONTROL AudienceManagement] módulo requiere que utilice [!UICONTROL Adobe Experience Platform Identity Service] 3.3 o posterior. <br><br>El [!UICONTROL Experience Cloud Organization ID] es el ID con el que se proporciona una compañía al registrarse para el [!UICONTROL Experience Cloud]. Descubra el identificador de organización de su compañía en [Organizaciones y vinculación](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html)de cuentas. |

## Resultados: Reenvío de datos a [!DNL Audience Manager] {#results-data-forwarding}

La [!DNL Analytics] implementación envía datos a [!DNL Audience Manager] después de:

* Habilitado [!UICONTROL Server-Side Forwarding] (consulte con su asesor sobre esta función);
* Se ha aplicado la [!DNL Adobe Experience Platform Identity Service];
* Se han seguido los pasos de implementación de este tutorial.

Este proceso envía datos a [!DNL Audience Manager]:

* En llamadas de vista de página;
* Desde vínculos rastreados;
* Desde vistas de vídeo de hito de vídeo y latidos.

>[!NOTE]
>
>Las variables enviadas a [!DNL Audience Manager] desde [!DNL Analytics] utilizan prefijos especiales. Debe comprender y tener en cuenta estos prefijos al crear [!DNL Audience Manager] características. Para obtener más información sobre estos prefijos, consulte Requisitos de [prefijo para variables](../../features/traits/trait-variable-prefixes.md)clave.
