---
description: Cree nuevas características a partir de todas las señales, incluidas las que ya se utilizan en características, y capture audiencias futuras que se califican tras la creación de características.
seo-description: Cree nuevas características a partir de todas las señales, incluidas las que ya se utilizan en características, y capture audiencias futuras que se califican tras la creación de características.
seo-title: Crear rasgos a partir de señales
title: Crear rasgos a partir de señales
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 3%

---


# Crear rasgos a partir de señales

Cree nuevas características a partir de todas las señales, incluidas las que ya se utilizan en características, y capture audiencias futuras que se califican tras la creación de características. Vea el vídeo para una rápida demostración o lea para obtener información detallada:

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## Crear características a partir del Panel de señal {#create-traits-from-signal-dashboard}

El [!UICONTROL Signal Dashboard] le permite crear nuevas características a partir de las [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals] y las búsquedas guardadas.

Cuando se crea una nueva característica, el tipo de característica se establece previamente en función del tipo de señal:

* **[!UICONTROL Rule-based]** características para señales en tiempo real, archivos de registro procesables y  [!DNL Adobe Analytics] señales;

* **[!UICONTROL Onboarded]** características de las señales incorporadas.

Para crear nuevas características a partir de **[!UICONTROL Signal Dashboard]**, identifique la señal que desee utilizar en la característica y, a continuación, haga clic en el vínculo correspondiente **[!UICONTROL Create Rule-Based Trait]** o **[!UICONTROL Create Onboarded Trait]**.

![](assets/signals-create-trait.png)

Se le redirigirá al **[Generador de características](../../features/traits/about-trait-builder.md)** para crear sus nuevas características.

## Crear características a partir de la búsqueda de señales {#create-traits-from-signal-search}

Cree características basadas en señales utilizadas o no utilizadas que no se muestren en el [!UICONTROL Signal Dashboard].

Busque señales específicas y cree características basadas en reglas o integradas en función de los resultados. A continuación se muestra cómo hacerlo:

1. Vaya a **[!UICONTROL Audience Data > Signals > Search]** y ejecute una búsqueda basada en los pares de clave-valor que busca, o haga clic en **[!UICONTROL Search]** sin introducir ningún par de clave-valor para mostrar todos los resultados.
2. Identifique las señales que desea utilizar en la característica, en la lista de resultados.
   * Para crear una característica a partir de una señal, haga clic en el vínculo correspondiente **[!UICONTROL Create Rule-Based Trait]** o **[!UICONTROL Create Onboarded Trait]**.
   * Para crear una característica a partir de varias señales, haga clic en la casilla de verificación correspondiente de cada señal y, a continuación, haga clic en **[!UICONTROL Create Trait from Multiple Signals]**.

   >[!NOTE]
   >Solo se pueden crear características a partir de señales del mismo tipo. No se puede crear una característica basada en una combinación de una señal en tiempo real y una señal incorporada.
   >
   > ![](assets/signals-create-trait-search.png)
   >También puede crear características a partir de señales usadas. Las señales que ya se utilizan en características tienen el número de características que se muestran en la columna **[!UICONTROL Included in Traits]**. Haga clic en la flecha para ver las características que incluyen la señal.
   >
   >![](assets/signals-used-traits.png)

3. Utilice el **[Generador de características](../../features/traits/about-trait-builder.md)** para crear sus nuevas características.
