---
description: Configure un grupo de Google para que los archivos de datos de Google Campaign Manager lleguen a Audience Manager. El contenido de esta sección resume el proceso de integración y le proporciona vínculos a los recursos de Google Campaign Manager para ayudarle a empezar.
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: Importación de archivos de datos de Google Campaign Manager en Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# Importación de archivos de datos de Google Campaign Manager en Audience Manager {#import-dcm-data-files-into-audience-manager}

Configure un [!DNL Google] para traer su [!DNL Google Campaign Manager] archivos de datos en Audience Manager. El contenido de esta sección resume el proceso de integración y le proporciona vínculos a [!DNL Google Campaign Manager] recursos para ayudarle a empezar.

## Resumen de la integración

[!DNL Google Campaign Manager] es el reemplazo de [!DNL Google] para [!DNL DoubleClick for Advertisers] (DFA). Similar a DFA, [!DNL Google Campaign Manager] los clientes pueden importar, ver y trabajar con sus datos en [!DNL Audience Manager]. Pero [!DNL Audience Manager] no puede acceder e importar directamente su [!UICONTROL Data Transfer] y [!UICONTROL Match Table] archivos. El cliente es el encargado de importar estos archivos.

Sin embargo, el procedimiento de configuración está bien documentado en la [Ayuda del administrador de campañas DoubleClick](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). Además, puede revisar los pasos que se enumeran a continuación para empezar.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] los archivos de datos contienen datos para todos sus anunciantes o clientes. Si necesita omitir clientes específicos, debe editar los archivos antes de ponerlos a disposición de [!DNL Audience Manager].

## Frecuencia y disponibilidad de la transferencia de datos

[!DNL Audience Manager] comprueba y transfiere datos una vez al día. Los datos suelen estar disponibles en [!DNL Audience Manager] después de 24 horas.

## Pasos

1. [Crear un grupo](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Los grupos controlan el acceso a su [!DNL Google Campaign Manager] datos. Al final, invitará y agregará [!DNL Audience Manager] a este grupo.

1. [Verifique su estado de almacenamiento en la nube de Google](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Google Cloud Storage contiene el bloque de datos que contiene su [!UICONTROL Data Transfer] y [!UICONTROL Match Tables]. Tendrá que configurar un espacio o asegurarse de que su nuevo grupo tenga acceso a un espacio de almacenamiento de datos existente.

1. [Obtener una dirección URL de archivo de datos](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   Trabaje con su [!DNL Google Campaign Manager] Administrador de cuentas o Consultor de soluciones de plataforma. Le proporcionarán una URL a sus archivos de datos. [!DNL Google] puede cambiar el formato de los nombres de archivos y contenedores en futuras versiones. De nuevo, trabaje con su [!DNL Google Campaign Manager] Administrador de cuentas para asegurarse de que está utilizando los formatos adecuados.

1. [Definir permisos de bucket](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   La variable [!DNL Cloud Storage Manager] permite controlar el uso compartido de datos y el acceso a bloques. Proporcione a su grupo acceso de lectura al contenedor que contiene su [!UICONTROL Data Transfer] y [!UICONTROL Match Table] archivos.

1. [Configuración del uso compartido de datos](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Compartido [!DNL Google Campaign Manager] los ID de usuario se cifran para proteger la privacidad. El cifrado agrega 2 columnas al final del archivo de transferencia de datos. `PartnerId1` y `PartnerId2`. Estas columnas contienen ID de usuario codificados específicos de cada empresa que recibe estos archivos.

   Como tercero autorizado, [!DNL Audience Manager] puede recibir [!DNL Google Campaign Manager] , pero no pueden decodificar los ID. Sin embargo, en la [!DNL Audience Manager] por otro lado, sabemos cómo coinciden los ID codificados con nuestros ID. Esto significa que podemos hacer coincidir y sincronizar a los usuarios con confianza y precisión.

   >[!NOTE]
   >No se puede importar [!DNL Google Campaign Manager] archivos en [!DNL Audience Manager] si ya está compartiendo datos con otros dos socios de terceros.

1. Invitar [!DNL Audience Manager] para unirse al grupo.

   Después de crear un grupo y darle acceso a un bloque de datos, invite a [!DNL Audience Manager] para unirse al grupo. Envíe una invitación por correo electrónico a dfaaam@adobe.com. Asegúrese de incluir la URL del archivo de datos del paso 3. Nuestros equipos internos trabajarán con usted para verificar el acceso después de aceptar la invitación. 1. Configure dos fuentes de datos para [!DNL Google Campaign Manager] los datos de [!DNL Audience Manager] Interfaz de usuario.

   Asigne un nombre a las fuentes de datos `Advertiser Analytics: DCM Platform` y `Advertiser Analytics: AAM+DCM Platform`. En el [Crear fuentes de datos](../../../features/manage-datasources.md#create-data-source) flujo de trabajo, establezca el tipo de ID en `Cookie`. Comparta los ID de las dos nuevas fuentes de datos con nuestros equipos internos.

1. Puede crear fácilmente rasgos desde la variable [!DNL Google Campaign Manager] archivos que se importan en [!DNL Audience Manager]. Consulte [Archivos de registro procesables](../../../integration/media-data-integration/actionable-log-files.md) y pregunte a su [!DNL Audience Manager] asesor de o servicio de atención al cliente para que habilite esta función.
