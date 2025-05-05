---
description: Cree nuevos rasgos a partir de todas las señales, incluidos los que ya se utilizan en rasgos, y capture audiencias futuras que se clasifiquen después de la creación de rasgos.
seo-description: Create new traits from all signals, including those that are already used in traits, and capture future audiences that qualify after trait creation.
seo-title: Create Traits from Signals
title: Crear rasgos a partir de señales
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: Data Explorer
exl-id: 14308ef0-58eb-4b76-858c-d0da560f55fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Crear rasgos a partir de señales

Cree nuevos rasgos a partir de todas las señales, incluidos los que ya se utilizan en rasgos, y capture audiencias futuras que se clasifiquen después de la creación de rasgos. Vea el vídeo para ver una demostración rápida o siga leyendo para obtener información detallada:

>[!VIDEO](https://video.tv.adobe.com/v/327529/?quality=12&captions=spa)

## Crear rasgos del panel de señales {#create-traits-from-signal-dashboard}

[!UICONTROL Signal Dashboard] le permite crear nuevas características a partir de [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals] y las búsquedas guardadas.

Cuando se crea un nuevo rasgo, el tipo de rasgo está preestablecido en función del tipo de señal:

* **[!UICONTROL Rule-based]** rasgos para señales en tiempo real, archivos de registro procesables y señales [!DNL Adobe Analytics];

* **[!UICONTROL Onboarded]** rasgos para señales incorporadas.

Para crear nuevas características a partir de **[!UICONTROL Signal Dashboard]**, identifique la señal que desee usar en la característica y, a continuación, haga clic en el vínculo **[!UICONTROL Create Rule-Based Trait]** o **[!UICONTROL Create Onboarded Trait]** correspondiente.

![](assets/signals-create-trait.png)

Se le redirigirá al **[Generador de características](../../features/traits/about-trait-builder.md)** para crear sus nuevas características.

## Crear rasgos a partir de búsqueda de señales {#create-traits-from-signal-search}

Crear rasgos basados en señales utilizadas o no utilizadas que no se muestran en [!UICONTROL Signal Dashboard].

Busque señales específicas y cree rasgos basados en reglas o incorporados en función de los resultados. A continuación se indica cómo hacerlo:

1. Vaya a **[!UICONTROL Audience Data > Signals > Search]** y ejecute una búsqueda basada en los pares clave-valor que está buscando, o haga clic en **[!UICONTROL Search]** sin especificar ningún par clave-valor para mostrar todos los resultados.
2. Identifique las señales que desee utilizar en el rasgo en la lista de resultados.
   * Para crear un rasgo a partir de una señal, haga clic en el vínculo **[!UICONTROL Create Rule-Based Trait]** o **[!UICONTROL Create Onboarded Trait]** correspondiente.
   * Para crear un rasgo a partir de varias señales, haga clic en la casilla de verificación correspondiente de cada señal y, a continuación, haga clic en **[!UICONTROL Create Trait from Multiple Signals]**.

   >[!NOTE]
   >Solo puede crear rasgos a partir de señales del mismo tipo. No se puede crear un rasgo basado en una combinación de una señal en tiempo real y una incorporada.
   >
   > ![](assets/signals-create-trait-search.png)
   >También puede crear rasgos a partir de señales utilizadas. Las señales que ya se utilizan en características muestran el número de características en la columna **[!UICONTROL Included in Traits]**. Haga clic en la flecha para ver los rasgos que incluyen la señal.
   >
   >![](assets/signals-used-traits.png)

3. Use **[Generador de características](../../features/traits/about-trait-builder.md)** para crear las nuevas características.
