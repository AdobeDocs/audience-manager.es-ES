---
description: Recupera una instancia DIL específica del socio.
keywords: audience manager api; aam api; audience manager apis; aam apis
seo-description: Recupera una instancia DIL específica del socio.
seo-title: Getdil
solution: Audience Manager
title: Getdil
uuid: 7 b 95 f 9 bf -14 c 0-4 c 74-b 6 b 9-d 6 b 38513 d 487
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Getdil{#getdil}

Recupera una instancia DIL específica del socio.

**Firma de función:**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parámetros

| Nombre | Tipo | Descripción |
|---|---|---|
| `partner` | Cadena | Nombre del socio que buscar. |
| `containerNSID` | Número entero | Los valores predeterminados `0`son. El NSID del contenedor que está buscando. Opcional. |

## Respuesta

Una coincidencia exitosa de socio y contenedor NSID devuelve [!UICONTROL DIL] una instancia específica del socio. Si no hay coincidencia, la API devuelve (no devuelve) un error con el mensaje " `The DIL instance with partner <name> and containerNSID <ID> was not found.`",

## Código de muestra

<pre class="java"><code>DIL. getdil ('<i>partner</i>', <i>containernsid</i>); 
DIL. getdil ('<i>partner</i>');</code></pre>
