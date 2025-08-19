---
title: Actualice su biblioteca de recopilación de datos para su Audience Manager desde el biblioteca de JavaScript AppMeasurement al SDK web JavaScript biblioteca.
description: Conozca los pasos para actualizar su biblioteca de recopilación de datos para Audience Manager desde el biblioteca de JavaScript AppMeasurement hasta el SDK web JavaScript biblioteca.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: f180e423d4bdf5535d8dcc000e1d0f908bc54d7b
workflow-type: tm+mt
source-wordcount: '3385'
ht-degree: 0%

---


# Actualizar el biblioteca de recopilación de datos para Audience Manager de AppMeasurement al SDK web

## Previsto audiencia {#intended-audience}

Este Página es para clientes Audience Manager y Adobe Analytics que utilizan el biblioteca JavaScript [!DNL AppMeasurement] para enviar datos web a Audience Manager.

Consulte la tabla siguiente para obtener instrucciones sobre los pasos de migración al SDK web, en función de su método de recopilación de datos actual.

| Su método recopilación de datos existente | Instrucciones de migración del SDK web |
|---------|----------|
| [!DNL AppMeasurement] JavaScript biblioteca con AudienceManagement módulo | Siga las instrucciones de este guía. |
| [!DNL Audience Manager][etiqueta extensión](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) | Siga las instrucciones de [actualización del biblioteca de recopilación de datos desde la extensión de etiqueta de Audience Manager a la extensión](dil-extension-to-web-sdk.md) de etiqueta SDK web. |
| [!DNL AppMeasurement]JavaScript biblioteca + biblioteca DIL independiente [!DNL Audience Manager] [](../dil/dil-overview.md) | Siga las instrucciones de [actualización del biblioteca de recopilación de datos desde la extensión de etiqueta de Audience Manager a la extensión](dil-extension-to-web-sdk.md) de etiqueta SDK web. |

## Información general sobre migración {#overview}

La migración desde al [!DNL AppMeasurement]SDK[ web es principalmente una migración Adobe Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home). Para Audience Manager clientes, esta migración también incluye Audience Manager. Ambos deben migrarse juntos. Si trabaja principalmente con Audience Manager, asegúrese de involucrar a los Analytics equipo en esta migración.

Si usa [!DNL AppMeasurement] para Audience Manager recopilación de datos, actualmente está utilizando el [!DNL Server-side Forwarding (SSF)] enfoque para enviar datos de Analytics a Audience Manager. En esta configuración, el solicitud recopilación de datos Analytics se reenvía a Audience Manager, que también gestiona la respuesta Audience Manager al Página.

Este ha sido el enfoque estándar durante muchos años y es probable que sea su configuración actual. Si el [!DNL AppMeasurement] biblioteca contiene la `AudienceManagement` módulo y las llamadas al recopilación de datos incluyen la ruta en `/10/` la solicitud (`/b/ss/examplereportsuite/10/`), esta guía es para usted.

## Flujos de datos de SDK web frente a reenvío de servidor (SSF) {#data-flows}

Conocer las diferencias de flujo de datos entre Analytics y Audience Manager al migrar al SDK web (y a la red perimetral) es crucial para las instrucciones que se indican a continuación.

Con del lado del servidor reenvío, el Analytics recopilación de datos regional nodo recopila los datos, los transforma en una señal aceptada por Audience Manager, los envía a Audience Manager y devuelve la respuesta Audience Manager al Página. A [!DNL AudienceManagement] continuación, la módulo del [!DNL AppMeasurement] biblioteca gestiona la respuesta (p. ej., soltar cookies o enviar URL destinos). Este proceso se denomina reenvío del lado del servidor porque Analytics reenvía los datos a Audience Manager utilizando servidores Adobe Systems.

Con el SDK web, la red perimetral envía datos a Analytics y Audience Manager en acciones independientes. El SDK web es un biblioteca único que envía datos a todas las soluciones y la red perimetral transforma los puntos de datos independientes de la solución en formatos específicos de la solución.

