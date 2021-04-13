---
description: El proceso de ingesta de datos de entrada en tiempo real utiliza una serie de solicitudes HTTP del explorador de un usuario para pasar datos al Audience Manager.
seo-description: El proceso de ingesta de datos de entrada en tiempo real utiliza una serie de solicitudes HTTP del explorador de un usuario para pasar datos al Audience Manager.
seo-title: Incorporación de datos de entrada en tiempo real
solution: Audience Manager
title: Incorporación de datos de entrada en tiempo real
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Transferencias de datos de entrada
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 8%

---

# Incorporación de datos de entrada en tiempo real {#real-time-inbound-data-ingestion}

El proceso de incorporación de datos de entrada en tiempo real utiliza una serie de `HTTP` solicitudes del explorador de un usuario para pasar datos al Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Los datos de entrada deben tener el formato de pares de clave-valor llamados señales. Normalmente, cada señal se asigna a un segmento creado o administrado a través de la interfaz de usuario o [!DNL API].

## Parámetros de cadena de URL y sintaxis {#url-string-syntax}

El [!DNL URL] para una transferencia de datos de entrada debe contener las variables que se describen a continuación. Recuerde [crear características](../../../features/traits/create-onboarded-rule-based-traits.md) y una [estructura de carpetas](../../../features/traits/trait-storage.md#create-trait-storage-folder) en la interfaz de usuario [!DNL Audience Manager] antes de configurar las transferencias de datos en tiempo real.

>[!NOTE]
>
>Reemplace el contenido en cursiva con valores de parámetro reales.

| Parámetro | Descripción |
|---|---|
| `<KEY>` | Identificador único en un par clave-valor (por ejemplo, sexo, color, precio). |
| `<VAL>` | Variable que pertenece al conjunto de datos definido por la clave (por ejemplo, gender=male, color=green, price=100) |

### Sintaxis de URL

Durante un proceso de ingesta de datos de entrada en tiempo real, una cadena [!DNL URL] con formato correcto utiliza la siguiente sintaxis:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
