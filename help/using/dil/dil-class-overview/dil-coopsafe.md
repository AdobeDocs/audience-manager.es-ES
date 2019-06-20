---
description: Una configuración booleana opcional que determina si DIL envía datos (o no) datos a Device Co-Op de Adobe Experience Cloud.
seo-description: Una configuración booleana opcional que determina si DIL envía datos (o no) datos a Device Co-Op de Adobe Experience Cloud.
seo-title: isCoopSafe
solution: Audience Manager
title: isCoopSafe
uuid: c 5362 a 38-93 c 0-4 edb-bdcb -106 e 43 f 33 a 92
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# isCoopSafe{#iscoopsafe}

Una configuración booleana opcional que determina si DIL envía datos (o no) datos a Device Co-Op de Adobe Experience Cloud.

## Requisitos {#requirements}

To use `isCoopSafe` you must:

* Use [!UICONTROL DIL] v6.11 or higher.
* Participar en [Device Co-Op de Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcdc/). Los potenciales miembros de la cooperación también deben revisar esta documentación para determinar si `isCoopSafe` soluciona los posibles problemas sobre cómo se utilizan los datos para crear el gráfico de dispositivos.

* Trabaje con su consultor de [!DNL Adobe] para establecer un indicador de lista de elementos permitidos o de lista de elementos bloqueados en su cuenta de Device Co-Op. No hay ruta de autoservicio para habilitar estos indicadores.

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
   <td colname="col2"> <p>Add <code> isCoopSafe </code> to your <span class="wintitle"> DIL </span> code to control how data for authenticated visitors who have or have not accepted term-of-use agreements is used by the Device Co-op to build the device graph. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>DIL en sitios de terceros</b> </p> </td> 
   <td colname="col2"> <p>Add <code> isCoopSafe </code> to your <span class="wintitle"> DIL </span> code for use on third-party sites where you: </p> <p> 
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

Configúrelo cuando DIL se instancie.

```js
var dilInstance = DIL.create({ 
     ... 
     isCoopSafe: true 
});
```

## Parámetros POST de llamada de evento {#post-parameters}

Depending on the flag you set ( `true` or `false`), [!UICONTROL DIL] translates `isCoopSafe` into these POST parameters and sends them to [!DNL Adobe] in an event call:

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

## API posteriores a la creación de instancias {#post-instantiation}

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
   <td colname="col1"> <p> <code> Dilinstance. api. setascoopsafe (); </code> </p> </td> 
   <td colname="col2"> <p>Establece el parámetro POST <code>d_coop_safe=1</code> en todas las llamadas de evento posteriores. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Dilinstance. api. setascoopunsafe (); </code> </p> </td> 
   <td colname="col2"> <p>Establece el parámetro POST <code>d_coop_unsafe=1</code> en todas las llamadas de evento posteriores. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- 

Wiki page https://wiki.corp.adobe.com/x/RCfFTg

 -->

