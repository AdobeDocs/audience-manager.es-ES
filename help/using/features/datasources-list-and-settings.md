---
description: Vea una lista de las fuentes de datos configuradas actualmente, agregue nuevas fuentes de datos y edite las fuentes existentes.
seo-description: Vea una lista de las fuentes de datos configuradas actualmente, agregue nuevas fuentes de datos y edite las fuentes existentes.
seo-title: Lista y configuración de fuentes de datos
solution: Audience Manager
title: Lista y configuración de fuentes de datos
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Fuentes de datos
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1116'
ht-degree: 2%

---

# [!UICONTROL Data Sources] Lista y configuración {#data-sources-list-and-settings}

Vea una lista de su [!UICONTROL data sources] configurado actualmente, añada [!UICONTROL data sources] nuevo y edite el [!UICONTROL data sources] existente.

También puede administrar [!UICONTROL data sources] mediante métodos [!DNL API]. Para obtener más información, consulte [Métodos de API de fuentes de datos](../api/rest-api-main/aam-api-data-sources.md).

## [!UICONTROL Data Sources] Vista de lista {#list-view}

El tablero [!UICONTROL Data Sources] es un espacio de trabajo centralizado para la administración de fuentes de datos.

El tablero [!UICONTROL Data Sources] (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) contiene funciones y herramientas que le ayudan a:

* Vea todos los [!UICONTROL data sources] existentes, incluida la descripción, el estado y si son [!UICONTROL Inbound], [!UICONTROL Outbound], ambos o un [!UICONTROL Shared Provider] de cada fuente de datos.
* Busque [!UICONTROL data sources] por nombre.
* Cree, edite y elimine [!UICONTROL data sources].

## [!DNL Data Source] Configuración y opciones de menú {#settings-menu-options}

