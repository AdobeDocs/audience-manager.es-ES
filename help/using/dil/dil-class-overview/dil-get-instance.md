---
description: Recupera una instancia de DIL específica del socio.
keywords: api de audience manager;api de aam;api de audience manager;api de aam
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 15%

---

# getDil{#getdil}

Recupera una instancia de DIL específica del socio.

**Firma de función:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parámetros

| Nombre | Tipo | Descripción |
|---|---|---|
| `partner` | Cadena | El nombre del socio que se va a buscar. |
| `containerNSID` | Número entero | El valor predeterminado es `0`. El NSID del contenedor que está buscando. Opcional. |

## Respuesta

Una coincidencia correcta de NSID de socio y contenedor devuelve un valor específico del socio [!UICONTROL DIL] ejemplo. Si no hay coincidencia, la API devuelve (no emite) un error con el mensaje: &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Código de muestra

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
