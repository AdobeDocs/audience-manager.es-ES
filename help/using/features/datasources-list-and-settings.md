---
description: Vea una lista de las fuentes de datos actualmente configuradas, agregue nuevas fuentes de datos y edite las fuentes existentes.
seo-description: Vea una lista de las fuentes de datos actualmente configuradas, agregue nuevas fuentes de datos y edite las fuentes existentes.
seo-title: Configuración y lista de fuentes de datos
solution: Audience Manager
title: Configuración y lista de fuentes de datos
uuid: 280 a 6 acd-fef 0-4737-a 96 d -9 e 22 fbc 8 bfaf
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Data Sources List and Settings {#data-sources-list-and-settings}

Vea una lista de las fuentes de datos actualmente configuradas, agregue nuevas fuentes de datos y edite las fuentes existentes.

<!-- c_datasources.xml -->

You can also manage data sources using [!DNL API] methods. For more information, see [Data Source API Methods](../api/rest-api-main/aam-api-data-sources.md).

## Data Sources List View {#list-view}

The [!UICONTROL Data Sources] dashboard is a centralized workspace for managing data sources.

<!-- c_datasources_list.xml -->

The [!UICONTROL Data Sources] dashboard (**[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**) contains features and tools that help you:

* See all your existing data sources, including each data source's description, status, and whether it is [!UICONTROL Inbound], [!UICONTROL Outbound], both, or a [!UICONTROL Shared Provider].
* Busque fuentes de datos por nombre.
* Crear, editar y eliminar fuentes de datos.

## Data Source Settings and Menu Options {#settings-menu-options}

The settings in the different sections of the [!UICONTROL Data Source] management interface identify your data source, determine how it is used or shared, and let you enable error reporting for the [!UICONTROL Onboarding Status Report].

## Data Source Details {#details}

<!-- datasource-settings-definitions.xml -->

In addition to text fields, the [!UICONTROL Data Source Details] section contains the controls and options listed below.

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: ID de cookie que identifica un dispositivo. Lo seleccionaría cuando su fuente de datos es un explorador Web o cuando trabaje con datos o datos anónimos que no pueden asociarse con una sola persona. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID de publicidad de dispositivo</span></b>: Identificador del dispositivo móvil. Seleccione esta opción cuando la fuente de datos sea un dispositivo móvil o un dispositivo habilitado para Internet. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Dispositivo cruzado</span></b>: Un ID autenticado proporcionado por el cliente. Seleccione esta opción cuando desee crear: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">A cross-device data source and build a <span class="wintitle"> Profile Merge Rule</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">A data source that uses links provided by the <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> or another, third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Definición de ID</span></b> </p> </td> 
   <td colname="col2"> <p>The <b><span class="uicontrol"> ID Definition</span></b> options define the relationship a data source has to an <span class="keyword"> Audience Manager</span> user ID (UUID) and associated devices linked by the <span class="keyword"> Adobe Experience Cloud Device Co-op</span> or another, third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. Las opciones incluyen: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Persona:</span></b> ID utilizado para definir una sola persona. This ID can be mapped to multiple <span class="keyword"> Audience Manager</span> IDs. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Hogar:</span></b> ID utilizado para definir un grupo de personas. Este ID se puede asignar a varios ID de Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Controles de exportación de datos {#export-controls}

[Los controles de exportación de datos](../features/data-export-controls.md) son reglas opcionales de clasificación que se pueden aplicar a un origen de datos y a un destino. Evita que envíe datos a un destino cuando esa acción infringe una privacidad de datos o utilice un acuerdo. Skip this section if you do not use [!UICONTROL Data Export Controls].

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

[!UICONTROL Data Source Settings] La contiene los controles y las opciones que se indican a continuación. Algunas de estas configuraciones tienen subopciones adicionales y elementos de menú que puede seleccionar para modificar un origen de datos.

### Configuración de fuentes de datos de entrada

Select the **[!UICONTROL Inbound]** check box when your data source is designed to receive inbound data. Selecting the **[!UICONTROL Inbound]** check box exposes 2 additional groups of controls described below.

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
   <td colname="col2"> <p>The <b><span class="uicontrol"> Inbound</span></b> option requires an ID type. Las opciones incluyen: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID de cliente</span></b>: Identifica los datos de entrada con un ID de cliente. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID de Audience Manager</span></b>: Identifica los datos de entrada con un <span class="keyword"> ID de Audience Manager</span> . </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: Identifica los datos de entrada con un <span class="keyword"> ID de Experience Cloud</span> . See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Solución de problemas de formato de archivos</span></b> </p> </td> 
   <td colname="col2"> <p>Select <b><span class="uicontrol"> Enable file error sampling</span></b> when you need to troubleshoot problems with inbound file processing. Esta función genera un informe de muestra de error que muestra el formato de archivo y los errores de sintaxis. </p> <p>See <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Onboarding Status Report: About</a> for information about error reporting and error sampling. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Otros ajustes de fuente de datos

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuración </th> 
   <th colname="col2" class="entry"> Seleccionar cuándo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Saliente</span></b> </p> </td> 
   <td colname="col2"> <p>Su fuente de datos envía datos a un destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartir activado</span></b> </p> </td> 
   <td colname="col2"> <p>Su fuente de datos se puede compartir con otros socios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Utilizar como perfil autenticado</span></b> </p> </td> 
   <td colname="col2"> <p>La fuente de datos entre dispositivos contiene un ID autenticado. An Authenticated ID is collected and synced to an <span class="keyword"> Audience Manager</span> ID during an authentication event (e.g, a user logs in on-site, in-app, etc.). El ID autenticado puede utilizarse para datos en tablero desde otras fuentes que almacenan este ID. It can also be used to link multiple device IDs in <span class="wintitle"> Profile Link</span>. </p> <p>Esta opción expone un campo de texto que permite cambiar el nombre de la fuente de datos con un alias. If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Authenticated Profile Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Utilizar como Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Creates a data source as a device graph which you can provide to other <span class="keyword"> Audience Manager</span> customers. Before you select this option, tell with your <span class="keyword"> Audience Manager</span> consultant which customers this <span class="wintitle"> Data Source</span> should be shared with. Su asesor tendrá que aprovisionar esas empresas a través de nuestros procesos internos. </p> <p>Esta opción expone un campo de texto que permite cambiar el nombre de la fuente de datos con un alias. If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Device Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartir ID de dispositivos o visitantes asociados con clientes específicos de Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>La fuente de datos entre dispositivos contiene ID desde un gráfico de dispositivos. A device graph is a collection of IDs which map to one or more <span class="keyword"> Audience Manager</span> IDs to a cluster. Este clúster suele representar a una persona o grupo de hogares más grande. Disponible solo para cuentas enumeradas como "Proveedor de datos". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartir ID de dispositivos o visitantes asociados en la plataforma de Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>Your data source contains visitor or device IDs that can be shared across other <span class="keyword"> Experience Cloud</span> solutions. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Retención de datos para ID de cliente inactivos</span></b> </p> </td> 
   <td colname="col2"> <p>Permite establecer el período de retención de datos para los ID de cliente inactivos. Esto determina el tiempo que Audience Manager mantiene los ID de cliente en nuestra base de datos después de que se vean por última vez en la plataforma de Audience Manager.</p> <p>El valor predeterminado es de 24 meses (720 días). El valor mínimo que puede configurar es 1 mes y el valor máximo es de 5 años. Tenga en cuenta que se cuentan todos los meses como 30 días.</p> <p>Audience Manager ejecuta un proceso que elimina los ID de cliente inactivos una vez a la semana, de acuerdo con la retención de datos establecida para los ID de cliente inactivos.</p> <p>Audience Manager ejecuta un proceso que elimina los ID de cliente inactivos una vez a la semana, de acuerdo con la retención de datos establecida para los ID de cliente inactivos.</p> <p><b>Nota</b>: Este control solo está disponible para fuentes de datos entre dispositivos. See also, <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Códigos de integración de rasgos únicos</span></b> </p> </td> 
   <td colname="col2"> <p>Desea imponer que dos características de la misma fuente de datos no tengan el mismo código de integración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Códigos de integración de segmentos únicos</span></b> </p> </td> 
   <td colname="col2"> <p>Desea exigir que dos segmentos de la misma fuente de datos no tengan el mismo código de integración. </p> </td> 
  </tr>
 </tbody>
</table>
