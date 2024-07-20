---
description: Los componentes de acción de datos incluyen las fuentes de datos del cliente, el servidor de recopilación de datos, los editores SFTP/S3/HTTP, IRIS y el servidor de caché de perfiles.
seo-description: Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.
seo-title: Data Action Components
solution: Audience Manager
title: Componentes de acción de datos
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: System Components
exl-id: 8065c19f-1930-4164-a952-1686aa5cb622
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 1%

---

# Componentes de acción de datos{#data-action-components}

Los componentes de acción de datos incluyen las fuentes de datos del cliente, el servidor de recopilación de datos, los editores SFTP/S3/HTTP, IRIS y el servidor de caché de perfiles.

<!-- 

c_compact.xml

 -->

Los componentes de acción son sistemas y procesos que le permiten mover datos dentro y fuera de [!DNL Audience Manager] y (a falta de una frase mejor) hacer cosas con ellos. Estos [!DNL Audience Manager] componentes incluyen:

## Fuentes de datos del cliente (CDF) {#cdf}

[!UICONTROL CDF] son archivos enviados cada hora a los clientes. Contienen ID de usuario junto con ID de segmento, ID de rasgos y otros datos asociados. Para obtener más información, consulte [Información general sobre la fuente de datos del cliente](../../features/cdf-files.md).

## Servidor de recopilación de datos (DCS) {#dcs}

Consulte [Componentes de recopilación de datos](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

Los editores [!UICONTROL SFTP/S3] reciben datos de identificador sincronizados de [!UICONTROL Outbound Feed Converter]. Cuando estos archivos estén listos, [!UICONTROL SFTP/S3 publishers] enviará estos datos a un destino especificado por el cliente. Estos archivos contienen datos de identificador sincronizados con una asignación de uno a varios de [!DNL Audience Manager] identificadores de usuario (UUID) a:

* ID de dispositivo/ID del proveedor de datos (DPUUID)
* ID de segmento cualificados
* ID de rasgos

[!DNL Audience Manager] clientes no tienen acceso a las características que controlan directamente [!UICONTROL SFPT/S3 publishers]. Los clientes utilizan este servicio indirectamente cuando crean y envían datos a destinos. El sistema [!UICONTROL SFTP/S3] es, en esencia, un proceso de trabajo automatizado que se ejecuta a intervalos programados.

## IRIS {#iris}

En la mitología griega, [!UICONTROL Iris] es una figura que viaja y envía mensajes rápidamente. El sistema [!UICONTROL IRIS] es un homónimo que refleja las características de esta figura del mundo antiguo. En términos modernos, [!UICONTROL IRIS] es un servicio de transferencia de datos y sincronización de cookies de baja latencia y alta frecuencia.

[!UICONTROL IRIS] funciona con el mismo tipo de datos que el sistema [!UICONTROL SFTP/S3]. Sin embargo, [!UICONTROL IRIS] es diferente porque envía datos a destinos en tiempo real en lugar de a intervalos establecidos. Este es un sistema independiente porque los editores de [!UICONTROL SFTP/S3] no pueden enviar datos a un destino HTTP y no están diseñados para transferencias de datos en tiempo real.

No hay controles de interfaz de usuario que permitan que los clientes trabajen directamente con [!UICONTROL IRIS]. Los clientes trabajan con [!UICONTROL IRIS] indirectamente cuando crean y envían datos a destinos y para otros procesos que requieren transferencias de datos rápidas.

Algunos ejemplos de servicios y características de [!UICONTROL IRIS] son:

* Proporciona una sincronización rápida (en 30 segundos) para cookies y segmentos. Puede sincronizar la cookie [!DNL Audience Manager], las cookies de socio o ambas.
* Transferencias de datos en tiempo real. [!UICONTROL IRIS] es responsable de enviar eventos de calificación de segmentos en tiempo real a un socio u otro destino. Estos datos tienen formato JSON y se envían mediante una solicitud HTTP `POST`.

* Transferencias masivas de datos de servidor a servidor: si intercambia grandes cantidades de datos con [!DNL Audience Manager], [!UICONTROL IRIS] es el sistema con el que interactúan los servidores para transferir datos.

* Infraestructura fiable que funciona a escala y es tolerante a fallos. Los sistemas que alimentan [!UICONTROL IRIS] incluyen Amazon SQS, Amazon EC2 y Cassandra.

**Reglas de asignación de segmentos**

Para optimizar el tráfico entre [!UICONTROL IRIS] y los destinos del segmento, [!UICONTROL IRIS] envía segmentos a destinos en función de un conjunto de reglas.

1. **Nueva calificación de segmentos**: cuando un dispositivo se califica para un nuevo segmento, [!UICONTROL IRIS] envía todos los segmentos asociados a ese dispositivo a todos los destinos asignados a estos segmentos.

1. **Nueva descalificación de segmento**: cuando un dispositivo ya no cumple los requisitos para un segmento, [!UICONTROL IRIS] envía todas las clasificaciones y desclasificaciones de segmento asociadas a ese dispositivo a todos los destinos asignados a estos segmentos.

1. **Actualizaciones de asignación de destino**: cuando se actualiza una asignación de destino, [!UICONTROL IRIS] envía todos los segmentos asociados a un dispositivo a todos los destinos asignados a estos segmentos, la próxima vez que el Audience Manager vea el dispositivo.

1. **Actualizaciones del gráfico de dispositivos**: cuando se agrega o elimina cualquier ID de dispositivo del gráfico de dispositivos utilizado para evaluar un segmento, [!UICONTROL IRIS] envía todos los segmentos asociados a ese dispositivo a todos los destinos asignados a estos segmentos, la próxima vez que el Audience Manager vea el dispositivo.

>[!IMPORTANT]
>
>Si el Audience Manager no detecta ninguna de las actualizaciones anteriores durante 3 días consecutivos, [!UICONTROL IRIS] enviará todos los segmentos asociados a un dispositivo a todos los destinos asignados a estos segmentos la próxima vez que el Audience Manager vea el dispositivo.

**Archivo de datos de muestra**

El siguiente ejemplo contiene datos de segmentos en tiempo real de [!UICONTROL IRIS]. Tenga en cuenta que solo son datos de ejemplo. Cada cliente puede tener diferentes requisitos de formato para que el contenido pueda variar.

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

## Servidor de caché de perfiles (PCS) {#pcs}

Consulte [Componentes de recopilación de datos](../../reference/system-components/components-data-collection.md).
