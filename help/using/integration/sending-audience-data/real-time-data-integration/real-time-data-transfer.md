---
description: El proceso de ingesta de datos entrantes en tiempo real utiliza una serie de solicitudes HTTP desde el explorador de un usuario para pasar datos al Audience Manager.
seo-description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-title: Real-Time Inbound Data Ingestion
solution: Audience Manager
title: Incorporación de datos de entrada en tiempo real
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 5%

---

# Incorporación de datos de entrada en tiempo real {#real-time-inbound-data-ingestion}

El proceso de ingesta de datos entrantes en tiempo real utiliza una serie de `HTTP` solicitudes del explorador de un usuario para pasar datos al Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Los datos entrantes deben tener el formato de pares clave-valor llamados señales. Normalmente, cada señal se asigna a un segmento creado o administrado a través de la interfaz de usuario o [!DNL API].

## Parámetros y sintaxis de la cadena URL {#url-string-syntax}

El [!DNL URL] para una transferencia de datos entrante debe contener las variables que se describen a continuación. Recuerde lo siguiente [crear rasgos](../../../features/traits/create-onboarded-rule-based-traits.md) y una [estructura de carpetas](../../../features/traits/trait-storage.md#create-trait-storage-folder) en el [!DNL Audience Manager] IU antes de configurar transferencias de datos en tiempo real.

>[!NOTE]
>
>Reemplace el contenido en cursiva por los valores de parámetro reales.

| Parámetro | Descripción |
|---|---|
| `<KEY>` | Un identificador único en un par clave-valor (por ejemplo, sexo, color, precio). |
| `<VAL>` | Variable que pertenece al conjunto de datos definido por la clave (por ejemplo, gender=male, color=green, price=100) |

### Sintaxis de URL

Durante un proceso de ingesta de datos entrantes en tiempo real, un [!DNL URL] La cadena utiliza la siguiente sintaxis:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
