---
description: 'Respuestas a preguntas frecuentes sobre People-Based Destinations.  '
seo-description: 'Respuestas a preguntas frecuentes sobre People-Based Destinations.  '
seo-title: Preguntas frecuentes sobre People-Based Destinations
solution: Audience Manager
title: Preguntas frecuentes sobre People-Based Destinations
feature: Destinos basados en personas
exl-id: 56506bf0-45f1-49df-81ac-10f57a2487eb
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 94%

---

# Preguntas frecuentes sobre People-Based Destinations {#people-based-destinations-faq}

Respuestas a preguntas frecuentes sobre [!DNL People-Based Destinations]

## Disponibilidad {#availability}

**No puedo ver [!DNL People-Based Destinations] en mi cuenta de Audience Manager. ¿Qué necesito saber sobre disponibilidad?**

[!DNL People-Based Destinations] es una función Premium de Audience Manager que está disponible en el momento de la compra. Póngase en contacto con su representante de ventas de Adobe para obtener más información sobre precios y disponibilidad.

## Integración de datos {#data-onboarding}

**¿Cómo puedo incluir direcciones de correo electrónico de clientes en Audience Manager para poder usarlas en [!DNL People-Based Destinations]?**

Existen dos maneras de incluir los datos sin conexión a Audience Manager para [!DNL People-Based Destinations].

* **Utilice la sincronización de ID basada en archivos**. Consulte [Requisitos de nombre y contenido para archivos de sincronización de ID](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) para obtener más información sobre la apariencia que deben tener los archivos de sincronización de ID. Con este método puede dirigir todas las direcciones de correo electrónico con hash desde su [!DNL CRM] base de datos.
* **Utilice los ID declarados** para declarar las direcciones de correo electrónico con hash al pasar los ID de cliente autenticados. Con este método, Audience Manager solo activa las direcciones de correo electrónico con hash de los usuarios que se han autenticado en línea. Las direcciones de correo electrónico activadas a través de Facebook solo son las que aparecen en las llamadas de evento de ID declaradas. Otras direcciones de correo electrónico asociadas con el ID de cliente no se activan en tiempo real.

**¿Puedo recopilar direcciones de correo electrónico con hash a través de un formulario web o una aplicación móvil o tienen que pasar por un archivo por lotes?**

Puede recopilar direcciones de correo electrónico con hash mediante la autenticación web utilizando [!DNL ECID] con [ID declarados](../features/declared-ids.md). El archivo por lotes también le permite recopilar direcciones de correo electrónico con hash que no se pueden enviar mediante autenticación (por ejemplo, usuarios inactivos en su ([!DNL CRM]) y activarlas en People-Based Destinations).

**¿En qué se diferencia la incorporación de direcciones de correo electrónico con hash a través de formularios web de la carga de direcciones de correo electrónico con hash a través de archivos por lotes?**

La incorporación de datos sin conexión está diseñada para admitir casos de uso sin autenticación, y una nueva regla de combinación de perfiles ([!UICONTROL All Cross-Device Profiles]) que se ejecuta en todos los [!DNL CRM] perfiles sin conexión independientemente de si la autenticación está disponible como parte de [!DNL People-Based Destinations]. Este método está diseñado para complementar la incorporación de audiencias autenticadas de fuentes en línea.

**¿Cuál es la frecuencia máxima con la que puedo enviar/actualizar direcciones de correo electrónico con hash?**

* Al utilizar ID declarados, Audience Manager envía las direcciones de correo electrónico con hash al destino en tiempo real.
* Cuando se asimilan datos mediante archivos de sincronización de ID, Audience Manager los procesa diariamente.

**¿Cómo sé si el hash de la dirección de correo electrónico se ha realizado correctamente?**

Audience Manager no está asimilando la dirección de correo electrónico sin procesar y no podemos verificar que el hash se haya realizado correctamente. Consulte [Requisitos previos y consideraciones](../features/destinations/people-based-destinations-prerequisites.md) para obtener detalles sobre cómo debe hash los datos incorporados.

## Reglas de combinación de perfiles {#profile-merge-rules}

**¿Existe una nueva norma de combinación de perfiles con la que puedo usar [!DNL People-Based Destinations]?**

Sí. Los clientes que compran [!DNL People-Based Destinations] también disponen de acceso a una nueva norma de combinación de perfiles para la segmentación sin conexión. Esta norma se denomina [!DNL All Cross-Device Profiles] y se utiliza para la segmentación únicamente sin conexión. Al registrarse en [!DNL People-Based Destinations], esta es la cuarta norma de combinación de perfiles que puede crear, además de las tres normas basadas en autenticación existentes.

**¿Tengo que duplicar los segmentos de audiencia existentes para activarlos en [!DNL People-Based Destinations]?**

Según su caso de uso. Si decide activar segmentos de origen existentes en canales basados en personas, no necesita crear nuevos segmentos. Puede asignar los segmentos a un destino basado en personas.

Si decide activar nuevas audiencias sin conexión en canales basados en personas, debe crear nuevos segmentos de origen mediante la norma de combinación de [!DNL All Cross-Device Profiles].
>[!NOTE]
>
> Solo puede asignar segmentos con datos de origen a [!DNL People-Based Destinations]. Nuestras plataformas de destino no aceptan segmentos con datos de segundas y terceras partes.

## Combinar tasas {#match-rates}

**¿[!DNL People-Based Destinations] puede ver las tasas de coincidencia o las audiencias a las que se puede dirigir?**

No. Al enviar segmentos de audiencia a [!DNL People-Based Destinations], la combinación de audiencias se produce en la parte del socio. Adobe no tiene acceso a esas métricas. Audience Manager muestra la audiencia máxima que se puede compartir para cada destino y el recuento en tiempo real de personas que pertenecen a un segmento. Esta información puede ayudarle con la planificación y previsión de campañas.

