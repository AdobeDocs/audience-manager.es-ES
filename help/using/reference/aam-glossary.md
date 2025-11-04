---
description: Definiciones y enlaces para obtener más información.
seo-description: Definitions and links to further reading.
seo-title: Glossary
solution: Audience Manager
title: Glosario
uuid: 01fc26f5-db9d-4e90-b4c1-27c6a510accc
feature: Reference
exl-id: 9e2ee3d3-01b2-4038-abda-fedf0f16f163
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '1157'
ht-degree: 96%

---

# Glosario{#glossary}

Definiciones y enlaces para obtener más información.

## A-B {#a-b}

**Modelado algorítmico**

Use [!UICONTROL Algorithmic Modeling] como medio para extender el alcance más allá del núcleo de usuarios que ha identificado. La función le ayuda a descubrir nuevas audiencias únicas mediante el análisis automatizado de datos. Administre su [!UICONTROL Algorithmic Models] en **[!UICONTROL Audience Data > Models]**.

Consulte [Explicación de los modelos algorítmicos](../features/algorithmic-models/algo-models-overview.md).

**BAAAM**

[!UICONTROL Bulk Management Tools]. Las [!UICONTROL Bulk Management Tools] en [!DNL Audience Manager] son un conjunto de herramientas basadas en Microsoft Excel que permiten crear, modificar o eliminar varios objetos a la vez con una sola operación. Puede trabajar con fuentes de datos, señales derivadas, destinos, carpetas, segmentos y rasgos. La funcionalidad utiliza una hoja de cálculo de Microsoft Excel con macros que realizan llamadas seguras y autenticadas a las API de [!DNL Audience Manager].

Consulte [Herramientas de administración masiva](../reference/bulk-management-tools/bulk-management-intro.md).

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]. Un archivo [!UICONTROL CDF] representa una descarga en lotes de datos recopilados por [!DNL Audience Manager] y le permite trabajar con datos de [!DNL Audience Manager] fuera de los límites impuestos por nuestra interfaz de usuario. Un archivo [!UICONTROL CDF] contiene los mismos datos que una llamada de evento de [!DNL Audience Manager] (`/event`) envía a nuestros servidores. Esto incluye datos como ID de usuario, ID de rasgos, ID de segmentos y todos los demás parámetros capturados por una llamada de evento.

Consulte [Fuentes de datos por cliente](../features/cdf-files.md).

**ID de CRM**

El ID de CRM es el ID mediante el cual los clientes identifican a los usuarios en su propio sistema CRM. En lugar del ID de CRM, se utiliza el término DPUUID en Audience Manager.

Consulte DPUUID en el [índice de ID en Audience Manager](../reference/ids-in-aam.md).



**Audiencia a la que se puede dirigir el cliente**

En la [Audiencia a la que se puede dirigir](/help/using/features/addressable-audiences.md), esta métrica representa los dispositivos que:

* Cuentan con rasgos basados en reglas o incorporados durante la ventana retrospectiva

  **Y**

* Tienen una sincronización de ID con el destino elegido independientemente del tiempo de sincronización.


**Atributos del cliente**

Consulte [Atributos del cliente](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=es) en la documentación del producto de [!DNL Experience Cloud Core Services]



**Tasa de coincidencia del cliente**

Audiencia a la que se puede dirigir el cliente ÷ Audiencia total del cliente expresada como porcentaje. Consulte [Audiencia a la que se puede dirigir](/help/using/features/addressable-audiences.md).



**Audiencia total del cliente**

En la [Audiencia a la que se puede dirigir](/help/using/features/addressable-audiences.md), esta métrica representa un recuento de dispositivos que cuentan con un rasgo basado en reglas en sus propiedades o un rasgo incorporado de los archivos sin conexión durante la ventana retroactiva.



**demdex.net**

Demdex.net es un dominio heredado controlado por [!DNL Adobe]. Refleja el nombre original de [!DNL Audience Manager] previo a la adquisición ([!DNL Demdex]). [!DNL Adobe] adquirió [!DNL Demdex] en 2011 y cambió su nombre a [!DNL Audience Manager]. Todas las llamadas HTTP a dominios `demdex.net` se redirigen a [!DNL Adobe].

