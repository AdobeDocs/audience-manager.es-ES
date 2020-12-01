---
description: Este artículo describe los prefijos que debe adjuntar a las variables clave al crear reglas de características.
seo-description: Este artículo describe los prefijos que debe adjuntar a las variables clave al crear reglas de características.
seo-title: Requisitos de prefijo para variables clave
solution: Audience Manager
title: Requisitos de prefijo para variables clave
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
translation-type: tm+mt
source-git-commit: 1c0d40082cd0753a9b4326aae764eb74aefb8be4
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 5%

---


# Requisitos de prefijo para variables clave {#prefix-requirements-for-key-variables}

Este artículo describe los prefijos que debe adjuntar a las variables clave al crear reglas de características.

<!-- r_tb_variable_prefixes.xml -->

## Propósito de los prefijos de variables clave

Al crear reglas [!UICONTROL Trait Builder], es importante anteponer la variable clave con un prefijo recomendado. Estos prefijos identifican el tipo de datos pasados y ayudan a evitar conflictos de Área de nombres dentro de [!DNL Audience Manager]. Generalmente, puede asignar a una variable cualquier nombre, pero los datos de una regla no se procesarán si el nombre de la variable clave no coincide con el nombre de la variable en una llamada de evento.

## Prefijos para variables clave

La siguiente tabla define los prefijos comunes utilizados por [!UICONTROL Trait Builder].

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prefijo de variable clave </th> 
   <th colname="col2" class="entry"> Identifica la variable </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>Como específico del cliente. Son datos clave que se envían desde sus propias propiedades. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>En el nivel <span class="keyword"> Audience Manager</span>. Estos datos son uniformes en el ecosistema <span class="keyword"> Audience Manager</span>. Consulte <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Atributos admitidos para llamadas de API de DCS</a> para obtener una lista más completa.</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Contiene <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> información sobre el encabezado HTTP</a>. Incluye parámetros de encabezado como <code> referer</code>,<code> IP</code>, <code> accept-language</code>, etc. </p> <p> <p>Nota: Para los clientes que utilizan versiones de DIL anteriores a la 9.0, la recopilación de datos mediante la señal <code> h_referer</code> no funcionará en los exploradores Safari. Con la introducción de <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, los navegadores Safari pueden clasificar el dominio demdex.net como rastreador y truncarán el remitente del reenvío en la solicitud de recopilación de datos para que solo contenga el origen en lugar de la dirección URL completa. Consulte <a href="../../dil/dil-overview.md#get-implement-dil-code">Obtención e implementación del código de DIL</a> para obtener la versión más reciente del DIL.<p>Las señales que utilizan este prefijo no aparecen en <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Búsqueda de señales</a>.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Nuestros <span class="wintitle"> Servidores de recopilación de datos</span> permiten pasar parámetros privados. Básicamente, cualquier parámetro que tenga inicios con <code> p_</code> se utilizará para la evaluación de características, pero no se registrará en el flujo descendente ni se almacenará. </p> <p>Ejemplo: dado <code> /event?p_age=23</code> y una característica como <code> YoungPeople = p_age &lt; 25</code>, la característica se materializará, pero el par <code> p_age=23</code> clave-valor se eliminará después de la solicitud y no se registrará. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Información general básica](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Administración de normas de rasgos](../../features/traits/manage-trait-rules.md#managing-trait-rules)

