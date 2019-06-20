---
description: Configure un grupo de Google para que los archivos de datos de doubleclick Campaign Manager (DCM) se carguen en Audience Manager. El contenido de esta sección resume el proceso de integración y le proporciona vínculos a recursos de DCM para ayudarle a empezar.
seo-description: Configure un grupo de Google para que los archivos de datos de doubleclick Campaign Manager (DCM) se carguen en Audience Manager. El contenido de esta sección resume el proceso de integración y le proporciona vínculos a recursos de DCM para ayudarle a empezar.
seo-title: Importación de archivos de datos de DCM en Audience Manager
solution: Audience Manager
title: Importación de archivos de datos de DCM en Audience Manager
uuid: 3578 cfe 1-6 d 30-4 a 73-ab 75-8 d 272 bebcd 60
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Import DCM Data Files Into Audience Manager {#import-dcm-data-files-into-audience-manager}

Configure un grupo de Google para que los archivos de datos de doubleclick Campaign Manager (DCM) se carguen en Audience Manager. El contenido de esta sección resume el proceso de integración y le proporciona vínculos a recursos de DCM para ayudarle a empezar.

## Resumen de integración

DCM es el reemplazo de [!DNL Google] para [!DNL DoubleClick for Advertisers] (DFA). Igual que para DFA, los clientes de DCM pueden importar, ver y trabajar con sus datos en [!DNL Audience Manager]. But [!DNL Audience Manager] cannot directly access and import your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files. El cliente es el encargado de importar estos archivos.

However, the set up procedure is well documented in the [DoubleClick Campaign Manager Help](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456). Asimismo, puede consultar los pasos que se indican a continuación para comenzar.

>[!CAUTION]
>
>Los archivos de datos de DCM contienen datos para todos los anunciantes o clientes. If you need to omit specific clients, then you must edit the files before making them available to [!DNL Audience Manager].

## Frecuencia y disponibilidad de transferencia de datos

[!DNL Audience Manager] comprueba y transfiere los datos una vez cada día. Data is usually available in [!DNL Audience Manager] after 24-hours.

## Pasos

1. [Crear un grupo](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   Los grupos controlan el acceso a los datos de DCM. Eventually, you&#39;ll invite and add [!DNL Audience Manager] to this group.

1. [Compruebe su estado de Almacenamiento en la nube de Google](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456).

   Google Cloud Storage contains the data bucket that holds your [!UICONTROL Data Transfer] and [!UICONTROL Match Tables]. Tendrá que configurar un bloque o asegurarse de que el nuevo grupo tenga acceso a un bloque de almacenamiento de datos existente.

1. [Obtenga una URL de archivo de datos](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456).

   Trabaje con el administrador de cuentas de DCM o con el consultor de soluciones de plataforma. Le proporcionarán una URL a sus archivos de datos. [!DNL Google] puede cambiar el formato de los nombres de archivos y bloques en próximas versiones. De nuevo, trabaje con el administrador de cuentas de DCM para asegurarse de que está utilizando los formatos adecuados.

1. [Defina permisos de bloque](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   The [!DNL Cloud Storage Manager] lets you control data sharing and bucket access. Give your group read access to the bucket that contains your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files.

1. [Configure el uso compartido de datos](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Los ID de usuarios de DCM compartidos están cifrados para proteger la privacidad. Encryption adds 2 columns to the end of your Data Transfer file, `PartnerId1` and `PartnerId2`. Estas columnas contienen ID de usuario codificados específicos de cada empresa que recibe estos archivos.

   As an authorized third-party, [!DNL Audience Manager] can receive DCM data, but cannot decode the IDs. However, on the [!DNL Audience Manager] side, we know how the encoded IDs match our IDs. Esto significa que podemos hacer coincidir y sincronizar usuarios con confianza y precisión.

   >[!NOTE]
   >You cannot import DCM files into [!DNL Audience Manager] if you&#39;re already sharing data with 2 other third-party partners.

1. Invite [!DNL Audience Manager] to join the group.

   After you create a group and give it access to a data bucket, invite [!DNL Audience Manager] to join the group. Envíe un correo electrónico de invitación a DFA-AAM@adobe.com. Asegúrese de incluir la URL del archivo de datos desde el paso 3. Nuestros equipos internos trabajarán con usted para verificar el acceso después de aceptar la invitación. 1. Set up two data sources for DCM data in the [!DNL Audience Manager] User Interface.

   Name the data sources `Advertiser Analytics: DCM Platform` and `Advertiser Analytics: AAM+DCM Platform`. In the [Create Data Sources](../../../features/manage-datasources.md#create-data-source) workflow, set the ID type to `Cookie`. Comparta los ID de las dos nuevas fuentes de datos con nuestros equipos internos.

1. You can easily create traits from the DCM files you import into [!DNL Audience Manager]. See [Actionable Log Files](../../../integration/media-data-integration/actionable-log-files.md) and ask your [!DNL Audience Manager] consultant or Customer Care to enable the feature for you.
