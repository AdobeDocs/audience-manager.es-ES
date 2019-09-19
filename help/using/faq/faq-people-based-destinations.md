---
description: 'Respuestas a preguntas comunes sobre los destinos basados en personas.  '
seo-description: 'Respuestas a preguntas comunes sobre los destinos basados en personas.  '
seo-title: Preguntas más frecuentes sobre destinos basados en personas
solution: Audience Manager
title: Preguntas más frecuentes sobre destinos basados en personas
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# Preguntas más frecuentes sobre destinos basados en personas {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability {#availability}

**No puedo ver[!DNL People-Based Destinations]en mi cuenta de Audience Manager. ¿Qué necesito saber sobre disponibilidad?**

[!DNL People-Based Destinations] es una función Premium de Audience Manager que está disponible en el momento de la compra. Póngase en contacto con su representante de ventas de Adobe para obtener más información sobre precios y disponibilidad.

## Integración de datos {#data-onboarding}

**¿Cómo puedo incorporar direcciones de correo electrónico de clientes en Audience Manager para poder usarlas en[!DNL People-Based Destinations]?**

Existen dos formas de llevar los datos sin conexión a Audience Manager para [!DNL People-Based Destinations].

* **Utilice la sincronización** de ID basada en archivos. Consulte Requisitos de [nombre y contenido para archivos](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) de sincronización de ID para obtener más información sobre el aspecto que deben tener los archivos de sincronización de ID. Al utilizar este método, puede segmentar todas las direcciones de correo electrónico con hash de la [!DNL CRM] base de datos.
* **Utilice ID** declarados para declarar direcciones de correo electrónico con hash al pasar ID de cliente autenticados. Al utilizar este método, Audience Manager solo activa las direcciones de correo electrónico con hash de los usuarios autenticados en línea. Las direcciones de correo electrónico activadas a través de Facebook son solo las que aparecen en las llamadas de evento de ID declaradas. Otras direcciones de correo electrónico asociadas con el ID de cliente no se activan en tiempo real.

**¿Puedo recopilar direcciones de correo electrónico con hash a través de un formulario web o una aplicación móvil, o bien tienen que pasar por un archivo por lotes?**

