---
description: Coloque los datos en los archivos de registro del informe de rendimiento de entrega en tablas que solo contengan ID. Coloque metadatos no ID en tablas de búsqueda independientes para ayudar a reducir el tamaño del archivo y los tiempos de procesamiento.
seo-description: Put data in Delivery Performance report log files into tables that contain IDs only. Put non-ID metadata in separate lookup tables to help reduce file size and processing times.
seo-title: Improve Log File Processing Times with Lookup Tables
solution: Audience Manager
title: Mejora de los tiempos de procesamiento de archivos de registro con tablas de búsqueda
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Reporting Reference
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 13%

---

# Mejora de los tiempos de procesamiento de archivos de registro con tablas de búsqueda{#improve-log-file-processing-times-with-lookup-tables}

Coloque los datos en los archivos de registro del informe de rendimiento de entrega en tablas que solo contengan ID. Coloque metadatos no ID en tablas de búsqueda independientes para ayudar a reducir el tamaño del archivo y los tiempos de procesamiento.

<!-- 

c_lookup_tables.xml

 -->

## Los metadatos de archivo de registro aumentan el tamaño del archivo y el tiempo de procesamiento

Normalmente, un archivo de registro utilizado por el informe [!UICONTROL Delivery Performance] contiene miles de filas y docenas de columnas. Consiste en ID numéricos e información legible en lenguaje natural como nombres de creativos, anunciantes, pedidos de inserción, etc.

Esta información que no es de identificador se denomina *`metadata`* (es decir, información acerca de otra información) y se escribe en cada fila del archivo de registro.

Sin embargo, el informe [!UICONTROL Delivery Performance] funciona principalmente con los identificadores del archivo de registro. Los metadatos son útiles, pero repetitivos. Aumenta el tamaño del archivo y los tiempos de ingesta de datos.

## Reducción del tamaño de archivo y reducción del tiempo de procesamiento con tablas de índice

Para ayudar a mejorar el rendimiento, el archivo de datos principal solo debe contener ID. Coloque los metadatos en una tabla de búsqueda (o índice) independiente y vincule esos registros al archivo principal con una variable clave común a ambas.

## Cómo reducen el tamaño de archivo las tablas de búsqueda

Supongamos que tiene un archivo de datos similar al de abajo.

| ID de usuario | ID de anuncio | Nombre de publicidad | ID de pedido | Nombre del pedido | ID de anunciante | Nombre del anunciante |
|---|---|---|---|---|---|---|
| 1 | 111 | Zapata A | 456 | Zapatillas | 27 | Empresa A |
| 2 | 111 | Zapata A | 456 | Zapatillas | 27 | Empresa A |
| 3 | 111 | Zapata A | 456 | Zapatillas | 27 | Empresa A |
| 4 | 222 | Zapato B | 789 | Senderismo | 14 | Empresa B |
| 5 | 222 | Zapato B | 789 | Senderismo | 14 | Empresa B |

<br> 

Este es el mismo archivo de registro con los metadatos eliminados. El archivo es más pequeño y fácil de procesar cuando solo consta de ID.

| ID de usuario | ID de anuncio | ID de pedido | ID de anunciante |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

El archivo de búsqueda siguiente contiene los metadatos y se puede vincular de nuevo al archivo principal con el ID de anuncio. Tenga en cuenta el tamaño también. En lugar de repetir cada anunciante varias veces, solo necesita una referencia para cada uno.

| ID de anuncio | Nombre de publicidad | Nombre del pedido | Nombre del anunciante |
|---|---|---|---|
| 111 | Zapata A | Zapatillas | Empresa A |
| 222 | Zapato B | Senderismo | Empresa B |

## Las API pueden eliminar la necesidad de tablas de búsqueda

Si el sistema de servicio de publicidad tiene una API, es posible que no necesite enviar metadatos en un archivo de búsqueda. Es posible que podamos obtener esa información a través de la API. En este caso, los archivos de registro solo deben contener ID. Trabajaremos con usted para determinar si se pueden obtener metadatos a través de una API.
