---
description: Recupera un valor específico de un servidor de anuncios.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 7%

---

# dexGetQSVars{#dexgetqsvars}

>[!WARNING]
>
>A partir de julio de 2023, Adobe Systems ha interrumpido el desarrollo de la [!DNL Data Integration Library (DIL)] y la [!DNL DIL] extensión.
>
>Los clientes existentes pueden seguir usando sus [!DNL DIL] implementación. Sin embargo, Adobe Systems no se desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes que evalúen [Experience Platform SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) web según su estrategia de recopilación de datos a largo plazo.
>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos después de julio de 2023 deberían usar [Experience Platform SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) web.

Recupera un valor específico de un servidor de anuncios.

**Firma de función:** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parámetros**

| Nombre | Tipo | Descripción |
|---|---|---|
| `variableName` | Cadena | Nombre de la variable para la que quiere obtener un valor. |
| `partner` | Cadena | Nombre socio al que búsqueda. |
| `containerNSID` | Número entero | El [!DNL NSID] de la contenedor que estás buscando. El valor predeterminado es `0`. |

**Respuesta**

Devuelve el valor variable de un [!UICONTROL DIL] instancia.

**Código de ejemplo**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
