---
description: Audience Manager establece un límite máximo para el número de características, segmentos, destinos y modelos algorítmicos que se pueden crear para una cuenta. Estos elementos se aplican límites tanto si se crean en la interfaz del usuario como mediante programación mediante métodos de API. Los límites de uso ayudan a proteger Audience Manager de procesos automatizados que pueden intentar comprometer nuestras API o usuario interfaz.
seo-description: Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through API methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our APIs or user interface.
seo-title: Usage Limits
solution: Audience Manager
title: Límites de uso
keywords: Asignación de ID, asignaciones de ID cookie asignaciones
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
exl-id: 8d29e231-d369-44ad-8e89-e6a4c83175f2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 4%

---

# Límites de uso {#usage-limits}

Audience Manager establece un límite máximo para el número de características, segmentos, destinos y modelos algorítmicos que se pueden crear para una cuenta. Los límites se aplican a estos elementos, tanto si se crean en la interfaz del usuario como mediante programación, mediante [!DNL API] métodos. Los límites de uso ayudan a proteger Audience Manager de procesos automatizados que pueden intentar comprometer nuestra [!DNL API]interfaz s o usuario.

## Límites de asignación de ID {#id-mapping-limits}

La tabla a continuación muestra los límites de asignación[&#x200B; de &#x200B;](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)ID para ID de dispositivos. Una vez que un ID alcanza cualquiera de los límites siguientes, Audience Manager agrega nuevas asignaciones de ID basadas en una lógica FIFO (primero en entrar, primero en salir), eliminando la asignación de ID almacenada más antigua y agregando la nueva. Consulte Index [de ID](../../reference/ids-in-aam.md) en Audience Manager para obtener detalles sobre los ID admitidos por Audience Manager.

| Asignación de ID | Límite máximo |
|-----------|-------------- |
| ID de publicidad de dispositivo ([DAID)](../../reference/ids-in-aam.md) a ID de dispositivos cruzado ([DPUUID)](../../reference/ids-in-aam.md) | 100 ID de publicidad de dispositivo ([DAID)](../../reference/ids-in-aam.md) a 1 ID dispositivos cruzado ([DPUUID)](../../reference/ids-in-aam.md) |
| ID dispositivos cruzado ([DPUUID)](../../reference/ids-in-aam.md) a ID de publicidad de dispositivo ([DAID)](../../reference/ids-in-aam.md) | 10 ID de dispositivos cruzado ([DPUUID)](../../reference/ids-in-aam.md) a un ID de publicidad de dispositivo ([DAID),](../../reference/ids-in-aam.md) por cada [DPID](../../reference/ids-in-aam.md) |
| ID de cookie/explorador a ID de cookie/explorador | 1000 ID de cookie/explorador a 1 ID de cookie/explorador |

## Límites de artículos {#item-limits}

Las tablas lista los límites actuales por tipo de elemento. No puede crear nuevas características, segmentos o destinos, o [!UICONTROL Algorithmic Models] si alcanza un límite específico para uno de estos elementos. Si llega a un límite, debe eliminar un elemento antiguo para poder crear uno nuevo.

### Límites de rasgos

| Tipo de rasgo | Límite máximo |
| -------------------------- | ------------------------------------- |
| Características totales | 100.000 |
| Total de cualificaciones de rasgos | 150,000. Para obtener más información sobre la cualificación de rasgos, consulte Límite de calificación de rasgos en [Referencia](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit) de cualificaciones de rasgos. |
| Algorítmico | 50 |
| Basado en reglas | 100.000 |
| Incorporado | 100.000 |
| Características Carpeta | 2.000 |

### Límites de segmento

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

### Límites del modelo algorítmico

| Elemento | Límite máximo |
| -------- | ----- |
| Activo [!UICONTROL Look-Alike Models] | &#x200B;20. Audience Manager solo cuenta *los modelos algorítmicos activos* contra el límite. |
| [!UICONTROL Look-Alike Models] Tamaño máximo audiencia | 25,000,000.  Tenga en cuenta que este límite no se puede ampliar. Puede reducir el tamaño de audiencia seleccionando menos orígenes de datos para el modelo o seleccionando un período de retrospectiva más corto. |
| Número máximo de características excluidas para un [!UICONTROL Look-Alike Model] | &#x200B;500. Consulte [Exclusión de rasgos en Modelado](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md) algorítmico. |
| Máximo [!UICONTROL Predictive Audiences Models] | 10 |
| Número máximo de perfiles de línea de base para [!UICONTROL Predictive Audiences Models] | 50 |

### Límites Carpeta

| Elemento | Límite máximo |
| ------------- | ------------------ |
| Carpetas de rasgos | 2,000.  La estructura de carpetas puede tener un máximo de 5 niveles. |

### Límites de señales derivadas

| Elemento | Límite máximo |
| --------------- | ------------- |
| Señales derivadas | 50,000. |

### Límite de cuentas de usuario de la empresa

| Elemento | Límite máximo |
| ----------- | ------------- |
| Número máximo de cuentas de usuario para una compañía | 1,000. |

## Supervisar el uso {#monitor-usage}

Puede ver el uso y los límites de su cuenta en **[!UICONTROL Administration > Limits]**. El acceso requiere permisos de administrador.

![Imagen de límites de uso](assets/usage-limits.png)

## Aumentar los límites de artículos {#increase-item-limits}

Los límites predeterminados que se enumeran aquí deben proporcionar capacidad suficiente para las necesidades empresariales. Si su organización alcanza estos límites constantemente, comuníquese con su representante de cuenta para discutir un aumento.
