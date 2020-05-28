---
description: Definiciones y enlaces a otras lecturas.
seo-description: Definiciones y enlaces a otras lecturas.
seo-title: Glosario
solution: Audience Manager
title: Glosario
uuid: 01fc26f5-db9d-4e90-b4c1-27c6a510accc
translation-type: tm+mt
source-git-commit: 62147fc719a59d2b2c7b444bce853334b03816c6
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 3%

---


# Glosario{#glossary}

Definiciones y enlaces a otras lecturas.

## A-B {#a-b}

**Modelado algorítmico**

Use [!UICONTROL Algorithmic Modeling] como medio para extender el alcance más allá del núcleo de usuarios que ha identificado. La función le ayuda a descubrir nuevas audiencias únicas mediante la análisis automatizada de datos. Administre su [!UICONTROL Algorithmic Models] en **[!UICONTROL Audience Data > Models]**.

Consulte [Explicación de los modelos](../features/algorithmic-models/algo-models-overview.md)algorítmicos.

<br> 

**BAAAM**

[!UICONTROL Bulk Management Tools]. Las [!UICONTROL Bulk Management Tools] siguientes [!DNL Audience Manager] son un conjunto de herramientas basadas en Microsoft Excel que permiten crear, modificar o eliminar varios objetos a la vez con una sola operación. Puede trabajar con orígenes de datos, señales derivadas, destinos, carpetas, segmentos y características. La función utiliza una hoja de cálculo de Microsoft Excel con macros que realizan llamadas seguras y autenticadas a las [!DNL Audience Manager] API.

Consulte Herramientas [de administración masiva](../reference/bulk-management-tools/bulk-management-intro.md).

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]. Un [!UICONTROL CDF] archivo representa una descarga masiva de datos recopilados por [!DNL Audience Manager] y le permite trabajar con [!DNL Audience Manager] datos fuera de los límites impuestos por nuestra interfaz de usuario. Un [!UICONTROL CDF] archivo contiene los mismos datos que una llamada de [!DNL Audience Manager] evento ( `/event`) envía a nuestros servidores. Esto incluye datos como ID de usuario, ID de características, ID de segmentos y todos los demás parámetros capturados por una llamada de evento.

See [Customer Data Feeds](../features/cdf-files.md).

<br> 

**ID de CRM**

El ID de CRM es el ID mediante el cual los clientes identifican a los usuarios en su propio sistema CRM. En lugar del ID de CRM, se utiliza el término DPUUID en el Administrador de Audiencias.

Consulte DPUUID en el [índice de ID en el Administrador](../reference/ids-in-aam.md)de Audiencias.

<br> 

**Audiencia direccionable al cliente**

En la Audiencia [](/help/using/features/addressable-audiences.md)direccionable, esta métrica representa los dispositivos que:
* Se han realizado características basadas en reglas o integradas durante la ventana retroactiva
   **Y**
* Haga una sincronización de ID con el destino elegido independientemente del tiempo de sincronización.

<br> 

**Atributos del cliente**

See [Customer Attributes](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) in the [!DNL Experience Cloud Core Services] product documentation.

<br> 

**Tasa de coincidencia del cliente**

Audiencia direccionable al cliente ÷ Audiencia total del cliente expresada como porcentaje. See [Addressable Audience](/help/using/features/addressable-audiences.md).

<br> 

**Audiencia total del cliente**

En la Audiencia [](/help/using/features/addressable-audiences.md)direccionable, esta métrica representa un recuento de dispositivos que han realizado una característica basada en reglas en sus propiedades o una característica incorporada de los archivos sin conexión durante la ventana retroactiva.

<br> 

**demdex.net**

Demdex.net es un dominio heredado controlado por [!DNL Adobe]. Refleja [!DNL Audience Manager]el nombre original previo a la adquisición ( [!DNL Demdex]). [!DNL Adobe] adquirido [!DNL Demdex] en 2011 y cambió la marca de la compañía como [!DNL Audience Manager]. Todas las llamadas HTTP a `demdex.net` dominios son llamadas enviadas a [!DNL Adobe].

Consulte [Explicación de las llamadas al dominio Demdex](../reference/demdex-calls.md).

<br> 

**DAID**

[!UICONTROL Device Advertising IDs] son identificadores de dispositivo únicos, utilizados para identificar un dispositivo móvil. Estos ID son asignados por el fabricante del dispositivo, no por Adobe. En [!DNL Audience Manager]la se admiten los ID de dispositivos iOS y Android.

See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Destino**

En [!DNL Audience Manager], un destino es cualquier otro sistema (servidor de publicidad, DSP, red de publicidad, etc.) que desea compartir datos con. El [!UICONTROL Destination Builder] en nuestra interfaz de usuario proporciona las herramientas que le permiten crear y administrar estos procesos de envío de datos. [!DNL Audience Manager] las características de destino se encuentran en **[!UICONTROL Audience Data > Destinations]**.

<br> 

**DIL**

La [!UICONTROL Data Integration Library] es una biblioteca de API que se utiliza [!DNL Audience Manager] para recopilar datos de interacción del usuario. See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**dpm**

[!UICONTROL Data Provider Match]. Indica a los sistemas internos [!DNL Adobe] que una llamada desde [!DNL Audience Manager] o el servicio de ID está pasando los datos del cliente para la sincronización o para solicitar un ID. Consulte [Explicación de las llamadas al dominio Demdex](../reference/demdex-calls.md).

## E-F {#e-f}

**Experience Cloud ID (ECID)**

Anteriormente denominado el [!DNL Marketing Cloud] ID (MID o MCID). El [!DNL Experience Cloud] ID es fundamental para el servicio de ID. Es un identificador único y persistente para los visitantes del sitio. Consulte Cookies y el servicio [de identidad de](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html)Adobe Experience Platform.

