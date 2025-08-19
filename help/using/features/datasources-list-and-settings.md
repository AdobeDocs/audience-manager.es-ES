---
description: Vea una lista de las fuentes de datos configuradas actualmente, agregue nuevas fuentes de datos y edite las fuentes existentes.
seo-description: View a list of your currently configured data sources, add new data sources, and edit existing sources.
seo-title: Data Sources List and Settings
solution: Audience Manager
title: Lista y configuración de fuentes de datos
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---

# Lista y configuración de [!UICONTROL Data Sources] {#data-sources-list-and-settings}

Vea una lista de su [!UICONTROL data sources] configurado actualmente, agregue un(a) nuevo(a) [!UICONTROL data sources] y edite un(a) [!UICONTROL data sources] existente.

También puede administrar [!UICONTROL data sources] mediante los métodos [!DNL API]. Para obtener más información, consulte [Métodos de API de Data Source](../api/rest-api-main/aam-api-data-sources.md).

## Vista de lista [!UICONTROL Data Sources] {#list-view}

El tablero [!UICONTROL Data Sources] es un espacio de trabajo centralizado para administrar orígenes de datos.

El panel [!UICONTROL Data Sources] (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) contiene características y herramientas que le ayudarán a:

* Ver todos los [!UICONTROL data sources] existentes, incluida la descripción, el estado y si se trata de [!UICONTROL Inbound], [!UICONTROL Outbound], ambos o un [!UICONTROL Shared Provider].
* Busque [!UICONTROL data sources] por su nombre.
* Crear, editar y eliminar [!UICONTROL data sources].

## Configuración de [!DNL Data Source] y opciones de menú {#settings-menu-options}

La configuración de las diferentes secciones de la interfaz de administración de [!UICONTROL Data Source] identifica su [!DNL data source], determina cómo se utiliza o comparte y le permite habilitar los informes de errores para [!UICONTROL Onboarding Status Report].

