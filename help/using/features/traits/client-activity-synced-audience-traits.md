---
description: Son rasgos especiales que utilizan las audiencias a las que se puede dirigir. Las características sincronizadas de Active Audience y Data Source se encuentran en Datos de audiencia > Características > Características de audiencia.
seo-description: These are special traits used by Addressable Audiences. Active Audience and Data Source Synced Traits are located in Audience Data > Traits > Audience Traits.
seo-title: Active Audience Traits and Data Source Synced Traits
solution: Audience Manager
title: Características de audiencia activa y características sincronizadas de datos de Source
uuid: b4f145ab-f343-4d71-86d1-5d03f7b03809
feature: Traits
exl-id: 8fa4ea24-1beb-40cb-bdec-540a3f7c2573
TQID: https://experienceleague.adobe.com/2DBCMtqRp0sQM04ec-2pKVnaEnQijjsnrk0JvqoNf3o
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 215
ht-degree: 0%

---

# Características de audiencia activa y características sincronizadas de datos de Source {#active-audience-traits-and-data-source-synced-traits}

Son rasgos especiales utilizados por [!UICONTROL Addressable Audiences]. [!UICONTROL Active Audience] y [!UICONTROL Data Source Synced Traits] se encuentran en [!UICONTROL Audience Data > Traits > Audience Traits].

>[!NOTE]
>
>El acceso requiere permisos de administrador.

## Características de audiencia activa {#active-audience-traits}

Un rasgo de [!UICONTROL Active Audience] contiene todos los dispositivos que se están administrando en su cuenta de [!DNL Audience Manager]. Puede usar un(a) [!UICONTROL Active Audience Trait] como otros rasgos al generar o editar segmentos. Además, [Audiencias direccionables](../../features/addressable-audiences.md) requiere que este rasgo genere datos de superposición. De manera predeterminada, todas las cuentas tienen un rasgo [!UICONTROL Active Audience]. No se puede eliminar este rasgo.

## Características sincronizadas de Data Source {#data-source-synced-traits}

[!UICONTROL Data Source Synced Traits] aparece en la carpeta [!UICONTROL Audience Traits] cuando [crea o edita un origen de datos](../../features/manage-datasources.md#create-data-source) y aplica cualquiera de estas configuraciones:

![](assets/datasource_synced.png)

[!UICONTROL Data Source Synced Traits] hace un seguimiento de todos los usuarios asociados a un origen de datos. Puede usar un(a) [!UICONTROL Data Source Synched Trait] como otros rasgos al generar o editar segmentos. Cuando crea un(a) [!UICONTROL Data Source Synced Trait], el nombre del rasgo coincide con el nombre usado por el origen de datos. Edite la fuente de datos para cambiar el nombre de la característica. Estos rasgos no se pueden eliminar.

>[!TIP]
>
>[!UICONTROL Data Source Synced Traits] son útiles para solucionar problemas. Haga clic en el nombre de un rasgo para comprobar las métricas en la página de resumen de rasgos. Si el rasgo seleccionado devuelve datos, esto indica que el proceso de sincronización de ID se ha configurado correctamente y que los datos se han transferido a [!DNL Audience Manager].

>[!MORELIKETHIS]
>
>* [Audiencias a las que se puede dirigir](../../features/addressable-audiences.md)
