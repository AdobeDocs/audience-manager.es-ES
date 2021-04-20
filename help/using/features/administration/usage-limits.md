---
description: El Audience Manager establece un límite máximo en el número de características, segmentos, destinos y modelos algorítmicos que puede crear para una cuenta. Los límites se aplican a estos elementos tanto si se crean en la interfaz de usuario como mediante programación a través de métodos API. Los límites de uso ayudan a proteger al Audience Manager de los procesos automatizados que pueden intentar poner en peligro nuestras API o interfaz de usuario.
seo-description: El Audience Manager establece un límite máximo en el número de características, segmentos, destinos y modelos algorítmicos que puede crear para una cuenta. Los límites se aplican a estos elementos tanto si se crean en la interfaz de usuario como mediante programación a través de métodos API. Los límites de uso ayudan a proteger al Audience Manager de los procesos automatizados que pueden intentar poner en peligro nuestras API o interfaz de usuario.
seo-title: Límites de uso
solution: Audience Manager
title: Límites de uso
keywords: Asignación de ID, asignaciones de ID, asignaciones de cookies
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
translation-type: tm+mt
source-git-commit: a696bc03e430e25e2752d84905009645c625d762
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 6%

---


# Límites de uso {#usage-limits}

El Audience Manager establece un límite máximo en el número de características, segmentos, destinos y modelos algorítmicos que puede crear para una cuenta. Los límites se aplican a estos elementos tanto si se crean en la interfaz de usuario como mediante programación a través de métodos [!DNL API]. Los límites de uso ayudan a proteger al Audience Manager de los procesos automatizados que pueden intentar comprometer nuestra [!DNL API]s o interfaz de usuario.

## Límites de asignación de ID {#id-mapping-limits}

En la tabla siguiente se enumeran los límites [ID mapping](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) para los ID de dispositivo. Una vez que un ID alcanza cualquiera de los límites siguientes, el Audience Manager agrega nuevas asignaciones de ID basadas en una lógica FIFO (primero en entrar, primero en salir), eliminando la asignación de ID almacenada más antigua y agregando la nueva. Consulte [Índice de ID](../../reference/ids-in-aam.md) en Audience Manager para obtener más información sobre los ID admitidos por el Audience Manager.

| Asignación de ID | Límite máximo |
|-----------|-------------- |
| ID de publicidad de dispositivo ([DAID](../../reference/ids-in-aam.md)) con ID entre dispositivos ([DPUUID](../../reference/ids-in-aam.md)) | 100 ID de publicidad de dispositivo ([DAID](../../reference/ids-in-aam.md)) a 1 ID entre dispositivos ([DPUUID](../../reference/ids-in-aam.md)) |
| ID entre dispositivos ([DPUUID](../../reference/ids-in-aam.md)) con ID de publicidad de dispositivo ([DAID](../../reference/ids-in-aam.md)) | 10 ID entre dispositivos ([DPUUID](../../reference/ids-in-aam.md)) a 1 ID de publicidad de dispositivo ([DAID](../../reference/ids-in-aam.md)), por cada [DPID](../../reference/ids-in-aam.md) |
| Cookie/ID de navegador a cookie/ID de navegador | 1000 ID de cookie/explorador a 1 ID de cookie/explorador |

## Límites de elementos {#item-limits}

En las tablas se enumeran los límites actuales por tipo de elemento. No puede crear nuevos rasgos, segmentos, destinos o [!UICONTROL Algorithmic Models] si alcanza un límite específico para uno de estos elementos. Si alcanza un límite, debe eliminar un elemento anterior antes de crear uno nuevo.

### Límites de rasgos

| Tipo de rasgo | Límite máximo |
| -------------------------- | ------------------------------------- |
| Características totales | 100.000 |
| Total de clasificaciones de rasgos | 150.000. Para obtener más información sobre la calificación de características, consulte Límite de calificación de características en [Referencia de cualificaciones de características](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit). |
| Algorítmico | 50 |
| Basado en reglas | 100.000 |
| Incorporado | 100.000 |
| Características de carpeta | 2.000 |

### Límites de segmentos

| Tipo de segmento | Límite máximo |
| -------------- | ------------- |
| Segmentos totales | 20.000 |

### Límites de destino

| Tipo de destino | Límite máximo |
| ------------------ | ------------- |
| Destinos totales | 1000 |
| Cookie | 1000 |
| URL | 1000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### Límites de modelo algorítmico

| Elemento | Límite máximo |
| -------- | ----- |
| Activo [!UICONTROL Look-Alike Models] | 20. El Audience Manager solo cuenta *modelos algorítmicos activos* con respecto al límite. |
| [!UICONTROL Look-Alike Models] tamaño máximo de audiencia | 25.000.000.  Tenga en cuenta que este límite no se puede aumentar. Puede reducir el tamaño de la audiencia seleccionando menos fuentes de datos para el modelo o seleccionando una ventana retrospectiva más corta. |
| Número máximo de rasgos excluidos para un [!UICONTROL Look-Alike Model] | 500. Consulte [Exclusión de características en el modelado algorítmico](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |
| Máximo [!UICONTROL Predictive Audiences Models] | 10 |
| Número máximo de personalidades de línea de base para [!UICONTROL Predictive Audiences Models] | 50 |

### Límites de carpetas

| Elemento | Límite máximo |
| ------------- | ------------------ |
| Carpetas de rasgos | 2.000.  La estructura de carpetas puede tener un máximo de 5 niveles de profundidad. |

### Límites de señales derivadas

| Elemento | Límite máximo |
| --------------- | ------------- |
| Señales derivadas | 50 000. |

### Límite de cuentas de usuario de la empresa

| Elemento | Límite máximo |
| ----------- | ------------- |
| Número máximo de cuentas de usuario de una empresa | 1000. |

## Uso del monitor {#monitor-usage}

Para ver el uso y los límites de su cuenta, vaya a **[!UICONTROL Administration > Limits]**. El acceso requiere permisos de administrador.

![imagen de límites de uso](assets/usage-limits.png)

## Aumentar límites de elementos {#increase-item-limits}

Los límites predeterminados que se enumeran aquí deben proporcionar suficiente capacidad para sus necesidades comerciales. Si su organización alcanza estos límites de forma coherente, póngase en contacto con su representante de cuentas para analizar un aumento.