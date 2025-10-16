---
description: Crear nuevos rasgos de todas las señales, incluidos los que ya se usan en los rasgos, y capture audiencias futuras que califiquen después de la creación del rasgo.
seo-description: Create new traits from all signals, including those that are already used in traits, and capture future audiences that qualify after trait creation.
seo-title: Create Traits from Signals
title: Crear Características de las señales
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: Data Explorer
exl-id: 14308ef0-58eb-4b76-858c-d0da560f55fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Crear Características de las señales

Crear nuevos rasgos de todas las señales, incluidos los que ya se usan en los rasgos, y capture audiencias futuras que califiquen después de la creación del rasgo. Vea el video para ver una demostración rápida o siga leyendo para obtener información detallada:

>[!VIDEO](https://video.tv.adobe.com/v/327529/?quality=12&captions=spa)

## Crear características del panel de señales {#create-traits-from-signal-dashboard}

El [!UICONTROL Signal Dashboard] le permite crear nuevas características a partir de , [!UICONTROL Top Unused Signals]&#x200B;[!UICONTROL New Unused Signals]y de las búsquedas guardadas.

Cuando se crea un rasgo nuevo, el tipo de rasgo se preconfigura en función del tipo de señal:

* **[!UICONTROL Rule-based]** características para señales en tiempo real, archivos de registro procesables y [!DNL Adobe Analytics] señales;

* **[!UICONTROL Onboarded]** características para señales integradas.

Para crear nuevas características a partir del **[!UICONTROL Signal Dashboard]**, identifique la señal que desea utilizar en la característica y, a continuación, haga clic en la vincular **[!UICONTROL Create Rule-Based Trait]** o **[!UICONTROL Create Onboarded Trait]** correspondiente.

![](assets/signals-create-trait.png)

Se le redirigirá al Generador **[de](../../features/traits/about-trait-builder.md)** rasgos para crear su(s) nuevo(s) rasgo(s).

## Crear Características de Signal Search {#create-traits-from-signal-search}

Crear características basadas en señales usadas o no utilizadas que no se muestran en el [!UICONTROL Signal Dashboard]archivo .

Search para señales específicas y crear rasgos basados en regla o incorporados en función de los resultados. A continuación, le indicamos cómo hacerlo:

1. Vaya y **[!UICONTROL Audience Data > Signals > Search]** ejecute un búsqueda basado en los pares clave-valor que está buscando, o haga clic **[!UICONTROL Search]** sin introducir ningún par clave-valor para mostrar todos los resultados.
2. Identifique las señales que desea utilizar en el rasgo, en los resultados lista.
   * Para crear un rasgo a partir de una señal, haga clic en la correspondiente **[!UICONTROL Create Rule-Based Trait]** o **[!UICONTROL Create Onboarded Trait]** vincular.
   * Para crear un rasgo a partir de varias señales, haga clic en la casilla de verificación correspondiente de cada señal y, a continuación, haga clic en **[!UICONTROL Create Trait from Multiple Signals]**.

   >[!NOTE]
   >Solo se pueden crear rasgos a partir de señales del mismo tipo. No se puede crear un rasgo basándose en una combinación de una señal en tiempo real y otra integrada.
   >
   > ![](assets/signals-create-trait-search.png)
   >También puede crear características a partir de señales usadas. Las señales que ya se utilizan en rasgos tienen el número de características que se muestran en la **[!UICONTROL Included in Traits]** columna. Haga clic en la flecha para ver los rasgos que incluyen la señal.
   >
   >![](assets/signals-used-traits.png)

3. Utilice el generador **[de](../../features/traits/about-trait-builder.md)** rasgos para crear sus nuevos rasgos.