La configuración de las diferentes secciones de la interfaz de administración [!UICONTROL Data Source] identifica su [!DNL data source], determina cómo se utiliza o comparte y le permite habilitar el informe de errores para [!UICONTROL Onboarding Status Report].

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: El ID de cookie que identifica un dispositivo. Esto se selecciona cuando la fuente de datos es un explorador web o cuando se trabaja con datos anónimos o datos que no se pueden asociar a una sola persona. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID de publicidad de dispositivo</span></b>: El identificador del dispositivo móvil. Seleccione esta opción cuando la fuente de datos sea un dispositivo móvil o un dispositivo habilitado para Internet. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Entre dispositivos</span></b>: Un ID autenticado proporcionado por el cliente. Seleccione esta opción cuando desee crear: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Fuente de datos entre dispositivos y compilación de una <span class="wintitle"> regla de combinación de perfiles</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Fuente de datos que utiliza vínculos proporcionados por <a href="https://experienceleague.adobe.com/docs/device-co-op/using/about/overview.html" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> u otro gráfico de dispositivos de terceros integrado con <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Definición de ID</span></b> </p> </td> 
   <td colname="col2"> <p>Las opciones de <b><span class="uicontrol"> definición de ID</span></b> definen la relación que tiene un origen de datos con un <span class="keyword"> ID de usuario </span> (UUID) y dispositivos asociados vinculados por <span class="keyword"> Adobe Experience Cloud Device Co-op</span> u otro gráfico de dispositivos de terceros integrado con <span class="keyword"> Audience Manager</span>. Las opciones incluyen: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Persona:</span></b> ID utilizado para definir una sola persona. Este ID se puede asignar a varios ID de <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Hogar: </span></b> el ID utilizado para definir un grupo de personas. Este ID se puede asignar a varios ID de Audience Manager. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[Los ](../features/data-export-controls.md) controles de exportación de datos son reglas de clasificación opcionales que puede aplicar a  [!UICONTROL data source] y  [!UICONTROL destination]. Evitan que envíe datos a un [!UICONTROL destination] cuando esa acción infringe un acuerdo de privacidad o uso de datos. Omita esta sección si no utiliza [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Las restricciones de exportación no funcionarán a menos que establezca una etiqueta de exportación coincidente en [!UICONTROL destination].

Las opciones incluyen:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] Configuración {#data-source-settings}

El [!UICONTROL Data Source Settings] contiene los controles y las opciones que se enumeran a continuación. Algunos de estos ajustes tienen subopciones y elementos de menú adicionales que puede seleccionar para modificar un origen de datos.

### [!UICONTROL Inbound Data Source] Configuración

Active la casilla **[!UICONTROL Inbound]** cuando el origen de datos esté diseñado para recibir datos entrantes. Al seleccionar la casilla de verificación **[!UICONTROL Inbound]**, se exponen dos grupos adicionales de controles que se describen a continuación.

>[!NOTE]
>
>La casilla de verificación **[!UICONTROL Inbound]** solo pretende mostrar u ocultar los controles [!UICONTROL data source] que se describen a continuación. La desactivación de la opción **[!UICONTROL Inbound]** no afecta a la ingesta de datos de ninguna manera. Los datos incorporados se procesarán independientemente de la opción que se marque.

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
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID</span></b> de cliente: Identifica datos de entrada con un ID de cliente. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> ID</span></b> de Audience Manager: Identifica los datos de entrada con un  <span class="keyword"> Audience </span> ManagerID. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> ID</span></b> de Experience Cloud: Identifica los datos de entrada con un  <span class="keyword"> Experience </span> Cloud ID. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies y el ID de Experience Cloud</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Solución de problemas del formato de archivo</span></b> </p> </td> 
   <td colname="col2"> <p>Seleccione <b><span class="uicontrol"> Habilitar muestreo de errores de archivo</span></b> cuando necesite solucionar problemas con el procesamiento de archivos entrantes. Esta función genera un informe de ejemplo de error que muestra errores de sintaxis y formato de archivo. </p> <p>Consulte <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Informe de estado de carga: Acerca de</a> para obtener información sobre los informes de errores y el muestreo de errores. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Otra [!UICONTROL Data Source] configuración

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuración </th> 
   <th colname="col2" class="entry"> Seleccionar cuando </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Saliente</span></b> </p> </td> 
   <td colname="col2"> <p>La fuente de datos envía datos a un destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartir habilitado</span></b> </p> </td> 
   <td colname="col2"> <p>La fuente de datos se puede compartir con otros socios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Usar como perfil autenticado</span></b> </p> </td> 
   <td colname="col2"> <p>La fuente de datos entre dispositivos contiene un ID autenticado. Se recopila y sincroniza un ID autenticado con un ID de <span class="keyword"> Audience Manager</span> durante un evento de autenticación (por ejemplo, un usuario inicia sesión en el sitio, en la aplicación, etc.). El ID autenticado se puede utilizar para datos incorporados de otras fuentes que almacenan este ID. También se puede usar para vincular varios ID de dispositivo en el <span class="wintitle"> vínculo de perfil</span>. </p> <p>Esta opción expone un campo de texto que permite cambiar el nombre del origen de datos por un alias. Si utiliza un alias, este nuevo nombre anula el nombre del origen de datos y aparece en las <span class="wintitle"> Opciones de perfil autenticadas</span> al <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> crear una regla de combinación de perfiles</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Usar como gráfico de dispositivos</span></b> </p> </td> 
   <td colname="col2"> <p>Crea una fuente de datos como un gráfico de dispositivos que puede proporcionar a otros clientes <span class="keyword"> Audience Manager</span>. Antes de seleccionar esta opción, indique a su asesor <span class="keyword"> Audience Manager</span> con qué clientes debe compartirse esta <span class="wintitle"> fuente de datos</span>. Su consultor tendrá que aprovisionar esas empresas a través de nuestros procesos internos. </p> <p>Esta opción expone un campo de texto que permite cambiar el nombre del origen de datos por un alias. Si utiliza un alias, este nuevo nombre anula el nombre del origen de datos y aparece en las <span class="wintitle"> Opciones del dispositivo</span> al <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> crear una regla de combinación de perfiles</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartir los ID de visitante o dispositivo asociados con clientes Audience Manager específicos</span></b> </p> </td> 
   <td colname="col2"> <p>La fuente de datos entre dispositivos contiene los ID de un gráfico de dispositivos. Un gráfico de dispositivos es una colección de ID que se asignan a uno o más <span class="keyword"> ID de Audience Manager</span> de un clúster. Este clúster suele representar a una persona o a un grupo familiar más grande. Disponible solo para cuentas que aparecen como "Proveedor de datos". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Compartir los ID de visitante o dispositivo asociados a través de la plataforma de Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>La fuente de datos contiene ID de visitante o dispositivo que se pueden compartir entre otras soluciones de <span class="keyword"> Experience Cloud</span>. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Retención de datos para ID de cliente inactivos</span></b> </p> </td> 
   <td colname="col2"> <p>Permite establecer el período de retención de datos para los ID de cliente inactivos. Esto determina cuánto tiempo el Audience Manager mantiene los ID de cliente en nuestra base de datos después de haberlos visto por última vez en la plataforma de Audience Manager.</p> <p>El valor predeterminado es 24 meses (720 días). El valor mínimo que puede establecer es 1 mes y el valor máximo es 5 años. Tenga en cuenta que todos los meses se cuentan como 30 días.</p> <p>Audience Manager ejecuta un proceso que elimina los ID de cliente inactivos una vez a la semana, de acuerdo con la retención de datos que configure para los ID de cliente inactivos.</p> <p>Audience Manager ejecuta un proceso que elimina los ID de cliente inactivos una vez a la semana, de acuerdo con la retención de datos que configure para los ID de cliente inactivos.</p> <p><b>Nota</b>: Este control solo está disponible para fuentes de datos entre dispositivos. Consulte también <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Crear una fuente de datos entre dispositivos </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Códigos de integración de rasgos únicos</span></b> </p> </td> 
   <td colname="col2"> <p>Desea hacer cumplir que dos características de la misma fuente de datos no tengan el mismo código de integración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Códigos de integración de segmentos únicos</span></b> </p> </td> 
   <td colname="col2"> <p>Desea hacer cumplir que dos segmentos de la misma fuente de datos no tengan el mismo código de integración. </p> </td> 
  </tr>
 </tbody>
</table>
