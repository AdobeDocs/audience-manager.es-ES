---
description: Utilice destinos basados en personas para enviar segmentos de audiencia de origen a entornos basados en personas. Estos entornos son ecosistemas cerrados que pertenecen a una entidad que controla el contenido que se muestra dentro de él. Incluyen plataformas sociales como Facebook y otras plataformas que dependen de las cuentas de los clientes para personalizar el contenido mostrado.
seo-description: Use people-based destinations to send first-party audience segments to people-based environments. These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. They include social platforms such as Facebook, and other platforms that rely on customer accounts to personalize the displayed content.
seo-title: People-Based Destinations Overview and Use Cases
solution: Audience Manager
title: Información general y casos de uso
feature: People-based Destinations
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
source-git-commit: ab3361a0a54a7200d2f0c03a82ae6ef61a755be9
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 0%

---

# Información general y casos de uso {#overview-use-cases}

Utilice [!DNL People-Based Destinations] esta opción para enviar segmentos de audiencia propios a entornos basados en personas. Estos entornos son ecosistemas cerrados que pertenecen a una entidad que controla el contenido que se muestra dentro de él. Incluyen plataformas sociales como [!DNL Facebook], y otras plataformas que dependen de las cuentas de los clientes para personalizar el contenido mostrado.

>[!IMPORTANT]
>Este artículo contiene documentación del producto destinada a ayudarle guía a través de la configuración y el uso de esta característica. Nada de lo contenido en este documento es asesoramiento legal. Consulte a su propio asesor legal para obtener orientación legal.

## Información general {#overview}

[!DNL People-Based Destinations] Permite aplicar segmentación en datos de en línea y sin conexión para crear segmentos audiencia basados en [identificadores](people-based-destinations-prerequisites.md#hashing-requirements) hash, como las direcciones correo electrónico. Luego, puede enviar estos segmentos a &quot;jardines amurallados&quot; como [!DNL Facebook], donde puede destino su audiencia en las plataformas sociales. [!DNL People-Based Destinations] puede ayudarle a:

* Target sin conexión y en línea audiencias en plataformas como [!DNL Facebook], basándose en direcciones de correo electrónico con hash;
* Complementar las capacidades existentes dispositivos y cookie direccionamiento de Audience Manager;
* Eliminar los costos asociados con las soluciones de incorporación de datos de terceros;
* Eliminar los costos asociados con el desarrollo de flujos de trabajo de incorporación de datos personalizados;
* Target audiencias en entornos sin cookie;
* Target audiencias eliminando la duplicación de direcciones correo electrónico con hash que coincidan con los ID de cliente.

Puede usar [!DNL People-Based Destinations] para segmento y destino clientes de alto valor que pueden no visitar su sitio web, o dejar de direccionamiento aquellos que ya se han convertido sin conexión. Además, puede impulsar [!DNL Profile Merge Rules] combinar sus datos de origen sin conexión con sus datos de origen en línea, incluidos los datos de clientes de otras soluciones Adobe Experience Cloud, para optimizar sus esfuerzos publicitarios medios sociales.

![Información general de PBD](assets/pbd-overview.png)

## Disponibilidad {#availability}

[!DNL People-Based Destinations] es una integración Audience Manager premium. Póngase en contacto con su representante de Adobe para aprovechar esta función premium.

## Por qué debería utilizar [!UICONTROL People-Based Destinations] {#why-use}

**Proporcione a sus clientes experiencias coherentes entre canal administrando todo su segmentación de audiencia desde Audience Manager.**

No activar sus segmentos de audiencia en canales basados en personas a través de Audience Manager conduce a experiencias inconexas entre lo que sus clientes ven cuando visitan su sitio web y lo que ven, por instancia, en sus [!DNL Facebook] feeds. Tener un direccionamiento consistente en todos los canales puede aumentar su ingresos de anuncios al tiempo que optimiza su gasto anuncios.

**Llegue a audiencias en canales basados en personas sin necesidad de una solución de incorporación de datos dedicada o flujos de trabajo personalizada para enviar audiencias.**

La forma más &quot;tradicional&quot; de direccionamiento audiencias a través de canales basados en personas implica que tenga que exportar los datos de sus clientes de una formato aceptada por la plataforma en la que desea anunciarse, y luego usar el método de incorporación de datos dedicado de la plataforma para llevar los datos de sus clientes a su anunciante cuenta. Todo esto es trabajo manual que debe hacer para cada plataforma en la que desea anunciarse. Además, diferentes plataformas pueden tener diferentes requisitos de formato de datos, lo que hace que el proceso sea igualado más tedioso.

![Información general de PBD](assets/pbd-diagram.png)

A través de [!DNL People-Based Destinations], Audience Manager le ayuda a centralizar los datos de los clientes, versión audiencia segmentos y activarlos en varios canales basados en personas. Puede hacer todo esto desde la interfaz de Audience Manager usuario, evitando el trabajo adicional de cargar manualmente datos en cada plataforma, lo que le ahorra un tiempo valioso en el proceso.

**Crear y activar audiencia segmentos desde perfiles puramente sin conexión.**

[!DNL People-Based Destinations] Resuelva el problema que, anteriormente, solo podía activar segmentos audiencia basados en dispositivos actividad. Con [!DNL People-Based Destinations], puede crear segmentos a partir de datos puramente sin conexión propios [!DNL CRM]y activarlos en plataformas basadas en personas. Además, puede correlacionar los datos de sin conexión con dispositivos datos que ya tiene en Audience Manager.

**Aproveche los controles de privacidad y gobernanza de datos de Audience Manager para gestionar los datos de los clientes de forma segura.**

[!DNL People-Based Destinations] requiere que solo utilice identificadores hash irreversibles. Esto reduce el riesgo asociado con la carga manual de datos del cliente en cada plataforma de destino.

Vea el vídeo siguiente para obtener una visión general del flujo de datos al utilizar [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## Casos de uso {#use-cases}

Para ayudarle a comprender mejor cómo y cuándo debe usar [!DNL People-Based Destinations], aquí hay dos casos de uso de ejemplo que Audience Manager clientes pueden resolver con esta característica.

### Caso de uso #1 {#use-case-1}

Una en línea minorista quiere llegar a los clientes existentes a través de plataformas sociales y mostrarles ofertas personalizadas basadas en sus pedidos anteriores. Con [!DNL People-Based Destinations], los minorista en línea pueden ingerir direcciones de correo electrónico hash propias a Audience Manager, versión segmentos a partir de sus propios datos de [!DNL CRM] sin conexión y enviar estos segmentos a las plataformas sociales en las que desean anunciarse, optimizando su gasto publicitario.

### Caso de uso #2 {#use-case-2}

Una aerolínea tiene diferentes niveles de clientes (Bronce, Plata y Oro) y desea proporcionar a cada uno de los niveles ofertas personalizadas a través de plataformas sociales. El compañía utiliza Audience Manager para analizar las actividad de los clientes en el sitio web. Sin embargo, no todos los clientes utilizan la aplicación móvil de la aerolínea, y algunos de ellos no han iniciado sesión en el sitio web de la compañía. Los únicos identificadores que el compañía tiene sobre estos clientes son ID de abono y direcciones correo electrónico.

Para destino a través de canales medios sociales y similares basados en personas, pueden incorporar los datos de los clientes a Audience Manager [!DNL CRM] , utilizando las direcciones de correo electrónico con hash como identificadores.

Siguiente, pueden combinar sus datos de sin conexión con sus características de actividad de en línea existentes para versión nuevos segmentos de audiencia que pueden destino a través de [!DNL People-Based Destinations].
