---
title: Actualice la biblioteca de recopilación de datos para el Audience Manager de la biblioteca JavaScript de AppMeasurement a la biblioteca JavaScript de Web SDK.
description: Conozca los pasos para actualizar la biblioteca de recopilación de datos para Audience Manager de la biblioteca JavaScript de AppMeasurement a la biblioteca JavaScript de Web SDK.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: f8d8eb722e7b5cc4371f400a76fbd548a1318668
workflow-type: tm+mt
source-wordcount: '2589'
ht-degree: 0%

---


# Actualice la biblioteca de recopilación de datos para el Audience Manager de la biblioteca JavaScript de AppMeasurement a la biblioteca JavaScript de Web SDK

## Destinatarios previstos {#intended-audience}

Esta página es para clientes de Audience Manager y Adobe Analytics que utilizan la biblioteca de JavaScript [!DNL AppMeasurement] para enviar datos web al Audience Manager.

Consulte la tabla siguiente para obtener instrucciones sobre los pasos de migración a Web SDK, según el método de recopilación de datos actual.

| Método de recopilación de datos existente | Instrucciones de migración de Web SDK |
|---------|----------|
| [!DNL AppMeasurement] biblioteca de JavaScript | Siga las instrucciones de esta guía. |
| [!DNL Audience Manager] [extensión de etiqueta](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) | Siga las instrucciones de [actualización de la biblioteca de recopilación de datos de la extensión de etiquetas de Audience Manager a la extensión de etiquetas de Web SDK](dil-extension-to-web-sdk.md). |
| [!DNL AppMeasurement] biblioteca de JavaScript + [!DNL Audience Manager] [biblioteca de DIL](../dil/dil-overview.md) | Siga las instrucciones de [actualización de la biblioteca de recopilación de datos de la extensión de etiquetas de Audience Manager a la extensión de etiquetas de Web SDK](dil-extension-to-web-sdk.md). |

## Información general sobre migración {#overview}

La migración de [!DNL AppMeasurement] a [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) es principalmente una migración de Adobe Analytics. Para los clientes de Audience Manager, esta migración también incluye Audience Manager. Ambos deben migrarse juntos. Si trabaja principalmente con Audience Manager, asegúrese de que implica al equipo de Analytics en esta migración.

Si usa [!DNL AppMeasurement] para la recopilación de datos de Audience Manager, actualmente está usando el método [!DNL Server-side Forwarding (SSF)] para enviar datos de Analytics a Audience Manager. Con esta configuración, la solicitud de recopilación de datos de Analytics se reenvía al Audience Manager, que también gestiona la respuesta del Audience Manager a la página.

Este ha sido el enfoque estándar durante muchos años y es probable que sea su configuración actual. Si la biblioteca [!DNL AppMeasurement] contiene el módulo `AudienceManagement` y las llamadas de recopilación de datos incluyen la ruta de acceso `/10/` en la solicitud (`/b/ss/examplereportsuite/10/`), esta guía es para usted.

## Reenvío del lado del servidor (SSF) frente a flujos de datos de Web SDK {#data-flows}

Comprender las diferencias del flujo de datos entre Analytics y Audience Manager al pasar a Web SDK (y el Edge Network) es crucial para las instrucciones siguientes.

Con el reenvío del lado del servidor, el nodo de recopilación de datos regionales de Analytics recopila los datos, los transforma en una señal aceptada por el Audience Manager, los envía al Audience Manager y devuelve la respuesta del Audience Manager a la página. A continuación, el módulo [!DNL AudienceManagement] de la biblioteca [!DNL AppMeasurement] se encarga de la respuesta (por ejemplo, soltar cookies y enviar destinos de URL). Este proceso se denomina reenvío del lado del servidor porque Analytics reenvía los datos al Audience Manager mediante servidores de Adobe.

Con Web SDK, el Edge Network envía datos a Analytics y al Audience Manager en acciones independientes. Web SDK es una biblioteca única que envía datos a todas las soluciones y el Edge Network transforma los puntos de datos no relacionados con las soluciones en formatos específicos de las soluciones.

