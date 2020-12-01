---
description: El proceso de ingesta de datos en tiempo real utiliza una serie de solicitudes HTTP del explorador de un usuario para pasar datos al Audience Manager.
seo-description: El proceso de ingesta de datos en tiempo real utiliza una serie de solicitudes HTTP del explorador de un usuario para pasar datos al Audience Manager.
seo-title: Incorporación de datos de entrada en tiempo real
solution: Audience Manager
title: Incorporación de datos de entrada en tiempo real
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---


# Incorporación de datos de entrada en tiempo real {#real-time-inbound-data-ingestion}

El proceso de ingestión de datos entrantes en tiempo real utiliza una serie de `HTTP` solicitudes del explorador de un usuario para pasar datos al Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Los datos entrantes deben formatearse como pares de clave-valor llamados señales. Normalmente, cada señal se asigna a un segmento creado o administrado a través de la interfaz de usuario o [!DNL API].

## Parámetros de cadena URL y sintaxis {#url-string-syntax}

El [!DNL URL] de una transferencia de datos de entrada debe contener las variables que se describen a continuación. Recuerde [crear características](../../../features/traits/create-onboarded-rule-based-traits.md) y una [estructura de carpetas](../../../features/traits/trait-storage.md#create-trait-storage-folder) en la interfaz de usuario [!DNL Audience Manager] antes de configurar las transferencias de datos en tiempo real.

>[!NOTE]
>
>Reemplazar contenido en cursiva con valores de parámetro reales.

| Parámetro | Descripción |
|---|---|
| `<KEY>` | Identificador único en un par de valor clave (por ejemplo, sexo, color, precio). |
| `<VAL>` | Variable que pertenece al conjunto de datos definido por la clave (por ejemplo: sexo=hombre, color=verde, precio=100) |

### Sintaxis de URL

Durante un proceso de ingestión de datos de entrada en tiempo real, una cadena [!DNL URL] correctamente formateada utiliza la siguiente sintaxis:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