En este nuevo flujo de datos, todos los datos se envían a un flujo[ de datos de red ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview)perimetral, que puede [configurar](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) para enviar datos a Adobe Systems soluciones según sea necesario. Por Audience Manager, la habilitación del servicio de Audience Manager en el flujo de datos transforma [!DNL XDM] y Analytics los datos en señales aceptadas por Audience Manager. La red perimetral también devuelve la respuesta Audience Manager al Página, donde el SDK web administra la respuesta, de forma similar a cómo [!DNL AppMeasurement] y lo hizo el [!DNL AudienceManagement] módulo.

## Migración de etiquetas frente a migración sin etiquetas {#tags-vs-non-tags}

Tanto si utiliza etiquetas con la [!DNL AppMeasurement] extensión, la [!DNL AppMeasurement] biblioteca en otro sistema administración de etiquetas o la coloca [!DNL AppMeasurement] directamente en el Página, los pasos para migrar Audience Manager al SDK web son los mismos. Dado que la migración de Audience Manager depende de la migración de Analytics, los pasos para migrar desde al SDK web se determinan durante la migración de [!DNL AppMeasurement] Analytics.

Esa información se trata en la documentación Analytics para [etiquetas](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) o [implementaciones basadas en JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk).

## XDM y los `data.__adobe.` nodos {#xdm-data-nodes}

Una de las funciones principales del [SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) web es enviar datos a [Real-Time Customer Data Platform (RTCDP).](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/home) Para lograr esto y seguir recopilando datos para otras Soluciones Experience Cloud sin una implementación completa, los datos específicos de la solución se compartimentan dentro de la recopilación de datos llamada al servidor. Esta llamada utiliza un esquema JSON estandarizado denominado Modelo de datos de [experiencia (XDM)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home)

Los elementos independientes de la solución, como la información sobre el explorador y el dispositivos, se envían a la red de Edge en una estructura XDM predeterminada. La red perimetral transforma estos datos en formatos específicos de la solución. Sin embargo, los datos específicos de Target, Analytics y Audience Manager se almacenan en un nodo dedicado `data.__adobe` dentro de la carga útil XDM.

Por ejemplo:

* El variable Analytics `s.eVar1` se representa en la carga útil XDM como `data.__adobe.analytics.evar1`.
* Un parámetro Target relacionado con Lealtad del cliente estado se almacena como `data.__adobe.target.loyaltyStatus`.

Los datos del `__adobe` nodo se envían a las soluciones respectivas (gustar Analytics y Audience Manager) sin enviarse a Experience Platform, igualado si el servicio Experience Platform está habilitado en el flujo de datos. Esto significa que puede mantener sus configuraciones actuales para Analytics y Audience Manager mientras tiene la flexibilidad de asignar los elementos de datos necesarios a los elementos de esquema XDM para casos de uso en tiempo real en Experience Platform utilizando [Data Prep for Data Collection](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep).

Por ejemplo, la cadena Analytics `s.products` , que se utiliza para informar sobre el contenido de carro de compras durante el cierre de compra, todavía se puede enviar a Analytics y Audience Manager en su formato original. Al mismo tiempo, puede utilizar los elementos de esta cadena para crear esquemas de carro de compras XDM más intuitivos para casos de uso Experience Platform.

Dado que la mayoría de las implementaciones de Audience Manager dependen de Analytics datos reenviados a Audience Manager, es probable que muchas de las expresiones de rasgos Audience Manager se basen en Analytics variables (`c_evar#`, `c_prop#`, y `c_events`). Para evitar reconstruir expresiones de rasgos con formatos XDM durante la migración, la red perimetral está configurada de forma predeterminada para transformar cualquier variable Analytics que se encuentre en el `data.__adobe.analytics` nodo en señales Audience Manager. Un proceso de transformación similar ocurre en el flujo de trabajo de reenvío de del lado del servidor.

