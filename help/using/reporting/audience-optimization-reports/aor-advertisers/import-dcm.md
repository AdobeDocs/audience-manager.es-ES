---
description: Configure un grupo de Google para que los archivos de datos de Google Campaign Manager lleguen al Audience Manager. El contenido de esta sección resume el proceso de integración y le proporciona vínculos a los recursos de Google Campaign Manager para ayudarle a empezar.
seo-description: Configure un grupo de Google para que los archivos de datos de Google Campaign Manager lleguen al Audience Manager. El contenido de esta sección resume el proceso de integración y le proporciona vínculos a los recursos de Google Campaign Manager para ayudarle a empezar.
seo-title: Importar archivos de datos de Google Campaign Manager en el Audience Manager
solution: Audience Manager
title: Importar archivos de datos de Google Campaign Manager en el Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Informes de optimización de Audiencia
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 3%

---

# Importar archivos de datos de Google Campaign Manager en el Audience Manager {#import-dcm-data-files-into-audience-manager}

Configure un grupo [!DNL Google] para incorporar los archivos de datos [!DNL Google Campaign Manager] al Audience Manager. El contenido de esta sección resume el proceso de integración y le proporciona vínculos a [!DNL Google Campaign Manager] recursos para ayudarle a empezar.

## Resumen de la integración

[!DNL Google Campaign Manager] es el reemplazo de [!DNL Google] para [!DNL DoubleClick for Advertisers] (DFA). De forma similar a DFA, los clientes [!DNL Google Campaign Manager] pueden importar, ver y trabajar con sus datos en [!DNL Audience Manager]. Pero [!DNL Audience Manager] no puede acceder e importar directamente sus archivos [!UICONTROL Data Transfer] y [!UICONTROL Match Table]. El cliente es el encargado de importar estos archivos.

Sin embargo, el procedimiento de configuración está bien documentado en la [Ayuda del administrador de campaña de DoubleClick](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). Además, puede revisar los pasos que se enumeran a continuación para empezar.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] los archivos de datos contienen datos para todos sus anunciantes o clientes. Si necesita omitir clientes específicos, debe editar los archivos antes de ponerlos a disposición de [!DNL Audience Manager].

## Frecuencia y disponibilidad de la transferencia de datos

[!DNL Audience Manager] comprueba y transfiere datos una vez al día. Los datos suelen estar disponibles en [!DNL Audience Manager] después de 24 horas.

## Pasos

1. [Crear un grupo](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Los grupos controlan el acceso a sus datos [!DNL Google Campaign Manager] . Finalmente, invitará y agregará [!DNL Audience Manager] a este grupo.

1. [Compruebe el estado](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456) de almacenamiento de Google Cloud.

   Google Cloud Storage contiene el bloque de datos que contiene sus [!UICONTROL Data Transfer] y [!UICONTROL Match Tables]. Tendrá que configurar un espacio o asegurarse de que su nuevo grupo tenga acceso a un espacio de almacenamiento de datos existente.

1. [Obtener una dirección URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456) del archivo de datos.

   Trabaje con su [!DNL Google Campaign Manager] administrador de cuentas o consultor de soluciones de plataforma. Le proporcionarán una URL a sus archivos de datos. [!DNL Google] puede cambiar el formato de los nombres de archivos y contenedores en futuras versiones. Una vez más, trabaje con su [!DNL Google Campaign Manager] administrador de cuentas para asegurarse de que está utilizando los formatos adecuados.

1. [Establezca permisos](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission) de compartimento.

   El [!DNL Cloud Storage Manager] permite controlar el uso compartido de datos y el acceso a bloques. Asigne al grupo acceso de lectura al contenedor que contiene sus archivos [!UICONTROL Data Transfer] y [!UICONTROL Match Table].

1. [Configuración del uso compartido de datos](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Los [!DNL Google Campaign Manager] ID de usuario compartidos se cifran para proteger la privacidad. El cifrado agrega 2 columnas al final del archivo de transferencia de datos, `PartnerId1` y `PartnerId2`. Estas columnas contienen ID de usuario codificados específicos de cada empresa que recibe estos archivos.

   Como tercero autorizado, [!DNL Audience Manager] puede recibir [!DNL Google Campaign Manager] datos, pero no puede descodificar los ID. Sin embargo, en el lado [!DNL Audience Manager], sabemos cómo coinciden los ID codificados con nuestros ID. Esto significa que podemos hacer coincidir y sincronizar a los usuarios con confianza y precisión.

   >[!NOTE]
   >No puede importar archivos [!DNL Google Campaign Manager] en [!DNL Audience Manager] si ya está compartiendo datos con otros dos socios de terceros.

1. Invite a [!DNL Audience Manager] a unirse al grupo.

   Después de crear un grupo y darle acceso a un bloque de datos, invite a [!DNL Audience Manager] a unirse al grupo. Envíe una invitación por correo electrónico a DFA-AAM@adobe.com. Asegúrese de incluir la URL del archivo de datos del paso 3. Nuestros equipos internos trabajarán con usted para verificar el acceso después de aceptar la invitación. 1. Configure dos fuentes de datos para [!DNL Google Campaign Manager] datos en la interfaz de usuario [!DNL Audience Manager].

   Asigne a las fuentes de datos los nombres `Advertiser Analytics: DCM Platform` y `Advertiser Analytics: AAM+DCM Platform`. En el flujo de trabajo [Crear fuentes de datos](../../../features/manage-datasources.md#create-data-source), establezca el tipo de ID en `Cookie`. Comparta los ID de las dos nuevas fuentes de datos con nuestros equipos internos.

1. Puede crear fácilmente rasgos a partir de los archivos [!DNL Google Campaign Manager] que importe en [!DNL Audience Manager]. Consulte [Archivos de registro procesables](../../../integration/media-data-integration/actionable-log-files.md) y pídale a su asesor de [!DNL Audience Manager] o al Servicio de atención al cliente que habilite la función.
