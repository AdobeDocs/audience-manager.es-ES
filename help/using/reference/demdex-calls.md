---
description: Audience Manager y el servicio de identidad de Adobe Experience Platform realizan llamadas al dominio demdex.net y reciben datos de él. Esto puede parecer que Adobe está trabajando con un dominio de terceros inusual, pero este no es el caso. En esta sección se describen los elementos de una llamada a demdex.net.
seo-description: Audience Manager y el servicio de identidad de Adobe Experience Platform realizan llamadas al dominio demdex.net y reciben datos de él. Esto puede parecer que Adobe está trabajando con un dominio de terceros inusual, pero este no es el caso. En esta sección se describen los elementos de una llamada a demdex.net.
seo-title: Explicación de las llamadas al dominio Demdex
solution: Audience Manager
title: Explicación de las llamadas al dominio Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: 'Referencia '
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 15%

---

# Explicación de las llamadas al dominio [!DNL Demdex] {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] y  [!DNL Adobe Experience Platform Identity Service] realizan llamadas a y reciben datos del  `demdex.net` dominio. Esto puede parecer que [!DNL Adobe] está trabajando con un dominio de terceros inusual, pero este no es el caso. Esta sección describe los elementos de una llamada `demdex.net` .

| Elemento de llamada | Descripción |
|---|---|
| `demdex.net` | Este es un dominio heredado controlado por [!DNL Adobe]. Refleja el nombre original previo a la adquisición de [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe] adquirió [!DNL Demdex] en 2011 y cambió su nombre a [!DNL Audience Manager]. Es difícil cambiar este dominio porque está entrelazado profundamente con [!DNL Audience Manager], [!DNL Adobe Experience Cloud ID Service] y nuestra base de usuarios instalada. Puede ver otros prefijos adjuntos a llamadas `demdex.net` heredadas (por ejemplo, `dcs.demdex.net`, `fast.demdex.net`, etc.). Independientemente del prefijo, una llamada a `something.demdex.net` siempre es una llamada a [!DNL Adobe] y no a un dominio de terceros desconocido o sospechoso. |
| `dpm` | [!DNL DPM] es una abreviatura de  [!DNL Data Provider Match]. Indica a los sistemas internos [!DNL Adobe] que una llamada desde [!DNL Audience Manager] o [!DNL Adobe Experience Cloud ID Service] está pasando los datos del cliente para su sincronización o para solicitar un ID. Esta es la llamada `demdex.net` más común que verá desde [!DNL Audience Manager] o desde [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] conceptos básicos de llamadas: <ul><li>[!DNL Audience Manager]: Una  [!DNL DPM] llamada de  [!DNL Audience Manager] envía datos a  [!DNL Data Collection Servers] y  [!DNL Profile Cache Servers]. Consulte [Componentes de recopilación de datos](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Una  [!DNL DPM] llamada desde  [!DNL Adobe Experience Cloud ID Service] es una solicitud de ID de visitante. Consulte [Cookies y el servicio de identidad de Adobe Experience Platform](https://docs.adobe.com/content/help/es-ES/id-service/using/intro/cookies.html) y [Solicitud y configuración de ID con el servicio de identidad de Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html).</li></ul><br>Nota:  [!DNL Adobe Experience Cloud ID Service] los clientes pueden cambiar el  [!DNL DPM] prefijo en el nombre de dominio. Consulte [audienceManager Server y audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Servicio de identidad de Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Cookies de Audience Manager](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-am.html)