En este nuevo flujo de datos, todos los datos se envían a un Edge Network [datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview), que puede [configurar](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) para enviar datos a las soluciones de Adobe según sea necesario. Para el Audience Manager, al habilitar el servicio de Audience Manager en el conjunto de datos, se transforman los datos de [!DNL XDM] y Analytics en señales aceptadas por el Audience Manager. El Edge Network también devuelve la respuesta del Audience Manager a la página, donde Web SDK administra la respuesta, de forma similar a como lo hicieron [!DNL AppMeasurement] y el módulo [!DNL AudienceManagement].

## Migración de etiquetas frente a no etiquetas {#tags-vs-non-tags}

Tanto si utiliza etiquetas con la extensión [!DNL AppMeasurement], la biblioteca [!DNL AppMeasurement] en otro sistema de administración de etiquetas como si coloca [!DNL AppMeasurement] directamente en la página, los pasos para migrar el Audience Manager a Web SDK son los mismos. Dado que la migración de Audience Manager depende de la migración de Analytics, los pasos para migrar de [!DNL AppMeasurement] a Web SDK se determinan durante la migración de Analytics.

Esa información se explica en la documentación de Analytics para implementaciones basadas en [Tags](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) o [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk).

## XDM y los nodos `data.__adobe.` {#xdm-data-nodes}

Una de las funciones principales de [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) es enviar datos a [Real-time Customer Data Platform (RTCDP)](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/home). Para conseguirlo y seguir recopilando datos para otras soluciones de Experience Cloud sin una reimplementación completa, los datos específicos de la solución se dividen en compartimentos dentro de la llamada al servidor de recopilación de datos. Esta llamada usa un esquema JSON estandarizado denominado [Experience Data Model (XDM)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home)

Los elementos no relacionados con las soluciones, como la información sobre el explorador y el dispositivo, se envían al Edge Network en una estructura XDM predeterminada. El Edge Network transforma estos datos en formatos específicos de la solución. Sin embargo, los datos específicos de Target, Analytics y Audience Manager se almacenan en un nodo `data.__adobe` específico dentro de la carga útil XDM.

Por ejemplo:

* La variable de Analytics `s.eVar1` se representa en la carga útil XDM como `data.__adobe.analytics.evar1`.
* Un parámetro de Target relacionado con el estado de lealtad del cliente se almacena como `data.__adobe.target.loyaltyStatus`.

Los datos del nodo `__adobe` se envían a las soluciones respectivas (como Analytics y Audience Manager) sin enviarse al Experience Platform, aunque el servicio de Experience Platform esté habilitado en la secuencia de datos. Esto significa que puede mantener las configuraciones actuales para Analytics y Audience Manager, al tiempo que tiene la flexibilidad de asignar los elementos de datos necesarios a elementos de esquema XDM para casos de uso en tiempo real en Experience Platform mediante [Preparación de datos para la recopilación de datos](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep).

Por ejemplo, la cadena `s.products` de Analytics, que se usa para informar del contenido del carro de compras durante el cierre de compra, se puede enviar a Analytics y al Audience Manager en su formato original. Al mismo tiempo, puede utilizar los elementos de esta cadena para crear esquemas de carro XDM más intuitivos para casos de uso de Experience Platform.

Dado que la mayoría de las implementaciones de Audience Manager dependen de los datos de Analytics reenviados al Audience Manager, es probable que muchas de las expresiones de características de Audience Manager se basen en variables de Analytics (`c_evar#`, `c_prop#` y `c_events`). Para evitar la reconstrucción de expresiones de rasgos mediante formatos XDM durante la migración, el Edge Network está configurado de forma predeterminada para transformar cualquier variable de Analytics que se encuentre en el nodo `data.__adobe.analytics` en señales de Audience Manager. Este proceso es similar al flujo de trabajo del reenvío del lado del servidor.

El Edge Network puede realizar esta transformación porque se envía una sola llamada de recopilación de datos desde la página a un único conjunto de datos que alimenta varias soluciones de Adobe. Por lo tanto, la mayoría de las migraciones de [!DNL AppMeasurement] a Web SDK tanto para Analytics como para Audience Manager utilizarán principalmente el nodo `data.__adobe.analytics`.

El Edge Network transforma los datos de dispositivos y exploradores de la carga útil XDM y los encabezados de paquetes en señales de Audience Manager. Esto le permite seguir utilizando `h_` y `d_` claves de plataforma en expresiones de rasgos de Audience Manager.

## El nodo `data.__adobe.audiencemanager` {#data-note}

