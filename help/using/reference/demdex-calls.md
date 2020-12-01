---
description: Audience Manager y Adobe Experience Platform Identity Service realizan llamadas y reciben datos del dominio demdex.net. Esto puede parecer que el Adobe está trabajando con un dominio de terceros inusual, pero este no es el caso. Esta sección describe los elementos de una llamada demdex.net.
seo-description: Audience Manager y Adobe Experience Platform Identity Service realizan llamadas y reciben datos del dominio demdex.net. Esto puede parecer que el Adobe está trabajando con un dominio de terceros inusual, pero este no es el caso. Esta sección describe los elementos de una llamada demdex.net.
seo-title: Explicación de las llamadas al dominio Demdex
solution: Audience Manager
title: Explicación de las llamadas al dominio Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 15%

---


# Explicación de las llamadas al dominio [!DNL Demdex] {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] y  [!DNL Adobe Experience Platform Identity Service] realizar llamadas y recibir datos del  `demdex.net` dominio. Esto puede parecer que [!DNL Adobe] está trabajando con un dominio de terceros inusual, pero este no es el caso. Esta sección describe los elementos de una llamada `demdex.net`.

| Elemento de llamada | Descripción |
|---|---|
| `demdex.net` | Es un dominio heredado controlado por [!DNL Adobe]. Refleja el nombre original previo a la adquisición de [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] adquirió [!DNL Demdex] en 2011 y cambió su nombre a [!DNL Audience Manager]. Es difícil cambiar este dominio porque está entrelazado profundamente con [!DNL Audience Manager], el [!DNL Adobe Experience Cloud ID Service] y nuestra base de usuarios instalada. Puede ver otros prefijos adjuntos a llamadas `demdex.net` heredadas (por ejemplo: `dcs.demdex.net`, `fast.demdex.net`, etc.). Independientemente del prefijo, una llamada a `something.demdex.net` es siempre una llamada a [!DNL Adobe] y no a un dominio de terceros desconocido o sospechoso. |
| `dpm` | [!DNL DPM] es una abreviatura de  [!DNL Data Provider Match]. Indica a los sistemas internos [!DNL Adobe] que una llamada desde [!DNL Audience Manager] o [!DNL Adobe Experience Cloud ID Service] está pasando los datos del cliente para la sincronización o para solicitar un ID. Esta es la llamada más común `demdex.net` que verá desde [!DNL Audience Manager] o desde [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] conceptos básicos de llamadas: <ul><li>[!DNL Audience Manager]:: Una  [!DNL DPM] llamada desde  [!DNL Audience Manager] envía datos al  [!DNL Data Collection Servers] y  [!DNL Profile Cache Servers]. Consulte [Componentes de recopilación de datos](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]:: Una  [!DNL DPM] llamada desde  [!DNL Adobe Experience Cloud ID Service] es una solicitud de ID de visitante. Consulte [Cookies y el servicio de identidad de Adobe Experience Platform](https://docs.adobe.com/content/help/es-ES/id-service/using/intro/cookies.html) y [Cómo solicita y establece los ID el servicio de identidad de Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html.</li></ul><br>Nota:  [!DNL Adobe Experience Cloud ID Service] los clientes pueden cambiar el  [!DNL DPM] prefijo en el nombre de dominio. Consulte [audienceManager Server y audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Servicio de identidad de Adobe Experience Platform](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html)
>* [Cookies de Audience Manager](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-am.html)

