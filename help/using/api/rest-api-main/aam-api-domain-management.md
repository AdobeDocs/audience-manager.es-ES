---
description: Métodos de administración de dominios que le permiten crear y administrar los dominios a los que desea enviar datos (solo para destinos de cookies).
seo-description: Métodos de administración de dominios que le permiten crear y administrar los dominios a los que desea enviar datos (solo para destinos de cookies).
seo-title: Métodos de API de administración de dominios
solution: Audience Manager
title: Métodos de API de administración de dominios
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
exl-id: f9907f6e-d553-4771-945b-2fddb3c9ce2f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 6%

---

# Métodos de API de administración de dominios {#domain-management-api-methods}

Métodos de administración de dominios que le permiten crear y administrar los dominios a los que desea enviar datos (solo para destinos de cookies).

<!-- c_partner_site.xml -->

## Crear un nuevo dominio {#create-new-domain}

Un método `POST` que le permite crear un nuevo dominio para (solo destinos de cookie).

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

Una respuesta correcta devuelve `201 created` y el sitio del socio, incluido su ID único.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Eliminar un dominio {#delete-domain}

Un método `DELETE` que permite eliminar un dominio (solo para destinos de cookies).

<!-- r_delete_partner_site.xml -->

### Solicitud

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Respuesta

Una respuesta correcta devuelve `204 no content`. Devuelve `404 not found` si no se encuentra el sitio del socio.

## Devolver propiedades de un dominio {#return-props-domain}

Un método `GET` que devuelve detalles sobre el dominio especificado (solo para destinos de cookies).

<!-- r_get_partner_site.xml -->

### Solicitud

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Respuesta

Una respuesta correcta devuelve `200 OK` y datos como se muestra en el ejemplo siguiente. Devuelve `404 Not found` si no se encuentra el ID del sitio o el socio.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Devolver propiedades para todos los dominios {#return-props-all-domains}

Un método `GET` que devuelve información sobre todos los dominios (solo para destinos de cookies).

<!-- r_get_partner_sites.xml -->

### Solicitud

`GET https://api.demdex.com/v1/partner-sites/`

### Parámetros de consulta opcionales

Puede utilizar estos parámetros opcionales con métodos [!DNL API] que devuelven *todas* propiedades para un objeto. Establezca estas opciones en la cadena de solicitud al pasar esa consulta a [!DNL API]. Consulte [Parámetros opcionales](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2"> Devuelve los resultados por número de página. La numeración comienza en 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> Define el número de resultados de respuesta que devuelve la solicitud (10 es el valor predeterminado). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> Ordena y devuelve resultados según la propiedad JSON especificada. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Ordena y devuelve los resultados en orden descendente. Ascending es el valor predeterminado. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Devuelve los resultados en función de la cadena especificada que desee utilizar como parámetro de búsqueda. Por ejemplo, supongamos que desea encontrar resultados para todos los modelos que tienen la palabra "Prueba" en cualquiera de los campos de valor para ese elemento. Su solicitud de ejemplo podría tener este aspecto: <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>. </p> <p>Puede buscar cualquier valor devuelto mediante un método "get all". </p> </td>
  </tr> 
 </tbody> 
</table>

### Respuesta

Una respuesta correcta devuelve `200 OK` y datos en una matriz como se muestra en el ejemplo siguiente. Devuelve `404 Not found` si no se encuentra el ID del sitio o el socio.

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
