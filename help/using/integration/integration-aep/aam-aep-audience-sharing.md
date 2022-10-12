---
description: Obtenga información sobre cómo habilitar el uso compartido de datos y cómo se comparten las audiencias entre Audience Manager y Adobe Experience Platform
solution: Audience Manager
title: uso compartido de segmentos de Experience Platform con Audience Manager y otras soluciones de Experience Cloud
keywords: Uso compartido de audiencias de AEP, segmentos de AEP, segmentos de plataforma, uso compartido de segmentos, uso compartido de audiencias, uso compartido de segmentos, AAM uso compartido de segmentos de AEP
feature: Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: 14e0ddd00d3a25674090ea9dbe485c77ad1d2aed
workflow-type: tm+mt
source-wordcount: '1862'
ht-degree: 1%

---

# uso compartido de segmentos de Experience Platform con Audience Manager y otras soluciones de Experience Cloud

## Información general {#overview}

La funcionalidad de uso compartido de audiencias entre Audience Manager y Adobe Experience Platform le permite compartir sus rasgos y segmentos de Audience Manager con Adobe Experience Platform y viceversa. Necesita el [[!DNL Audience Manager Connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html) para permitir el uso compartido de audiencias entre Audience Manager y Adobe Experience Platform.

Puede utilizar rasgos y segmentos de Audience Manager en Experience Platform para agregar datos de Audience Manager a sus perfiles de cliente y beneficiarse del Experience Platform [servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=en).

En Audience Manager, puede utilizar segmentos de Experience Platform para casos de uso de la plataforma de gestión de datos, como:
* Agregar [datos de terceros](/help/using/overview/data-types-collected.md#third-party-data) a sus segmentos;
* [Modelado algorítmico](/help/using/features/algorithmic-models/understanding-models.md);
* Active los segmentos en destinos que aún no sean compatibles con el Experience Platform [catálogo de destinos](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

Además, los segmentos del Experience Platform se comparten con otras soluciones de Experience Cloud a través de [Servicios principales](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * Necesita una licencia de Audience Manager para habilitar los casos de uso de la plataforma de gestión de datos mencionados anteriormente.
> * You *no es necesario* licencia de Audience Manager para compartir segmentos de Experience Platform con Adobe Advertising Cloud, Adobe Target, Marketo y otras soluciones de Experience Cloud a través de la integración de servicios principales.


Consulte la siguiente tabla para obtener una descripción general de los casos de uso de uso compartido de audiencias:

| **Caso de uso** | **Adobe Experience Platform** | **Audience Manager** | **Servicios principales** |
|---------|----------|---------|---------|
| **Uso compartido de audiencias** | <ul><li>Enriquecimiento de los perfiles de los clientes con datos de Audience Manager</li><li>Uso de datos de Audience Manager en la segmentación de Experience Platform</li></ul> | <ul><li>Añadir datos de terceros a segmentos</li><li>Modelado algorítmico</li><li>Activación en destinos adicionales</li></ul> | Utilice segmentos de Experience Platform en otras soluciones de Experience Cloud, como Adobe Target, Advertising Cloud o Marketo. |

{style=&quot;table-layout:auto&quot;}

## Introducción: Cómo habilitar el uso compartido de datos entre Audience Manager y Experience Platform {#enable-data-sharing-aam-aep}

Las dos secciones siguientes indican cómo habilitar el uso compartido de datos entre Audience Manager y Experience Platform.

### Habilitar el uso compartido de datos de Audience Manager a Experience Platform {#enable-aam-to-aep-data}

Para enviar segmentos y características de Audience Manager a Experience Platform, debe configurar el conector de origen del Audience Manager en el catálogo de fuentes del Experience Platform. Se trata de un flujo de trabajo de autoservicio que no requiere la participación del Servicio de atención al cliente de Adobe ni de equipos de ingeniería. Para configurar el conector de origen del Audience Manager, lea:

* [origen del Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
* [Crear una conexión de origen de Adobe Audience Manager en la interfaz de usuario](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=en)

>[!IMPORTANT]
>
>Adobe anima a los clientes a configurar la conexión sin seleccionar la opción **[!UICONTROL Select all segments]** y **[!UICONTROL Select all traits]** como se muestra a continuación. La ingesta de grandes poblaciones de segmentos de Audience Manager tiene un impacto directo en el recuento total de perfiles cuando envía por primera vez un segmento de Audience Manager a Platform mediante la fuente de Audience Manager. Esto significa que si selecciona todos los segmentos, es posible que se produzca un recuento de perfiles superior a su derecho de uso de licencia.
>
>![Captura de pantalla que muestra las opciones Seleccionar todos los segmentos y Seleccionar todas las características desmarcadas en el flujo de trabajo para conectarse al conector de origen del Audience Manager.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Habilitar el uso compartido de datos de Experience Platform a Audience Manager {#enable-aep-to-aam-data}

>[!NOTE]
>
> Póngase en contacto con el administrador de éxito de los clientes de Adobe o con el Servicio de atención al cliente para desbloquear el acceso a esta funcionalidad.

Para enviar segmentos de Experience Platform a Audience Manager, debe ponerse en contacto con el Servicio de atención al cliente o con el Administrador de éxito de clientes. Los equipos de Servicio de atención al cliente y de Administración de asistencia al cliente deben presentar un ticket (consulte el ticket de plantilla AAM-52354) para habilitar la conexión de Platform a Audience Manager.

Asegúrese de compartir los planes para los datos que van de Platform a Audience Manager, para asegurarse de que la conexión esté configurada correctamente. Por ejemplo, si necesita compartir datos regionales para segmentos enviados a Adobe Target, esta información debe comunicarse en el ticket. La conexión de uso compartido de datos de Experience Platform a Audience Manager se configura en un plazo de seis días laborables a partir de la presentación de la solicitud.

## Segmentos y características de Audience Manager en Adobe Experience Platform {#aam-segments-traits-in-aep}

Después de configurar el conector de origen del Audience Manager para importar rasgos y segmentos desde el Audience Manager, los datos del Audience Manager aparecen en el Experience Platform como **Audiencias** en el flujo de trabajo del segmento. Para obtener más información sobre los segmentos y las características del Audience Manager en Experience Platform, lea:

* [Información general del servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
* [Guía del usuario del Generador de segmentos del Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)

## Segmentos de Adobe Experience Platform en Audience Manager {#aep-segments-in-aam}

Los segmentos que crea en el Experience Platform aparecen en la interfaz del Audience Manager como señales, rasgos y segmentos, con las siguientes reglas de composición:

* Señal: Para cada segmento de Experience Platform, debería ver señales en el formulario `segID = segment ID`.
* Característica: La regla de rasgos es el ID del segmento del Experience Platform.
* Segmento: El segmento consiste en el rasgo descrito anteriormente.

### Señales {#aep-segments-as-aam-signals}

Select **[!UICONTROL Audience Data > Signals > General Online Data]** y buscar por `SegId` para encontrar señales procedentes del Experience Platform. Puede utilizar esta pantalla para depurar, para comprobar si la integración entre Experience Platform y Audience Manager se ha configurado correctamente.

![Consulte las señales del Experience Platform en el Audience Manager en el panel de señales](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Rasgos  {#aep-segments-as-aam-traits}

El Audience Manager crea automáticamente una carpeta de características llamada **Características del Experience Platform** en el almacenamiento de rasgos.

![Características del panel Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Puede utilizar características creadas automáticamente en segmentos junto con otras características. Por ejemplo, puede combinar características creadas a partir de segmentos de Experience Platform con características de terceros adquiridas a través del [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Para ver un ejemplo de una característica creada automáticamente a partir de un segmento de Experience Platform, consulte la captura de pantalla siguiente:

![Característica del Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Número de artículo | Nombre | Descripción |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Las características creadas a partir de segmentos de Experience Platform se crean como características integradas en Audience Manager. |
| 2 | [!UICONTROL Data Source] | Creado automáticamente. Todos los rasgos y segmentos que se crean automáticamente a partir de segmentos del Experience Platform se almacenan en la fuente de datos **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | El código de integración corresponde al ID del segmento en Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | La expresión de rasgo es `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Un segmento creado automáticamente que utiliza este rasgo como su composición. |

{style=&quot;table-layout:auto&quot;}

### Segmentos  {#aep-segments-as-aam-segments}

El Audience Manager crea automáticamente una carpeta de segmentos llamada **Segmentos del Experience Platform** en el almacenamiento de segmentos.

![Captura de pantalla del tablero](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Para ver un ejemplo de un segmento creado automáticamente a partir de un segmento de Experience Platform, consulte la captura de pantalla siguiente:

![Captura de pantalla del segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Número de artículo | Nombre | Descripción |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | El código de integración corresponde al ID del segmento en Experience Platform. |
| 2 | [!UICONTROL Data Source] | Creado automáticamente. Todos los rasgos y segmentos que se crean automáticamente a partir de segmentos del Experience Platform se almacenan en la fuente de datos **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indica que los segmentos creados automáticamente siguen la configuración de la directiva de combinación en Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | El segmento consiste en el rasgo descrito en la variable [Sección Características](#aep-segments-as-aam-traits). |

{style=&quot;table-layout:auto&quot;}

## Compatibilidad con el control de exportación de datos del Audience Manager en el Experience Platform {#aam-data-export-control-in-aep}

Para hacer cumplir el uso de los datos en el Experience Platform, todos los conjuntos de datos y campos aplicables deben recibir la información adecuada [etiquetas de uso de datos](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html). Además, [políticas de uso de datos](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html) debe estar habilitado para acciones de marketing específicas con respecto a esas etiquetas, tal como se indica en la [Marco de etiquetado y aplicación del uso de los datos (DULE)](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html#dule-framework).

En el proceso de uso compartido de audiencias entre el Audience Manager y el Experience Platform, cualquier control de exportación de datos que se haya aplicado a segmentos de Audience Manager se traduce a etiquetas y acciones de marketing equivalentes reconocidas por el control de datos del Experience Platform y viceversa.

>[!NOTE]
>
>Para obtener información más general sobre los controles de exportación de datos, consulte la [Documentación de Controles de exportación de datos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html).
>
>Este documento proporciona una referencia sobre cómo los controles de exportación de datos de Audience Manager específicos se asignan a las etiquetas de uso de datos y a las acciones de marketing en Platform.

### Controles de exportación de datos a etiquetas de uso de datos

La tabla siguiente describe cómo los controles de exportación de datos específicos se asignan a etiquetas de uso de datos reconocidas:

| Control de exportación de datos | Etiqueta de uso de datos |
| --- | --- |
| No se puede utilizar con información de identificación personal | C3: Los datos no pueden combinarse ni utilizarse de otro modo con información directamente identificable |
| No se puede usar para direccionamiento de anuncios externos | C5: Los datos no se pueden usar para segmentar contenido o anuncios en sitios múltiples basados en intereses |
| No se puede usar para la segmentación de anuncios en el sitio | C6: Los datos no se pueden usar para la segmentación de anuncios en el sitio |
| No se puede usar para la personalización en el sitio | C7: Los datos no se pueden usar para segmentar el contenido en el sitio |

{style=&quot;table-layout:auto&quot;}

### Controles de exportación de datos a acciones de marketing

La siguiente tabla describe cómo las etiquetas de exportación de datos específicas se asignan a acciones de marketing reconocidas:

| Etiqueta de exportación de datos | Acción de marketing |
| --- | --- |
| Este destino puede permitir una combinación con información de identificación personal (PII) | Combinación con PII |
| Este destino se puede usar para la segmentación de anuncios fuera del sitio | Segmentación entre sitios |
| Este destino se puede usar para la segmentación de anuncios en el sitio | Publicidad en el sitio |
| Este destino puede utilizarse para la personalización de anuncios en el sitio | Personalización en el sitio |

{style=&quot;table-layout:auto&quot;}

## Comprender las diferencias de población entre Audience Manager y Experience Platform {#aep-aam-segment-population-differences}

Los números de población de segmentos pueden variar entre los segmentos del Audience Manager y del Experience Platform. Aunque los números de segmentos para audiencias similares o idénticas deberían estar cerca, las diferencias en la población pueden deberse a los factores que se enumeran a continuación.

### Evaluación de segmentos en el Experience Platform

El Audience Manager actualiza los números de los informes en la interfaz una vez al día. El momento de esta actualización raramente se alinea con el momento de la evaluación del segmento en el Experience Platform.

### Diferencias entre las reglas de combinación de perfiles y las políticas de combinación

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) en Audience Manager y [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html) en el Experience Platform trabaja de forma diferente, y el gráfico de identidad utilizado para cada uno varía. Debido a esto, se esperan algunas diferencias entre las poblaciones de segmentos.

>[!NOTE]
>
> Al compartir segmentos de Experience Platform a Audience Manager, su organización de Platform [directiva de combinación predeterminada](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en#default-merge-policy) tiene prioridad sobre la variable [directiva de combinación utilizada por el segmento](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#merge-policies) compartido con Audience Manager. Por ejemplo, si la política de fusión del segmento compartido permite [Vinculación de ID](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=en#configure), pero la directiva de combinación predeterminada de la organización no lo hace, esto puede provocar diferencias de población entre Platform y Audience Manager.

### Composición de segmentos en el Experience Platform

La integración entre Adobe Experience Platform y Audience Manager comparte una serie de [áreas de nombres de identidad](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#identity-types) para todos los clientes: ECID, IDFA, GAID, direcciones de correo electrónico con hash (EMAIL_LC_SHA256), AdCloud ID. Si los segmentos del Experience Platform utilizan cualquiera de estos elementos como identidad principal para los perfiles cualificados, los perfiles se cuentan en rasgos y segmentos del Audience Manager.

>[!NOTE]
>
> Las audiencias en Experience Platform con identidades marcadas por correos electrónicos sin procesar nunca aparecen en Audience Manager.

Por ejemplo, si tuviera un segmento de Experience Platform &quot;Todos mis clientes&quot; y los perfiles cualificados fueran ID de CRM, ECID, IDFA, direcciones de correo electrónico sin procesar y con hash, el segmento correspondiente en Audience Manager solo incluiría perfiles desactivados de ECID, IDFA y direcciones de correo electrónico con hash. La población del segmento en Audience Manager sería menor que la del Experience Platform.

![Experience Platform al uso compartido de segmentos del Audience Manager: composición de segmentos](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Información general del servicio de segmentación](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
>* [Guía del usuario del Generador de segmentos del Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)
>* [Conector del Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

