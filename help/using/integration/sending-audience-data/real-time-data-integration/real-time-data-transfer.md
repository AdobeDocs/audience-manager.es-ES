---
description: El proceso de ingesta de datos entrantes en tiempo real utiliza una serie de solicitudes HTTP desde el explorador de un usuario para pasar datos a Audience Manager.
seo-description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-title: Real-Time Inbound Data Ingestion
solution: Audience Manager
title: Ingesta de datos de entrada en tiempo real
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
TQID: https://experienceleague.adobe.com/ps6Iks-zvDnIIEagSND0LEnW18K6odtuwIJOsBfp2v0
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 169
ht-degree: 1%

---

# Ingesta de datos de entrada en tiempo real {#real-time-inbound-data-ingestion}

El proceso de ingesta de datos de entrada en tiempo real usa una serie de `HTTP` solicitudes del explorador de un usuario para pasar datos a Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Los datos entrantes deben tener el formato de pares clave-valor llamados señales. Normalmente, cada señal se asigna a un segmento creado o administrado mediante la interfaz de usuario o [!DNL API].

## Parámetros y sintaxis de la cadena URL {#url-string-syntax}

[!DNL URL] para una transferencia de datos de entrada debe contener las variables que se describen a continuación. Recuerde [crear características](../../../features/traits/create-onboarded-rule-based-traits.md) y una [estructura de carpetas](../../../features/traits/trait-storage.md#create-trait-storage-folder) en la interfaz de usuario de [!DNL Audience Manager] antes de configurar las transferencias de datos en tiempo real.

>[!NOTE]
>
>Reemplace el contenido en cursiva por los valores de parámetro reales.

| Parámetro | Descripción |
|---|---|
| `<KEY>` | Un identificador único en un par clave-valor (por ejemplo, sexo, color, precio). |
| `<VAL>` | Variable que pertenece al conjunto de datos definido por la clave (por ejemplo, gender=male, color=green, price=100) |

### Sintaxis de URL

Durante un proceso de ingesta de datos de entrada en tiempo real, una cadena [!DNL URL] con el formato correcto utiliza la sintaxis siguiente:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
