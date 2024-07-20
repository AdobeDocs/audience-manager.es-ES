---
description: Información conceptual, descripciones y definiciones de código, métodos y procesos de la API de DCS.
seo-description: Conceptual information, descriptions, and definitions for DCS API code, methods, and processes in Adobe Audience Manager (AAM).
seo-title: DCS API Reference Overview in Adobe Audience Manager (AAM)
title: Descripción general de referencia de API DCS
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---

# Descripción general de referencia de API DCS

Información conceptual, descripciones y definiciones del código, métodos y procesos de [!DNL DCS API].

* [Métodos de API de DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

  Enviar datos a [!DNL DCS API] mediante métodos de GET o POST.

* [Códigos de error DCS, mensajes y ejemplos](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

  Códigos de error y mensajes generados por los servidores de recopilación de datos (DCS) enumerados en orden numérico por ID de código.

* [Monitorización de ID e Inclusión en la lista de bloqueados de](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

  El DCS supervisa los ID que recibe y añade a una lista de bloqueados los que se envían a una tasa inusualmente alta en un corto período de tiempo.

* [ID de región de DCS, ubicaciones y nombres de host](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

  Se requiere el nombre de host del servidor DCS regional para realizar llamadas al DCS. Esto se debe a que el DCS almacena información en centros de datos ubicados geográficamente cerca de los visitantes del sitio. Sus consultas funcionarán si las envía al DCS incorrecto, pero estas llamadas son ineficientes y pueden retrasar la respuesta. Para realizar una solicitud de DCS, combine el ID de región con su nombre de host regional correspondiente y forme la consulta con el nombre de host adecuado.

* [Formato de pares de clave-valor en llamadas DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

  Al realizar una llamada, el DCS acepta datos de clave-valor en formato estándar o serializado. Consulte esta sección para obtener información sobre el formato de datos de clave-valor estándar y serializados.

* [Condiciones de carrera y gestión de errores](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

  Describe cómo evitar condiciones de carrera y la administración de errores DCS.

* [Atributos admitidos para llamadas a la API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

  Enumera y describe la sintaxis y los atributos admitidos (o pares clave-valor) que puede pasar a los servidores de recopilación de datos (DCS). Esta información puede ayudarle a dar formato a sus solicitudes de DCS y a comprender los parámetros devueltos por este sistema.
