---
description: Recupera un valor específico de un servidor de publicidad.
seo-description: Recupera un valor específico de un servidor de publicidad.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# dexGetQSVars{#dexgetqsvars}

Recupera un valor específico de un servidor de publicidad.

**** Firma de función: `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parámetros**

| Nombre | Tipo | Descripción |
|---|---|---|
| `variableName` | Cadena | Nombre de la variable para la que desea obtener un valor. |
| `partner` | Cadena | El nombre del socio que se va a buscar. |
| `containerNSID` | Número entero | El [!DNL NSID] del contenedor que está buscando. El valor predeterminado es `0`. |

**Respuesta**

Devuelve el valor de variable de una [!UICONTROL DIL] instancia.

**Código de ejemplo**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
