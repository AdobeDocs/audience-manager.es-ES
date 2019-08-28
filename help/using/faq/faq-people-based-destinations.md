---
description: 'Respuestas a preguntas comunes sobre destinos basados en personas.  '
seo-description: 'Respuestas a preguntas comunes sobre destinos basados en personas.  '
seo-title: Preguntas frecuentes sobre destinos basados en personas
solution: Audience Manager
title: Preguntas frecuentes sobre destinos basados en personas
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# Preguntas frecuentes sobre destinos basados en personas {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability {#availability}

**No puedo ver[!DNL People-Based Destinations]en mi cuenta de Audience Manager. ¿Qué debo saber sobre la disponibilidad?**

[!DNL People-Based Destinations] es una función Premium Audience Manager disponible durante la compra. Póngase en contacto con su representante de ventas de Adobe para obtener más detalles sobre los precios y la disponibilidad.

## Integración de datos {#data-onboarding}

**¿Cómo puedo integrar las direcciones de correo electrónico de los clientes en Audience Manager para poder utilizarlas[!DNL People-Based Destinations]?**

Existen dos maneras de introducir los datos sin conexión en Audience Manager.[!DNL People-Based Destinations]

* **Utilice la sincronización de ID basada en archivos**. Consulte [Requisitos de nombre y contenido para archivos de sincronización de ID](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) para obtener más información sobre los archivos de sincronización de ID que deben aparecer. Al utilizar este método, puede dirigir todas las direcciones de correo electrónico con hash de la [!DNL CRM] base de datos.
* **Utilice ID declarados** para declarar direcciones de correo electrónico con hash al pasar ID de cliente autenticados. Al utilizar este método, Audience Manager activa únicamente las direcciones de correo electrónico con hash de los usuarios que se han autenticado en línea. Las direcciones de correo electrónico activadas a través de Facebook son sólo las de las llamadas de eventos de ID declarados. Otras direcciones de correo electrónico asociadas con el ID de cliente no se activan en tiempo real.

**¿Se pueden recopilar direcciones de correo electrónico hash a través de un formulario Web o una aplicación móvil, o bien se tienen que ver en un archivo por lotes?**

