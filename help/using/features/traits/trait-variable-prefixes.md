---
description: Este artículo describe los prefijos que debe adjuntar a las variables clave al crear reglas de características.
seo-description: Este artículo describe los prefijos que debe adjuntar a las variables clave al crear reglas de características.
seo-title: Requisitos de prefijo para variables clave
solution: Audience Manager
title: Requisitos de prefijo para variables clave
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: 'Rasgos '
exl-id: 67fe0c74-6831-48cb-90cf-417ebbf7f272
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 5%

---

# Requisitos de prefijo para variables clave {#prefix-requirements-for-key-variables}

Este artículo describe los prefijos que debe adjuntar a las variables clave al crear reglas de características.

<!-- r_tb_variable_prefixes.xml -->

## Objetivo de los prefijo de variables clave

Al crear reglas [!UICONTROL Trait Builder], es importante anteponer la variable clave con un prefijo recomendado. Estos prefijos identifican el tipo de datos transferidos y ayudan a evitar conflictos de área de nombres dentro de [!DNL Audience Manager]. Por lo general, puede asignarle cualquier nombre a una variable, pero los datos de una regla no se procesarán si el nombre de la variable clave no coincide con el nombre de la variable en una llamada de evento.

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
   <td colname="col2"> <p>Como específico del cliente. Estos son datos clave que se envían desde sus propias propiedades. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>En el nivel <span class="keyword"> Audience Manager</span>. Estos datos son uniformes en el ecosistema <span class="keyword"> Audience Manager</span>. Consulte <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Atributos admitidos para llamadas a la API DCS</a> para obtener una lista más completa.</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Que contiene información del <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> encabezado HTTP</a>. Incluye parámetros de encabezado como <code> referer</code>,<code> IP</code>, <code> accept-language</code>, etc. </p> <p> <p>Nota: Para los clientes que utilizan versiones de DIL anteriores a la 9.0, la recopilación de datos que utilizan la señal <code> h_referer</code> no funcionará en los navegadores Safari. Con la introducción de <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, los navegadores Safari pueden clasificar el dominio demdex.net como rastreador y truncarán el referente en la solicitud de recopilación de datos para que solo contenga el origen en lugar de la dirección URL completa. Consulte <a href="../../dil/dil-overview.md#get-implement-dil-code">Obtención e implementación del código de DIL</a> para obtener la última versión del DIL.<p>Las señales que utilizan este prefijo no aparecen en <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Signal Search</a>.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Nuestros <span class="wintitle"> servidores de recopilación de datos</span> permiten pasar parámetros privados. Básicamente, cualquier parámetro que comience por <code> p_</code> se utilizará para la evaluación de características, pero no se registrará de forma descendente ni se almacenará. </p> <p>Ejemplo: dado <code> /event?p_age=23</code> y un rasgo como <code> YoungPeople = p_age &lt; 25</code>, el rasgo se realiza, pero el par <code> p_age=23</code> clave-valor se perderá después de la solicitud y no se registrará. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Información general básica](../../features/traits/create-onboarded-rule-based-traits.md)
* [Administración de normas de rasgos](../../features/traits/manage-trait-rules.md#managing-trait-rules)

