---
description: Coloque los datos en los archivos de registro del informe Rendimiento de entrega en tablas que contengan solo ID. Coloque metadatos que no sean de ID en tablas de búsqueda independientes para reducir el tamaño de archivo y los tiempos de procesamiento.
seo-description: Coloque los datos en los archivos de registro del informe Rendimiento de entrega en tablas que contengan solo ID. Coloque metadatos que no sean de ID en tablas de búsqueda independientes para reducir el tamaño de archivo y los tiempos de procesamiento.
seo-title: Mejore los tiempos de procesamiento de archivos de registro con tablas de búsqueda
solution: Audience Manager
title: Mejore los tiempos de procesamiento de archivos de registro con tablas de búsqueda
uuid: ffc 77618-474 b -455 e -9 c 91-15 b 32 fc 151 a 5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Improve Log File Processing Times with Lookup Tables{#improve-log-file-processing-times-with-lookup-tables}

Coloque los datos en los archivos de registro del informe Rendimiento de entrega en tablas que contengan solo ID. Coloque metadatos que no sean de ID en tablas de búsqueda independientes para reducir el tamaño de archivo y los tiempos de procesamiento.

<!-- 

c_lookup_tables.xml

 -->

## Los metadatos del archivo de registro aumentan el tamaño del archivo y el tiempo de procesamiento

A typical log file used by the [!UICONTROL Delivery Performance] report usually contains thousands of rows and dozens of columns. Consiste en ID numéricos y información legible en lenguaje natural, como nombres para creativos, anunciantes, pedidos de inserción, etc.

This non-ID information is referred to as *`metadata`* (i.e., information about other information) and gets written in each row of the log file.

However, the [!UICONTROL Delivery Performance] report mainly works with the IDs in the log file. Los metadatos son útiles, pero repetitivos. Aumenta el tamaño del archivo y los tiempos de inserción de datos.

## Reducir el tamaño de archivo y abreviar el tiempo de procesamiento con tablas de índice

Para ayudar a mejorar el rendimiento, el archivo de datos principal debe contener solamente ID. Coloque los metadatos en una tabla de búsqueda (o índice) independiente y vincule esos registros al archivo principal con una variable clave común a ambos.

## Cómo reducen las tablas de búsqueda el tamaño de archivo

Supongamos que tiene un archivo de datos similar al de abajo.

| ID de usuario | ID de anuncio | Nombre de publicidad | ID de pedido | Nombre del pedido | ID del anunciante | Nombre del anunciante |
|---|---|---|---|---|---|---|
| 1 | 111 | Zapatos A | 456 | Zapatillas | 27 | Empresa A |
| 2 | 111 | Zapatos A | 456 | Zapatillas | 27 | Empresa A |
| 3 | 111 | Zapatos A | 456 | Zapatillas | 27 | Empresa A |
| 4 | 222 | Zapatos B | 789 | Senderismo | 14 | Empresa B |
| 5 | 222 | Zapatos B | 789 | Senderismo | 14 | Empresa B |

<br> 

Este es el mismo archivo de registro con los metadatos eliminados. El archivo es más pequeño y fácil de procesar cuando consta de ID solamente.

| ID de usuario | ID de anuncio | ID de pedido | ID del anunciante |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

El archivo de búsqueda siguiente contiene los metadatos y se puede vincular al archivo principal con el ID de anuncio. También tenga en cuenta el tamaño. En lugar de repetir cada anunciante varias veces, solo necesita una referencia para cada uno.

| ID de anuncio | Nombre de publicidad | Nombre del pedido | Nombre del anunciante |
|---|---|---|---|
| 111 | Zapatos A | Zapatillas | Empresa A |
| 222 | Zapatos B | Senderismo | Empresa B |

## Las API pueden eliminar la necesidad de tablas de búsqueda

Si el sistema de servicio de publicidad tiene una API, es posible que no necesite enviar metadatos en un archivo de búsqueda. Es posible que podamos obtener esa información a través de la API. Cuando éste sea el caso, los archivos de registro deben contener sólo ID. Colaboraremos con usted para determinar si los metadatos se pueden obtener mediante una API.

>[!MORE_ LIKE_ THIS]
>
>* [Informe de entrega y rendimiento](../../reporting/dynamic-reports/delivery-performance-report.md)

