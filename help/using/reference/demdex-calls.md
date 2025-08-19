---
description: Audience Manager y el servicio de identidad Adobe Experience Platform realizan llamadas y reciben datos del dominio demdex.net. Esto puede parecer gustar Adobe Systems está trabajando con un dominio terceros inusual, pero este no es el caso. En esta sección se describen los elementos de una llamada de demdex.net.
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

# Explicación de las [!DNL Demdex] llamadas al dominio {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] y realizar [!DNL Adobe Experience Platform Identity Service] llamadas y recibir datos del `demdex.net` dominio. Esto puede parecer gustar [!DNL Adobe] está funcionando con un dominio terceros inusual, pero este no es el caso. En esta sección se describen los elementos de una `demdex.net` llamada.

| Elemento de llamada | Descripción |
|---|---|
| `demdex.net` | Este es un dominio heredado controlado por [!DNL Adobe]. Refleja el nombre original anterior a Adquisición de [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] adquirió [!DNL Demdex] en 2011 y cambió su nombre a [!DNL Audience Manager]. Es difícil cambiar este dominio porque está profundamente entrelazado con [!DNL Audience Manager], el [!DNL Adobe Experience Cloud ID Service], y nuestra base de usuario instalada. Es posible que vea otros prefijos asociados a llamadas heredadas `demdex.net` (por ejemplo, `dcs.demdex.net`, `fast.demdex.net`, , etc.). Independientemente del prefijo, una llamada a `something.demdex.net` es siempre una llamada a [!DNL Adobe] y no a algún dominio terceros desconocido o sospechoso. |
| `dpm` | [!DNL DPM] es la abreviatura de [!DNL Data Provider Match]. Indica a los sistemas internos [!DNL Adobe] que una llamada de o el está pasando en datos de [!DNL Audience Manager] clientes para sincronizarlos [!DNL Adobe Experience Cloud ID Service] o solicitarlos ID. Esta es la llamada más común `demdex.net` que verá desde [!DNL Audience Manager] o el [!DNL Adobe Experience Cloud ID Service]archivo . <br><br>[!DNL DPM] Conceptos básicos de llamada: <ul><li>[!DNL Audience Manager]: Una [!DNL DPM] llamada desde [!DNL Audience Manager] envía datos al [!DNL Data Collection Servers] y [!DNL Profile Cache Servers]. Consulte [Componentes de recopilación de datos](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Una [!DNL DPM] llamada desde es [!DNL Adobe Experience Cloud ID Service] una solicitud para un ID de visitante. Consulte [Cookies y el servicio](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) de identidad de Adobe Experience Platform y [Cómo solicita y establece los ID](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html) el servicio de identidad de Adobe Experience Platform.</li></ul><br>Nota: [!DNL Adobe Experience Cloud ID Service] Los clientes pueden cambiar el prefijo del [!DNL DPM] nombre de dominio. Consulte [audienceManager Server y audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Servicio de identidad de Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html)
>* [Audience Manager Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html)
