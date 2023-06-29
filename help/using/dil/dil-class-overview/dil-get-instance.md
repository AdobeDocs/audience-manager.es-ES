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
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 7%

---

# getDil{#getdil}

>[!WARNING]
>
>A partir de julio de 2023, el Adobe ha interrumpido el desarrollo del [!DNL Data Integration Library (DIL)] y el [!DNL DIL] extensión.
><br>
>Los clientes existentes pueden seguir utilizando su [!DNL DIL] implementación. Sin embargo, el Adobe no se desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes que evalúen [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para su estrategia de recopilación de datos a largo plazo.
><br>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos a partir de julio de 2023 deben utilizar [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) en su lugar.

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