Puede recopilar direcciones de correo electrónico hash a través de la autenticación Web con [!DNL ECID] ID [declarados](../features/declared-ids.md). El archivo por lotes permite también recopilar direcciones de correo electrónico hash que no se pueden enviar a través de la autenticación (p. ej. usuarios inactivos en el ([!DNL CRM]) y activarlos en destinos basados en personas.

**¿Cómo se ingestan direcciones de correo electrónico hash a través de formularios Web diferentes de la carga de direcciones de correo electrónico hash a través de archivos por lotes?**

La ingesta de datos sin conexión está diseñada para admitir casos de uso sin autenticación y una nueva regla de combinación de perfiles ([!UICONTROL All Cross-Device Profiles]) que se ejecuta en todos [!DNL CRM] los perfiles sin conexión, independientemente de la autenticación disponible como parte [!DNL People-Based Destinations]de. Este método está diseñado para complementar la ingestión de audiencias autenticadas de fuentes en línea.

**¿Cuál es la frecuencia máxima en la que puedo enviar/actualizar las direcciones de correo electrónico con hash?**

* Cuando se usan ID declarados, Audience Manager envía las direcciones de correo electrónico con hash al destino en tiempo real.
* Al ingestar datos mediante archivos de sincronización de ID, Audience Manager los procesa diariamente.

**¿Cómo sé si el hash de la dirección de correo electrónico se realiza correctamente?**

Audience Manager no está ingestando la dirección de correo electrónico sin procesar y no podemos validar que el hash se haya realizado correctamente. Consulte [Requisitos previos y consideraciones](../features/destinations/people-based-destinations-prerequisites.md) para obtener detalles sobre cómo debe hash los datos cargados.

## Reglas de combinación de perfiles {#profile-merge-rules}

**¿Existe una nueva regla de combinación de perfiles con[!DNL People-Based Destinations]la que puedo utilizar?**

Sí. Los clientes que compran [!DNL People-Based Destinations] también reciben acceso a una nueva regla de combinación de perfiles para la segmentación sin conexión. Se llama a la regla [!DNL All Cross-Device Profiles] y se utiliza para la segmentación sin conexión. Cuando se registra, [!DNL People-Based Destinations]es la cuarta regla de combinación de perfiles que puede crear, aparte de las tres reglas existentes basadas en autenticación.

**¿Tengo que duplicar mis segmentos de audiencia existentes para activarlos?[!DNL People-Based Destinations]**

Depende del caso de uso. Si planea activar segmentos de origen existentes en canales basados en personas, no necesita crear nuevos segmentos. Solo puede asignar los segmentos a un destino basado en personas.

Si planea activar nuevas audiencias sin conexión en canales basados en personas, debe crear nuevos segmentos de origen mediante la regla [!DNL All Cross-Device Profiles] de combinación.
>[!NOTE]
>
> Solo puede asignar segmentos con datos de origen a [!DNL People-Based Destinations]. Las plataformas de destino no aceptan segmentos con datos de segundo y tercero.

## Tasas de coincidencia {#match-rates}

**[!DNL People-Based Destinations]¿Tiene visibilidad de tasas de coincidencia o audiencias direccionables?**

No. Al enviar segmentos de audiencia a [!DNL People-Based Destinations], la coincidencia de audiencia se produce en el lado del socio. Adobe no tiene acceso a esas métricas. Audience Manager muestra la audiencia máxima compartible para cada destino y el recuento en tiempo real de las personas que pertenecen a un segmento. Esta información le ayudará con la planificación y previsión de campañas.

**¿Cómo se comparan las tasas[!DNL People-Based Destinations]teóricamente con otros métodos de envío de audiencias a plataformas de destino?**

Siempre y cuando la dirección de correo electrónico sea hash e ingesta correctamente, no habrá diferencia en la tasa de coincidencia entre [!DNL People-Based Destinations] y otros métodos. La única razón por la que una tasa de coincidencia sería inferior al 100% es si las direcciones de correo electrónico que se trajeron a Audience Manager no pueden coincidir con una dirección de correo electrónico en la base de usuarios de la plataforma de destino.

**Recopilo direcciones de correo electrónico de mis clientes, que difieren de las direcciones de correo electrónico personales utilizadas en las redes sociales. ¿Cómo coincide con las identidades en varias direcciones de correo electrónico?**

Audience Manager puede recopilar y enviar 10 correos electrónicos por usuario a plataformas de destino, pero las direcciones de correo electrónico deben capturarse a través de archivos de sincronización. Cuando Audience Manager envía las direcciones de correo electrónico a plataformas de destino, es posible que las plataformas coincidan con las direcciones de correo electrónico con respecto a su propia base de usuario. Algunas plataformas pueden tener gráficos de direcciones de correo electrónico adicionales para coincidir con las direcciones enviadas desde Audience Manager a perfiles de usuario.

## Controles de exportación de datos {#data-export-controls}

**¿Cómo[!DNL Data Export Controls][!DNL People-Based Destinations]funcionan?**

[!DNL Data Export Controls] bloquearán cualquier segmento que contenga datos de segundo y tercero que los usuarios intenten enviar [!DNL People-Based Destinations]. [!DNL People-Based Destinations] permitir solamente que se usen datos de origen para la segmentación. [!DNL Data Export Controls] bloquear también segmentos con [!DNL Profile Merge Rules] gráficos de dispositivos. [!DNL People-Based Destinations] se crean con las etiquetas adecuadas de exportación de datos activadas y no se puede sobrescribir la configuración de exportación.

## Preguntas específicas de socio {#partner-specific-questions}

### [!DNL Facebook]

**¿Qué debo hacer antes de poder enviar segmentos de audiencia a[!DNL Facebook]?**

Antes de utilizar [!DNL People-Based Destinations] para enviar segmentos de audiencia, [!DNL Facebook]debe realizar las siguientes tareas de configuración:

1. Agregue la cuenta comercial de Adobe Experience Cloud como socio de publicidad en [!DNL Facebook Ad Account]su. Utilice `business ID=206617933627973`. Consulte Agregar socios a su Administrador comercial para obtener más información.

   >[!IMPORTANT]
   >
   > Al configurar los permisos para Adobe Experience Cloud, debe habilitar el permiso Administrar campañas. Esto es necesario para [!DNL People-Based Destinations] la integración.

1. Lea y firme [!DNL Facebook Custom Audiences Terms of Service]el. Para hacerlo, vaya a `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, donde `accountID` es [!DNL Facebook Ad Account ID]su.

**[!DNL People-Based Destinations]¿Es compatible con la segmentación de audiencias en otras[!DNL Facebook]aplicaciones, como[!DNL Instagram]?**

Puede usar [!DNL People-Based Destinations] la [!DNL Facebook]familia de aplicaciones compatibles con [!DNL Custom Audiences], incluido [!DNL Facebook], [!DNL Instagram][!DNL Audience Network] y [!DNL Messenger]. La selección de la aplicación en la que desee ejecutar la campaña se indica en el nivel de ubicación en [!DNL Facebook Ads Manager].

**¿Cuál es la diferencia[!DNL People-Based Destinations]entre y[!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] aprovecha la [!DNL Custom Audiences (CA)] integración con [!DNL Facebook]. La diferencia entre [!DNL WCA] y [!DNL CA] las integraciones es la clave que utilizan los clientes al enviar audiencias. [!DNL Facebook] [!DNL WCA] utiliza [!DNL Facebook] el píxel (que sería un ID de usuario de un sitio web) mientras [!DNL People-Based Destinations] se usan direcciones de correo electrónico con hash para integrar [!DNL CA].

Puede utilizar [!DNL Facebook][!DNL WCA] la integración de Audience Manager mediante [!DNL URL Destinations] la función sin costes adicionales.

Estas dos integraciones son complementarias; Puede utilizar ambos para garantizar una mejor cobertura de audiencia. Como ejemplo, [!DNL WCA] se puede utilizar para la publicación cuando una empresa está buscando dirigirse a visitantes del sitio Web que no hayan registrado una cuenta, y [!DNL People-Based Destinations] puede ayudarle a dirigirse a clientes existentes que hayan proporcionado su dirección de correo electrónico pero tal vez no hayan visitado el sitio Web.