Consulte [Explicación de las llamadas al dominio Demdex](../reference/demdex-calls.md).



**DAID**

[!UICONTROL Device Advertising IDs] son identificadores de dispositivo únicos, utilizados para identificar un dispositivo móvil. El fabricante del dispositivo es el encargado de asignar estos ID, no Adobe. En [!DNL Audience Manager] admiten los ID de dispositivos iOS y Android.

Consulte [Índice de ID en Audience Manager](../reference/ids-in-aam.md).



**Destino**

En [!DNL Audience Manager], un destino es cualquier otro sistema (servidor de publicidad, DSP, red de publicidad, etc.) con el que desee compartir datos. El [!UICONTROL Destination Builder] en nuestra interfaz de usuario proporciona las herramientas que le permiten crear y administrar estos procesos de envío de datos. Las funcionalidades de destinos de [!DNL Audience Manager] se encuentran en **[!UICONTROL Audience Data > Destinations]**.



**DIL**

La [!UICONTROL Data Integration Library] es una biblioteca de API que utiliza [!DNL Audience Manager] para recopilar datos de interacción del usuario. Consulte [API de Data Integration Library (DIL)](../dil/dil-overview.md).



**dpm**

[!UICONTROL Data Provider Match]. Indica a los sistemas internos de [!DNL Adobe] que una llamada desde [!DNL Audience Manager] o el servicio de ID está pasando los datos del cliente para su sincronización o para solicitar un ID. Consulte [Explicación de las llamadas al dominio Demdex](../reference/demdex-calls.md).

## E-F {#e-f}

**Experience Cloud ID (ECID)**

Anteriormente conocido como [!DNL Marketing Cloud] ID (MID o MCID). El [!DNL Experience Cloud] ID es fundamental para el servicio de ID. Es un identificador único y persistente para los visitantes del sitio. Consulte Cookies y el [servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=es).



**Rasgos de carpeta**

Agrupación automática de rasgos dentro de la taxonomía de carpetas. Cada carpeta de la jerarquía crea automáticamente un rasgo que puede utilizarse para definir segmentos.

Consulte [Acerca de los rasgos de carpeta](../features/traits/about-folder-traits.md).



**Restricción de frecuencia**

Límite de veces que un anunciante desea mostrar un elemento creativo determinado a un usuario final. Puede configurar varias expresiones de límite de frecuencia en [!UICONTROL Segment Builder].

Consulte [Actualización y frecuencia](../features/segments/recency-and-frequency.md).

## G-H {#g-h}

**GAID**

Google Advertising ID, el ID de dispositivo exclusivo que Google asigna a los dispositivos de hardware que ejecutan el sistema operativo Android. Consulte [Índice de ID en Audience Manager](../reference/ids-in-aam.md).



**GUID**

Siglas para el identificador único global (Globally Unique Identifier). No usamos el término GUID en [!DNL Audience Manager]. En nuestro caso, el GUID en [!DNL Audience Manager] es el UUID.
Consulte [Índice de ID en Audience Manager](../reference/ids-in-aam.md).

## I-J {#i-j}

**IDFA**

Identificador para anunciantes, el ID de dispositivo único que Apple asigna a sus productos. Consulte [Índice de ID en Audience Manager](../reference/ids-in-aam.md).



**Entrante**

Proceso mediante el cual se pueden enviar datos de audiencia de otras fuentes a [!DNL Audience Manager]. Consulte [Envío de datos de audiencia](/help/using/integration/sending-audience-data/send-audience-data.md).



**Código de integración**

Al trabajar con la interfaz de usuario o la API de [!DNL Audience Manager], tiene la opción de agregar un código de integración al crear rasgos, segmentos o fuentes de datos. Los códigos de integración tienen diferentes propósitos en estos casos:

