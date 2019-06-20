---
description: Los componentes de acción de datos incluyen Fuentes de datos de clientes, Servidor de recopilación de datos, SFTP/S 3/editores HTTP, IRIS y el Servidor de caché de perfil.
seo-description: Los componentes de acción de datos incluyen Fuentes de datos de clientes, Servidor de recopilación de datos, SFTP/S 3/editores HTTP, IRIS y el Servidor de caché de perfil.
seo-title: Componentes de acción de datos
solution: Audience Manager
title: Componentes de acción de datos
uuid: c 4 c 4 cc 46-8 c 96-4 ef 5-8269-571 cc 5 ac 9276
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Action Components{#data-action-components}

Los componentes de acción de datos incluyen Fuentes de datos de clientes, Servidor de recopilación de datos, SFTP/S 3/editores HTTP, IRIS y el Servidor de caché de perfil.

<!-- 

c_compact.xml

 -->

Action components are systems and processes that let you move data in and out of [!DNL Audience Manager] and (for the lack of a better phrase) do things with it. These [!DNL Audience Manager] components include:

## Customer Data Feeds (CDF) {#cdf}

[!UICONTROL CDF] son archivos enviados por hora a los clientes. Éstos contienen ID de usuario junto con ID de segmentos asociados, ID de características y otros datos. For more information, see [Customer Data Feed Overview](../../features/cdf-files.md).

## Data Collection Server (DCS) {#dcs}

See [Data Collection Components](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

[!UICONTROL SFTP/S3] Los editores reciben datos de ID sincronizados del [!UICONTROL Outbound Feed Converter]. When these files are ready, the [!UICONTROL SFTP/S3 publishers] send this data to a destination specified by the client. These files contain synchronized ID data with a one-to-many mapping of [!DNL Audience Manager] user IDs (UUID) to:

* ID del dispositivo/ID del proveedor de datos (DPUUID)
* ID de segmentos cualificados
* ID de características

[!DNL Audience Manager] los clientes no tienen acceso a funciones que controlan directamente la [!UICONTROL SFPT/S3 publishers]. Los clientes utilizan este servicio indirectamente cuando crean y envían datos a destinos. The [!UICONTROL SFTP/S3] system is, essentially, an automated job process that runs at scheduled intervals.

## IRIS {#iris}

In Greek mythology, [!UICONTROL Iris] is a figure who travels and delivers messages rapidly. [!UICONTROL IRIS] El sistema es un namesake que refleja las características de esta figura del mundo antiguo. In modern terms, [!UICONTROL IRIS] is a low-latency, high-frequency cookie synchronization and data transfer service.

[!UICONTROL IRIS] funciona con el mismo tipo de datos que [!UICONTROL SFTP/S3] el sistema. However, [!UICONTROL IRIS] is different because it sends data to destinations in real time rather than at set intervals. This is a separate system because the [!UICONTROL SFTP/S3] publishers can&#39;t send data to an HTTP destination and they&#39;re not designed for real-time data transfers.

There are no UI controls that let customers work directly with [!UICONTROL IRIS]. Customers work with [!UICONTROL IRIS] indirectly when they create and send data to destinations, and for other processes that require rapid data transfers.

Examples of [!UICONTROL IRIS] services and features include:

* La sincronización rápida (dentro de 30 segundos) para cookies y segmentos. It can synchronize the [!DNL Audience Manager] cookie, partner cookies, or both.
* Transferencias de datos en tiempo real. [!UICONTROL IRIS] es responsable de enviar eventos de cualificación de segmentos en tiempo real a un socio u otro destino. This data is JSON-formatted and sent via an HTTP `POST` request.

* Bulk server-to-server data transfers: If you exchange large amounts of data with [!DNL Audience Manager], [!UICONTROL IRIS] is the system that your servers engage with to transfer data.

* Infraestructura fiable que funciona a escala y que admite fallos. Systems that power [!UICONTROL IRIS] include Amazon SQS, Amazon EC2, and Cassandra.

**Reglas de asignación de segmentos**

To optimize traffic between [!UICONTROL IRIS] and segment destinations, [!UICONTROL IRIS] sends segments to destinations based on a set of rules.

1. **Nueva cualificación de segmentos**: Cuando un dispositivo cumple los criterios para un nuevo segmento [!UICONTROL IRIS] , envía todos los segmentos asociados a dicho dispositivo a todos los destinos asignados a estos segmentos.

1. **Nueva descalificación de segmentos**: cuando un dispositivo ya no cumple los requisitos de un segmento [!UICONTROL IRIS] , envía todas las calificaciones y descalificaciones de segmentos asociadas a dicho dispositivo a todos los destinos asignados a estos segmentos.

1. **Actualizaciones de asignación de destino**: cuando se actualiza una asignación de destino [!UICONTROL IRIS] , envía todos los segmentos asociados a un dispositivo a todos los destinos asignados a estos segmentos, la próxima vez que Audience Manager ve el dispositivo.

1. **Actualizaciones del gráfico de dispositivo**: Cuando se agrega o elimina cualquier ID de dispositivo del gráfico de dispositivos utilizado para evaluar un segmento, [!UICONTROL IRIS] envía todos los segmentos asociados a dicho dispositivo a todos los destinos asignados a estos segmentos, la próxima vez que Audience Manager ve el dispositivo.

>[!IMPORTANT]
>
>If Audience Manager doesn&#39;t detect any of the updates above for 3 consecutive days, [!UICONTROL IRIS] sends all segments associated to a device to all of the destinations mapped to these segments, the next time Audience Manager sees the device.

**Archivo de datos de ejemplo**

The following example contains real-time segment data from [!UICONTROL IRIS]. Tenga en cuenta que solo son datos de ejemplo. Cada cliente puede tener diferentes requisitos de formato para que el contenido pueda variar.

```
{
    "ProcessTime": "Tue Jul 21 19:12:45 UTC 2015",
    "Client_ID": "111111",
    "AAM_Destination_Id": "22222",
    "User_count": "5",
    "Users": [
        {
            "AAM_UUID": "28272096202945091600036434734793744071",
            "DataPartner_UUID": "CAESEFdv5pk-Lurd8vL9Yfb3qFg",
            "Segments": [
                {
                    "Segment_ID": "1200598",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:12 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "35183292386788708387827965829455926157",
            "DataPartner_UUID": "CAESEF_d8blvZjchQ2WTzdB65yk",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:15 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "28012470144260632050402316345856327572",
            "DataPartner_UUID": "CAESEEPfHBiRjhkzvBPXQ-0MFRE|UzCESAAABOnFeHJy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:33 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "18981483751565214534184221210627150539",
            "DataPartner_UUID": "CAK4NDH0ESEE6NBEhoWDkB7s7ZY|VPYFQQAAASXPElL0",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:36 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "04761851136483019318109155624251711702",
            "DataPartner_UUID": "CAESEDkM5aSaKMV8MfaBhgSspmE|VYnTNwAAASzvVhxy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:42 UTC 2015"
                }
            ]
        }
    ]
}
```

## Profile Cache Server (PCS) {#pcs}

See [Data Collection Components](../../reference/system-components/components-data-collection.md).
