---
description: Los píxeles simples (que se pueden utilizar para calificar a los usuarios para las características) realizan transferencias de datos en tiempo real. La interfaz de Audience Manager permite a los clientes crear cualquier número de píxeles por autoservicio. Las cadenas de píxeles consisten en ID simples o pares de clave-valor.
seo-description: Los píxeles simples (que se pueden utilizar para calificar a los usuarios para las características) realizan transferencias de datos en tiempo real. La interfaz de Audience Manager permite a los clientes crear cualquier número de píxeles por autoservicio. Las cadenas de píxeles consisten en ID simples o pares de clave-valor.
seo-title: Transferencias de datos basadas en píxeles
solution: Audience Manager
title: Transferencias de datos basadas en píxeles
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 4%

---


# Transferencias de datos basadas en píxeles {#pixel-based-data-transfers}

Los píxeles simples (que se pueden utilizar para calificar a los usuarios para las características) realizan transferencias de datos en tiempo real. La interfaz de Audience Manager permite a los clientes crear cualquier número de píxeles por autoservicio. Las cadenas de píxeles consisten en ID simples o pares de clave-valor.

<!-- c_rt_inbound_pixel_transfers.xml -->

Para habilitar las transferencias de datos de entrada, el proveedor y el cliente:

1. Determine qué características desea que el proveedor o socio active.
1. Obtenga el píxel de la característica. En la pantalla de lista de características, pase el ratón por encima de la columna **[!UICONTROL Actions]** y haga clic en el símbolo **[!UICONTROL Get trait URL]** de la característica deseada.
1. Proporcione el [!DNL URL] al proveedor o socio.

## Ejemplos

Esta llamada de evento básica envía el ID de característica 1234 a [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Puede serializar las ID de características en una llamada de evento para ayudar a reducir el tráfico `HTTP` desde la página. Anexe ID de características adicionales a la cadena URL, como se muestra en el siguiente ejemplo:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
