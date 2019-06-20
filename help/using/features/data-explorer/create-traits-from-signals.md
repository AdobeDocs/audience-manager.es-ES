---
description: Cree nuevas características a partir de todas las señales, incluidas las que ya se usan en características, y capture audiencias futuras que califiquen después de la creación de características.
seo-description: Cree nuevas características a partir de todas las señales, incluidas las que ya se usan en características, y capture audiencias futuras que califiquen después de la creación de características.
seo-title: Crear características a partir de señales
title: Crear características a partir de señales
uuid: 4 f 324404-0 c 24-4 e 3 b -96 c 1-7 c 1 b 28 a 4536 d
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# Crear características a partir de señales

Cree nuevas características a partir de todas las señales, incluidas las que ya se usan en características, y capture audiencias futuras que califiquen después de la creación de características. Vea el vídeo para ver una demostración rápida o leída para obtener información detallada:

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12&captions=spa)

## Create Traits from Signal Dashboard {#create-traits-from-signal-dashboard}

[!UICONTROL Signal Dashboard] Permite crear nuevas características a partir de [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals]y las búsquedas guardadas.

Cuando crea un nuevo rasgo, el tipo de característica está predefinido en función del tipo de señal:

* **[!UICONTROL Rule-based]** características para señales en tiempo real, archivos de registro procesables e [!DNL Adobe Analytics] indicaciones;

* **[!UICONTROL Onboarded]** características para señales integradas.

To create new traits from the **[!UICONTROL Signal Dashboard]**, identify the signal that you want to use in the trait, then click the corresponding **[!UICONTROL Create Rule-Based Trait]** or **[!UICONTROL Create Onboarded Trait]** link.

![](assets/signals-create-trait.png)

You&#39;ll be redirected to the **[Trait Builder](../../features/traits/about-trait-builder.md)** to create your new trait(s).

## Create Traits from Signal Search {#create-traits-from-signal-search}

Create traits based on used or unused signals that are not shown in the [!UICONTROL Signal Dashboard].

Busque señales específicas y cree características basadas en reglas o integradas según los resultados. A continuación se muestra cómo hacer esto:

1. Go to **[!UICONTROL Audience Data > Signals > Search]** and run a search based on the key-value pairs that you are looking for, or click **[!UICONTROL Search]** without entering any key-value pair to display all results.
2. Identifique las señales que desee utilizar en la característica, en la lista de resultados.
   * To create a trait from one signal, click the corresponding **[!UICONTROL Create Rule-Based Trait]** or **[!UICONTROL Create Onboarded Trait]** link.
   * To create a trait from multiple signals, click the corresponding check box of each signal, then click **[!UICONTROL Create Trait from Multiple Signals]**.
   >[!NOTE]
   >Solo puede crear características a partir de señales del mismo tipo. No se puede crear un rasgo basado en una combinación de señal en tiempo real y uno introducido.
   >
   > ![](assets/signals-create-trait-search.png)
   >También puede crear características a partir de señales utilizadas. Signals that are already used in traits have the number of traits displayed in the **[!UICONTROL Included in Traits]** column. Haga clic en la flecha para ver las características que incluyen la señal.
   >
   >![](assets/signals-used-traits.png)

3. Use the **[Trait Builder](../../features/traits/about-trait-builder.md)** to create your new traits.
