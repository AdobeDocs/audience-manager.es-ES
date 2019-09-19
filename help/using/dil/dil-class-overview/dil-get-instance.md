---
description: Recupera una instancia DIL específica del socio.
keywords: api del administrador de público;aam api;apis del administrador de público;aam apis
seo-description: Recupera una instancia DIL específica del socio.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# getDil{#getdil}

Recupera una instancia DIL específica del socio.

**** Firma de función: `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parámetros

| Nombre | Tipo | Descripción |
|---|---|---|
| `partner` | Cadena | El nombre del socio que se va a buscar. |
| `containerNSID` | Número entero | El valor predeterminado es `0`. El NSID del contenedor que está buscando. Opcional. |

## Respuesta

Una coincidencia NSID de socio y contenedor correcta devuelve una [!UICONTROL DIL] instancia específica del socio. Si no hay coincidencia, la API devuelve (no emite) un error con el mensaje " `The DIL instance with partner <name> and containerNSID <ID> was not found.`"

## Código de muestra

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
