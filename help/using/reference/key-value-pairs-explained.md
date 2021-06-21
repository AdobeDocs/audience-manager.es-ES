---
description: Define y describe pares de clave-valor estándar y serializados.
keywords: integration code
seo-description: Define y describe pares de clave-valor estándar y serializados.
seo-title: Pares de clave-valor explicados
solution: Audience Manager
title: Pares de clave-valor explicados
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: 'Referencia '
exl-id: de4e6fdb-2d6d-4fed-9255-9438b42b2570
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 7%

---

# Pares de clave-valor explicados{#key-value-pairs-explained}

Define y describe pares de clave-valor estándar y serializados.

<!-- 

c_key_value_explained.xml

 -->

Un par clave-valor consta de dos elementos de datos relacionados: Clave, que es una constante que define el conjunto de datos (por ejemplo, sexo, color, precio) y un valor, que es una variable que pertenece al conjunto (por ejemplo, hombre/mujer, verde, 100). Totalmente formado, un par clave-valor podría tener el siguiente aspecto:

* `gender = male`
* `color = green`
* `price > 100`

## Pares de clave-valor estándar y serializados {#standard-serialized-pairs}

Los destinos aceptan datos de clave-valor en formato *`standard`* o *`serialized`* . El formato estándar organiza los datos en pares clave-valor independientes. Cada clave se indica explícitamente, incluso cuando se utiliza de nuevo para definir un valor diferente. Por el contrario, el formato serializado condensa varios valores en un conjunto definido por una sola clave. Además, en un par serializado, se utiliza un indicador especial para separar los valores dentro del conjunto clave-valor. Por último, los valores de clave estándar y serializados pueden contener uno o varios valores. En la tabla siguiente se proporcionan ejemplos de formatos de clave-valor estándar y serie.

| Formato | Clave única | Pares de clave-valor |
|---|---|---|
| **Estándar** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serializado** | `x=1;2` | `x=1;2&y=3;4` |



## Claves, delimitadores y separadores {#keys-delimiters-separators}

Al trabajar con datos serializados, debe especificar los caracteres que separan los valores *dentro de* y *entre* los pares clave-valor. Los elementos de pares clave-valor se definen de la siguiente manera:

* **Clave:**  identificador único en el par clave-valor.
* **Delimitador de valores:** separa pares de clave-valor individuales.
* **Separador clave-valor:** separa una clave de los valores de un par clave-valor.
* **Separador de serie:** separa valores individuales dentro de pares de clave-valor serializados.

## Elementos de clave-valor estándar y serializados {#standard-serialized-key-value-elements}


| Tipo | Ejemplo | Clave | Separador de clave-valor | Delimitador de clave-valor | Separador serie |
|---------|----------|---------|---------|----------|---------|
| **Clave única**  (estándar) | `x=1&x=2` | `x` | `=` | `&` | n.d. |
| **Pares clave-valor**  (estándar) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | n.d. |
| **Clave única**  (serie) | `x=1;2;3` | `x` | `=` | n.d. | `;` |
| **Pares clave-valor**  (serie) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
