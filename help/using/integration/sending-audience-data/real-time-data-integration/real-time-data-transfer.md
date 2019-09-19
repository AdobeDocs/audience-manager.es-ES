---
description: El proceso de ingesta de datos en tiempo real utiliza una serie de solicitudes HTTP del explorador de un usuario para pasar datos a Audience Manager.
seo-description: El proceso de ingesta de datos en tiempo real utiliza una serie de solicitudes HTTP del explorador de un usuario para pasar datos a Audience Manager.
seo-title: Ingesta de datos de entrada en tiempo real
solution: Audience Manager
title: Ingesta de datos de entrada en tiempo real
uuid: 43cb0ebc-6c36-4391-bfb-6b203d63c69a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ingesta de datos de entrada en tiempo real {#real-time-inbound-data-ingestion}

El proceso de ingesta de datos en tiempo real utiliza una serie de `HTTP` solicitudes del explorador de un usuario para pasar datos a Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Los datos entrantes deben formatearse como pares de clave-valor llamados señales. Normalmente, cada señal se asigna a un segmento creado o administrado a través de la interfaz de usuario o [!DNL API].

## Parámetros y sintaxis de la cadena URL {#url-string-syntax}

El [!DNL URL] de una transferencia de datos de entrada debe contener las variables que se describen a continuación. Recuerde [crear características](../../../features/traits/create-onboarded-rule-based-traits.md) y una estructura [de](../../../features/traits/trait-storage.md#create-trait-storage-folder) [!DNL Audience Manager] carpetas en la interfaz de usuario antes de configurar las transferencias de datos en tiempo real.

>[!NOTE]
>
>Reemplazar contenido en cursiva con valores de parámetro reales.

| Parámetro | Descripción |
|---|---|
| `<KEY>` | Identificador único en un par de valor clave (por ejemplo, sexo, color, precio). |
| `<VAL>` | Variable que pertenece al conjunto de datos definido por la clave (por ejemplo: sexo=hombre, color=verde, precio=100) |

### Sintaxis de URL

Durante un proceso de ingestión de datos de entrada en tiempo real, una [!DNL URL] cadena con el formato correcto utiliza la siguiente sintaxis:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