El nodo `data.__adobe.audiencemanager` se usa para implementaciones de Audience Manager que no dependen de Analytics. Almacena pares de clave/valor de Audience Manager personalizados que se enviaron anteriormente a través de la biblioteca [DIL library](../dil/dil-overview.md), tal como se describe en la [guía de migración de la extensión de etiquetas](dil-extension-to-web-sdk.md).

Aunque el nodo `data.__adobe.audiencemanager` no es necesario para la migración descrita en esta guía, el nuevo flujo de datos que se explica aquí permite enviar datos al Audience Manager sin que se registren en Analytics.

Si necesita enviar un par clave/valor personalizado al Audience Manager sin incluirlo en Analytics, puede utilizar el nodo `data.__adobe.audiencemanager`. Cualquier conjunto de datos de este nodo se anexará a los datos de Analytics transformados por el Audience Manager en la llamada al servidor de recopilación de datos.

## Ventajas y desventajas de esta ruta de implementación

El uso de este enfoque de migración tiene ventajas y desventajas. Valore cuidadosamente cada opción para decidir qué enfoque es el mejor para su organización.

| Ventajas | Desventajas |
| --- | --- |
| <ul><li>**Utiliza su implementación existente**: Aunque este enfoque requiere algunos cambios de implementación, no requiere una implementación completamente nueva desde cero. Puede utilizar la capa de datos y el código existentes con cambios mínimos en la lógica de implementación.</li><li>**No requiere un esquema**: Para esta fase de migración a Web SDK, no necesita un esquema XDM. En su lugar, puede rellenar el objeto `data`, que envía los datos directamente al Audience Manager. Una vez completada la migración a Web SDK, puede crear un esquema para su organización y utilizar la asignación de flujos de datos para rellenar los campos XDM aplicables. Si se requiere un esquema en esta fase del proceso de migración, su organización se vería obligada a utilizar un esquema XDM de Audience Manager. El uso de este esquema dificulta que su organización utilice su propio esquema en el futuro.</li></ul> | <ul><li>**Deuda técnica de la implementación**: dado que este método usa una forma modificada de la implementación existente, puede ser más difícil rastrear la lógica de la implementación y realizar cambios en el futuro cuando sea necesario.</li><li>**Requiere asignación para enviar datos a la plataforma**: cuando su organización esté lista para usar Real-Time CDP, debe enviar datos a un conjunto de datos en Adobe Experience Platform. Esta acción requiere que cada campo del objeto `data` sea una entrada en la herramienta de asignación de secuencia de datos que lo asigne a un campo de esquema XDM. La asignación solo debe realizarse una vez para este flujo de trabajo y no implica realizar cambios de implementación. Sin embargo, es un paso adicional que no es necesario al enviar datos en un objeto XDM.</li></ul> |

El Adobe recomienda seguir esta ruta de implementación en los siguientes casos:

* Tiene una implementación existente de mediante la biblioteca JavaScript de AppMeasurement de Adobe Analytics. Si tiene una implementación que usa la extensión de etiquetas de Audience Manager, siga [Migrar de la extensión de etiquetas de Audience Manager a la extensión de etiquetas de Web SDK](dil-extension-to-web-sdk.md) en su lugar.
* Tiene intención de utilizar Real-Time CDP en el futuro, pero no desea reemplazar la implementación de Audience Manager con una implementación de Web SDK desde cero. Reemplazar la implementación desde cero en Web SDK requiere el mayor esfuerzo, pero también ofrece la arquitectura de implementación a largo plazo más viable. Si su organización desea realizar el esfuerzo de una implementación limpia de Web SDK, consulte la [documentación de Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) para obtener más información.

## Pasos necesarios para migrar a Web SDK

Siga los pasos a continuación para migrar la integración de recopilación de datos a Web SDK.

+++**1. Migre su implementación de Analytics**.

Trabaje con su equipo de Analytics para seguir los pasos de migración de Analytics en las implementaciones basadas en [Etiquetas](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) o en [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk). Después de migrar su implementación de Analytics, continúe con los siguientes pasos.

+++

+++**2. Agregar el servicio Audience Manager al conjunto de datos**

Agregue el servicio Audience Manager al conjunto de datos que creó durante el paso 1.

