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
TQID: https://experienceleague.adobe.com/C4wUrtnwE8WXsgDzXSTJQ1qUf-aB-RNWoBDbDFCNeZ8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2:
  - id: d7e573ad-4eda-46ec-90c4-239e75362af9
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 143
ht-degree: 6%

---

# getDil{#getdil}

>[!WARNING]
>
>Desde julio de 2023, Adobe ha interrumpido el desarrollo de la extensión [!DNL Data Integration Library (DIL)] y [!DNL DIL].
>
>Los clientes existentes pueden seguir usando su implementación de [!DNL DIL]. Sin embargo, Adobe no desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes evaluar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) para su estrategia de recopilación de datos a largo plazo.
>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos a partir de julio de 2023 deben utilizar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) en su lugar.

Recupera una instancia de DIL específica del socio.

**Firma de función:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parámetros

| Nombre | Tipo | Descripción |
|---|---|---|
| `partner` | Cadena | El nombre del socio que se va a buscar. |
| `containerNSID` | Número entero | El valor predeterminado es `0`. El NSID del contenedor que está buscando. Opcional. |

## Respuesta

Una coincidencia correcta de NSID de contenedor y socio devuelve una instancia [!UICONTROL DIL] específica de un socio. Si no hay ninguna coincidencia, la API devuelve (no emite) un error con el mensaje &quot;`The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Código de muestra

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
