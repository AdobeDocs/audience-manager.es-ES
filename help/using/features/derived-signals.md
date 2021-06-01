---
description: Una señal derivada califica a los visitantes del sitio para rasgos adicionales en función de un rasgo que ya han visto. En otras palabras, la calificación de características adicionales puede derivarse de un rasgo que se muestra actualmente, incluso aunque un usuario nunca haya visto el nuevo rasgo antes.
seo-description: Una señal derivada califica a los visitantes del sitio para rasgos adicionales en función de un rasgo que ya han visto. En otras palabras, la calificación de características adicionales puede derivarse de un rasgo que se muestra actualmente, incluso aunque un usuario nunca haya visto el nuevo rasgo antes.
seo-title: Señales derivadas
solution: Audience Manager
title: Señales derivadas
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: 'Rasgos '
exl-id: 64bc004a-a31a-49bb-aa58-323fbc92f76f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 2%

---

# Señales derivadas {#derived-signals}

Un [!UICONTROL derived signal] califica a los visitantes del sitio para rasgos adicionales en función de un rasgo que ya han visto. En otras palabras, la calificación de características adicionales puede derivarse de un rasgo que se muestra actualmente, incluso aunque un usuario nunca haya visto el nuevo rasgo antes.

<!-- c_tb_derived_signal.xml -->

## Objetivo de las señales derivadas

En [!DNL Audience Manager], puede crear una relación entre las señales (o reglas de rasgos) pasadas durante una llamada de evento a otras señales o rasgos especificados. Por ejemplo, supongamos que una llamada de evento pasa una señal compuesta por el valor clave [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] conectaría esa señal a cualquier otra persona creada con la  [!UICONTROL derived signals] herramienta. Aunque las señales asociadas pueden ser cualquier valor clave que especifique, son más útiles cuando se vinculan a señales existentes ya configuradas como reglas [!UICONTROL Trait Builder]. Por ejemplo, en la siguiente ilustración, cuando una acción del usuario activa la señal [!DNL "product = new car"] , ese usuario también puede calificar para características definidas por la clave de destino y las señales de valor.

![](assets/derived_signal_example.png)

## Ubicación de las señales derivadas

Cree y administre [!UICONTROL derived signals] en **[!UICONTROL Tools > Derived Signals]** desde la navegación de la barra lateral.

## Crear una señal derivada {#create}

<!-- t_tb_create_derived.xml -->

Para crear un [!UICONTROL derived signal]:

1. Seleccione **[!UICONTROL Derived Signals]** en el menú [!UICONTROL Tools].
1. Proporcione un:
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
2. Realice los cambios necesarios en el código, clave o valor y, a continuación, haga clic en **[!UICONTROL Save]**.

## Eliminar una señal derivada {#delete}

<!-- t_tb_delete_derived.xml -->

Para eliminar un [!UICONTROL derived signal], pase el ratón sobre la señal y haga clic en **[!UICONTROL Delete]**.
