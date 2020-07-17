---
description: El Audience Manager establece un límite máximo en el número de características, segmentos, destinos y modelos algorítmicos que puede crear para una cuenta. Los límites se aplican a estos elementos, tanto si se crean en la interfaz de usuario como mediante métodos de API. Los límites de uso ayudan a proteger al Audience Manager de los procesos automatizados que pueden intentar comprometer nuestras API o interfaz de usuario.
seo-description: El Audience Manager establece un límite máximo en el número de características, segmentos, destinos y modelos algorítmicos que puede crear para una cuenta. Los límites se aplican a estos elementos, tanto si se crean en la interfaz de usuario como mediante métodos de API. Los límites de uso ayudan a proteger al Audience Manager de los procesos automatizados que pueden intentar comprometer nuestras API o interfaz de usuario.
seo-title: Límites de uso
solution: Audience Manager
title: Límites de uso
keywords: ID mapping, ID mappings, cookie mappings
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 6%

---


# Límites de uso {#usage-limits}

El Audience Manager establece un límite máximo en el número de características, segmentos, destinos y modelos algorítmicos que puede crear para una cuenta. Los límites se aplican a estos elementos, tanto si se crean en la interfaz de usuario como mediante [!DNL API] métodos programáticos. Los límites de uso ayudan a proteger al Audience Manager de los procesos automatizados que pueden intentar poner en peligro nuestra interfaz [!DNL API]de usuario o de usuario.

## Límites de asignación de ID {#id-mapping-limits}

La siguiente tabla lista los límites de asignación [de](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) ID para los ID de dispositivo. Una vez que un ID alcanza cualquiera de los límites siguientes, el Audience Manager agrega nuevas asignaciones de ID basadas en una lógica [!DNL FIFO] (primero en, primero en salir), eliminando la asignación de ID almacenada más antigua y agregando la nueva. Consulte [Índice de IDs](../../reference/ids-in-aam.md) en Audience Manager para obtener detalles sobre los ID admitidos por el Audience Manager.

| Asignación de ID | Límite máximo |
|-----------|-------------- |
| ID de publicidad del dispositivo ([DAID](../../reference/ids-in-aam.md)) al ID entre dispositivos ([DPUUID](../../reference/ids-in-aam.md)) | 100 ID de publicidad de dispositivo ([DAID](../../reference/ids-in-aam.md)) a 1 ID de dispositivo cruzado ([DPUUID](../../reference/ids-in-aam.md)) |
| ID entre dispositivos ([DPUUID](../../reference/ids-in-aam.md)) e ID de publicidad del dispositivo ([DAID](../../reference/ids-in-aam.md)) | 10 ID entre dispositivos ([DPUUID](../../reference/ids-in-aam.md)) a 1 ID de publicidad de dispositivo ([DAID](../../reference/ids-in-aam.md)) por cada [DPID](../../reference/ids-in-aam.md) |
| Cookie/ID del explorador a cookie/ID del explorador | 1000 ID de cookie/explorador a 1 ID de cookie/explorador |

## Límites de elementos {#item-limits}

Las tablas lista los límites actuales por tipo de elemento. No se pueden crear nuevas características, segmentos, destinos ni [!UICONTROL Algorithmic Models] si se alcanza un límite específico para uno de estos elementos. Si alcanza un límite, debe eliminar un elemento anterior para poder crear uno nuevo.

### Límites de características

| Tipo de característica | Límite máximo |
| -------------------------- | ------------------------------------- |
| Características totales | 100,000 |
| Total de cualificaciones de características | 150,000. Para obtener más información sobre la cualificación de características, consulte Límite de cualificación de características en Referencia [de cualificaciones de](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit)características. |
| Algoritmo | 50 |
| Basado en reglas | 100,000 |
| Integrado | 100,000 |
| Características de la carpeta | 2,000 |

### Límites de segmento

| Tipo de segmento | Límite máximo |
| -------------- | ------------- |
| Total de segmentos | 20,000 |

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
| Modelos algorítmicos activos | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| Modelos algorítmicos tamaño máximo de audiencia | 25,000,000.  Tenga en cuenta que este límite no se puede aumentar. Puede reducir los tamaños de audiencia seleccionando menos fuentes de datos para el modelo o seleccionando una ventana retroactiva más corta. |
| Número máximo de características excluidas para un modelo | 500. Consulte Exclusión [de características en modelado](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)algorítmico. |

### Límites de carpetas

| Elemento | Límite máximo |
| ------------- | ------------------ |
| Carpetas de características | 2,000.  La estructura de carpetas puede tener un máximo de 5 niveles de profundidad. |

### Límites de señales derivadas

| Elemento | Límite máximo |
| --------------- | ------------- |
| Señales derivadas | 50 000. |

### Límite de cuentas de usuario de Compañía

| Elemento | Límite máximo |
| ----------- | ------------- |
| Número máximo de cuentas de usuario para una compañía | 1000. |

## Monitoreo del uso {#monitor-usage}

Puede ver el uso y los límites de su cuenta si ingresa a **[!UICONTROL Administration > Limits]**. Access requiere permisos de administrador.

![el uso limita la imagen](assets/usage-limits.png)

## Aumentar límites de elementos {#increase-item-limits}

Los límites predeterminados que se indican aquí deben proporcionar suficiente capacidad para sus necesidades comerciales. Si su organización alcanza estos límites de manera consistente, póngase en contacto con el representante de cuentas para discutir un aumento.