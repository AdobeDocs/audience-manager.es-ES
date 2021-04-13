---
description: Coloque los datos en los archivos de registro de informes Rendimiento de entrega en tablas que contengan solo ID. Coloque metadatos que no sean de ID en tablas de búsqueda independientes para ayudar a reducir el tamaño del archivo y los tiempos de procesamiento.
seo-description: Coloque los datos en los archivos de registro de informes Rendimiento de entrega en tablas que contengan solo ID. Coloque metadatos que no sean de ID en tablas de búsqueda independientes para ayudar a reducir el tamaño del archivo y los tiempos de procesamiento.
seo-title: Mejorar los tiempos de procesamiento de los archivos de registro con tablas de búsqueda
solution: Audience Manager
title: Mejorar los tiempos de procesamiento de los archivos de registro con tablas de búsqueda
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Referencia de referencia de informes
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 18%

---

# Mejorar los tiempos de procesamiento de los archivos de registro con tablas de búsqueda{#improve-log-file-processing-times-with-lookup-tables}

Coloque los datos en los archivos de registro de informes Rendimiento de entrega en tablas que contengan solo ID. Coloque metadatos que no sean de ID en tablas de búsqueda independientes para ayudar a reducir el tamaño del archivo y los tiempos de procesamiento.

<!-- 

c_lookup_tables.xml

 -->

## Los metadatos del archivo de registro aumentan el tamaño del archivo y el tiempo de procesamiento

Un archivo de registro típico utilizado por el informe [!UICONTROL Delivery Performance] generalmente contiene miles de filas y docenas de columnas. Consta de ID numéricos e información legible por el usuario, como nombres para creativos, anunciantes, pedidos de inserción, etc.

Esta información que no es de ID se denomina *`metadata`* (es decir, información sobre otra información) y se escribe en cada fila del archivo de registro.

Sin embargo, el informe [!UICONTROL Delivery Performance] funciona principalmente con los ID del archivo de registro. Los metadatos son útiles, pero repetitivos. Aumenta el tamaño del archivo y los tiempos de ingesta de datos.

## Reducir el tamaño del archivo y acortar el tiempo de procesamiento con tablas de índice

Para mejorar el rendimiento, el archivo de datos principal debe contener solo ID. Coloque los metadatos en una tabla de búsqueda (o índice) independiente y vincule esos registros al archivo principal con una variable clave común a ambos.

## Cómo las tablas de búsqueda reducen el tamaño del archivo

Supongamos que tiene un archivo de datos que se parece al que se muestra a continuación.

| ID de usuario | ID de anuncio | Nombre de publicidad | ID de pedido | Nombre del pedido | ID del anunciante | Nombre del anunciante |
|---|---|---|---|---|---|---|
| 1 | 111 | Zapato A | 456 | Sneakers | 27 | Empresa A |
| 2 | 111 | Zapato A | 456 | Sneakers | 27 | Empresa A |
| 3 | 111 | Zapato A | 456 | Sneakers | 27 | Empresa A |
| 4 | 222 | Zapata B | 789 | Senderismo | 14 | Empresa B |
| 5 | 222 | Zapata B | 789 | Senderismo | 14 | Empresa B |

<br> 

Este es el mismo archivo de registro con los metadatos eliminados. El archivo es más pequeño y fácil de procesar cuando solo consta de ID.

| ID de usuario | ID de anuncio | ID de pedido | ID del anunciante |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 1 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

El siguiente archivo de búsqueda contiene los metadatos y se puede vincular de nuevo al archivo principal con el ID de anuncio. Tenga en cuenta también el tamaño. En lugar de repetir cada anunciante varias veces, solo necesita una referencia para cada una.

| ID de anuncio | Nombre de publicidad | Nombre del pedido | Nombre del anunciante |
|---|---|---|---|
| 111 | Zapato A | Sneakers | Empresa A |
| 222 | Zapata B | Senderismo | Empresa B |

## Las API pueden eliminar la necesidad de tablas de búsqueda

Si el sistema de servicio de publicidad tiene una API, es posible que no necesite enviar metadatos en un archivo de búsqueda. Es posible que podamos obtener esa información a través de la API. En este caso, los archivos de registro solo deben contener ID. Trabajaremos con usted para determinar si los metadatos se pueden obtener a través de una API.
