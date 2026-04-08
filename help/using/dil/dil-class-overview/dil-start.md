---
description: Describe los requisitos de autenticación y el formato de texto utilizado en la documentación de DIL de nivel de clase.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Introducción a las API de DIL de nivel de clase
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
TQID: https://experienceleague.adobe.com/RlkKHc2IuInFWfWOnTKS94XhBmbDbQYjtQZI40DsU-8
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
source-wordcount: 203
ht-degree: 0%

---

# Introducción a las API de DIL de nivel de clase{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>Desde julio de 2023, Adobe ha interrumpido el desarrollo de la extensión [!DNL Data Integration Library (DIL)] y [!DNL DIL].
>
>Los clientes existentes pueden seguir usando su implementación de [!DNL DIL]. Sin embargo, Adobe no desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes evaluar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) para su estrategia de recopilación de datos a largo plazo.
>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos a partir de julio de 2023 deben utilizar [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) en su lugar.

Las API de DIL de nivel de clase le permiten crear y trabajar con objetos Audience Manager mediante programación. Las API de nivel de clase funcionan con las otras funciones de nivel de instancia para establecer valores o devolver datos.

## Introducción a las API de DIL de nivel de clase {#get-started}

Describe los requisitos de autenticación y el formato de texto utilizado en la documentación de nivel de clase [!UICONTROL DIL].

<!-- 

c_class_start.xml

 -->

Al trabajar con las API [!UICONTROL DIL] de nivel de clase:

* Access requiere un nombre de socio y un identificador de área de nombres de contenedor (NSID). Póngase en contacto con el administrador de cuentas de Audience Manager para obtener esta información.
* Reemplace cualquier texto de *cursiva* de muestra en la documentación de la API por un valor, ID u otra variable según lo requiera el método con el que esté trabajando.
* [!UICONTROL DIL] escribe datos codificados en una cookie de destino. Por ejemplo, los espacios se codifican como `%20` y los puntos y comas como `%3B`.
