---
description: El proceso de inserción de datos de entrada en tiempo real utiliza una serie de solicitudes HTTP desde el explorador del usuario para pasar datos a Audience Manager.
seo-description: El proceso de inserción de datos de entrada en tiempo real utiliza una serie de solicitudes HTTP desde el explorador del usuario para pasar datos a Audience Manager.
seo-title: Ingesta de datos de entrada en tiempo real
solution: Audience Manager
title: Ingesta de datos de entrada en tiempo real
uuid: 43 cb 0 ebc -6 c 36-4391-bbfb -6 b 203 d 63 c 69 a 69
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Real-Time Inbound Data Ingestion {#real-time-inbound-data-ingestion}

The real-time inbound data ingestion process uses a series of `HTTP` requests from a user's browser to pass in data to Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Los datos de entrada deben formatearse como pares clave-valor denominados señales. Typically, each signal is mapped to a segment created or managed through the user interface or [!DNL API].

## URL String Parameters and Syntax {#url-string-syntax}

The [!DNL URL] for an inbound data transfer should contain the variables described below. Remember to [create traits](../../../features/traits/create-onboarded-rule-based-traits.md) and a [folder structure](../../../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI before setting up real-time data transfers.

>[!NOTE]
>
>Reemplazar contenido en cursiva con valores de parámetro reales.

| Parámetro | Descripción |
|---|---|
| `<KEY>` | Identificador único en un par clave-valor (por ejemplo: sexo, color, precio). |
| `<VAL>` | Una variable que pertenece al conjunto de datos definido por la clave (por ejemplo: sexo = hombre, color = verde, price = 100) |

### Sintaxis URL

During a real-time inbound data ingestion process, a properly formatted [!DNL URL] string uses the following syntax:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
