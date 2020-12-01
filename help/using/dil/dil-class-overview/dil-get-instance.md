---
description: Recupera una instancia de DIL específica del socio.
keywords: audience manager api;aam api;audience manager apis;aam apis
seo-description: Recupera una instancia de DIL específica del socio.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 17%

---


# getDil{#getdil}

Recupera una instancia de DIL específica del socio.

**Firma de función:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parámetros

| Nombre | Tipo | Descripción |
|---|---|---|
| `partner` | Cadena | El nombre del socio que se va a buscar. |
| `containerNSID` | Número entero | El valor predeterminado es `0`. El NSID del contenedor que estás buscando. Opcional. |

## Respuesta

Una coincidencia de socio y contenedor con NSID devuelve una instancia específica de socio [!UICONTROL DIL]. Si no hay coincidencia, la API devuelve (no emite) un error con el mensaje &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Código de muestra

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
