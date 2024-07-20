---
description: Configure un grupo de Google para incorporar los archivos de datos de Google Campaign Manager al Audience Manager. El contenido de esta sección resume el proceso de integración y le proporciona vínculos a recursos de Google Campaign Manager para ayudarle a empezar.
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: Importación De Archivos De Datos Del Administrador De Google Campaign En Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 2%

---

# Importación De Archivos De Datos Del Administrador De Google Campaign En Audience Manager {#import-dcm-data-files-into-audience-manager}

Configure un grupo [!DNL Google] para llevar los archivos de datos [!DNL Google Campaign Manager] al Audience Manager. El contenido de esta sección resume el proceso de integración y le proporciona vínculos a [!DNL Google Campaign Manager] recursos para ayudarle a empezar.

## Resumen de integración

[!DNL Google Campaign Manager] es el reemplazo de [!DNL Google] para [!DNL DoubleClick for Advertisers] (DFA). Similar a DFA, [!DNL Google Campaign Manager] clientes pueden importar, ver y trabajar con sus datos en [!DNL Audience Manager]. Pero [!DNL Audience Manager] no puede acceder e importar directamente sus archivos de [!UICONTROL Data Transfer] y [!UICONTROL Match Table]. El cliente es el encargado de importar estos archivos.

Sin embargo, el procedimiento de configuración está bien documentado en la [Ayuda de DoubleClick Campaign Manager](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). Además, puede revisar los pasos que se enumeran a continuación para comenzar.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] archivos de datos contienen datos de todos sus anunciantes o clientes. Si necesita omitir clientes específicos, debe editar los archivos antes de ponerlos a disposición de [!DNL Audience Manager].

## Frecuencia y disponibilidad de la transferencia de datos

[!DNL Audience Manager] comprueba y transfiere datos una vez al día. Los datos suelen estar disponibles en [!DNL Audience Manager] pasadas las 24 horas.

## Pasos

1. [Crear un grupo](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Los grupos controlan el acceso a los datos de [!DNL Google Campaign Manager]. Al final, invitarás a [!DNL Audience Manager] y lo agregarás a este grupo.

1. [Compruebe su estado de Google Cloud Storage](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Almacenamiento en la nube de Google contiene el contenedor de datos que contiene sus [!UICONTROL Data Transfer] y [!UICONTROL Match Tables]. Tendrá que configurar un bloque o asegurarse de que el nuevo grupo tenga acceso a un bloque de almacenamiento de datos existente.

1. [Obtener una dirección URL de archivo de datos](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   Trabaje con el administrador de cuentas de [!DNL Google Campaign Manager] o con el consultor de soluciones de Platform. Proporcionarán una dirección URL a los archivos de datos. [!DNL Google] podría cambiar el formato de los nombres de archivo y contenedor en futuras versiones. De nuevo, trabaje con el administrador de cuentas de [!DNL Google Campaign Manager] para asegurarse de que está empleando los formatos correctos.

1. [Establecer permisos de compartimento](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   [!DNL Cloud Storage Manager] le permite controlar el uso compartido de datos y el acceso al bloque. Conceda a su grupo acceso de lectura al contenedor que contiene sus archivos [!UICONTROL Data Transfer] y [!UICONTROL Match Table].

1. [Configurar el uso compartido de datos](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Los identificadores de usuario [!DNL Google Campaign Manager] compartidos están cifrados para proteger la privacidad. El cifrado agrega 2 columnas al final del archivo de transferencia de datos, `PartnerId1` y `PartnerId2`. Estas columnas contienen ID de usuario codificados específicos de cada empresa que recibe estos archivos.

   Como tercero autorizado, [!DNL Audience Manager] puede recibir datos de [!DNL Google Campaign Manager], pero no puede descodificar los identificadores. Sin embargo, en el lado [!DNL Audience Manager], sabemos cómo coinciden los ID codificados con nuestros ID. Esto significa que podemos hacer coincidir y sincronizar usuarios con confianza y precisión.

   >[!NOTE]
   >No puede importar [!DNL Google Campaign Manager] archivos en [!DNL Audience Manager] si ya está compartiendo datos con otros 2 socios de terceros.

1. Invitar a [!DNL Audience Manager] a unirse al grupo.

   Después de crear un grupo y darle acceso a un bloque de datos, invite a [!DNL Audience Manager] a unirse al grupo. Envíe un correo electrónico de invitación a dfaaam@adobe.com. Asegúrese de incluir la dirección URL del archivo de datos del paso 3. Nuestros equipos internos trabajarán con usted para verificar el acceso después de aceptar la invitación. 1. Configure dos orígenes de datos para los datos de [!DNL Google Campaign Manager] en la interfaz de usuario de [!DNL Audience Manager].

   Asigne un nombre a los orígenes de datos `Advertiser Analytics: DCM Platform` y `Advertiser Analytics: AAM+DCM Platform`. En el flujo de trabajo [Crear fuentes de datos](../../../features/manage-datasources.md#create-data-source), establezca el tipo de identificador en `Cookie`. Comparta los ID de las dos nuevas fuentes de datos con nuestros equipos internos.

1. Puede crear fácilmente rasgos a partir de los [!DNL Google Campaign Manager] archivos que importa a [!DNL Audience Manager]. Consulte [Archivos de registro procesables](../../../integration/media-data-integration/actionable-log-files.md) y pídale al asesor de [!DNL Audience Manager] o al Servicio de atención al cliente que habiliten la característica.