**¿Cómo se comparan las tasas de coincidencia usando [!DNL People-Based Destinations] con otros métodos de envío de audiencias a las plataformas de destino?**

Siempre que la dirección de correo electrónico esté correctamente almacenada y anidada en hash, no debería haber ninguna diferencia en la tasa de coincidencia entre [!DNL People-Based Destinations] y otros métodos. La única razón por la que una tasa de coincidencia sería inferior al 100% es si las direcciones de correo electrónico introducidas en Audience Manager no pueden coincidir con una dirección de correo electrónico en la base de usuarios de la plataforma de destino.

**Recopilo direcciones de correo electrónico de trabajo de mis clientes diferentes a las direcciones de correo electrónico personales utilizadas en las redes sociales. ¿Cómo se relacionan las identidades en varias direcciones de correo electrónico?**

Audience Manager puede recopilar y enviar hasta 10 correos electrónicos por usuario a las plataformas de destino, pero las direcciones de correo electrónico deben recopilarse con archivos de sincronización. Cuando Audience Manager envía las direcciones de correo electrónico a las plataformas de destino, es función de las plataformas hacer coincidir las direcciones de correo electrónico con su propia base de usuarios. Algunas plataformas pueden tener otros gráficos de direcciones de correo electrónico para combinar con las direcciones enviadas desde Audience Manager a los perfiles de usuario.

**¿Puedo usar  [!DNL People-Based Destinations] en  [!DNL Audience Lab]?**

No. Actualmente, todos los destinos [!DNL People-Based Destinations] están excluidos de [!DNL Audience Lab]. Dado que [!DNL People-Based Destinations] y las plataformas del lado de la demanda utilizan ID diferentes, no se puede probar ni medir el rendimiento con audiencias divididas uniformemente entre ellas.

## Controles de exportación de datos {#data-export-controls}

**¿Cómo trabajan los [!DNL Data Export Controls] con [!DNL People-Based Destinations]?**

[!DNL Data Export Controls] bloqueará cualquier segmento que contenga datos de segundo nivel y de terceros que los usuarios intenten enviar a [!DNL People-Based Destinations]. [!DNL People-Based Destinations] solo permiten que se utilicen datos de origen para la segmentación. [!DNL Data Export Controls] también bloquea segmentos usando [!DNL Profile Merge Rules] con gráficos de dispositivos. Los [!DNL People-Based Destinations] se crean con las etiquetas de exportación de datos correspondientes marcadas y no se puede sobrescribir la configuración de exportación.

## Preguntas de socios {#partner-specific-questions}

### [!DNL Facebook]

**¿Qué debo hacer antes de poder enviar segmentos de audiencia a [!DNL Facebook]?**

Antes de poder utilizar [!DNL People-Based Destinations] para enviar segmentos de audiencia a [!DNL Facebook], debe realizar las siguientes tareas de configuración:

1. Añada la cuenta comercial de Adobe Experience Cloud como socio de publicidad en su [!DNL Facebook Ad Account]. Utilice `business ID=206617933627973`. Consulte Añadir socios a su administrador comercial para obtener más información.

   >[!IMPORTANT]
   >
   > Cuando configure los permisos para Adobe Experience Cloud, deberá habilitar el permiso Administrar campañas. Es necesario para la integración de [!DNL People-Based Destinations].

1. Lea y firme el [!DNL Facebook Custom Audiences Terms of Service]. Para ello, vaya a `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, donde `accountID` es su [!DNL Facebook Ad Account ID].

**¿[!DNL People-Based Destinations] admite la segmentación por audiencias en otras aplicaciones de [!DNL Facebook], como [!DNL Instagram]?**

Puede usar [!DNL People-Based Destinations] en toda la familia de aplicaciones de [!DNL Facebook]compatibles con [!DNL Custom Audiences], como [!DNL Facebook], [!DNL Instagram], [!DNL Audience Network] y [!DNL Messenger]. La selección de la aplicación con la que quiere ejecutar la campaña se indica en el nivel de colocación de [!DNL Facebook Ads Manager].

**¿Cuál es la diferencia entre [!DNL People-Based Destinations] y [!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] utiliza la integración de [!DNL Custom Audiences (CA)] con [!DNL Facebook]. La diferencia entre las integraciones de [!DNL WCA] y [!DNL CA] es la clave que utilizan los clientes al enviar audiencias a [!DNL Facebook]. [!DNL WCA] utiliza el píxel de [!DNL Facebook] (que sería un ID de usuario del sitio web) y [!DNL People-Based Destinations] utiliza direcciones de correo electrónico con hash para integrarse con [!DNL CA].

Puede utilizar la integración [!DNL WCA] de Audience Manager para [!DNL Facebook] con la función [!DNL URL Destinations] sin coste adicional.

Estas dos integraciones son complementarias; pueden utilizarse las dos para garantizar una mejor cobertura de audiencia. Por ejemplo, [!DNL WCA] se puede utilizar para la prospección cuando una compañía busca visitantes de sitios web de destinatario que no han registrado una cuenta, mientras que [!DNL People-Based Destinations] puede ayudarle a dirigir a los clientes existentes que han proporcionado su dirección de correo electrónico pero que quizá no hayan visitado el sitio web.

**¿La  [!DNL People-Based Destinations] integración con  [!DNL Facebook] permite descalificar a los usuarios de una audiencia cuando ya no cumplen los requisitos para ella?**

Sí, la integración admite la eliminación de usuarios de [!DNL Facebook] audiencias cuando ya no cumplen los requisitos para ellas.
