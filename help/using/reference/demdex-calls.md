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
source-wordcount: '308'
ht-degree: 8%

---

# Explicación de las llamadas a [!DNL Demdex] Dominio {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] y el [!DNL Adobe Experience Platform Identity Service] realizar llamadas a y recibir datos de `demdex.net` dominio. Esto puede parecer como [!DNL Adobe] está trabajando con un dominio de terceros inusual, pero este no es el caso. En esta sección se describen los elementos de un `demdex.net` llamada.

| Elemento de llamada | Descripción |
|---|---|
| `demdex.net` | Este es un dominio heredado controlado por [!DNL Adobe]. Refleja el nombre original de previo a la adquisición de [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] adquirió [!DNL Demdex] en 2011 y cambió su nombre a [!DNL Audience Manager]. Es difícil cambiar este dominio porque está profundamente entrelazado con [!DNL Audience Manager], el [!DNL Adobe Experience Cloud ID Service], y nuestra base de usuarios instalada. Puede ver otros prefijos adjuntos a legacy `demdex.net` llamadas (por ejemplo, `dcs.demdex.net`, `fast.demdex.net`, etc.). Independientemente del prefijo, se llama a `something.demdex.net` siempre es una llamada a [!DNL Adobe] y no a algún dominio de terceros desconocido o sospechoso. |
| `dpm` | [!DNL DPM] es una abreviatura de [!DNL Data Provider Match]. Le dice a la interna, [!DNL Adobe] sistemas desde los que se llama a [!DNL Audience Manager] o el [!DNL Adobe Experience Cloud ID Service] pasa datos de clientes para su sincronización o solicita un ID. Este es el más común `demdex.net` llamada que verá de [!DNL Audience Manager] o el [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] conceptos básicos de llamada: <ul><li>[!DNL Audience Manager]: A [!DNL DPM] llamada desde [!DNL Audience Manager] envía datos a [!DNL Data Collection Servers] y [!DNL Profile Cache Servers]. Consulte [Componentes de recopilación de datos](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: A [!DNL DPM] llamada desde el [!DNL Adobe Experience Cloud ID Service] es una solicitud de ID de visitante. Consulte [Cookies y el servicio de Adobe Experience Platform ID](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) y [Solicitud y configuración de ID con el servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html).</li></ul><br>Nota: [!DNL Adobe Experience Cloud ID Service] Los clientes de pueden cambiar el [!DNL DPM] en el nombre de dominio. Consulte [audienceManager Server y audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html)
>* [Cookies de Audience Manager](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html)

