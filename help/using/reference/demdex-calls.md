---
description: El Audience Manager de y el servicio de Adobe Experience Platform ID realizan llamadas a y reciben datos del dominio demdex.net. Esto puede parecer que el Adobe funciona con un dominio de terceros inusual, pero no es el caso. Esta sección describe los elementos de una llamada a demdex.net.
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: Explicación de las llamadas al dominio Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 4%

---

# Explicación de las llamadas al dominio [!DNL Demdex] {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] y [!DNL Adobe Experience Platform Identity Service] realizan llamadas a y reciben datos del dominio `demdex.net`. Puede parecer que [!DNL Adobe] está trabajando con un dominio de terceros inusual, pero no es el caso. Esta sección describe los elementos de una llamada a `demdex.net`.

| Elemento de llamada | Descripción |
|---|---|
| `demdex.net` | Este es un dominio heredado controlado por [!DNL Adobe]. Refleja el nombre original anterior a la adquisición de [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] adquirió [!DNL Demdex] en 2011 y cambió su nombre a [!DNL Audience Manager]. Es difícil cambiar este dominio porque está entrelazado profundamente con [!DNL Audience Manager], [!DNL Adobe Experience Cloud ID Service] y nuestra base de usuarios instalada. Puede ver otros prefijos adjuntos a llamadas heredadas de `demdex.net` (por ejemplo, `dcs.demdex.net`, `fast.demdex.net`, etc.). Independientemente del prefijo, una llamada a `something.demdex.net` es siempre una llamada a [!DNL Adobe] y no a algún dominio de terceros desconocido o sospechoso. |
| `dpm` | [!DNL DPM] es una abreviatura de [!DNL Data Provider Match]. Indica a los sistemas internos de [!DNL Adobe] que una llamada de [!DNL Audience Manager] o [!DNL Adobe Experience Cloud ID Service] está pasando datos del cliente para su sincronización o para solicitar un identificador. Esta es la llamada `demdex.net` más común que verá de [!DNL Audience Manager] o de [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] conceptos básicos de llamada: <ul><li>[!DNL Audience Manager]: una llamada de [!DNL DPM] desde [!DNL Audience Manager] envía datos a [!DNL Data Collection Servers] y a [!DNL Profile Cache Servers]. Consulte [Componentes de recopilación de datos](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: una llamada de [!DNL DPM] desde [!DNL Adobe Experience Cloud ID Service] es una solicitud de ID de visitante. Consulte [Cookies y el servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=es) y [Solicitud y configuración de ID con el servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html?lang=es).</li></ul><br>Nota: [!DNL Adobe Experience Cloud ID Service] clientes pueden cambiar el prefijo [!DNL DPM] del nombre de dominio. Consulte [audienceManager Server y audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html?lang=es). |

>[!MORELIKETHIS]
>
>* [Servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es)
>* [Cookies de Audience Manager](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html?lang=es)
