---
description: Métodos de administración de dominios que permiten crear y administrar los dominios a los que desea enviar datos (solo para destinos de cookies).
seo-description: Métodos de administración de dominios que permiten crear y administrar los dominios a los que desea enviar datos (solo para destinos de cookies).
seo-title: Métodos API de administración de dominios
solution: Audience Manager
title: Métodos API de administración de dominios
uuid: f 2 f 08 bc 5-ea 42-4171-9 a 43-0 b 20976 f 0 cb 0
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Domain Management API Methods {#domain-management-api-methods}

Métodos de administración de dominios que permiten crear y administrar los dominios a los que desea enviar datos (solo para destinos de cookies).

<!-- c_partner_site.xml -->

## Create a New Domain {#create-new-domain}

`POST` Método que permite crear un nuevo dominio para (solo destinos de cookies).

<!-- r_post_new_partner_site.xml -->

### Solicitud

`POST` `https://api.demdex.com/v1/partner-sites/`

### Solicitud de ejemplo

```
{
   "url":"example1.com"
}
```

### Respuesta

A successful response returns `201 created` and the partner site, including its unique ID.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Delete a Domain {#delete-domain}

`DELETE` Método que permite eliminar un dominio (solo para destinos de cookies).

<!-- r_delete_partner_site.xml -->

### Solicitud

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Respuesta

A successful response returns `204 no content`. Returns `404 not found` if the partner site cannot be found.

## Return Properties for a Domain {#return-props-domain}

`GET` Método que devuelve detalles sobre el dominio especificado (solo para destinos de cookies).

<!-- r_get_partner_site.xml -->

### Solicitud

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Respuesta

A successful response returns `200 OK` and data as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Return Properties for all Domains {#return-props-all-domains}

`GET` Método que devuelve información sobre todos los dominios (solo para destinos de cookies).

<!-- r_get_partner_sites.xml -->

### Solicitud

`GET https://api.demdex.com/v1/partner-sites/`

### Parámetros de consulta opcionales

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API]. See [Optional Parameters](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parámetro </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td> 
   <td colname="col2"> Devuelve resultados por número de página. La numeración comienza en 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> Pagesize</code> </td> 
   <td colname="col2"> Define el número de resultados de respuesta devueltos por la solicitud (10 es predeterminado). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> Sortby</code> </td> 
   <td colname="col2"> Ordena y devuelve resultados según la propiedad JSON especificada. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descendente</code> </td>
   <td colname="col2"> Ordena y devuelve resultados en orden descendente. Ascendente es predeterminado. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> buscar</code> </td>
   <td colname="col2">Devuelve resultados basados en la cadena especificada que se desea utilizar como parámetro de búsqueda. Por ejemplo, supongamos que desea encontrar resultados para todos los modelos que tengan la palabra "Test" en cualquiera de los campos de valor de dicho elemento. Su solicitud de ejemplo podría verse así: <p><code> ' GET '' https://api.demdex.com/v1/models/?search=Test '</code>. </p> <p>Puede buscar cualquier valor devuelto por el método "get all". </p> </td>
  </tr> 
 </tbody> 
</table>

### Respuesta

A successful response returns `200 OK` and data in an array as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

```
[
    {
        "pid": 1111,
        "siteId": 111,
        "url": "example1.com"
    },
    {
        "pid": 2222,
        "siteId": 222,
        "url": "example2.com"
    },
    {
        "pid": 3333,
        "siteId": 333,
        "url": "example3.com"
    }
]
```
