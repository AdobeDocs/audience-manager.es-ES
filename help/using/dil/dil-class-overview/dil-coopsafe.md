---
description: Una configuración booleana opcional que determina si DIL envía datos (o no) datos a Device Co-Op de Adobe Experience Cloud.
seo-description: Una configuración booleana opcional que determina si DIL envía datos (o no) datos a Device Co-Op de Adobe Experience Cloud.
seo-title: isCoopSafe
solution: Audience Manager
title: isCoopSafe
uuid: c5362a38-93c0-4edb-bdcb-106e43f33a92
feature: Implementación del DIL
exl-id: 33dca495-6923-4966-9ec3-8b0fd2f17649
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 77%

---

# isCoopSafe{#iscoopsafe}

Una configuración booleana opcional que determina si DIL envía datos (o no) datos a Device Co-Op de Adobe Experience Cloud.

## Requisitos {#requirements}

Para utilizar `isCoopSafe` debe:

* Utilice [!UICONTROL DIL] v6.11 o superior.
* Participar en [Device Co-Op de Experience Cloud](https://docs.adobe.com/content/help/es-ES/device-co-op/using/home.html). Los potenciales miembros de la cooperación también deben revisar esta documentación para determinar si `isCoopSafe` soluciona los posibles problemas sobre cómo se utilizan los datos para crear el gráfico de dispositivos.

* Póngase en contacto con su consultor de [!DNL Adobe] para establecer un indicador de lista de permitidos o de lista de bloqueados en su cuenta de Device Co-op. No hay una ruta de autoservicio para habilitar estos indicadores.

## Casos de uso {#use-cases}

`isCoopSafe` ayuda a resolver dos casos de uso relacionados con la recopilación de datos que efectúan los miembros actuales o potenciales de Device Co-Op. Estos casos de uso están relacionados con la forma en la que se pasan los datos de visitantes del sitio a Device Co-Op para ayudar a crear el gráfico de dispositivos. En la tabla siguiente se describe cómo `isCoopSafe` funciona con estos casos de uso para bloquear o enviar datos al gráfico de dispositivos.

<table id="table_A24C63D2A21F47EDBAC8FA5E7BE888D8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso de uso </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Visitantes autenticados</b> </p> </td> 
   <td colname="col2"> <p>Agregue <code> isCoopSafe </code> a su código <span class="wintitle"> DIL </span> para controlar cómo Device Co-Op utiliza los datos para los visitantes autenticados que han aceptado o no los acuerdos de condiciones de uso para crear el gráfico de dispositivos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>DIL en sitios de terceros</b> </p> </td> 
   <td colname="col2"> <p>Agregue <code> isCoopSafe </code> a su código <span class="wintitle"> DIL </span> para usarlo en sitios de terceros en los que: </p> <p> 
     <ul id="ul_C27BB26510314834A2A7CD99D46DA4AC"> 
      <li id="li_4E6AE574F18646F09C0CF4553EEA1A9E">No puede garantizar que los visitantes autenticados han aceptado o no los acuerdos de condiciones de uso. </li> 
      <li id="li_26D0561BF32B4278B0A6B5082C17FED8">Debe controlar cómo Device Co-Op utiliza los datos para crear el gráfico de dispositivos. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplo de sintaxis y código {#syntax-code-sample}

**Sintaxis:** `isCoopSafe: true | false`

Las opciones booleanas determinan cómo Device Co-Op utiliza o no los datos de cliente.

* `isCoopSafe: true`: los datos de visitante recopilados por un SDK móvil o sitio web se *pueden* utilizar para ayudar a crear el gráfico de dispositivos.

* `isCoopSafe: false`: los datos de visitante recopilados por un SDK móvil o sitio web *no se pueden* utilizar para ayudar a crear el gráfico de dispositivos.

**Ejemplo de código**

Establezca esta opción cuando el DIL cree una instancia.

```js
var dilInstance = DIL.create({ 
     ... 
     isCoopSafe: true 
});
```

## Parámetros POST de llamada de evento {#post-parameters}

Según el indicador que establezca ( `true` o `false`), [!UICONTROL DIL] traduce `isCoopSafe` a estos parámetros de POST y los envía a [!DNL Adobe] en una llamada de evento:

* `d_coop_safe=1`
* `d_coop_unsafe=1`

Los parámetros POST indican a Device Co-Op de [!DNL Experience Cloud] si puede incluir o no datos en el gráfico de dispositivos. En la siguiente tabla se define la relación entre los indicadores booleanos `isCoopSafe` y los parámetros POST que se han transferido en una llamada de evento. Si no utiliza `isCoopSafe`, no se transferirá ninguno de estos elementos en una llamada de evento.

<table id="table_0A544534CA904F4D9836A34B8C1EACBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Estado de configuración </th> 
   <th colname="col2" class="entry"> Parámetro POST </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: true </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_safe=1 </code> </p> <p>Device Co-Op puede utilizar los datos de visitante para ayudar a crear el gráfico de dispositivos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: false </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_unsafe=1 </code> </p> <p>Device Co-Op no puede utilizar los datos de visitante para ayudar a crear el gráfico de dispositivos. </p> </td> 
  </tr> 
 </tbody> 
</table>

## API posteriores a la creación de instancias  {#post-instantiation}

Estas API permiten sobrescribir el estado de `isCoopSafe`. Son necesarias porque le permiten cambiar el estado posterior a la creación de instancias/inicio de sesión de un visitante en un sitio o en una aplicación de una página en la que la página no se actualiza. Por ejemplo, debería llamar a estas API si un usuario se autenticara en su sitio o aplicación y, posteriormente, aceptara una política de condiciones de uso que permitiera a Device Co-Op utilizar sus datos.

<table id="table_BAA96B1F82BE48C3A61A1AF1367BA45C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopSafe(); </code> </p> </td> 
   <td colname="col2"> <p>Establece el parámetro de POST <code> d_coop_safe=1 </code> en todas las llamadas de evento posteriores. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopUnsafe(); </code> </p> </td> 
   <td colname="col2"> <p>Establece el parámetro de POST <code> d_coop_unsafe=1 </code> en todas las llamadas de evento posteriores. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- 

Wiki page https://wiki.corp.adobe.com/x/RCfFTg

 -->
