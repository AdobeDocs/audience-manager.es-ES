---
description: Conceptos, descripciones y definiciones para código, métodos y procesos de API DCS.
seo-description: Conceptos, descripciones y definiciones de código, métodos y procesos de API DCS en Adobe Audience Manager (AAM).
seo-title: Descripción general de referencia de API de DCS en Adobe Audience Manager (AAM)
title: Descripción general de referencia de API de DCS
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Descripción general de referencia de API de DCS

Conceptos, descripciones y definiciones para código, métodos y procesos de API DCS.

* [Métodos de API de DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Envíe datos a la API de DCS utilizando métodos GET o POST.

* [Códigos de error DCS, mensajes y ejemplos](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Códigos y mensajes de error generados por los servidores de recopilación de datos (DCS) enumerados en orden numérico por ID de código.

* [Control de ID y lista negra](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-blacklisting.md)

   El DCS supervisa los ID que recibe y detalla los que se envían a una tasa inusualmente alta en un corto período de tiempo.

* [ID de región de DCS, ubicaciones y nombres de host](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   Se requiere el nombre de host de servidor DCS regional para realizar llamadas al DCS. Esto se debe a que el DCS almacena información en centros de datos que están geográficamente cerca de los visitantes del sitio. Las consultas funcionarán si se envían al DCS incorrecto, pero estas llamadas son ineficientes y pueden retrasar la respuesta. Para realizar una solicitud de DCS, haga coincidir el ID de región con su nombre de host regional correspondiente y forme la consulta con el nombre de host adecuado.

* [Formato de pares clave-valor en llamadas DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Al realizar una llamada, el DCS acepta datos de valor clave en formato estándar o serializado. Consulte esta sección para obtener información sobre cómo dar formato a los datos de valor clave estándar y serializados.

* [Condiciones de carrera y administración de errores](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Describe cómo evitar las condiciones de carrera y la gestión de errores de DCS.

* [Atributos admitidos para llamadas de API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Enumera y describe la sintaxis y los atributos admitidos (o pares de valor clave) que puede pasar a los servidores de recopilación de datos (DCS). Esta información le ayudará a dar formato a las solicitudes de DCS y a comprender los parámetros que devuelve este sistema.
