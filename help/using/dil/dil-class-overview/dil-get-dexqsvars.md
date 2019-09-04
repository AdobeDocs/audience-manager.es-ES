---
description: Recupera un valor específico de un servidor de publicidad.
seo-description: Recupera un valor específico de un servidor de publicidad.
seo-title: Dexgetqsvars
solution: Audience Manager
title: Dexgetqsvars
uuid: 6 d 21 c 7 a 4-43 f 8-456 b -8831-47343 dbb 047 e
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Dexgetqsvars{#dexgetqsvars}

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
| `containerNSID` | Número entero | [!DNL NSID] El contenedor que está buscando. Los valores predeterminados `0`son. |

**Respuesta**

Devuelve el valor de variable de una [!UICONTROL DIL] instancia.

**Código de ejemplo**

<pre class="java"><code>var value = DIL. dexgetqsvars ('<i>variablename</i>','<i>partnername</i>',<i>containernsid</i>);</code></pre>
