---
description: Vea una lista de las fuentes de datos configuradas actualmente, agregue nuevas fuentes de datos y edite las fuentes existentes.
seo-description: Vea una lista de las fuentes de datos configuradas actualmente, agregue nuevas fuentes de datos y edite las fuentes existentes.
seo-title: Lista y configuración de fuentes de datos
solution: Audience Manager
title: Lista y configuración de fuentes de datos
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Lista y configuración de fuentes de datos {#data-sources-list-and-settings}

Vea una lista de las fuentes de datos configuradas actualmente, agregue nuevas fuentes de datos y edite las fuentes existentes.

<!-- c_datasources.xml -->

También puede administrar fuentes de datos mediante [!DNL API] métodos. Para obtener más información, consulte Métodos [de API de fuentes de](../api/rest-api-main/aam-api-data-sources.md)datos.

## Vista de lista de fuentes de datos {#list-view}

El [!UICONTROL Data Sources] tablero es un espacio de trabajo centralizado para administrar las fuentes de datos.

<!-- c_datasources_list.xml -->

El [!UICONTROL Data Sources] tablero (**[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**) contiene funciones y herramientas que le ayudan a:

* Ver todas las fuentes de datos existentes, incluida la descripción, el estado y si son [!UICONTROL Inbound], [!UICONTROL Outbound]ambas o una [!UICONTROL Shared Provider].
* Buscar fuentes de datos por nombre.
* Crear, editar y eliminar fuentes de datos.

## Configuración y opciones de menú de la fuente de datos {#settings-menu-options}

La configuración de las diferentes secciones de la interfaz de [!UICONTROL Data Source] administración identifica el origen de datos, determina cómo se utiliza o comparte y permite habilitar los informes de errores para el [!UICONTROL Onboarding Status Report].

## Detalles de la fuente de datos {#details}

<!-- datasource-settings-definitions.xml -->

Además de los campos de texto, la [!UICONTROL Data Source Details] sección contiene los controles y las opciones que se enumeran a continuación.

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuración </th> 
   <th colname="col2" class="entry"> Opciones de menú </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tipo de ID</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: ID de cookie que identifica un dispositivo. Esto se selecciona cuando el origen de datos es un explorador Web o cuando se trabaja con datos anónimos o datos que no se pueden asociar con una sola persona. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID</span></b>de publicidad del dispositivo: Identificador del dispositivo móvil. Seleccione esta opción cuando la fuente de datos sea un dispositivo móvil o con Internet habilitado. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Dispositivo</span></b>cruzado: Un ID autenticado proporcionado por el cliente. Seleccione esta opción cuando desee crear: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Origen de datos entre dispositivos y generación de una regla <span class="wintitle"> de combinación de perfiles</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Origen de datos que utiliza vínculos proporcionados por <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> u otro gráfico de dispositivos de terceros integrado con <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Definición de ID</span></b> </p> </td> 
   <td colname="col2"> <p>Las opciones de definición <b><span class="uicontrol"> de</span></b> ID definen la relación que tiene un origen de datos con un ID de usuario de <span class="keyword"> Audience Manager</span> (UUID) y los dispositivos asociados vinculados por <span class="keyword"> Adobe Experience Cloud Device Co-op</span> u otro gráfico de dispositivos de terceros integrado con <span class="keyword"> Audience Manager</span>. Las opciones incluyen: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"></span></b> Persona: ID utilizado para definir una sola persona. Este ID se puede asignar a varios <span class="keyword"> ID de Audience Manager</span> . </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"></span></b> Hogar: ID utilizado para definir un grupo de personas. Este ID se puede asignar a varios ID de Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Controles de exportación de datos {#export-controls}

[Los controles](../features/data-export-controls.md) de exportación de datos son reglas de clasificación opcionales que se pueden aplicar a un origen y destino de datos. Le impiden enviar datos a un destino cuando dicha acción infringe una privacidad de datos o un acuerdo de uso. Omita esta sección si no utiliza [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Las restricciones de exportación no funcionarán a menos que establezca una etiqueta de exportación coincidente en un destino.

Las opciones incluyen:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Data Source Settings {#data-source-settings}

El [!UICONTROL Data Source Settings] contiene los controles y las opciones que se enumeran a continuación. Algunos de estos ajustes tienen subopciones y elementos de menú adicionales que puede seleccionar para modificar un origen de datos.

### Configuración de fuentes de datos de entrada

Seleccione la **[!UICONTROL Inbound]** casilla de verificación cuando el origen de datos esté diseñado para recibir datos de entrada. Al seleccionar la **[!UICONTROL Inbound]** casilla de verificación se exponen dos grupos adicionales de controles que se describen a continuación.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuración </th> 
   <th colname="col2" class="entry"> Opciones de menú </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tipo de ID</span></b> </p> </td> 
   <td colname="col2"> <p>La opción <b><span class="uicontrol"> Entrante</span></b> requiere un tipo de ID. Las opciones incluyen: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID</span></b>del cliente: Identifica los datos de entrada con un ID de cliente. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID</span></b>de Audience Manager: Identifica los datos de entrada con un <span class="keyword"> ID de Audience Manager</span> . </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: Identifica los datos de entrada con un ID de <span class="keyword"> Experience Cloud</span> . See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Resolución de problemas de formato de archivo</span></b> </p> </td> 
   <td colname="col2"> <p>Seleccione <b><span class="uicontrol"> Activar muestreo</span></b> de errores de archivo cuando necesite solucionar problemas con el procesamiento de archivos de entrada. Esta función genera un informe de muestra de errores que muestra errores de sintaxis y formato de archivo. </p> <p>Consulte <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Informe de estado de integración: Acerca</a> de para obtener información sobre los informes de errores y el muestreo de errores. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Otras opciones de fuente de datos

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuración </th> 
   <th colname="col2" class="entry"> Seleccionar al </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Saliente</span></b> </p> </td> 
   <td colname="col2"> <p>El origen de datos envía datos a un destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Uso compartido habilitado</span></b> </p> </td> 
   <td colname="col2"> <p>La fuente de datos se puede compartir con otros socios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Usar como perfil autenticado</span></b> </p> </td> 
   <td colname="col2"> <p>El origen de datos entre dispositivos contiene un ID autenticado. Un ID autenticado se recopila y sincroniza con un ID de <span class="keyword"> Audience Manager</span> durante un evento de autenticación (por ejemplo, un usuario inicia sesión en el sitio, en la aplicación, etc.). El ID autenticado puede utilizarse para datos a bordo de otras fuentes que almacenen este ID. También se puede usar para vincular varios ID de dispositivo en el vínculo <span class="wintitle"></span>de perfil. </p> <p>Esta opción muestra un campo de texto que permite cambiar el nombre del origen de datos por un alias. Si utiliza un alias, este nuevo nombre anula el nombre del origen de datos y aparece en las <span class="wintitle"> Opciones</span> de perfil autenticadas al <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> crear una regla</a>de combinación de perfiles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Uso como Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Crea un origen de datos como un gráfico de dispositivos que puede proporcionar a otros <span class="keyword"> clientes de Audience Manager</span> . Antes de seleccionar esta opción, informe a su consultor de <span class="keyword"> Audience Manager</span> con qué clientes debe compartir esta <span class="wintitle"> fuente</span> de datos. Su consultor tendrá que proveer a esas empresas a través de nuestros procesos internos. </p> <p>Esta opción muestra un campo de texto que permite cambiar el nombre del origen de datos por un alias. Si utiliza un alias, este nuevo nombre anula el nombre del origen de datos y aparece en las <span class="wintitle"> Opciones</span> del dispositivo al <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> crear una regla</a>de combinación de perfiles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartir los ID de visitante o dispositivo asociados con clientes específicos de Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>La fuente de datos entre dispositivos contiene ID de un gráfico de dispositivos. Un gráfico de dispositivo es una colección de ID que se asignan a uno o varios ID de <span class="keyword"> Audience Manager</span> en un clúster. Este grupo suele representar a una persona o a un grupo familiar mayor. Disponible sólo para cuentas que se enumeran como "Proveedor de datos". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartir los ID de visitante o dispositivo asociados en la plataforma de Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>La fuente de datos contiene ID de visitante o dispositivo que se pueden compartir en otras <span class="keyword"> soluciones de Experience Cloud</span> . </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Retención de datos para ID de cliente inactivos</span></b> </p> </td> 
   <td colname="col2"> <p>Permite configurar el período de retención de datos para los ID de cliente inactivos. Esto determina cuánto tiempo Audience Manager mantiene los ID de cliente en la base de datos después de la última vez que se vieron en la plataforma de Audience Manager.</p> <p>El valor predeterminado es 24 meses (720 días). El valor mínimo que puede establecer es 1 mes y el valor máximo es 5 años. Tenga en cuenta que todos los meses se cuentan como 30 días.</p> <p>Audience Manager ejecuta un proceso que elimina los ID de cliente inactivos una vez a la semana, de acuerdo con la retención de datos establecida para los ID de cliente inactivos.</p> <p>Audience Manager ejecuta un proceso que elimina los ID de cliente inactivos una vez a la semana, de acuerdo con la retención de datos establecida para los ID de cliente inactivos.</p> <p><b>Nota</b>: Este control solo está disponible para fuentes de datos entre dispositivos. Consulte también <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Creación de una fuente de datos entre dispositivos </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Códigos de integración de características únicas</span></b> </p> </td> 
   <td colname="col2"> <p>Desea aplicar que dos características de la misma fuente de datos no tengan el mismo código de integración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Códigos de integración de segmentos únicos</span></b> </p> </td> 
   <td colname="col2"> <p>Desea aplicar que dos segmentos del mismo origen de datos no tengan el mismo código de integración. </p> </td> 
  </tr>
 </tbody>
</table>