1. Vaya a [experience.adobe.com](https://experience.adobe.com) e inicie sesión con sus credenciales.
1. Utilice la página de inicio o el selector de producto en la parte superior derecha para navegar a **[!UICONTROL Data Collection]**.
1. En el panel de navegación izquierdo, seleccione **[!UICONTROL Datastreams]**.
1. Seleccione el conjunto de datos que creó como parte de la migración de Analytics en el paso 1.
1. Seleccione **[!UICONTROL Add Service]**.
1. En el menú desplegable del servicio, seleccione **[!UICONTROL Audience Manager]**.
1. Compruebe las opciones **[!UICONTROL Cookie Destinations Enabled]** y **[!UICONTROL URL Destinations Enabled]**. Estas opciones permiten al Edge Network devolver esos tipos de destinos de Audience Manager a la página.
1. Asegúrese de que **[!UICONTROL Enable XDM Flattened Fields]** esté deshabilitado. Esta opción deshabilita la transformación automática de variables de Analytics en señales de Audience Manager. Esta opción está diseñada para mantener la compatibilidad con versiones anteriores para los usuarios que migraron a Web SDK antes de que el Edge Network transformara automáticamente los datos de Analytics en señales de Audience Manager.

   >[!NOTE]
   >
   >La migración a Web SDK con la opción **[!UICONTROL Enabled XDM Flattened Fields]** habilitada requiere que todos los datos necesarios en Audience Manager con formato XDM y todos los rasgos de Audience Manager mediante props, eVars o eventos se actualicen para buscar datos con formato XDM en su lugar. El Adobe recomienda dejar esta opción desactivada.


   ![Agregar servicio de Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

1. Seleccione **[!UICONTROL Save]** para guardar la configuración de la secuencia de datos.

El conjunto de datos está listo para recibir y pasar datos al Audience Manager. Tenga en cuenta el ID de la secuencia de datos, ya que este ID es necesario al configurar Web SDK en el código.

+++

+++**3. Habilite las sincronizaciones de ID de terceros y establezca el ID de contenedor de Audience Manager**

1. Vaya a [experience.adobe.com](https://experience.adobe.com) e inicie sesión con sus credenciales.
1. Utilice la página de inicio o el selector de producto en la parte superior derecha para navegar a **[!UICONTROL Data Collection]**.
1. En el panel de navegación izquierdo, seleccione **[!UICONTROL Datastreams]**.
1. Seleccione el conjunto de datos que creó como parte de la migración de Analytics en el paso 1.
1. Seleccione **[!UICONTROL Edit]** en la esquina superior derecha de la página de configuración de la secuencia de datos.
1. Expanda el menú desplegable **[!UICONTROL Advanced Options]** y habilite la funcionalidad **[!UICONTROL Third Party ID Sync]** si aún no está habilitada. Esta opción indica al Edge Network que devuelva las sincronizaciones de ID de socio para los socios de datos de Audience Manager y Experience Platform.

   ![Habilitar sincronización de ID de terceros.](assets/third-party-id-sync.png) {style="border:1px solid lightslategray"}

1. En la mayoría de los casos, puede dejar en blanco el campo **[!UICONTROL Third Party ID Sync Container ID]**. Lo hará de forma predeterminada en `0`. Sin embargo, si prefiere asegurarse de que se utiliza el ID de contenedor correcto, siga los siguientes pasos:
   * Abra una ventana del explorador en modo incógnito o privado y vaya a una página que forme parte de la migración.
   * Utilice las herramientas para desarrolladores del explorador para filtrar la llamada de red a `dpm.demdex.net/id`. Esta llamada solo se activa en la primera página de una primera visita, por lo que se necesita un explorador de incógnito o privado.
   * Consultar la carga útil de la solicitud. Si el parámetro `d_nsid` es diferente a cero, cópielo en el campo **[!UICONTROL Third Party ID Sync Container ID]**.

1. Seleccione **[!UICONTROL Save]**.

El conjunto de datos está listo para enviar datos al Audience Manager y pasar las respuestas del Audience Manager a Web SDK.

+++

+++**4. Agregar ID de cliente al mapa de identidad**

La mayoría de las implementaciones de Audience Manager usan [Reglas de combinación de perfiles](../features/profile-merge-rules/merge-rules-overview.md) en escenarios de personalización entre dispositivos y para ayudar a controlar para qué segmentos pueden calificar los visitantes según su estado de autenticación (con sesión iniciada o cerrada). Las reglas de combinación de perfiles requieren que se envíe un identificador de propiedad del cliente (ID de CRM, número de cuenta, etc.) al Audience Manager en cada llamada de recopilación de datos después de la autenticación. Anteriormente, la función `setCustomerIDs` del servicio de ID de visitante ([!DNL visitor.js]) se usaba para anexar los ID de cliente a cada llamada de recopilación de datos de Analytics, que luego se reenviaba al Audience Manager.

Con Web SDK, estas identidades ahora deben enviarse al Edge Network mediante una construcción XDM especial llamada [IdentityMap](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/identitymap).

Para pasar las identidades correctamente en un mapa de identidad, es necesario comprender [áreas de nombres de identidad](https://experienceleague.adobe.com/es/docs/experience-platform/identity/features/namespaces) y considerar cuidadosamente qué identidades pasar, especialmente al enviar datos a una zona protegida de Experience Platform. [Este artículo](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-21305) describe estas consideraciones e instrucciones.

Una vez que determine qué identidades pasar y cuándo, siga las guías para usar el [!UICONTROL Identity map] **[!UICONTROL Identity map]** [elemento de datos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/data-element-types#identity-map) en las etiquetas o configúrelo manualmente como se describe en la [descripción general de datos de identidad](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/identity/overview) para alinearlo con su estrategia de implementación de Web SDK.

+++

## Configuración del reenvío y el Audience Analytics del lado del servidor en la interfaz de usuario del administrador de grupos de informes de Analytics {#configure-ssf-analytics}

Si está familiarizado con la función [reenvío del lado del servidor](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf) de Analytics, podría preguntarse: &quot;*¿Debo deshabilitar la configuración del reenvío del lado del servidor en la interfaz de usuario del administrador de grupos de informes de Analytics para evitar que se envíen datos de Analytics al Audience Manager dos veces?*&quot;.

La respuesta es no, no debe deshabilitar esta configuración. He aquí la razón:

Cuando esta configuración está habilitada y el módulo [!DNL AudienceManagement] se agrega a la biblioteca [!DNL AppMeasurement] de la página, todos los datos enviados a ese grupo de informes también fluirán al Audience Manager.

Para cumplir con las normas de privacidad del RGPD, hay escenarios en los que los datos se pueden recopilar en Analytics pero no en Audience Manager. Además, hay casos que implican grupos de informes globales y casos de uso específicos de la región en los que algunas llamadas de recopilación de datos no deben enviarse al Audience Manager. Para solucionarlo, Adobe ha introducido un botón de desactivación del reenvío del lado del servidor.

Como se explica en la [página de cumplimiento de Analytics y RGPD centrada en el reenvío del lado del servidor](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf-gdpr), al agregar la variable de contexto `cm.ssf=1` a un servidor de recopilación de datos de Analytics se impide que la llamada de recopilación de datos se reenvíe al Audience Manager.

Existen dos razones por las que no debe deshabilitar esta configuración.

1. Cuando el servicio de Audience Manager está habilitado en una secuencia de datos, el Edge Network anexa la variable `cm.ssf` a todas las solicitudes de recopilación de datos enviadas a Analytics. Esto evita que los datos de Analytics también se envíen al Audience Manager. Cualquier registro de Assurance utilizado para validar la migración de Analytics mostrará la variable `cm.ssf=1` cuando el servicio de Audience Manager esté habilitado en la secuencia de datos.
1. Esta configuración también habilita el flujo de datos para la integración de [!DNL Audience Analytics]. Como se describe en la [descripción general del Audience Analytics](https://experienceleague.adobe.com/en/docs/analytics/integration/audience-analytics/mc-audiences-aam), se requiere reenvío del lado del servidor para esta integración porque la respuesta del Audience Manager al servidor de recopilación de datos de Analytics se agrega a la visita de Analytics antes de procesarse. Un proceso similar ocurre dentro del Edge Network. Cuando el reenvío del lado del servidor está habilitado, el Edge Network agrega los segmentos necesarios desde la respuesta del Audience Manager a los datos enviados a Analytics.

En resumen, es importante que esta configuración permanezca habilitada para que Audience Analytics siga funcionando con una implementación de Web SDK y que no se cuenten dos veces los datos en Audience Manager.
