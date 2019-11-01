---
description: Cree destinos con estos métodos de API de RESTful.
seo-description: Cree destinos con estos métodos de API de RESTful.
seo-title: Crear destinos
solution: Audience Manager
title: Crear destinos
uuid: 12f04151-ad0e-4cb6-8f3b-b5c427dc2cef
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Crear destinos {#create-destinations}

Cree destinos con estos [!UICONTROL RESTful API] métodos.

<!-- c_create_destinations.xml -->

## Tipos de destino admitidos: Solo URL y cookie

Los `POST` métodos disponibles le permiten crear [!UICONTROL URL] y [!UICONTROL cookie destinations] solo. Actualmente no puede crear [!UICONTROL server-to-server destinations] con estos [!DNL REST API] métodos. Sin embargo, los `GET` métodos de destino relacionados permiten recuperar información sobre [!UICONTROL server-to-server destinations] los elementos creados en la interfaz de usuario.

## Creación de un destino de URL que no sea de serie {#create-nonserial-dest}

Un `POST` método que permite crear un destino que acepta segmentos compuestos por pares de clave-valor únicos (por ejemplo, `gender=male` o `gender=female`).

<!-- r_create_nonserial_destination.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`

### Solicitud de ejemplo

Esta solicitud crea un único destino. Todos los valores de solicitud son obligatorios a menos que se indique lo contrario.

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Respuesta

Se devuelve una solicitud correcta `201 created` y el destino.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4033, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (not serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"ACTIVE", 
   "destinationType":"PUSH", 
   "createTime":1338937116000, 
   "updateTime":1338937116000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":false, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "delimiter":null,
   "mappings":null
} 
```

## Crear un destino de URL serializado {#create-serial-url-dest}

Un `POST` método que permite crear un destino que acepta varios valores asociados a una sola clave (por ejemplo, `color=blue, red, green`).

<!-- r_create_serial_url_destination.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`

### Solicitud de ejemplo

Especifique el valor seguro [!DNL URL] y delimitador para el par clave-valor que se pasa al destino. Todos los valores de solicitud son obligatorios a menos que se indique lo contrario.

```
{ 
   "name":"Sample URL Destination (Serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":true,
   "urlFormatString":"https://www.adobe.com/send?data=%ALIAS%",
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%",
   "delimiter":","
}
```

### Respuesta

Una actualización correcta devuelve el código de respuesta `201 created` y el destino.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4034, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (Serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"active", 
   "destinationType":"PUSH", 
   "createTime":1338937420000, 
   "updateTime":1338937420000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":true, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%", 
   "delimiter":"-", 
   "mappings":null 
}
```

## Crear un destino de cookie: Clave única, sin serializar {#create-cookie-dest-single}

Un `POST` método que permite crear un [!UICONTROL cookie destination] que acepta segmentos compuestos por pares de clave-valor únicos (por ejemplo, `gender=male` o `gender=female`).

<!-- r_cookie_destination_singlekey_noserial.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`

### Solicitud de ejemplo

Todos los valores de solicitud son obligatorios a menos que se indique lo contrario.

```
{ 
   "name":"Cookie Destination Single Key Not Serialized",
   "destinationType":"ADS",
   "adServerTypeID":1,
   "cookieName":"adobe",
   "cnameDomain":"adobe.com",
   "maxSize":"2048",
   "ttl":"0",
   "domainRestrictions":"inclusion",
   "siteIDs":[
      312
   ],
   "formatType":"single_key",
   "singleKey":"key",
   "keySeparator":"=",
   "valueSeparator":",",
   "serializationEnabled":false
}
```

### Respuesta

Una actualización correcta devuelve el código de respuesta `201 created` y el destino.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4035, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Not Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338937984000, 
   "updateTime":1338937984000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"inclusion", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"key", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
      312 
   ], 
   "uparamEnabled":false
} 
```

## Crear un destino de cookie: Clave única, serializada {#create-cookie-dest-single-serial}

Un `POST` método que permite crear un destino que acepta varios valores asociados a una sola clave (por ejemplo, `color=blue, red, green`).

<!-- r_cookie_destination_singlekey_serial.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`

### Solicitud de ejemplo

Todos los valores de solicitud son obligatorios a menos que se indique lo contrario.

```
{ 
   "name":"Cookie Destination Single Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
 
   ], 
   "formatType":"single_key", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### Respuesta

Una actualización correcta devuelve el código de respuesta `201 created` y el destino.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4036, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938329000, 
   "updateTime":1338938329000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false
}
```

## Crear un destino de cookie: Clave múltiple, sin serializar {#create-cookie-dest-multi}

Un `POST` método que permite crear un destino que acepta segmentos que contienen varias claves con diferentes valores (por ejemplo, `gender=male; gender=female; color=blue; color=red`).

<!-- r_create_cookie_multikey_noserial.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`

### Solicitud de ejemplo

Todos los valores de solicitud son obligatorios a menos que se indique lo contrario.

```
{ 
   "name":"Ad Server Multi-Key Not Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
  
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":false 
}
```

### Respuesta

Una actualización correcta devuelve el código de respuesta `201 created` y el destino.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4037, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Not Serialized", 
   "status":1, 
   "destinationType":"ADS", 
   "createTime":1338938666000, 
   "updateTime":1338938666000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
  
   ], 
   "uparamEnabled":false 
}
```

## Crear un destino de cookie: Clave múltiple, serializada {#create-cookie-dest-multi-serial}

Un `POST` método que permite crear un destino que acepta segmentos que contienen varias claves y valores (por ejemplo, `gender=male, female; color=blue, red, green`).

<!-- r_cookie_destination_multikey_serial.xml -->

### Solicitud

`POST https://api.demdex.com/v1/destinations/`

### Solicitud de ejemplo

Todos los valores de solicitud son obligatorios a menos que se indique lo contrario.

```
{ 
   "name":"Cookie Destination Multi-Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains",
   "siteIDs":[ 
 
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### Respuesta

Una actualización correcta devuelve el código de respuesta `201 created` y el destino.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4038, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938872000, 
   "updateTime":1338938872000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false 
}
```

>[!MORELIKETHIS]
>
>* [Destinos](../../../features/destinations/destinations.md)
>* [Serialización de destino](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Pares de clave-valor explicados](../../../reference/key-value-pairs-explained.md)

