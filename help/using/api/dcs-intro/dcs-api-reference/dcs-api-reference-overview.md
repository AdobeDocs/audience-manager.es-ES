---
description: Información conceptual, descripciones y definiciones para el código, los métodos y los procesos de la API de DCS.
seo-description: Información conceptual, descripciones y definiciones para el código, los métodos y los procesos de la API de DCS en Adobe Audience Manager (AAM).
seo-title: Información general de referencia de la API de DCS en Adobe Audience Manager (AAM)
title: Información general sobre referencia de la API de DCS
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 13%

---


# Información general sobre referencia de la API de DCS

Información conceptual, descripciones y definiciones para código, métodos y procesos [!DNL DCS API].

* [Métodos de API de DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Envíe datos a [!DNL DCS API] mediante métodos de GET o POST.

* [Códigos de error DCS, mensajes y ejemplos](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Códigos de error y mensajes generados por los Servidores de recopilación de datos (DCS) enumerados en orden numérico por ID de código.

* [Supervisión y Inclusión en la lista de bloqueados de ID](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   El DCS supervisa los ID que recibe y agrega los que se envían a una lista de bloqueados a una velocidad inusualmente alta durante un corto período de tiempo.

* [ID de región de DCS, ubicaciones y nombres de host](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   El nombre de host del servidor DCS regional es necesario para realizar llamadas al DCS. Esto se debe a que el DCS almacena información en centros de datos geográficamente cercanos a los visitantes del sitio. Sus consultas funcionarán si las envía al DCS incorrecto, pero estas llamadas son ineficientes y pueden retrasar la respuesta. Para realizar una solicitud de DCS, combine el ID de región con el nombre de host regional correspondiente y forme la consulta con el nombre de host adecuado.

* [Formato de pares de clave-valor en llamadas DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Al realizar una llamada, el DCS acepta datos de clave-valor en formato estándar o serializado. Consulte esta sección para obtener información sobre cómo dar formato a los datos de clave-valor estándar y serializados.

* [Condiciones de carrera y gestión de errores](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Describe cómo evitar las condiciones de carrera y el manejo de errores de DCS.

* [Atributos admitidos para llamadas a la API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Lista y describe la sintaxis y los atributos admitidos (o pares clave-valor) que puede pasar a los Servidores de recopilación de datos (DCS). Esta información puede ayudarle a dar formato a sus solicitudes de DCS y a comprender los parámetros devueltos por este sistema.
