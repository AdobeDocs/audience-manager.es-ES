---
description: Recupera una instancia DIL específica del socio.
keywords: audience manager api; aam api; audience manager apis; aam apis
seo-description: Recupera una instancia DIL específica del socio.
seo-title: Getdil
solution: Audience Manager
title: Getdil
uuid: 7 b 95 f 9 bf -14 c 0-4 c 74-b 6 b 9-d 6 b 38513 d 487
translation-type: tm+mt
source-git-commit: 128368669163097e604f6b23ab538341adcf8d7a

---


# getDil{#getdil}

Recupera una instancia DIL específica del socio.

**Firma de función:**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parámetros

| Nombre | Tipo | Descripción |
|---|---|---|
| `partner` | Cadena | Nombre del socio que buscar. |
| `containerNSID` | Número entero | Defaults is `0`. El NSID del contenedor que está buscando. Opcional. |

## Respuesta

A successful partner and container NSID match returns a partner-specific [!UICONTROL DIL] instance. If there is no match, the API returns (does not throw) an error with the message, &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Código de muestra

<pre class="java"><code>DIL. getdil ('<i>partner</i>', <i>containernsid</i>); 
DIL. getdil ('<i>partner</i>');</code>
</pre>
