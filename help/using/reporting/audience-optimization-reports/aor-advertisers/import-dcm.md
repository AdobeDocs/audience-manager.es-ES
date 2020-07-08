---
description: Configure un grupo de Google para que los archivos de datos de Google Campaña Manager se pongan en Audience Manager. El contenido de esta sección resume el proceso de integración y le proporciona vínculos a los recursos del Administrador de Campañas de Google para ayudarle a comenzar.
seo-description: Configure un grupo de Google para que los archivos de datos de Google Campaña Manager se pongan en Audience Manager. El contenido de esta sección resume el proceso de integración y le proporciona vínculos a los recursos del Administrador de Campañas de Google para ayudarle a comenzar.
seo-title: Importar archivos de datos de Google Campaña Manager en Audience Manager
solution: Audience Manager
title: Importar archivos de datos de Google Campaña Manager en Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 97129b435ab8e13def14bc85dcaab8254b2c4bda
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 3%

---


# Importar archivos de datos de Google Campaña Manager en Audience Manager {#import-dcm-data-files-into-audience-manager}

Configure un [!DNL Google] grupo para que los archivos [!DNL Google Campaign Manager] de datos se conviertan en Audience Manager. El contenido de esta sección resume el proceso de integración y le proporciona vínculos a [!DNL Google Campaign Manager] los recursos para ayudarle a comenzar.

## Resumen de integración

[!DNL Google Campaign Manager] es el reemplazo de [!DNL Google] para [!DNL DoubleClick for Advertisers] (DFA). Similar to DFA, [!DNL Google Campaign Manager] customers can import, view, and work with their data in [!DNL Audience Manager]. Pero [!DNL Audience Manager] no puede acceder e importar directamente sus [!UICONTROL Data Transfer] archivos y [!UICONTROL Match Table] archivos. El cliente es el encargado de importar estos archivos.

Sin embargo, el procedimiento de configuración está bien documentado en la Ayuda [del Administrador de Campañas de](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456)DoubleClick. Además, puede revisar los pasos que se indican a continuación para empezar.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] los archivos de datos contienen datos para todos los anunciantes o clientes. Si necesita omitir clientes específicos, debe editar los archivos antes de ponerlos a disposición de [!DNL Audience Manager].

## Frecuencia y disponibilidad de la transferencia de datos

[!DNL Audience Manager] comprueba y transfiere datos una vez al día. Los datos suelen estar disponibles [!DNL Audience Manager] al cabo de 24 horas.

## Pasos

1. [Crear un grupo](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Los grupos controlan el acceso a sus [!DNL Google Campaign Manager] datos. Al final, invitará y agregará [!DNL Audience Manager] a este grupo.

1. [Compruebe el estado](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456)del Almacenamiento de Google Cloud.

   El Almacenamiento de Google Cloud contiene el bloque de datos que contiene [!UICONTROL Data Transfer] y [!UICONTROL Match Tables]. Deberá configurar un bloque o asegurarse de que el nuevo grupo tenga acceso a un contenedor de almacenamiento de datos existente.

1. [Obtenga una dirección URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456)de archivo de datos.

   Trabaje con el administrador [!DNL Google Campaign Manager] de cuentas o con el consultor de soluciones de Platform. Le proporcionarán una dirección URL a sus archivos de datos. [!DNL Google] podría cambiar el formato de los nombres de archivos y bucket en futuras versiones. De nuevo, trabaje con el administrador [!DNL Google Campaign Manager] de cuentas para asegurarse de que está utilizando los formatos adecuados.

1. [Establezca los permisos](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)del bloque.

   El [!DNL Cloud Storage Manager] permite controlar el uso compartido de datos y el acceso al bloque. Proporcione al grupo acceso de lectura al bloque que contiene los archivos [!UICONTROL Data Transfer] y [!UICONTROL Match Table] .

1. [Configure el uso compartido](https://support.google.com/dcm/partner/answer/6206106?hl=en)de datos.

   Los ID [!DNL Google Campaign Manager] de usuario compartidos están cifrados para proteger la privacidad. El cifrado agrega 2 columnas al final del archivo de transferencia de datos `PartnerId1` y `PartnerId2`. Estas columnas contienen ID de usuario codificados específicos de cada compañía que recibe estos archivos.

   Como tercero autorizado, [!DNL Audience Manager] puede recibir [!DNL Google Campaign Manager] datos, pero no puede descodificar los ID. Sin embargo, por el [!DNL Audience Manager] lado, sabemos cómo coinciden los ID codificados con nuestros ID. Esto significa que podemos hacer coincidir y sincronizar a los usuarios con confianza y precisión.

   >[!NOTE]
   >No puede importar [!DNL Google Campaign Manager] archivos en [!DNL Audience Manager] si ya está compartiendo datos con otros dos socios de terceros.

1. Invite [!DNL Audience Manager] a unirse al grupo.

   Después de crear un grupo y darle acceso a un bloque de datos, invite [!DNL Audience Manager] a unirse al grupo. Envíe un correo electrónico de invitación a DFA-AAM@adobe.com. Asegúrese de incluir la dirección URL del archivo de datos del paso 3. Nuestros equipos internos trabajarán con usted para verificar el acceso después de aceptar la invitación. 1. Configure dos fuentes de datos para [!DNL Google Campaign Manager] los datos en la interfaz [!DNL Audience Manager] de usuario.

   Asigne un nombre a las fuentes de datos `Advertiser Analytics: DCM Platform` y `Advertiser Analytics: AAM+DCM Platform`. En el flujo de trabajo [Crear fuentes](../../../features/manage-datasources.md#create-data-source) de datos, establezca el tipo de ID en `Cookie`. Comparta los ID de las dos nuevas fuentes de datos con nuestros equipos internos.

1. Puede crear características fácilmente a partir de los [!DNL Google Campaign Manager] archivos que importe en [!DNL Audience Manager]. Consulte Archivos [de registro](../../../integration/media-data-integration/actionable-log-files.md) procesables y pida a su [!DNL Audience Manager] asesor o al Servicio de atención al cliente que habilite la función.
