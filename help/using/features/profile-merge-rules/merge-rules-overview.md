---
description: Con las reglas de combinación de Perfiles, obtiene el control sobre los conjuntos de datos utilizados para la segmentación y puede realizar el destinatario de una persona con precisión en varios dispositivos.
seo-description: Con las reglas de combinación de Perfiles, obtiene el control sobre los conjuntos de datos utilizados para la segmentación y puede realizar el destinatario de una persona con precisión en varios dispositivos.
seo-title: Información general sobre las reglas de combinación de Perfiles
solution: Audience Manager
title: Información general sobre las reglas de combinación de Perfiles
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 2%

---


# Información general sobre las reglas de combinación de Perfiles {#profile-merge-rules-overview}

Con [!UICONTROL Profile Merge Rules] puede controlar qué conjuntos de datos se utilizan para la segmentación y puede realizar un destinatario preciso de los usuarios en varios dispositivos.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Recopilación y segmentación de datos con perfiles anónimos y autenticados {#data-collection-targeting}

Generalmente, la segmentación y la segmentación de audiencias dependen de los datos recopilados de todos los usuarios en un dispositivo. La recopilación de datos y la determinación de objetivos en función de los datos a nivel de dispositivo tienen algunas desventajas. Por ejemplo, no puede distinguir entre varios usuarios que comparten un dispositivo o que destinatario con precisión a usuarios en varios dispositivos. La recopilación de datos centrada en el dispositivo ya no es suficiente para las campañas de marketing digital o la segmentación entre dispositivos.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] cambia fundamentalmente la forma en que [!DNL Audience Manager] recopila datos y segmenta a los usuarios para la segmentación. Le permite trabajar con dos tipos distintos de perfiles, un perfil de dispositivo y un perfil [](../../reference/visitor-authentication-states.md)autenticado.

<table id="table_CE98C0E32A964B27804736A896233869"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de Perfil </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Device perfil </td> 
   <td colname="col2"> <p>Un perfil de dispositivo está vinculado a un ID de un dispositivo determinado, como un ID de cookie o un ID de dispositivo móvil. Incluye: </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">Características basadas en reglas realizadas cuando un usuario no está autenticado. </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">Características integradas vinculadas a un ID de dispositivo, como datos de terceros basados en cookies. </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> perfil autenticado </td> 
   <td colname="col2"> <p>El perfil autenticado está vinculado a un ID de usuario que se pasa cuando una persona inicia sesión en el sitio. Incluye </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">Características basadas en reglas recopiladas en distintos dispositivos cuando se autentica a un usuario. </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">Características integradas en un archivo sin conexión vinculado al mismo ID de usuario. </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

Estos diferentes perfiles controlan los datos que puede utilizar para la segmentación. Por ejemplo, con un perfil [](../../reference/visitor-authentication-states.md)autenticado, puede crear segmentos precisos basados en datos de varios dispositivos para un solo usuario. Esto significa que puede ofrecer una experiencia de marca uniforme a los clientes en varios dispositivos. [!DNL Audience Manager] lo logra almacenando la asignación de los diferentes dispositivos que una persona utiliza para sus actividades en línea a su perfil [](../../reference/visitor-authentication-states.md)autenticado. Estas asignaciones se denominan [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Ventajas {#advantages}

Con [!UICONTROL Profile Merge Rules] usted puede:

* Destinatario usuarios en función de perfiles [](../../reference/visitor-authentication-states.md)autenticados, perfiles anónimos o combinaciones de ambos.
* Destinatario a un cliente específico en sus dispositivos.
* Cree un gráfico de dispositivos basado en datos determinísticos.
* Ajuste los datos de los segmentos en función de diferentes perfiles.
* Obtenga información adicional sobre su audiencia.
