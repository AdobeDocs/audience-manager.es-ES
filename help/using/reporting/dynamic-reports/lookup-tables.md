---
description: Coloque los datos en los archivos de registro de informes de rendimiento de Envío en tablas que contengan únicamente ID. Coloque metadatos que no sean de ID en tablas de búsqueda independientes para reducir el tamaño del archivo y los tiempos de procesamiento.
seo-description: Coloque los datos en los archivos de registro de informes de rendimiento de Envío en tablas que contengan únicamente ID. Coloque metadatos que no sean de ID en tablas de búsqueda independientes para reducir el tamaño del archivo y los tiempos de procesamiento.
seo-title: Mejorar los tiempos de procesamiento de los archivos de registro con tablas de búsqueda
solution: Audience Manager
title: Mejorar los tiempos de procesamiento de los archivos de registro con tablas de búsqueda
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 18%

---


# Mejorar los tiempos de procesamiento de los archivos de registro con tablas de búsqueda{#improve-log-file-processing-times-with-lookup-tables}

Coloque los datos en los archivos de registro de informes de rendimiento de Envío en tablas que contengan únicamente ID. Coloque metadatos que no sean de ID en tablas de búsqueda independientes para reducir el tamaño del archivo y los tiempos de procesamiento.

<!-- 

c_lookup_tables.xml

 -->

## Los metadatos del archivo de registro aumentan el tamaño del archivo y el tiempo de procesamiento

Un archivo de registro típico utilizado por el informe [!UICONTROL Delivery Performance] generalmente contiene miles de filas y docenas de columnas. Consta de ID numéricos e información legible por el usuario, como nombres para creativos, anunciantes, pedidos de inserción, etc.

Esta información que no es de ID se denomina *`metadata`* (es decir, información sobre otra información) y se escribe en cada fila del archivo de registro.

Sin embargo, el informe [!UICONTROL Delivery Performance] funciona principalmente con los ID del archivo de registro. Los metadatos son útiles, pero repetitivos. Aumenta el tamaño del archivo y los tiempos de ingestión de datos.

## Reducir el tamaño del archivo y acortar el tiempo de procesamiento con las tablas de índice

Para ayudar a mejorar el rendimiento, el archivo de datos principal debe contener solamente ID. Coloque los metadatos en una tabla de búsqueda (o índice) independiente y vincule dichos registros al archivo principal con una variable clave común a ambos.

## Cómo las tablas de búsqueda reducen el tamaño del archivo

Supongamos que tiene un archivo de datos similar al que se muestra a continuación.

| ID de usuario | ID de anuncio | Nombre de publicidad | ID de pedido | Nombre del pedido | ID del anunciante | Nombre del anunciante |
|---|---|---|---|---|---|---|
| 1 | 111 | Zapato A | 456 | Esponjas | 27 | Compañía A |
| 2 | 111 | Zapato A | 456 | Esponjas | 27 | Compañía A |
| 3 | 111 | Zapato A | 456 | Esponjas | 27 | Compañía A |
| 4 | 222 | Zapato B | 789 | Senderismo | 14 | Compañía B |
| 5 | 222 | Zapato B | 789 | Senderismo | 14 | Compañía B |

<br> 

Este es el mismo archivo de registro con los metadatos eliminados. El archivo es más pequeño y fácil de procesar cuando se compone únicamente de ID.

| ID de usuario | ID de anuncio | ID de pedido | ID del anunciante |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

El archivo de búsqueda siguiente contiene los metadatos y se puede vincular al archivo principal con el ID de publicidad. Observe también el tamaño. En lugar de repetir varias veces cada anunciante, solo necesita una referencia para cada uno.

| ID de anuncio | Nombre de publicidad | Nombre del pedido | Nombre del anunciante |
|---|---|---|---|
| 111 | Zapato A | Esponjas | Compañía A |
| 222 | Zapato B | Senderismo | Compañía B |

## Las API pueden eliminar la necesidad de tablas de búsqueda

Si el sistema de servicio de publicidad tiene una API, es posible que no necesite enviar metadatos en un archivo de búsqueda. Es posible que podamos obtener esa información a través de la API. En este caso, los archivos de registro deben contener únicamente ID. Trabajaremos con usted para determinar si los metadatos se pueden obtener a través de una API.