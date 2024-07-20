---
description: Una señal derivada califica a los visitantes del sitio para rasgos adicionales en función de un rasgo que ya han visto. En otras palabras, la clasificación de rasgos adicional se puede derivar de un rasgo mostrado actualmente, incluso si un usuario nunca ha visto el nuevo rasgo antes.
seo-description: A derived signal qualifies site visitors for additional traits based on a trait they've already seen. In other words, additional trait qualification can be derived from a currently exhibited trait even if a user has never seen the new trait before.
seo-title: Derived Signals
solution: Audience Manager
title: Señales derivadas
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
exl-id: 64bc004a-a31a-49bb-aa58-323fbc92f76f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Señales derivadas {#derived-signals}

Un [!UICONTROL derived signal] clasifica a los visitantes del sitio para rasgos adicionales basados en un rasgo que ya han visto. En otras palabras, la clasificación de rasgos adicional se puede derivar de un rasgo mostrado actualmente, incluso si un usuario nunca ha visto el nuevo rasgo antes.

<!-- c_tb_derived_signal.xml -->

## Objetivo de las señales derivadas

En [!DNL Audience Manager], puede crear una relación entre las señales (o reglas de rasgos) pasadas durante una llamada de evento a otras señales o rasgos especificados. Por ejemplo, supongamos que una llamada de evento pasa una señal compuesta por el valor clave [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] conectaría esa señal a cualquier otra creada con la herramienta [!UICONTROL derived signals]. Aunque las señales asociadas pueden ser cualquier clave-valor que especifique, son más útiles cuando se vinculan a señales existentes ya configuradas como reglas de [!UICONTROL Trait Builder]. Por ejemplo, en la ilustración siguiente, cuando una acción del usuario activa la señal [!DNL "product = new car"], ese usuario también puede cumplir los requisitos para los rasgos definidos por las señales de clave y valor de destino.

![](assets/derived_signal_example.png)

## Ubicación de señales derivadas

Crear y administrar [!UICONTROL derived signals] en **[!UICONTROL Tools > Derived Signals]** desde la barra lateral de navegación.

## Crear una señal derivada {#create}

<!-- t_tb_create_derived.xml -->

Para crear un [!UICONTROL derived signal]:

1. Seleccione **[!UICONTROL Derived Signals]** del menú [!UICONTROL Tools].
1. Proporcione un:
   * *(Opcional)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Haga clic en **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>El límite de caracteres para los campos [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key] y [!UICONTROL Target Value] es de 228 caracteres.

## Editar una señal derivada {#edit}

<!-- t_tb_edit_derived.xml -->

Para editar [!UICONTROL derived signal]:

1. Pase el ratón sobre la señal y luego haga clic en **[!UICONTROL Edit]**.
2. Realice los cambios de código, clave o valor necesarios y, a continuación, haga clic en **[!UICONTROL Save]**.

## Eliminar una señal derivada {#delete}

<!-- t_tb_delete_derived.xml -->

Para eliminar un(a) [!UICONTROL derived signal], pase el ratón sobre la señal y haga clic en **[!UICONTROL Delete]**.
