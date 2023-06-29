---
description: Recupera un valor específico de un servidor de publicidad.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 8%

---

# dexGetQSVars{#dexgetqsvars}

>[!WARNING]
>
>A partir de julio de 2023, el Adobe ha interrumpido el desarrollo del [!DNL Data Integration Library (DIL)] y el [!DNL DIL] extensión.
><br>
>Los clientes existentes pueden seguir utilizando su [!DNL DIL] implementación. Sin embargo, el Adobe no se desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes que evalúen [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para su estrategia de recopilación de datos a largo plazo.
><br>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos a partir de julio de 2023 deben utilizar [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) en su lugar.

Recupera un valor específico de un servidor de publicidad.

**Firma de función:** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

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

Devuelve el valor de la variable para un [!UICONTROL DIL] ejemplo.

**Código de ejemplo**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