## Detalles de [!DNL Data Source] {#details}

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
   <td colname="col1"> <p> <b><span class="uicontrol"> tipo de identificador</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: El identificador de cookie que identifica un dispositivo. Seleccionaría esta opción cuando la fuente de datos sea un explorador web o cuando trabaje con datos anónimos o datos que no se puedan asociar con una sola persona. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> ID de Advertising de dispositivo</span></b>: El identificador del dispositivo móvil. Seleccione esta opción cuando la fuente de datos sea un dispositivo móvil o un dispositivo habilitado para Internet. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> entre dispositivos</span></b>: ID autenticado proporcionado por el cliente. Seleccione esta opción cuando desee crear: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Crear una fuente de datos entre dispositivos y generar una regla de combinación de perfiles <span class="wintitle"></span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Origen de datos que utiliza vínculos proporcionados por un gráfico de dispositivos de terceros integrado con <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> definición de ID</span></b> </p> </td> 
   <td colname="col2"> <p>Las opciones de <b><span class="uicontrol"> ID Definition</span></b> definen la relación que tiene un origen de datos con un ID de usuario (UUID) de <span class="keyword"> Audience Manager</span> y dispositivos asociados vinculados por un gráfico de dispositivos de terceros integrado con <span class="keyword"> Audience Manager</span>. Las opciones incluyen: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> persona:</span></b> Identificador utilizado para definir a una sola persona. Este identificador se puede asignar a varios <span class="keyword"> identificadores Audience Manager</span>. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Hogar:</span></b> Identificador utilizado para definir un grupo de personas. Este ID se puede asignar a varios Audience Manager ID. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[Los controles de exportación de datos](../features/data-export-controls.md) son reglas de clasificación opcionales que puede aplicar a [!UICONTROL data source] y a [!UICONTROL destination]. Impiden que se envíen datos a [!UICONTROL destination] cuando esa acción infringe un acuerdo de uso o privacidad de datos. Omita esta sección si no usa [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Las restricciones de exportación no funcionarán a menos que establezca una etiqueta de exportación coincidente en [!UICONTROL destination].

Las opciones incluyen:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Configuración de [!UICONTROL Data Source] {#data-source-settings}

[!UICONTROL Data Source Settings] contiene los controles y las opciones que se enumeran a continuación. Algunos de estos ajustes tienen subopciones y elementos de menú adicionales que puede seleccionar para modificar una fuente de datos.

### Configuración de [!UICONTROL Inbound Data Source]

Active la casilla de verificación **[!UICONTROL Inbound]** cuando el origen de datos esté diseñado para recibir datos de entrada. Al seleccionar la casilla de verificación **[!UICONTROL Inbound]**, se exponen dos grupos adicionales de controles que se describen a continuación.

>[!NOTE]
>
>La casilla de verificación **[!UICONTROL Inbound]** solo está diseñada para mostrar u ocultar los controles [!UICONTROL data source] que se describen a continuación. Desmarcar la opción **[!UICONTROL Inbound]** no afecta la ingesta de datos de ninguna manera. Los datos incorporados se procesarán independientemente de si se marca esta opción.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuración </th> 
   <th colname="col2" class="entry"> Opciones de menú </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> tipo de identificador</span></b> </p> </td> 
   <td colname="col2"> <p>La opción <b><span class="uicontrol"> Inbound</span></b> requiere un tipo de identificador. Las opciones incluyen: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> ID de cliente</span></b>: identifica los datos de entrada con un ID de cliente. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager ID</span></b>: Identifica datos de entrada con un ID de <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: Identifica datos de entrada con un ID de <span class="keyword"> Experience Cloud</span>. Consulte <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=es" format="https" scope="external"> cookies y el Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> resolución de problemas de formato de archivo</span></b> </p> </td> 
   <td colname="col2"> <p>Seleccione <b><span class="uicontrol"> Habilitar muestreo de errores de archivo</span></b> cuando necesite solucionar problemas con el procesamiento de archivos entrantes. Esta función genera un informe de ejemplo de error que muestra los errores de formato de archivo y sintaxis. </p> <p>Consulte <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Informe de estado de carga: Acerca de </a> para obtener información sobre los informes de errores y el muestreo de errores. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Otra configuración de [!UICONTROL Data Source]

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuración </th> 
   <th colname="col2" class="entry"> Seleccionar cuando </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> saliente</span></b> </p> </td> 
   <td colname="col2"> <p>La fuente de datos envía datos a un destino. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Uso compartido de <b><span class="uicontrol"> habilitado</span></b> </p> </td> 
   <td colname="col2"> <p>Su fuente de datos se puede compartir con otros socios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> usar como perfil autenticado</span></b> </p> </td> 
   <td colname="col2"> <p>La fuente de datos entre dispositivos contiene un ID autenticado. Se recopila un identificador autenticado y se sincroniza con un identificador Audience Manager<span class="keyword"> de </span> durante un evento de autenticación (por ejemplo, un usuario inicia sesión en el sitio, en la aplicación, etc.). El ID autenticado se puede utilizar para incorporar datos de otras fuentes que almacenan este ID. También se puede usar para vincular varios ID de dispositivo en <span class="wintitle"> vínculo de perfil </span>. </p> <p>Esta opción expone un campo de texto que le permite cambiar el nombre del origen de datos con un alias. Si usa un alias, este nuevo nombre anula el nombre del origen de datos y aparece en las <span class="wintitle"> opciones de perfil autenticado</span> cuando <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> crea una regla de combinación de perfiles</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> usar como gráfico de dispositivo</span></b> </p> </td> 
   <td colname="col2"> <p>Crea un origen de datos como un gráfico de dispositivo que puede proporcionar a otros <span class="keyword"> clientes de Audience Manager</span>. Antes de seleccionar esta opción, indique al consultor de <span class="keyword"> Audience Manager</span> con qué clientes se debe compartir este Source de datos <span class="wintitle"></span>. Su asesor tendrá que suministrar esas compañías a través de nuestros procesos internos. </p> <p>Esta opción expone un campo de texto que le permite cambiar el nombre del origen de datos con un alias. Si usa un alias, este nuevo nombre anula el nombre del origen de datos y aparece en <span class="wintitle"> Opciones de dispositivo</span> cuando <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> crea una regla de combinación de perfiles</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> comparte ID de visitante o dispositivo asociados con clientes específicos de Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>La fuente de datos entre dispositivos contiene los ID de un gráfico de dispositivos. Un gráfico de dispositivos es una colección de identificadores que se asignan a uno o más <span class="keyword"> ID de Audience Manager</span> a un clúster. Este grupo suele representar a una persona o a un grupo familiar más grande. Disponible solo para cuentas enumeradas como "Proveedor de datos". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> comparte ID de visitante o dispositivo asociados en toda la plataforma Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>Su fuente de datos contiene ID de visitantes o dispositivos que se pueden compartir en otras soluciones de <span class="keyword"> Experience Cloud</span>. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Retención de datos para ID de cliente inactivos</span></b> </p> </td> 
   <td colname="col2"> <p>Permite establecer el período de retención de datos para los ID de cliente inactivos. Esto determina cuánto tiempo mantiene Audience Manager los ID de cliente en nuestra base de datos después de que se hayan visto por última vez en la plataforma Audience Manager.</p> <p>El valor predeterminado es 24 meses (720 días). El valor mínimo que puede establecer es 1 mes y el valor máximo es 5 años. Tenga en cuenta que contamos todos los meses como 30 días.</p> <p>Audience Manager ejecuta un proceso que elimina los ID de cliente inactivos una vez a la semana, de acuerdo con la retención de datos establecida para los ID de cliente inactivos.</p> <p>Audience Manager ejecuta un proceso que elimina los ID de cliente inactivos una vez a la semana, de acuerdo con la retención de datos establecida para los ID de cliente inactivos.</p> <p><b>Nota</b>: este control solo está disponible para orígenes de datos entre dispositivos. Vea también <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Crear un Source de datos entre dispositivos </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> códigos de integración de rasgos únicos</span></b> </p> </td> 
   <td colname="col2"> <p>Debe comprobar que dos características de la misma fuente de datos no tienen el mismo código de integración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> códigos de integración de segmento únicos</span></b> </p> </td> 
   <td colname="col2"> <p>Debe comprobar que dos segmentos del mismo origen de datos no tienen el mismo código de integración. </p> </td> 
  </tr>
 </tbody>
</table>
