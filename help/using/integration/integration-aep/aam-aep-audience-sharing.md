---
description: Obtenga información sobre cómo habilitar el uso compartido de datos y cómo se comparten las audiencias entre Audience Manager y Adobe Experience Platform
solution: Audience Manager
title: Uso compartido de segmentos de Experience Platform con Audience Manager y otras soluciones de Experience Cloud
keywords: AAM Uso compartido de audiencias de AEP, segmentos de AEP, segmentos de Platform, uso compartido de segmentos, uso compartido de audiencias, uso compartido de segmentos, uso compartido de segmentos de AEP, uso compartido de segmentos de AEP,
feature: Experience Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: d21d0574ee0338dbd5e11c60e0d64042182aa18b
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 1%

---

# Uso compartido de segmentos de Experience Platform con Audience Manager y otras soluciones de Experience Cloud

## Información general {#overview}

La funcionalidad de uso compartido de audiencias entre Audience Manager y Adobe Experience Platform le permite compartir sus rasgos de Audience Manager y segmentos con Adobe Experience Platform y segmentos de Experience Platform con Audience Manager.

Necesita el destino [[!DNL Audience Manager source connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=es) y [Audiencias de Experience Cloud](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html?lang=es) en Experience Platform para habilitar el uso compartido de audiencias entre Audience Manager y Adobe Experience Platform.

Puede usar rasgos y segmentos de Audience Manager en Experience Platform para agregar datos de Audience Manager a sus perfiles de cliente y beneficiarse del servicio de segmentación del Experience Platform [1&rbrace;.](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=es)

En Audience Manager, puede utilizar segmentos de Experience Platform para casos de uso de Data Management Platform, como:
* Agregue [datos de terceros](/help/using/overview/data-types-collected.md#third-party-data) a sus segmentos;
* [Modelado algorítmico](/help/using/features/algorithmic-models/understanding-models.md);
* Active los segmentos a destinos que aún no sean compatibles con el Experience Platform [catálogo de destinos](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html?lang=es).

Además, los segmentos de Experience Platform se comparten con otras soluciones de Experience Cloud a través de [Servicios principales](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html?lang=es).

>[!IMPORTANT]
>
> * Necesita una licencia de Audience Manager para habilitar los casos de uso de la plataforma de administración de datos mencionados anteriormente.
> * *no necesita* una licencia de Audience Manager para compartir segmentos de Experience Platform con Adobe Advertising Cloud, Adobe Target, Marketo y otras soluciones de Experience Cloud a través de la integración de servicios principales.

Consulte la tabla siguiente para obtener una descripción general de los casos de uso compartido de audiencias:

| **Caso de uso** | **Adobe Experience Platform** | **Audience Manager** | **Servicios principales** |
|---------|----------|---------|---------|
| **Uso compartido de audiencias** | <ul><li>Enriquecimiento de los perfiles de los clientes con datos de Audience Manager</li><li>Uso de datos de Audience Manager en la segmentación de Experience Platform</li></ul> | <ul><li>Añadir datos de terceros a los segmentos</li><li>Modelado algorítmico</li><li>Activación a destinos adicionales</li></ul> | Utilice segmentos de Experience Platform en otras soluciones de Experience Cloud, como Adobe Target, Advertising Cloud o Marketo. |

{style="table-layout:auto"}

## Segmentos y rasgos de Audience Manager en Adobe Experience Platform {#aam-segments-traits-in-aep}

En las secciones siguientes se describe cómo habilitar el uso compartido de datos de Audience Manager a Experience Platform, y cómo utilizar los rasgos y segmentos de Audience Manager en Experience Platform.

### Habilitar el uso compartido de datos de Audience Manager a Experience Platform {#enable-aam-to-aep-data}

Para enviar segmentos y rasgos de Audience Manager a Experience Platform, debe configurar el conector de origen del Audience Manager en el catálogo de fuentes del Experience Platform. Se trata de un flujo de trabajo de autoservicio que no requiere la participación del Servicio de atención al cliente de Adobe ni de equipos de ingeniería. Para configurar el conector de origen del Audience Manager, lea:

* [origen del Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=es)
* [Crear una conexión de origen de Adobe Audience Manager en la interfaz de usuario](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=es)

>[!IMPORTANT]
>
>El Adobe anima a los clientes a configurar la conexión sin seleccionar las opciones **[!UICONTROL Select all segments]** y **[!UICONTROL Select all traits]**, como se muestra a continuación. La ingesta de poblaciones de segmentos de Audience Manager de tamaño considerable tiene un impacto directo en el recuento total de perfiles al enviar por primera vez un segmento de Audience Manager a Platform mediante la fuente de Audience Manager. Esto significa que la selección de todos los segmentos puede dar lugar potencialmente a un recuento de perfiles que supere el derecho de uso de la licencia.
>
>![Captura de pantalla que muestra las opciones Seleccionar todos los segmentos y Seleccionar todos los rasgos desmarcadas en el flujo de trabajo para conectarse al conector de origen del Audience Manager.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Uso de rasgos y segmentos de Audience Manager en Experience Platform {#use-aam-data-in-aep}

Después de configurar el conector de origen del Audience Manager para importar características y segmentos de Audience Manager, los datos del Audience Manager aparecen en el Experience Platform como **Audiencias** en el flujo de trabajo de segmentos. Para obtener más información sobre los segmentos y las características de los Audience Manager en Experience Platform, lea:

* [Resumen del servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=es#audiences)
* [Guía del usuario del Generador de segmentos de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=es#audiences)

## Segmentos de Adobe Experience Platform en Audience Manager {#aep-segments-in-aam}

En las secciones siguientes se describe cómo habilitar el uso compartido de datos de Experience Platform a Audience Manager y cómo utilizar los segmentos de Experience Platform en Audience Manager.

### Habilitar el uso compartido de datos de Experience Platform a Audience Manager {#enable-aep-to-aam-data}

>[!IMPORTANT]
>
> En esta sección se describe la integración de uso compartido de segmentos heredados de Experience Platform a Audience Manager. Ahora puede configurar esta integración sin la asistencia de representantes de clientes de Adobe. Para obtener más información, lea la documentación de destino de [Audiencias de Experience Cloud](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html?lang=es).

>[!NOTE]
>
> Póngase en contacto con el administrador de éxito del cliente de Adobe o con el servicio de atención al cliente para desbloquear el acceso a esta funcionalidad.

Para enviar segmentos de Experience Platform a Audience Manager, debe ponerse en contacto con el Servicio de atención al cliente o con el Customer Success Manager. AAM Los equipos de atención al cliente y de administración de la asistencia al cliente deben presentar un ticket (consulte ticket de plantilla-52354) para habilitar la conexión de Platform a Audience Manager.

Asegúrese de compartir planes para los datos que van de Platform a Audience Manager para asegurarse de que la conexión esté configurada correctamente. Por ejemplo, si necesita que se compartan los datos regionales de los segmentos enviados a Adobe Target, esta información debe comunicarse en el ticket. La conexión de uso compartido de datos del Experience Platform al Audience Manager se configura en un plazo de seis días hábiles a partir de la solicitud que se envía.

### Uso de segmentos del Experience Platform en Audience Manager {#use-aep-data-in-aam}

Los segmentos que se crean en Experience Platform aparecen en la interfaz de Audience Manager como señales, rasgos y segmentos, con las siguientes reglas de composición:

* Señal: para cada segmento de Experience Platform, debería ver las señales en el formulario `segID = segment ID`.
* Característica: La regla de características es el ID del segmento de Experience Platform.
* Segmento: el segmento consta del rasgo descrito anteriormente.

### Señales {#aep-segments-as-aam-signals}

Seleccione **[!UICONTROL Audience Data > Signals > General Online Data]** y busque `SegId` para encontrar las señales que llegan desde el Experience Platform. Puede utilizar esta pantalla con fines de depuración para comprobar si la integración entre el Experience Platform y el Audience Manager se ha configurado correctamente.

![Ver señales de Experience Platform en el Audience Manager en el panel Señales](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Características {#aep-segments-as-aam-traits}

El Audience Manager crea automáticamente una carpeta de características llamada **Características de Experience Platform** en su almacenamiento de características.

![Características del tablero del Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Puede utilizar características creadas automáticamente en segmentos junto con otras características. Por ejemplo, puede combinar características creadas a partir de segmentos de Experience Platform con características de terceros adquiridas mediante [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Para ver un ejemplo de una característica creada automáticamente a partir de un segmento de Experience Platform, consulte la siguiente captura de pantalla:

![Rasgo del Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Número de artículo | Nombre | Descripción |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Las características creadas a partir de segmentos de Experience Platform se crean como características integradas en Audience Manager. |
| 2 | [!UICONTROL Data Source] | Creado automáticamente. Todos los rasgos y segmentos que se crean automáticamente a partir de segmentos del Experience Platform se almacenan en el origen de datos **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | El código de integración corresponde al ID del segmento en el Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | La expresión de rasgos es `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Un segmento creado automáticamente que utiliza este rasgo como composición. |

{style="table-layout:auto"}

### Segmentos {#aep-segments-as-aam-segments}

El Audience Manager crea automáticamente una carpeta de segmentos llamada **Segmentos del Experience Platform** en su almacenamiento de segmentos.

![Captura de pantalla del tablero](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Para ver un ejemplo de un segmento creado automáticamente a partir de un segmento de Experience Platform, consulte la siguiente captura de pantalla:

![Captura de pantalla del segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Número de artículo | Nombre | Descripción |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | El código de integración corresponde al ID del segmento en el Experience Platform. |
| 2 | [!UICONTROL Data Source] | Creado automáticamente. Todos los rasgos y segmentos que se crean automáticamente a partir de segmentos del Experience Platform se almacenan en el origen de datos **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indica que los segmentos creados automáticamente siguen la política de combinación configurada en el Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | El segmento consiste en el rasgo descrito en la [sección Rasgos](#aep-segments-as-aam-traits). |

{style="table-layout:auto"}

## Compatibilidad con el control de exportación de datos de Audience Manager en Experience Platform {#aam-data-export-control-in-aep}

Para aplicar el cumplimiento del uso de datos en Experience Platform, todos los conjuntos de datos y campos aplicables deben tener [etiquetas de uso de datos](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=es) apropiadas. Además, las [políticas de uso de datos](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=es) deben habilitarse para acciones de marketing específicas contra esas etiquetas, como se describe en el marco de [etiquetado y aplicación del uso de datos (Data Usage Labeling and Enforcement, DULE)](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=es#dule-framework).

En el proceso de uso compartido de audiencias entre Audience Manager y Experience Platform, cualquier control de exportación de datos que se haya aplicado a segmentos de Audience Manager se traduce en etiquetas y acciones de marketing equivalentes que reconoce Gobernanza de datos de Experience Platform, y viceversa.

>[!NOTE]
>
>Para obtener información más general sobre los controles de exportación de datos, consulte la [documentación sobre los controles de exportación de datos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=es).
>
>Este documento proporciona una referencia sobre cómo los controles específicos de exportación de datos de Audience Manager se asignan a las etiquetas de uso de datos y a las acciones de marketing en Platform.

### Controles de exportación de datos a etiquetas de uso de datos

En la tabla siguiente se describe cómo se asignan los controles de exportación de datos específicos a las etiquetas de uso de datos reconocidas:

| Control de exportación de datos | Etiqueta de uso de datos |
| --- | --- |
| No se puede usar con información de identificación personal | C3: Los datos no se pueden combinar ni utilizar de otro modo con información directamente identificable |
| No se puede usar para la segmentación de anuncios fuera del sitio | C5: Los datos no pueden utilizarse para la segmentación de contenido o anuncios entre sitios basada en intereses |
| No se puede usar para la segmentación de anuncios en el sitio | C6: los datos no se pueden usar para la segmentación de anuncios en el sitio |
| No se puede usar para la personalización en el sitio | C7: Los datos no se pueden usar para la segmentación de contenido en el sitio |

{style="table-layout:auto"}

### Controles de exportación de datos para acciones de marketing

En la tabla siguiente se describe cómo se asignan las etiquetas de exportación de datos específicas a las acciones de marketing reconocidas:

| Etiqueta de exportación de datos | Acción de marketing |
| --- | --- |
| Este destino puede permitir una combinación con información de identificación personal (PII) | Combinar con PII |
| Este destino se puede utilizar para la segmentación de anuncios fuera del sitio | Segmentación entre sitios |
| Este destino se puede utilizar para la segmentación de anuncios en el sitio | Advertising in situ |
| Este destino se puede utilizar para la personalización de anuncios en el sitio | Personalization in situ |

{style="table-layout:auto"}

## Comprender las diferencias de población de segmentos entre Audience Manager y Experience Platform {#aep-aam-segment-population-differences}

Los números de población de los segmentos pueden variar entre los segmentos del Audience Manager y del Experience Platform. Aunque los números de segmento de audiencias similares o idénticas deben estar cerca, las diferencias en las poblaciones pueden deberse a los factores enumerados a continuación.

### Evaluación de segmentos en el Experience Platform

El Audience Manager actualiza los números de los informes en la interfaz una vez al día. El momento de esta actualización rara vez se alinea con el momento de la evaluación del segmento en Experience Platform.

### Diferencias entre las reglas de combinación de perfiles y las directivas de combinación

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) en el Audience Manager y [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html?lang=es) en el Experience Platform funcionan de manera diferente, y el gráfico de identidades usado para cada uno varía. Debido a esto, se esperan algunas diferencias entre las poblaciones de segmentos.

>[!NOTE]
>
> Al compartir segmentos de Experience Platform a Audience Manager, su organización de Platform [política de combinación predeterminada](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=es#default-merge-policy) tiene prioridad sobre la [política de combinación utilizada por el segmento](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=es#merge-policies) compartido con el Audience Manager. Por ejemplo, si la política de combinación del segmento compartido permite la [vinculación de ID](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=es#configure), pero no la política de combinación predeterminada de la organización, podrían producirse diferencias de población entre Platform y el Audience Manager.

### Composición de segmentos en el Experience Platform

La integración entre Adobe Experience Platform y Audience Manager comparte una serie de [áreas de nombres de identidad](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=es#identity-types) estándar para todos los clientes: ECID, IDFA, GAID, direcciones de correo electrónico con hash (EMAIL_LC_SHA256) e ID de AdCloud. Si los segmentos de Experience Platform utilizan cualquiera de ellos como identidad principal para los perfiles cualificados, los perfiles se cuentan en rasgos y segmentos de Audience Manager.

>[!NOTE]
>
> Las audiencias en Experience Platform con identidades marcadas por correos electrónicos sin procesar nunca aparecen en Audience Manager.

Por ejemplo, si tuviera un segmento de Experience Platform &quot;Todos mis clientes&quot; y los perfiles cualificados fueran CRM ID, ECID, IDFA, direcciones de correo electrónico sin procesar y con hash, el segmento correspondiente en Audience Manager solo incluiría perfiles sin clave de ECID, IDFA y direcciones de correo electrónico con hash. La población del segmento en Audience Manager sería menor que la del Experience Platform.

![Uso compartido de segmentos de Experience Platform a Audience Manager - composición de segmentos](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Resumen del servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=es#audiences)
>* [Guía del usuario del Generador de segmentos de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=es#audiences)
>* [Conector de Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=es)
