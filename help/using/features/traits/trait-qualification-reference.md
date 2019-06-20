---
description: La cualificación de características, o realización de características, se trata de forma diferente en Audience Manager, según el tipo de característica. Consulte la tabla siguiente para obtener información detallada sobre la cualificación de características.
keywords: características de características; trait implementation; Realización de características únicas; UTR; Población total de características; TTP
seo-description: La cualificación de características, o realización de características, se trata de forma diferente en Audience Manager, según el tipo de característica. Consulte la tabla siguiente para obtener información detallada sobre la cualificación de características.
seo-title: Referencia de calificación de características
solution: Audience Manager
title: Referencia de calificación de características
uuid: 07 e 0 a 639-2 fb 2-45 d 8-bad 7-10 fb 46 b 08 ba 9
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Referencia de calificación de características {#trait-qualification-reference}

La cualificación de características, o realización de características, se trata de forma diferente en Audience Manager, según el tipo de característica. Consulte la tabla siguiente para obtener información detallada sobre la cualificación de características.

## Trait Qualification by Trait Type {#trait-type}

<table id="table_14CD705F376B44EEA9A6C011984356F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de característica </th> 
   <th colname="col2" class="entry"> Criterios de cualificación </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Características basadas en reglas </p> </td> 
   <td colname="col2"> <p>La cualificación de características se produce en tiempo real, ya que los usuarios cumplen los requisitos de un rasgo en el navegador. Your users will start qualifying for a rule-based trait approximately 4 hours after you <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> create the trait</a> in the UI. </p> <p>Rule-based traits allow you to use <a href="../../features/segments/recency-and-frequency.md"> recency and frequency</a> controls for ad frequency capping and other use cases. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Características integradas </p> </td> 
   <td colname="col2"> <p>Trait qualification happens after an inbound file is processed, i.e. the inbound file is <a href="../../faq/faq-inbound-data-ingestion.md"> imported into Audience Manager</a> and that is when the trait qualification happens. </p> <p> Para características integradas, el número máximo de cualificaciones para un perfil de usuario es 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Características algorítmicas </p> </td> 
   <td colname="col2"> <p>Para las características algorítmicas, el número máximo de cualificaciones para un perfil de usuario es 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Características de carpeta </p> </td> 
   <td colname="col2"> <p>Una característica de carpeta suma las calificaciones de características de las características que contiene. </p> <p>Read <a href="../../features/traits/about-folder-traits.md"> Folder Traits: About</a> for more information. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>Características de audiencia activas y características sincronizadas de fuentes de datos </p> </td> 
   <td colname="col2"> <p>An <span class="wintitle"> Active Audience</span> trait contains all of the devices under management in your <span class="wintitle"> Audience Manager</span> account. </p> <p><span class="wintitle"> Características sincronizadas de fuentes de datos</span> Realiza un seguimiento de todos los usuarios asociados a un origen de datos. </p> <p>Read more about <a href="../../features/traits/client-activity-synced-audience-traits.md"> Active Audience Traits and Data Source Synced Traits</a>. </p> </td>
  </tr>
 </tbody>
</table>

## Unique Trait Realizations and Total Trait Population {#unique-trait-realizations}

![](assets/utr-ttp1.png)

**[!UICONTROL Unique Trait Realizations]** El recuento de los visitantes que han agregado la característica a su perfil, dentro de intervalos de tiempo diferentes.

**[!UICONTROL Total Trait Population]** Representa el número de visitantes que tienen este rasgo en su perfil.

Considere los números de esta manera. In the image above, from the [Trait Details](../../features/traits/trait-details-page.md) view, 181 represents the number of active devices, that visited your properties yesterday. The [!UICONTROL Total Trait Population] of 1,595 represents the amount of users currently qualified for this trait. The [!UICONTROL Total Trait Population] figure is meant to show the total amount of users who could be used for segmentation/targeting. Normalmente, los usuarios permanecerán formados parte de un rasgo durante 120 días.

Because we run two different computational jobs to calculate the two populations, the [!UICONTROL Total Trait Population] always lags behind the [!UICONTROL Unique Trait Realizations] by 24 hours. In the graph above, you can see 175 [!UICONTROL Unique Trait Realizations] and a [!UICONTROL Total Trait Population] of 6 for February 11. The 175 profiles are added to the [!UICONTROL Total Trait Population] on the following day.

To further drive the point home, if you experienced a spike of 10,000 visitors right now, they would show up in tomorrow&#39;s [!UICONTROL Unique Trait Realizations], but would only show up 24 hours later in the [!UICONTROL Total Trait Population].

## Trait Qualification Limit {#trait-qualification-limit}

We enforce a limit of 150,000 trait qualifications for each user profile, whether it is an authenticated profile ( [DPUUID](../../reference/ids-in-aam.md)) or a device ID ( [UUID](../../reference/ids-in-aam.md)). Note that while the DPUUIDs are unique to a specific instance of [!DNL Audience Manager], UUIDs are shared across the [!DNL Audience Manager] platform. For [!UICONTROL UUID]s, we impose a fairness policy when storing trait qualifications. An algorithm ensures that an equal share of the [!UICONTROL UUID] profile is made available for every instance of [!DNL Audience Manager].
