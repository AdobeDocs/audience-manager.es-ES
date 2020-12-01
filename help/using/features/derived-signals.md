---
description: Una señal derivada califica a los visitantes del sitio para características adicionales según una característica que ya han visto. En otras palabras, la calificación de rasgos adicionales puede derivarse de una característica exhibida actualmente, incluso si un usuario nunca ha visto la nueva característica antes.
seo-description: Una señal derivada califica a los visitantes del sitio para características adicionales según una característica que ya han visto. En otras palabras, la calificación de rasgos adicionales puede derivarse de una característica exhibida actualmente, incluso si un usuario nunca ha visto la nueva característica antes.
seo-title: Señales derivadas
solution: Audience Manager
title: Señales derivadas
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 2%

---


# Señales derivadas {#derived-signals}

Un [!UICONTROL derived signal] califica a los visitantes del sitio para características adicionales según una característica que ya han visto. En otras palabras, la calificación de rasgos adicionales puede derivarse de una característica exhibida actualmente, incluso si un usuario nunca ha visto la nueva característica antes.

<!-- c_tb_derived_signal.xml -->

## Finalidad de las señales derivadas

En [!DNL Audience Manager], puede crear una relación entre las señales (o reglas de características) pasadas durante una llamada de evento a otras señales o características especificadas. Por ejemplo, supongamos que una llamada de evento pasa en una señal compuesta por el valor clave [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] conectaría esa señal a cualquier otro usuario creado con la  [!UICONTROL derived signals] herramienta. Aunque las señales asociadas pueden ser cualquier valor clave que especifique, son más útiles cuando se vinculan a señales existentes ya configuradas como reglas [!UICONTROL Trait Builder]. Por ejemplo, en la siguiente ilustración, cuando una acción del usuario activa la señal [!DNL "product = new car"], ese usuario también puede calificar para características definidas por las señales de valor y clave de destinatario.

![](assets/derived_signal_example.png)

## Ubicación de señales derivadas

Cree y administre [!UICONTROL derived signals] en **[!UICONTROL Tools > Derived Signals]** desde la navegación de la barra lateral.

## Crear una señal derivada {#create}

<!-- t_tb_create_derived.xml -->

Para crear un [!UICONTROL derived signal]:

1. Seleccione **[!UICONTROL Derived Signals]** en el menú [!UICONTROL Tools].
1. Proporcione una:
   * *(Opcional)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Haga clic **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>El límite de caracteres para los campos [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key] y [!UICONTROL Target Value] es de 228 caracteres.

## Editar una señal derivada {#edit}

<!-- t_tb_edit_derived.xml -->

Para editar un [!UICONTROL derived signal]:

1. Pase el ratón sobre la señal y haga clic en **[!UICONTROL Edit]**.
2. Realice los cambios necesarios en el código, clave o valor, luego haga clic en **[!UICONTROL Save]**.

## Eliminar una señal derivada {#delete}

<!-- t_tb_delete_derived.xml -->

Para eliminar un [!UICONTROL derived signal], pase el ratón sobre la señal y haga clic en **[!UICONTROL Delete]**.