La red perimetral puede realizar esta transformación porque una sola llamada de recopilación de datos desde el Página se envía a un único flujo de datos que alimenta varias soluciones de Adobe Systems. Por lo tanto, la mayoría de las migraciones desde [!DNL AppMeasurement] al SDK web, tanto para Analytics como para Audience Manager, utilizarán principalmente el `data.__adobe.analytics` nodo.

La red perimetral transforma los datos de dispositivos y explorador de la carga útil XDM y los encabezados de paquetes en señales Audience Manager. Esto le permite seguir usando y `h_` claves `d_` de plataforma en Audience Manager expresiones de rasgos.

## El `data.__adobe.audiencemanager` nodo {#data-note}

El `data.__adobe.audiencemanager` nodo se utiliza para implementaciones Audience Manager que no dependen de Analytics. Almacena pares personalizados clave/valor Audience Manager que se enviaban previamente a través del [biblioteca DIL biblioteca](../dil/dil-overview.md) , como se describe en el guía de migración de extensiones [de etiqueta](dil-extension-to-web-sdk.md).

Si bien la `data.__adobe.audiencemanager` nodo no es necesaria para la migración descrita en este guía, el nuevo flujo de datos que se explica aquí permite que los datos se envíen a Audience Manager sin registrarse en Analytics.

Si necesita enviar un par clave/valor personalizado a Audience Manager sin incluirlo en Analytics, puede usar el `data.__adobe.audiencemanager` nodo. Todos los conjuntos de datos de este nodo se anexarán a los datos de Analytics transformados en Audience Manager en el llamada al servidor de recopilación de datos.

## Ventajas y desventajas de esta ruta de implementación

El uso de este enfoque de migración tiene ventajas y desventajas. Sopese cuidadosamente cada opción para decidir qué enfoque es mejor para su organización.

| Ventajas | Desventajas |
| --- | --- |
| <ul><li>**Utiliza sus implementación** existentes: Aunque este enfoque requiere algunos cambios implementación, no requiere una implementación completamente nueva desde cero. Puede usar el código y la capa de datos existentes con cambios mínimos en implementación lógica.</li><li>**No necesita un esquema**: para este fase de migración al SDK web, no necesita un esquema XDM. En su lugar, puede rellenar el `data` objeto, que envía los datos directamente a Audience Manager. Una vez completada la migración al SDK web, puede crear un esquema para su organización y utilizar la asignación de secuencias de datos para rellenar los campos XDM aplicables. Si se necesitara un esquema en este fase del proceso de migración, su organización se vería obligada a utilizar un esquema XDM Audience Manager. El uso de este esquema hace que sea más difícil para su organización utilizar sus propios esquema en el futuro.</li></ul> | <ul><li>**Deuda** técnica de implementación: Dado que este enfoque utiliza una forma modificada de su implementación existente, puede ser más difícil rastrear implementación lógica y realizar cambios en el futuro cuando sea necesario.</li><li>**Requiere asignación para enviar datos a Platform**: Cuando su organización esté lista para usar CDP en tiempo real, debe enviar datos a un conjunto de datos en Adobe Experience Platform. Esta acción requiere que cada campo del `data` objeto sea una entrada en el herramienta de asignación del flujo de datos que lo asigna a un campo de esquema XDM. Para este flujo de trabajo, el mapeo solo debe realizarse una vez, y no implica realizar cambios implementación. Sin embargo, es un paso adicional que no es necesario al enviar datos en un objeto XDM.</li></ul> |

Adobe Systems recomienda seguir esta ruta de implementación en los siguientes escenarios:

