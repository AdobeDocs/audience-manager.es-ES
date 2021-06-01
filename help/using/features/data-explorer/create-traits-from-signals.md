---
description: Cree nuevas características a partir de todas las señales, incluidas las que ya se hayan utilizado en características, y capture las audiencias futuras que cumplen los requisitos después de la creación de características.
seo-description: Cree nuevas características a partir de todas las señales, incluidas las que ya se hayan utilizado en características, y capture las audiencias futuras que cumplen los requisitos después de la creación de características.
seo-title: Crear rasgos a partir de señales
title: Crear rasgos a partir de señales
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: 'Explorador de datos '
exl-id: 14308ef0-58eb-4b76-858c-d0da560f55fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%

---

# Crear rasgos a partir de señales

Cree nuevas características a partir de todas las señales, incluidas las que ya se hayan utilizado en características, y capture las audiencias futuras que cumplen los requisitos después de la creación de características. Vea el vídeo para ver una demostración rápida o lea la información detallada:

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## Crear rasgos a partir del panel de señales {#create-traits-from-signal-dashboard}

El [!UICONTROL Signal Dashboard] permite crear nuevos rasgos a partir de [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals] y las búsquedas guardadas.

Cuando se crea un nuevo rasgo, el tipo de rasgo se establece previamente en función del tipo de señal:

* **[!UICONTROL Rule-based]** características para señales en tiempo real, archivos de registro procesables y  [!DNL Adobe Analytics] señales;

* **[!UICONTROL Onboarded]** características para señales incorporadas.

Para crear nuevas características a partir de **[!UICONTROL Signal Dashboard]**, identifique la señal que desee utilizar en la característica y, a continuación, haga clic en el enlace **[!UICONTROL Create Rule-Based Trait]** o **[!UICONTROL Create Onboarded Trait]** correspondiente.

![](assets/signals-create-trait.png)

Se le redirigirá al **[Generador de rasgos](../../features/traits/about-trait-builder.md)** para crear sus nuevos rasgos.

## Crear rasgos a partir de la búsqueda de señales {#create-traits-from-signal-search}

Cree rasgos basados en señales utilizadas o no utilizadas que no se muestren en el [!UICONTROL Signal Dashboard].

Busque señales específicas y cree rasgos basados en reglas o integrados según los resultados. A continuación se muestra cómo hacerlo:

1. Vaya a **[!UICONTROL Audience Data > Signals > Search]** y ejecute una búsqueda basada en los pares clave-valor que está buscando, o haga clic en **[!UICONTROL Search]** sin introducir ningún par clave-valor para mostrar todos los resultados.
2. Identifique las señales que desee utilizar en la lista de resultados.
   * Para crear un rasgo a partir de una señal, haga clic en el enlace **[!UICONTROL Create Rule-Based Trait]** o **[!UICONTROL Create Onboarded Trait]** correspondiente.
   * Para crear un rasgo a partir de varias señales, haga clic en la casilla de verificación correspondiente de cada señal y, a continuación, haga clic en **[!UICONTROL Create Trait from Multiple Signals]**.

   >[!NOTE]
   >Solo se pueden crear rasgos a partir de señales del mismo tipo. No se puede crear un rasgo basado en una combinación de una señal en tiempo real y una señal incorporada.
   >
   > ![](assets/signals-create-trait-search.png)
   >También puede crear características a partir de señales usadas. Las señales que ya se utilizan en rasgos tienen el número de rasgos mostrado en la columna **[!UICONTROL Included in Traits]**. Haga clic en la flecha para ver los rasgos que incluyen la señal.
   >
   >![](assets/signals-used-traits.png)

3. Utilice el **[Generador de rasgos](../../features/traits/about-trait-builder.md)** para crear las nuevas características.
