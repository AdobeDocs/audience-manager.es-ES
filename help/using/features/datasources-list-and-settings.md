---
description: Vista de una lista de las fuentes de datos configuradas actualmente, agregue nuevas fuentes de datos y edite las fuentes existentes.
seo-description: Vista de una lista de las fuentes de datos configuradas actualmente, agregue nuevas fuentes de datos y edite las fuentes existentes.
seo-title: Lista y configuración de fuentes de datos
solution: Audience Manager
title: Lista y configuración de fuentes de datos
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1118'
ht-degree: 3%

---


# [!UICONTROL Data Sources] Lista y configuración  {#data-sources-list-and-settings}

Vista una lista de su [!UICONTROL data sources] configurado actualmente, agregue [!UICONTROL data sources] nuevo y edite el [!UICONTROL data sources] existente.

También puede administrar [!UICONTROL data sources] mediante métodos [!DNL API]. Para obtener más información, consulte [Métodos de API de fuentes de datos](../api/rest-api-main/aam-api-data-sources.md).

## [!UICONTROL Data Sources] Vista de lista {#list-view}

El panel [!UICONTROL Data Sources] es un espacio de trabajo centralizado para administrar fuentes de datos.

El panel [!UICONTROL Data Sources] (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) contiene funciones y herramientas que le ayudan a:

* Vea todos los [!UICONTROL data sources] existentes, incluyendo la descripción, el estado y si son [!UICONTROL Inbound], [!UICONTROL Outbound], ambos o un [!UICONTROL Shared Provider].
* Busque [!UICONTROL data sources] por nombre.
* Cree, edite y elimine [!UICONTROL data sources].

## [!DNL Data Source] Configuración y opciones de menú  {#settings-menu-options}

La configuración de las diferentes secciones de la interfaz de administración [!UICONTROL Data Source] identifica su [!DNL data source], determina cómo se usa o comparte y permite habilitar el sistema de informes de errores para el [!UICONTROL Onboarding Status Report].

## [!DNL Data Source] Detalles {#details}