* Ya tiene un implementación que utiliza el biblioteca JavaScript Adobe Analytics AppMeasurement. Si tiene un implementación que usa la extensión de etiqueta de Audience Manager, seguir [migre de la extensión de etiqueta de Audience Manager a la extensión](dil-extension-to-web-sdk.md) de etiqueta del SDK web.
* Tiene intención de utilizar CDP en tiempo real en el futuro, pero no desea reemplazar su implementación de Audience Manager por un implementación de SDK web desde cero. La alternativa de reemplazar su implementación desde cero con el SDK web requiere el mayor esfuerzo, ya que necesita reconstruir todos sus rasgos Audience Manager para buscar datos con formato XDM. Sin embargo, también es la arquitectura implementación a largo plazo más viable. Si su organización está dispuesta a realizar el esfuerzo de una implementación de SDK web limpia, consulte la [documentación](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) del SDK web en lugar de usar este guía para obtener más información.

## Pasos necesarios para migrar al SDK web

Siga los pasos que se indican a continuación para migrar la integración de recopilación de datos al SDK web.

+++**1. plan su migración** Analytics.

Trabaje con el equipo de Analytics para seguir los pasos para la migración Analytics en las [implementaciones basadas en etiquetas](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) o [en JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk). Después de haber planeado la migración de Analytics, vuelva a este guía y continúe con los pasos Audience Manager para determinar qué debe hacer por Audience Manager para que pueda implementar la migración Analytics y Audience Manager juntos.

+++

+++**2. añadir del servicio Audience Manager al flujo de datos**

añadir el servicio Audience Manager al flujo de datos que está utilizando en la migración de Analytics mencionada en el paso 1.

