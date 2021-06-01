---
description: Información conceptual, descripciones y definiciones del código, los métodos y los procesos de la API de DCS.
seo-description: Información conceptual, descripciones y definiciones del código, los métodos y los procesos de la API de DCS en Adobe Audience Manager (AAM).
seo-title: Información general sobre la referencia de la API de DCS en Adobe Audience Manager (AAM)
title: Información general sobre referencia de la API de DCS
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 13%

---

# Información general sobre referencia de la API de DCS

Información conceptual, descripciones y definiciones para código, métodos y procesos [!DNL DCS API].

* [Métodos de API de DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Envíe datos a [!DNL DCS API] mediante métodos de GET o POST.

* [Códigos de error DCS, mensajes y ejemplos](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Códigos de error y mensajes generados por los servidores de recopilación de datos (DCS) enumerados en orden numérico por ID de código.

* [Monitorización de ID y Inclusión en la lista de bloqueados](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   El DCS supervisa los ID que recibe y añade a una lista de bloqueados aquellos que se envían a una tasa inusualmente alta durante un corto periodo de tiempo.

* [ID de región de DCS, ubicaciones y nombres de host](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   El nombre de host del servidor DCS regional es necesario para realizar llamadas al DCS. Esto se debe a que el DCS almacena información en centros de datos geográficamente cercanos a los visitantes del sitio. Sus consultas funcionarán si las envía al DCS incorrecto, pero estas llamadas son ineficientes y pueden retrasar la respuesta. Para realizar una solicitud de DCS, combine el ID de región con su nombre de host regional correspondiente y forme la consulta con el nombre de host adecuado.

* [Formato de pares de clave-valor en llamadas DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Al realizar una llamada a , el DCS acepta datos de valor clave en formato estándar o serializado. Consulte esta sección para obtener información sobre cómo dar formato a datos de clave-valor estándar y serializados.

* [Condiciones de carrera y gestión de errores](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Describe cómo evitar las condiciones de carrera y la gestión de errores de DCS.

* [Atributos admitidos para llamadas a la API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Enumera y describe la sintaxis y los atributos admitidos (o pares clave-valor) que puede pasar a los Servidores de recopilación de datos (DCS). Esta información puede ayudarle a dar formato a sus solicitudes de DCS y a comprender los parámetros que devuelve este sistema.