Puede recopilar direcciones de correo electrónico con hash mediante la autenticación web mediante [!DNL ECID] el uso de ID [declarados](../features/declared-ids.md). El archivo por lotes también permite recopilar direcciones de correo electrónico con hash que no se pueden enviar mediante autenticación (por ejemplo, usuarios inactivos en su ([!DNL CRM]) y activarlas en destinos basados en personas.

**¿En qué se diferencia la ingesta de direcciones de correo electrónico con hash a través de formularios web de la carga de direcciones de correo electrónico con hash a través de archivos por lotes?**

La ingestión de datos sin conexión está diseñada para admitir casos de uso sin autenticación, y una nueva regla de combinación de perfiles ([!UICONTROL All Cross-Device Profiles]) que se ejecuta en todos los [!DNL CRM] perfiles sin conexión independientemente de la autenticación está disponible como parte de [!DNL People-Based Destinations]. Este método está diseñado para complementar la ingestión de audiencias autenticadas a partir de fuentes en línea.

**¿Cuál es la frecuencia máxima con la que puedo enviar/actualizar direcciones de correo electrónico con hash?**

* Al utilizar ID declarados, Audience Manager envía las direcciones de correo electrónico con hash al destino en tiempo real.
* Al transferir datos mediante archivos de sincronización de ID, Audience Manager los procesa diariamente.

**¿Cómo sé si el hash de la dirección de correo electrónico se ha realizado correctamente?**

Audience Manager no está ingiriendo la dirección de correo electrónico sin procesar y no podemos validar que el hash se haya realizado correctamente. Consulte [Requisitos previos y consideraciones](../features/destinations/people-based-destinations-prerequisites.md) para obtener detalles sobre cómo debe hash los datos incorporados.

## Reglas de combinación de perfiles {#profile-merge-rules}

**¿Hay una nueva regla de combinación de perfiles que pueda usar con[!DNL People-Based Destinations]?**

Sí. A los clientes que compran también [!DNL People-Based Destinations] se les concede acceso a una nueva regla de combinación de perfiles para la segmentación sin conexión. Se llama a la regla [!DNL All Cross-Device Profiles] y se utiliza para la segmentación solo sin conexión. Al registrarse para [!DNL People-Based Destinations], esta es la cuarta regla de combinación de perfiles que puede crear, aparte de las tres reglas basadas en autenticación existentes.

**¿Tengo que duplicar mis segmentos de audiencia existentes para activarlos en[!DNL People-Based Destinations]?**

Depende de su caso de uso. Si planea activar segmentos de origen existentes en canales basados en personas, no necesita crear nuevos segmentos. Puede asignar los segmentos a un destino basado en personas.

Si planea activar nuevas audiencias sin conexión en canales basados en personas, debe crear nuevos segmentos de origen mediante la regla de [!DNL All Cross-Device Profiles] combinación.
>[!NOTE]
>
> Solo puede asignar segmentos con datos de origen a [!DNL People-Based Destinations]. Nuestras plataformas de destino no aceptan segmentos con datos de segundo y de terceros.

## Coincidir tasas {#match-rates}

**¿[!DNL People-Based Destinations]Tiene visibilidad sobre las tasas de coincidencia o las audiencias a las que se puede dirigir?**

No. Al enviar segmentos de audiencia a [!DNL People-Based Destinations], la coincidencia de audiencias se produce en el lado del socio. Adobe no tiene acceso a esas métricas. Audience Manager muestra la audiencia máxima que se puede compartir para cada destino y el recuento en tiempo real de personas que pertenecen a un segmento. Esta información puede ayudarle con la planificación y previsión de campañas.

**¿Cómo se compararían teóricamente las tasas de coincidencia con otros métodos de envío de audiencias a plataformas de destino?[!DNL People-Based Destinations]**

Siempre y cuando la dirección de correo electrónico esté correctamente almacenada en hash y anidada, no debería haber ninguna diferencia en la tasa de coincidencia entre [!DNL People-Based Destinations] y otros métodos. La única razón por la que una tasa de coincidencia sería inferior al 100 % es si las direcciones de correo electrónico introducidas en Audience Manager no pueden coincidir con una dirección de correo electrónico en la base de usuarios de la plataforma de destino.

**Recopilo direcciones de correo electrónico de trabajo de mis clientes, que son diferentes de las direcciones de correo electrónico personales utilizadas en las redes sociales. ¿Cómo se relacionan las identidades en varias direcciones de correo electrónico?**

Audience Manager puede recopilar y enviar hasta 10 correos electrónicos por usuario a las plataformas de destino, pero las direcciones de correo electrónico deben capturarse mediante archivos de sincronización. Una vez que Audience Manager envía las direcciones de correo electrónico a las plataformas de destino, las plataformas deben hacer coincidir las direcciones de correo electrónico con su propia base de usuarios. Algunas plataformas pueden tener gráficos de direcciones de correo electrónico adicionales para coincidir con las direcciones enviadas desde Audience Manager a los perfiles de usuario.

## Controles de exportación de datos {#data-export-controls}

**¿Cómo[!DNL Data Export Controls]trabajar con[!DNL People-Based Destinations]?**

[!DNL Data Export Controls] bloqueará cualquier segmento que contenga datos de segundo y de terceros a los que los usuarios intenten enviar [!DNL People-Based Destinations]. [!DNL People-Based Destinations] solo permiten que se utilicen datos de origen para la segmentación. [!DNL Data Export Controls] también bloquee segmentos con gráficos [!DNL Profile Merge Rules] de dispositivos. [!DNL People-Based Destinations] se crean con las etiquetas de exportación de datos correspondientes marcadas y no se puede sobrescribir la configuración de exportación.

## Preguntas específicas del socio {#partner-specific-questions}

### [!DNL Facebook]

**¿Qué debo hacer antes de poder enviar segmentos de audiencia a[!DNL Facebook]?**

Antes de poder usar [!DNL People-Based Destinations] para enviar segmentos de audiencia a [!DNL Facebook], debe realizar las siguientes tareas de configuración:

1. Agregue la cuenta comercial de Adobe Experience Cloud como socio de publicidad en su [!DNL Facebook Ad Account]. Utilice `business ID=206617933627973`. Consulte Agregar socios a su administrador comercial para obtener más información.

   >[!IMPORTANT]
   >
   > Al configurar los permisos para Adobe Experience Cloud, debe habilitar el permiso Administrar campañas. Esto es necesario para la [!DNL People-Based Destinations] integración.

1. Lea y firme el [!DNL Facebook Custom Audiences Terms of Service]. Para hacerlo, vaya a `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, donde `accountID` está su [!DNL Facebook Ad Account ID].

**¿[!DNL People-Based Destinations]Admite la segmentación de audiencia en otras[!DNL Facebook]aplicaciones, como[!DNL Instagram]?**

Puede utilizar [!DNL People-Based Destinations] la familia [!DNL Facebook]de aplicaciones compatibles con [!DNL Custom Audiences]las aplicaciones, incluidas [!DNL Facebook], [!DNL Instagram]y [!DNL Audience Network] [!DNL Messenger]. La selección de la aplicación con la que desea ejecutar la campaña se indica en el nivel de colocación de [!DNL Facebook Ads Manager].

**¿Cuál es la diferencia entre[!DNL People-Based Destinations]y[!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] aprovecha la [!DNL Custom Audiences (CA)] integración con [!DNL Facebook]. La diferencia entre [!DNL WCA] e [!DNL CA] integraciones es la clave que utilizan los clientes al enviar audiencias a [!DNL Facebook]. [!DNL WCA] utiliza el [!DNL Facebook] píxel (que sería un ID de usuario del sitio web) mientras [!DNL People-Based Destinations] utiliza direcciones de correo electrónico con hash para integrarlas con [!DNL CA].

Puede utilizar la integración de Audience Manager [!DNL Facebook][!DNL WCA] mediante la [!DNL URL Destinations] función sin costo adicional.

Estas dos integraciones son complementarias; puede usar ambos para garantizar una mejor cobertura de la audiencia. Por ejemplo, [!DNL WCA] se puede utilizar para la prospección cuando una empresa busca dirigirse a visitantes del sitio web que no hayan registrado una cuenta, mientras que [!DNL People-Based Destinations] puede ayudarle a dirigirse a clientes existentes que hayan proporcionado su dirección de correo electrónico pero que tal vez no hayan visitado el sitio web.