1. Navegue hasta [experience.adobe.com](https://experience.adobe.com) e inicie sesión con sus credenciales.
1. Utilice el selector página de inicio o producto de la parte superior derecha para desplazarse hasta **[!UICONTROL Data Collection]**.
1. En el navegación izquierdo, seleccione **[!UICONTROL Datastreams]**.
1. Seleccione el flujo de datos que ha creado como parte de la migración de Analytics en el paso 1.
1. Seleccione **[!UICONTROL Add Service]**.
1. En el menú desplegable de servicio, seleccione **[!UICONTROL Audience Manager]**.
1. Compruebe las **[!UICONTROL Cookie Destinations Enabled]** opciones y **[!UICONTROL URL Destinations Enabled]** . Estas opciones permiten que la red perimetral devuelva esos tipos de destino Audience Manager al Página.
1. Asegúrese de que **[!UICONTROL Enable XDM Flattened Fields]** esté deshabilitado. Esta opción deshabilita el transformación automático de variables Analytics en señales de Audience Manager. Esta opción está diseñada para mantener la compatibilidad con versiones anteriores para los usuarios que migraron al SDK web antes de que la red perimetral transformara automáticamente los datos de Analytics en señales Audience Manager.

   >[!NOTE]
   >
   >La migración al SDK web con la **[!UICONTROL Enabled XDM Flattened Fields]** opción activada requiere que todos los datos necesarios en Audience Manager formateen como XDM y que todas las características Audience Manager que utilizan props, eVars o eventos se actualicen para buscar datos con formato XDM. Adobe Systems recomienda dejar esta opción desactivada.


   ![añadir servicio Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

1. Seleccione **[!UICONTROL Save]** esta opción para guardar la configuración del flujo de datos.

El flujo de datos ya está listo para recibir y pasar datos a Audience Manager. Tenga en cuenta el ID del flujo de datos, ya que este ID es necesario al configurar el SDK web en código.

+++

+++**3. Habilite la sincronización de ID de terceros y establezca el ID de contenedor de Audience Manager**

1. Navegue hasta [experience.adobe.com](https://experience.adobe.com) e inicie sesión con sus credenciales.
1. Utilice el selector página de inicio o producto de la parte superior derecha para desplazarse hasta **[!UICONTROL Data Collection]**.
1. En el navegación izquierdo, seleccione **[!UICONTROL Datastreams]**.
1. Seleccione el flujo de datos que ha creado como parte de la migración de Analytics en el paso 1.
1. Seleccione **[!UICONTROL Edit]** esta opción en la esquina superior derecha del Página de configuración del flujo de datos.
1. Expanda el **[!UICONTROL Advanced Options]** menú desplegable y habilite la **[!UICONTROL Third Party ID Sync]** funcionalidad si aún no está habilitada. Esta opción indica a la red perimetral que devuelva las sincronizaciones de ID de socio para socios de datos Audience Manager y Experience Platform.

   ![Habilite los sincronizar de ID de terceros.](assets/third-party-id-sync.png) {style="border:1px solid lightslategray"}

1. En la mayoría de los casos, puede dejar el **[!UICONTROL Third Party ID Sync Container ID]** campo en blanco. Se establecerá de forma predeterminada en `0`. Sin embargo, si prefiere asegurarse de que se utiliza el ID de contenedor correcto, seguir los siguientes pasos:
   * Abra una ventana del explorador en modo incógnito o privado y navegue hasta una Página que forme parte de la migración.
   * Utilice las herramientas de desarrollo de la explorador para filtrar por la llamada de red a `dpm.demdex.net/id`. Esta llamada solo se activará en la primera Página de una primera visita, por lo que se necesita una explorador de incógnito o privada.
   * Ver la carga útil del solicitud. Si el `d_nsid` parámetro es distinto de cero, cópielo en el **[!UICONTROL Third Party ID Sync Container ID]** campo.

1. Seleccione **[!UICONTROL Save]**.

El flujo de datos ya está listo para enviar datos a Audience Manager y pasar las respuestas Audience Manager al SDK web.

+++

+++**4. añadir ID de cliente al mapa de identidad**

La mayoría de las implementaciones de Audience Manager usan [reglas](../features/profile-merge-rules/merge-rules-overview.md) de combinación de perfiles en escenarios de personalización dispositivos y para ayudar a controlar para qué segmentos pueden calificar los visitantes según su estado de autenticación (sesión o desconexión). Las reglas de combinación de perfiles requieren que se envíe un identificador propiedad del cliente (ID de CRM, número de cuenta, etc.) al Audience Manager en cada llamada recopilación de datos después de la autenticación. Anteriormente, la `setCustomerIDs` función del Servicio de ID de visitante ([!DNL visitor.js]) se utilizaba para anexar ID de cliente a cada Analytics recopilación de datos llamada, que luego se reenviaba a Audience Manager.

Con el SDK web, estas identidades ahora deben enviarse a la red perimetral mediante una construcción XDM especial denominada [IdentityMap](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/identitymap).

Pasar identidades correctamente en un mapa de identidad requiere comprender [los espacios](https://experienceleague.adobe.com/es/docs/experience-platform/identity/features/namespaces) de nombres de identidad y considerar cuidadosamente qué identidades pasar, especialmente cuando se envían datos a un Experience Platform sandbox. [Este artículo](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-21305) describe estas consideraciones e instrucciones.

Una vez que determine qué identidades transferir y cuándo, seguir las guías para usar el elemento[!UICONTROL Identity map] de datos dentro de **[!UICONTROL Identity map]**[ ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/data-element-types#identity-map) Etiquetas o configúrelo manualmente como se describe en la información general[ de ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/identity/overview)datos de identidad para alinearlo con su estrategia de implementación del SDK web.

+++

+++**5. (Opcional) Establecer el cookie de origen `aam_uuid`**

Una práctica estándar durante muchos años fue colocar el Audience Manager UUID (el valor en el cookie demdex de 3rd party) en un cookie de origen generalmente llamado `aam_uuid`.

Para establecer el cookie, debe introducir un nombre de cookie en el **[!UICONTROL Name]** campo de la **[!UICONTROL Unique User ID Cookie]** sección del Analytics etiqueta extensión o el `uuidCookie` campo al configurar el `audienceManagementModule`. Aunque normalmente se configura en el código, el cookie rara vez se usaba porque el valor UUID Audience Manager es un identificador entre dominios específico de dispositivos utilizado por plataformas publicitarias y proporciona poco valor como identificador de origen.

Si encuentra que su implementación requiere que este `aam_uuid` cookie se siga configurando después de la migración al SDK web, puede recuperar el UUID de Audience Manager de dos maneras.

1. Cada respuesta del extremo[ de interacción de ](https://developer.adobe.com/data-collection-apis/docs/endpoints/interact/)red perimetral contiene una carga útil con `id` nodos. La `id` nodo de la `CORE` carga útil del espacio de nombres contiene el UUID Audience Manager.

2. Utilice el [comando getIdentity](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/getidentity) del SDK web para recuperarlo. Utilice el `CORE` espacio de nombres como se describe en la documentación y recupere el valor del `identity.CORE` campo en la respuesta.

Independientemente del método utilizado para recuperar el UUID Audience Manager, depende de su equipo de desarrollo analizar la respuesta, recuperar el UUID y establecer el cookie. No existe ninguna forma automática de establecer este cookie a través del SDK web.

+++

## Configurar el reenvío del lado del servidor y la Analytics de audiencia en el Administrador de grupos de informes de Analytics IU {#configure-ssf-analytics}

Si está familiarizado con la función de reenvío[ de del lado del servidor Analytics](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf), es posible que se pregunte: &quot;¿*Debo deshabilitar la configuración de reenvío de del lado del servidor en el Administrador de grupos de informes de Analytics IU para evitar enviar datos de Analytics a Audience Manager dos veces?&quot;.*

La respuesta es no, no debe desactivar esta configuración, por las siguientes razones:

1. Cuando el servicio Audience Manager está habilitado en un flujo de datos, la red perimetral anexa el `cm.ssf` variable a todas las solicitudes de recopilación de datos enviadas a Analytics. Esto evita que los datos del Analytics también se envíen a Audience Manager. Todos los registros de garantía utilizados para validar la migración de Analytics mostrarán la `cm.ssf=1` variable cuando el servicio de Audience Manager esté habilitado en el flujo de datos. Consulte el Página de cumplimiento de Analytics y RGPD centrado en el [reenvío de](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf-gdpr) del lado del servidor para obtener más detalles.

1. Esta configuración también habilita el flujo de datos para la [!DNL Audience Analytics] integración. Tal y como se describe en la descripción general de la [Analytics de](https://experienceleague.adobe.com/en/docs/analytics/integration/audience-analytics/mc-audiences-aam) audiencia, se requiere del lado del servidor reenvío para esta integración, ya que la respuesta Audience Manager al servidor recopilación de datos de Analytics se añade al Analytics Visita antes de procesar. Un proceso similar ocurre dentro de la red de Edge. Cuando del lado del servidor reenvío está habilitado, la red perimetral agrega los segmentos necesarios de la respuesta Audience Manager a los datos enviados a Analytics.

En resumen, es importante que esta configuración permanezca habilitada para que Audience Analytics siga funcionando con un implementación de SDK web y no se cuente doble datos en Audience Manager.

## Validación de la migración {#validation}

Dado que todas las Adobe Systems soluciones ahora cuentan con una única llamada al SDK web, los pasos para validación pueden cambiar en función de las soluciones que ofrezca el SDK web.

Si Adobe Target o Adobe Systems Journey Optimizer (incluido [!DNL Decisioning]) forman parte de la pila de soluciones a la que presta servicio su implementación, tendrá varias llamadas de red a la red perimetral en el Página. Algunos de ellos están pensados para recuperar personalizaciones y ofertas, mientras que otros están pensados para recopilación de datos y sistema de informes.

Independientemente de su implementación, se aplican los principios generales siguientes para validar que los datos fluyan correctamente hacia y desde Audience Manager a través del SDK web.

1. La primera llamada de red para una visitante por primera Página será al `adobedc.demdex.net` dominio y al `/interact` extremo. Para ver las llamadas de red realizadas por el SDK web, abra el pestaña de desarrollador del explorador web, haga clic en el pestaña Red y, a continuación, filtre por `/interact`.
Existen otros tipos de llamadas al SDK web, pero solo `interact` las llamadas envían datos y obtienen una carga útil de respuesta de la red perimetral.

   ![Imagen de una red de explorador pestaña que muestra las llamadas de interacción.](assets/network.png)

1. La respuesta a la primera llamada de red tiene varias cargas útiles. Uno de esos nodos de carga útil incluye varios subnodos de tipo `url`. Estos `url` nodos son las sincronizaciones de ID de terceros que históricamente fueron activadas por el [!DNL Visitor ID] servicio. Debe haber un `url` nodo para cada sincronizar de ID de terceros que esté configurada en su contenedor (consulte el paso 3 anterior).

   ![Imagen de una red de explorador pestaña que muestra las cargas útiles.](assets/payload.png)

   Además, puede filtrar y `demdex` encontrar que cada una de las URL a las que se hace referencia en la carga útil activó su propia solicitud de red para la sincronización de ID tal gustar como lo hizo el [!DNL Visitor ID] servicio. Estas sincronizaciones de ID solo deben activarse la primera Página de una visitante por primera vez y solo una vez cada 14 días después de eso.

1. Cualquier solicitud posterior `/interact` utilizada para Analytics y Audience Manager recopilación de datos debe contener los `data.__adobe.analytics` nodos de la carga útil.

   ![Imagen de un pestaña de red de explorador que muestra el nodo de análisis en la carga útil.](assets/analytics-node.png)

   Audience Manager características que dependen de estas variables Analytics, así como las que usan las claves de plataforma `h_` OR `d_` deben seguir rellenándose.

   >[!TIP]
   >
   >Es posible que desee crear un rasgo prueba con un expresión regla que solo se pueda expresar si se recopilan los datos del SDK web. Dado que no hay desarrollo Audience Manager entorno y varios sitios podrían estar enviando datos a la misma instancia de Audience Manager, solo mirar los recuentos generales de la población puede no brindarle la validación necesaria.

1. En la misma `/interact` llamada donde se pasan Analytics variables, se puede encontrar cualquier destino cookie o URL en los nodos de carga útil de la respuesta. URL destinos estarán en cargas útiles de tipo `url` (solo gustar en sincronizaciones de ID de terceros) y cookie destinos estarán en cargas útiles de tipo `cookie`.

   ![Imagen de un pestaña de red de explorador que muestra los datos de carga útil.](assets/destinations.png)

   También debe asegurarse de que las cookies se colocaron en el almacenamiento de cookie del explorador.

   >[!TIP]
   >
   >Al igual que en el paso validación anterior, calificar para una segmento que debe devolver un destino cookie es una forma segura de garantizar que los datos fluyan hacia y desde Audience Manager.

1. Si necesita pasar ID de cliente adicionales a través del mapa de identidad, autentifíquese en el sitio y asegúrese de que las identidades y sus parámetros asociados se pasen en el nodo del mapa de identidad de la carga útil de solicitud.

   ![Imagen de un pestaña de red de explorador que muestran datos de identityMap.](assets/pass-customer-ids.png)

   >[!TIP]
   >
   >Si Adobe Target es una de las soluciones receptoras y hay actividades Target que dependen de segmentos Audience Manager que requieren que se pase la identidad correcta, asegúrese de que el mapa de identidad se pasa en las `/interact` llamadas que se usan para recuperar personalizaciones y no solo en recopilación de datos llamadas. Adobe Target utilizará esas identidades en la llamada de del lado del servidor para Audience Manager al recuperar segmento información.

