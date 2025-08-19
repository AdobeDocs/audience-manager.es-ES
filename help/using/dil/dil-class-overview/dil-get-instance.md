---
description: Recupera un instancia DIL específico de socio.
keywords: API del administrador de audiencia; API de AAM; API del administrador de audiencia; API de AAM
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 6%

---

# getDil{#getdil}

>[!WARNING]
>
>A partir de julio de 2023, Adobe Systems ha interrumpido el desarrollo de la [!DNL Data Integration Library (DIL)] y la [!DNL DIL] extensión.
>
>Los clientes existentes pueden seguir usando sus [!DNL DIL] implementación. Sin embargo, Adobe Systems no se desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes que evalúen [Experience Platform SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) web según su estrategia de recopilación de datos a largo plazo.
>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos después de julio de 2023 deberían usar [Experience Platform SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) web.

Recupera un instancia DIL específico de socio.

**Firma de función:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parámetros

| Nombre | Tipo | Descripción |
|---|---|---|
| `partner` | Cadena | Nombre socio al que búsqueda. |
| `containerNSID` | Número entero | El valor predeterminado es `0`. El NSID del contenedor está buscando. Opcional. |

## Respuesta

Una coincidencia de NSID socio y contenedor correcta devuelve un instancia específico [!UICONTROL DIL] del socio. Si no hay coincidencias, la API devuelve (no arroja) un error con el mensaje &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Código de muestra

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
