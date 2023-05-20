---
description: Los píxeles simples (que se pueden utilizar para clasificar usuarios para rasgos) realizan transferencias de datos en tiempo real. La interfaz de Audience Manager permite a los clientes crear cualquier número de píxeles en modo de autoservicio. Las cadenas de píxeles constan de ID simples o pares clave-valor.
seo-description: Simple pixels (that can be used to qualify users for traits) perform real-time data transfers. The Audience Manager interface lets clients create any number of pixels on a self-service basis. Pixel strings consist of simple IDs or key-value pairs.
seo-title: Pixel-based Data Transfers
solution: Audience Manager
title: Transferencias de datos basadas en píxeles
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 4%

---

# Transferencias de datos basadas en píxeles {#pixel-based-data-transfers}

Los píxeles simples (que se pueden utilizar para clasificar usuarios para rasgos) realizan transferencias de datos en tiempo real. La interfaz de Audience Manager permite a los clientes crear cualquier número de píxeles en modo de autoservicio. Las cadenas de píxeles constan de ID simples o pares clave-valor.

<!-- c_rt_inbound_pixel_transfers.xml -->

Para habilitar las transferencias de datos entrantes, el proveedor y el cliente deberían hacer lo siguiente:

1. Determine qué características desea que el proveedor o socio active.
1. Obtenga el píxel del rasgo. En la pantalla de la lista de características, pase el ratón sobre **[!UICONTROL Actions]** y haga clic en **[!UICONTROL Get trait URL]** símbolo para el rasgo deseado.
1. Proporcione el [!DNL URL] al proveedor o socio.

## Ejemplos

Esta llamada de evento básica envía el ID de rasgo 1234 a [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Puede serializar los ID de rasgos en una llamada de evento para reducir `HTTP` tráfico de la página. Anexe ID de rasgos adicionales a la cadena URL como se muestra en el siguiente ejemplo:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
