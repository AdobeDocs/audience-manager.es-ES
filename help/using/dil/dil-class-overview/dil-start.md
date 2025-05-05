---
description: Describe los requisitos de autenticación y el formato de texto utilizado en la documentación del DIL de nivel de clase.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Introducción a las API de DIL de nivel de clase
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---

# Introducción a las API de DIL de nivel de clase{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>A partir de julio de 2023, el Adobe ha interrumpido el desarrollo de la extensión [!DNL Data Integration Library (DIL)] y [!DNL DIL].
>
>Los clientes existentes pueden seguir usando su implementación de [!DNL DIL]. Sin embargo, el Adobe no se desarrollará [!DNL DIL] más allá de este punto. Se recomienda a los clientes que evalúen [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) para su estrategia de recopilación de datos a largo plazo.
>
>Los clientes que deseen implementar nuevas integraciones de recopilación de datos a partir de julio de 2023 deben utilizar [SDK web de Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=es) en su lugar.

Las API de DIL de nivel de clase permiten crear y trabajar mediante programación con objetos de Audience Manager. Las API de nivel de clase funcionan con las otras funciones de nivel de instancia para establecer valores o devolver datos.

## Introducción a las API de DIL de nivel de clase {#get-started}

Describe los requisitos de autenticación y el formato de texto utilizado en la documentación de nivel de clase [!UICONTROL DIL].

<!-- 

c_class_start.xml

 -->

Al trabajar con las API [!UICONTROL DIL] de nivel de clase:

* Access requiere un nombre de socio y un identificador de área de nombres de contenedor (NSID). Póngase en contacto con el administrador de cuentas de Audience Manager para obtener esta información.
* Reemplace cualquier texto de *cursiva* de muestra en la documentación de la API por un valor, ID u otra variable según lo requiera el método con el que esté trabajando.
* [!UICONTROL DIL] escribe datos codificados en una cookie de destino. Por ejemplo, los espacios se codifican como `%20` y los puntos y comas como `%3B`.