Además de los campos de texto, la sección [!UICONTROL Data Source Details] contiene los controles y las opciones que se enumeran a continuación.

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
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID</span></b> de publicidad del dispositivo: Identificador del dispositivo móvil. Seleccione esta opción cuando la fuente de datos sea un dispositivo móvil o con Internet habilitado. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Dispositivo</span></b> cruzado: Un ID autenticado proporcionado por el cliente. Seleccione esta opción cuando desee crear: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Origen de datos entre dispositivos y compilación de una <span class="wintitle"> regla de combinación de Perfiles</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Origen de datos que utiliza vínculos proporcionados por <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Device Co-op</a> de Adobe Experience Cloud u otro gráfico de dispositivos de terceros que está integrado con <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Definición de ID</span></b> </p> </td> 
   <td colname="col2"> <p>Las opciones <b><span class="uicontrol"> Definición de ID</span></b> definen la relación que tiene un origen de datos con un <span class="keyword"> ID de usuario </span> (UUID) y dispositivos asociados vinculados por la <span class="keyword"> cooperación entre dispositivos de Adobe Experience Cloud</span> u otro gráfico de dispositivos de terceros que esté integrado con <span class="keyword"> Audience Manager</span>. Las opciones incluyen: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Persona:</span></b> ID utilizado para definir una sola persona. Este ID se puede asignar a varios <span class="keyword"> ID de Audience Manager</span>. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Hogar:</span></b> El ID utilizado para definir un grupo de personas. Este ID se puede asignar a varios ID de Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[Los ](../features/data-export-controls.md) controles de exportación de datos son reglas de clasificación opcionales que se pueden aplicar a  [!UICONTROL data source] y  [!UICONTROL destination]. Le impiden enviar datos a [!UICONTROL destination] cuando dicha acción infringe una privacidad de datos o un acuerdo de uso. Omita esta sección si no utiliza [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Las restricciones de exportación no funcionarán a menos que establezca una etiqueta de exportación coincidente en un [!UICONTROL destination].

Las opciones incluyen:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] Configuración {#data-source-settings}

El [!UICONTROL Data Source Settings] contiene los controles y las opciones que se enumeran a continuación. Algunos de estos ajustes tienen subopciones y elementos de menú adicionales que puede seleccionar para modificar un origen de datos.

### [!UICONTROL Inbound Data Source] Configuración

Seleccione la casilla **[!UICONTROL Inbound]** cuando el origen de datos esté diseñado para recibir datos de entrada. Al seleccionar la casilla de verificación **[!UICONTROL Inbound]** se exponen dos grupos adicionales de controles que se describen a continuación.

>[!NOTE]
>
>La casilla de verificación **[!UICONTROL Inbound]** sólo tiene el propósito de mostrar u ocultar los controles [!UICONTROL data source] que se describen a continuación. La desactivación de la opción **[!UICONTROL Inbound]** no afecta la ingestión de datos de ninguna manera. Los datos incorporados se procesarán independientemente de esta opción que se esté comprobando.

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
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID</span></b> del cliente: Identifica los datos de entrada con un ID de cliente. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID</span></b> del Audience Manager: Identifica los datos de entrada con una  <span class="keyword"> Audiencia </span> ManagerID. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> ID</span></b> del Experience Cloud: Identifica los datos de entrada con un  <span class="keyword"> Experience </span> CloudID. Consulte <a href="https://docs.adobe.com/content/help/es-ES/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies y el ID de Experience Cloud</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Resolución de problemas de formato de archivo</span></b> </p> </td> 
   <td colname="col2"> <p>Seleccione <b><span class="uicontrol"> Habilitar el muestreo de errores de archivo</span></b> cuando necesite solucionar problemas con el procesamiento de archivos de entrada. Esta función genera un informe de muestra de errores que muestra errores de sintaxis y formato de archivo. </p> <p>Consulte <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Informe de estado de integración: Acerca de</a> para obtener información sobre el sistema de informes de errores y el muestreo de errores. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Otros [!UICONTROL Data Source] ajustes

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
   <td colname="col1"> <p> <b><span class="uicontrol"> Usar como Perfil autenticado</span></b> </p> </td> 
   <td colname="col2"> <p>El origen de datos entre dispositivos contiene un ID autenticado. Un ID autenticado se recopila y sincroniza con un <span class="keyword"> ID de Audience Manager</span> durante un evento de autenticación (por ejemplo, un usuario inicia sesión en el sitio, en la aplicación, etc.). El ID autenticado puede utilizarse para datos a bordo de otras fuentes que almacenen este ID. También se puede usar para vincular varios ID de dispositivo en <span class="wintitle"> Vínculo de Perfil</span>. </p> <p>Esta opción muestra un campo de texto que permite cambiar el nombre del origen de datos por un alias. Si utiliza un alias, este nuevo nombre anula el nombre del origen de datos y aparece en las <span class="wintitle"> Opciones de Perfil autenticadas</span> cuando <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> crea una regla de combinación de Perfiles</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Uso como Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Crea un origen de datos como un gráfico de dispositivos que puede proporcionar a otros clientes <span class="keyword"> Audience Manager</span>. Antes de seleccionar esta opción, informe a su <span class="keyword"> Audience Manager</span> asesor con qué clientes debe compartir esta <span class="wintitle"> fuente de datos</span>. Su consultor tendrá que suministrar esas compañías a través de nuestros procesos internos. </p> <p>Esta opción muestra un campo de texto que permite cambiar el nombre del origen de datos por un alias. Si utiliza un alias, este nuevo nombre anula el nombre del origen de datos y aparece en las <span class="wintitle"> Opciones del dispositivo</span> cuando <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> crea una regla de combinación de Perfiles</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartir los ID de dispositivo o visitante asociados con clientes Audience Manager específicos</span></b> </p> </td> 
   <td colname="col2"> <p>La fuente de datos entre dispositivos contiene los ID de un gráfico de dispositivos. Un gráfico de dispositivo es una colección de ID que se asignan a uno o más <span class="keyword"> ID de Audience Manager</span> de un clúster. Este grupo suele representar a una persona o a un grupo familiar mayor. Disponible sólo para cuentas que se enumeran como "Proveedor de datos". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartir los ID de dispositivo o visitante asociados en la plataforma Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>La fuente de datos contiene ID de dispositivo o visitante que se pueden compartir en otras soluciones <span class="keyword"> Experience Cloud</span>. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Retención de datos para ID de cliente inactivos</span></b> </p> </td> 
   <td colname="col2"> <p>Permite configurar el período de retención de datos para los ID de cliente inactivos. Esto determina cuánto tiempo el Audience Manager mantiene los ID de cliente en nuestra base de datos después de que se vieron por última vez en la plataforma Audience Manager.</p> <p>El valor predeterminado es 24 meses (720 días). El valor mínimo que puede establecer es 1 mes y el valor máximo es 5 años. Tenga en cuenta que todos los meses se cuentan como 30 días.</p> <p>Audience Manager ejecuta un proceso que elimina los ID de cliente inactivos una vez a la semana, de acuerdo con la retención de datos que configuró para los ID de cliente inactivos.</p> <p>Audience Manager ejecuta un proceso que elimina los ID de cliente inactivos una vez a la semana, de acuerdo con la retención de datos que configuró para los ID de cliente inactivos.</p> <p><b>Nota</b>: Este control solo está disponible para fuentes de datos entre dispositivos. Consulte también <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Creación de una fuente de datos entre dispositivos </a>.</p></td> 
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