<br> 

**Característica de la carpeta**

Agrupación automática de características dentro de la taxonomía de carpetas. Cada carpeta de la jerarquía crea automáticamente una característica que puede utilizarse para definir segmentos.

Consulte Características [de la carpeta: Acerca](../features/traits/about-folder-traits.md).

<br> 

**Límite de frecuencia**

Límite de un número de veces que un anunciante desea mostrar un elemento creativo determinado a un usuario final. Puede configurar varias expresiones de límite de frecuencia en [!UICONTROL Segment Builder].

Consulte [Actualización y Frecuencia](../features/segments/recency-and-frequency.md).

## G-H {#g-h}

**GAID**

ID de publicidad de Google, el ID de dispositivo exclusivo que Google asigna a los dispositivos de hardware que ejecutan el sistema operativo Android. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**GUID**

Siglas para el identificador único global. No usamos el término GUID en [!DNL Audience Manager]. En nuestro caso, el GUID es el [!DNL Audience Manager] UUID.
See [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

## I-J {#i-j}

**IDFA**

Identificador para anunciantes, el ID de dispositivo único que Apple asigna a sus productos. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Entrante**

Proceso mediante el cual se pueden enviar datos de audiencia de otras fuentes a [!DNL Audience Manager]. Consulte [Envío de datos](/help/using/integration/sending-audience-data/send-audience-data.md)de Audiencia.

<br> 

**Código de integración**

Al trabajar con la interfaz de usuario o la API, tiene la opción de agregar un código de integración al crear características, segmentos o fuentes de datos. [!DNL Audience Manager] Los códigos de integración tienen diferentes propósitos en estos casos:

* [!UICONTROL Traits]:: un código de integración es un campo para un ID, SKU u otro valor utilizado por los procesos empresariales internos. Opcional.
* [!UICONTROL Segments]:: un código de integración es un campo para un ID definido por el usuario u otra información específica de la compañía. Opcional.
* [!UICONTROL Data Sources]:: los códigos de integración son necesarios cuando desea crear fuentes de datos entre dispositivos, utilizar el servicio de identidad de la plataforma Adobe Experience Platform o trabajar con [!UICONTROL Profile Merge Rules]. Consulte [Crear una fuente](../features/manage-datasources.md#create-data-source) de datos para obtener más información.

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

Consulte [Modelado](../reference/aam-glossary.md#a-b)algorítmico.

## M-N {#m-n}

**MCID**, **MID**

Consulte el ID [de](../reference/aam-glossary.md#e-f)Experience Cloud.

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]. La [!UICONTROL PCS] es una base de datos grande, que se ejecuta en Apache Cassandra. Almacena los datos recibidos para los usuarios activos desde las transferencias de servidor a servidor y desde el [!UICONTROL DCS]. [!UICONTROL PCS] los datos constan de ID de dispositivo, ID de perfil autenticados y sus características asociadas.

Consulte Componentes [de recopilación de datos](../reference/system-components/components-data-collection.md).

<br> 

**Vínculo de perfil**

See [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

<br> 

**Reglas de combinación de Perfil**

[!UICONTROL Profile Merge Rules] permite controlar el tipo de datos que [!DNL Audience Manager] se utilizan para la segmentación.

See [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

## Q-R {#q-r}

**Realización**

Acción mediante la cual un visitante del sitio califica para una característica. Puede utilizar la herramienta [Visitante Perfil Viewer](../features/visitor-profile-viewer.md) para obtener información sobre la realización de características por un usuario específico.

## S-T {#s-t}

**Segmento**

Un segmento (o una audiencia) es un conjunto de usuarios que comparten atributos comunes.

Consulte [Segmentos: Propósito, Composición y Reglas](../features/segments/segments-purpose.md).

<br> 

**Audiencia direccionable del segmento**

En la Audiencia [](/help/using/features/addressable-audiences.md)direccionable, esta métrica representa el número de usuarios que han pertenecido al segmento durante el período de retroactividad del informe y que tienen una sincronización de ID activa en el sitio. Los segmentos pueden incluir sus propios datos de origen y datos de terceros y de terceros, a través de las características adquiridas en [Audiencia Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

<br> 

**Población total del segmento**

En la Audiencia [](/help/using/features/addressable-audiences.md)direccionable, esta métrica representa un recuento de todos los dispositivos que fueron miembros de su segmento durante el período de retroactividad del informe.

<br> 

**Tasa de coincidencia de segmentos**

Audiencia direccionable del segmento ÷ Población total del segmento expresada como porcentaje. See [Addressable Audience](/help/using/features/addressable-audiences.md).

<br> 

**Señal**

Las señales son las unidades de datos más pequeñas de [!DNL Audience Manager] y se expresan como pares clave-valor.

Consulte [Señales, características y segmentos](../reference/signal-trait-segment.md).

<br> 

**Rasgo**

Una característica es una combinación de una o más señales. Consulte [Señales, características y segmentos](../reference/signal-trait-segment.md).

<br> 

**Población de características**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

**TTL (Tiempo de vida)**

TTL define cuántos días permanece un visitante cualificado en una característica. TTL se establece en características y no en segmentos. Los Visitantes salen de un segmento si no ven una característica cualificada antes del final del intervalo TTL. Obtenga más información en [Segmento y características Tiempo de vida explicado](/help/using/features/traits/segment-ttl-explained.md).

<br> 

## U-V {#u-v}

**UUID**

[!DNL Audience Manager] ID de usuario único. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Visitor ID**

The [!DNL Experience Cloud] ID Service (formerly visitor ID) provides a universal, persistent ID that identifies your visitors across all the solutions in the [!DNL Experience Cloud].

Consulte la documentación de [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) .

## W-X-Y-Z {#w-z}

