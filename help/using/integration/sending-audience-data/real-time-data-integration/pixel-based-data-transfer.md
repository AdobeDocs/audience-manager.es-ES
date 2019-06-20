---
description: Los píxeles simples (que se pueden utilizar para calificar a los usuarios para características) realizan transferencias de datos en tiempo real. La interfaz de Audience Manager permite a los clientes crear cualquier cantidad de píxeles por autoservicio. Las cadenas de píxeles consisten en ID simples o pares clave-valor.
seo-description: Los píxeles simples (que se pueden utilizar para calificar a los usuarios para características) realizan transferencias de datos en tiempo real. La interfaz de Audience Manager permite a los clientes crear cualquier cantidad de píxeles por autoservicio. Las cadenas de píxeles consisten en ID simples o pares clave-valor.
seo-title: Transferencias de datos basadas en píxeles
solution: Audience Manager
title: Transferencias de datos basadas en píxeles
uuid: 8773 bfc 0-6 b 8 d -4 a 6 a-a 8 b 7-e 043744486 ab
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Pixel-based Data Transfers {#pixel-based-data-transfers}

Los píxeles simples (que se pueden utilizar para calificar a los usuarios para características) realizan transferencias de datos en tiempo real. La interfaz de Audience Manager permite a los clientes crear cualquier cantidad de píxeles por autoservicio. Las cadenas de píxeles consisten en ID simples o pares clave-valor.

<!-- c_rt_inbound_pixel_transfers.xml -->

Para habilitar transferencias de datos entrantes, el proveedor y el cliente harían lo siguiente:

1. Determine qué características desea que se active el proveedor o el socio.
1. Obtener el píxel de la característica. In the traits list screen, hover over the **[!UICONTROL Actions]** column and click the **[!UICONTROL Get trait URL]** symbol for the desired trait.
1. Provide the [!DNL URL] to the vendor or partner.

## Ejemplos

This basic event call sends trait ID 1234 to [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

You can serialize trait IDs in an event call to help reduce `HTTP` traffic from the page. Anexe ID de características adicionales a la cadena URL como se muestra en el siguiente ejemplo:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
