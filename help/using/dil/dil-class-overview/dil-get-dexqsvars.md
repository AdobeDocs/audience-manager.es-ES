---
description: Recupera un valor específico de un servidor de publicidad.
seo-description: Recupera un valor específico de un servidor de publicidad.
seo-title: Dexgetqsvars
solution: Audience Manager
title: Dexgetqsvars
uuid: 6 d 21 c 7 a 4-43 f 8-456 b -8831-47343 dbb 047 e
translation-type: tm+mt
source-git-commit: 128368669163097e604f6b23ab538341adcf8d7a

---


# dexGetQSVars{#dexgetqsvars}

Recupera un valor específico de un servidor de publicidad.

**Firma de función:**`dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parámetros**

| Nombre | Tipo | Descripción |
|---|---|---|
| `variableName` | Cadena | El nombre de la variable para la que desea obtener un valor. |
| `partner` | Cadena | Nombre del socio que buscar. |
| `containerNSID` | Número entero | [!DNL NSID] El contenedor que está buscando. Defaults is `0`. |

**Respuesta**

Returns the variable value for a [!UICONTROL DIL] instance.

**Código de ejemplo**

<pre class="java"><code>var value = DIL. dexgetqsvars ('<i>variablename</i>','<i>partnername</i>',<i>containernsid</i>);</code>
</pre>