* [!UICONTROL Traits]: un código de integración es un campo para un ID, SKU u otro valor utilizado por los procesos empresariales internos. Opcional.
* [!UICONTROL Segments]: un código de integración es un campo para un ID definido por el usuario u otra información específica de la compañía. Opcional.
* [!UICONTROL Data Sources]: los códigos de integración son necesarios cuando desea crear fuentes de datos entre dispositivos, utilizar el servicio de identidad de Adobe Experience Platform o trabajar con [!UICONTROL Profile Merge Rules]. Consulte [Crear una fuente de datos](../features/manage-datasources.md#create-data-source) para obtener más información.

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

Consulte [Modelado algorítmico](../reference/aam-glossary.md#a-b).

## M-N {#m-n}

**MCID**, **MID**

Consulte [Experience Cloud ID](../reference/aam-glossary.md#e-f).

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]. [!UICONTROL PCS] es una base de datos grande, que se ejecuta en Apache Cassandra. Almacena los datos recibidos para los usuarios activos desde las transferencias de servidor a servidor y desde [!DNL DCS]. Los datos [!UICONTROL PCS] constan de los ID de dispositivo, ID de perfil autenticados y sus rasgos asociados.

Consulte [Componentes de recopilación de datos](../reference/system-components/components-data-collection.md).



**Vínculo de perfil**

Consulte [Opciones definidas de reglas de combinación de perfiles](../features/profile-merge-rules/merge-rule-definitions.md).



**Reglas de combinación de perfiles**

[!UICONTROL Profile Merge Rules] permite controlar el tipo de datos que [!DNL Audience Manager] utiliza para la segmentación.

Consulte [Opciones definidas de reglas de combinación de perfiles](../features/profile-merge-rules/merge-rule-definitions.md).

## Q-R {#q-r}

**Realización**

Acción mediante la cual un visitante del sitio se clasifica para un rasgo. Puede utilizar la herramienta [Visualizador de perfil del visitante](../features/visitor-profile-viewer.md) para obtener información sobre la realización de rasgos de un usuario específico.

## S-T {#s-t}

**Segmento**

Un segmento (o audiencia) es un conjunto de usuarios que comparten atributos similares.

Consulte [Segmentos: Finalidad, composición y reglas](../features/segments/segments-purpose.md).



**Audiencia a la que se puede dirigir el segmento**

En la [Audiencia a la que se puede dirigir](/help/using/features/addressable-audiences.md), esta métrica representa el número de usuarios que han pertenecido al segmento durante el período retrospectivo del informe y que tienen una sincronización de ID activa en el sitio. Los segmentos pueden incluir sus propios datos de origen y de terceros, a través de los rasgos adquiridos en [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).



**Población total del segmento**

En [Audiencias a las que se puede dirigir](/help/using/features/addressable-audiences.md), esta métrica representa un recuento de todos los dispositivos que fueron miembros de su segmento durante el período retrospectivo del informe.



**Tasa de coincidencia de segmentos**

Audiencia a la que se puede dirigir el segmento ÷ Población total del segmento expresada como porcentaje. Consulte [Audiencia a la que se puede dirigir](/help/using/features/addressable-audiences.md).



**Señal**

Las señales son las unidades de datos más pequeñas de [!DNL Audience Manager] y se expresan como pares clave-valor.

Consulte [Señales, rasgos y segmentos](../reference/signal-trait-segment.md).



**Rasgo**

Un rasgo es una combinación de una o más señales. Consulte [Señales, rasgos y segmentos](../reference/signal-trait-segment.md).



**Población de rasgos**

Consulte [Datos de tamaño de segmentos y rasgos en el Generador de segmentos](../features/segments/segment-builder-data.md)

**TTL (Tiempo de vida)**

TTL define cuántos días permanece un visitante clasificado en un rasgo. El TTL se establece en rasgos y no en segmentos. Los visitantes salen de un segmento si no se clasifican para un rasgo del final del TTL. Obtenga más información en [Explicación del TTL de segmentos y rasgos](/help/using/features/traits/segment-ttl-explained.md).



## U-V {#u-v}

**UUID**

[!DNL Audience Manager] ID de usuario único. Consulte [Índice de ID en Audience Manager](../reference/ids-in-aam.md).



**ID de visitante**

El servicio [!DNL Experience Cloud]ID (antes conocido como ID de visitante) ofrece un identificador universal y persistente que identifica a los visitantes en todas las soluciones de [!DNL Experience Cloud].

Consulte la documentación del [servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es).

## W-X-Y-Z {#w-z}
