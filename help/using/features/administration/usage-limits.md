---
description: Audience Manager establece un límite máximo en el número de características, segmentos, destinos y modelos algorítmicos que puede crear para una cuenta. Los límites se aplican a estos elementos tanto si se crean en la interfaz de usuario como mediante programación a través de métodos API. Los límites de uso ayudan a proteger Audience Manager de procesos automatizados que pueden intentar poner en peligro nuestras API o interfaz de usuario.
seo-description: Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through API methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our APIs or user interface.
seo-title: Usage Limits
solution: Audience Manager
title: Límites de uso
keywords: Asignación de ID, asignaciones de ID, asignaciones de cookies
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
exl-id: 8d29e231-d369-44ad-8e89-e6a4c83175f2
TQID: https://experienceleague.adobe.com/hyvYo82mjW-ZK5zn5nVzeQNavwIYTnd8LsjpNjiHofs
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baaid: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: c814092e-2730-45e8-a12d-e084529f52cbid: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: d12f0729-c5e9-4a4a-bb39-687f9ab4a97cid: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 530
ht-degree: 4%

---

# Límites de uso {#usage-limits}

Audience Manager establece un límite máximo en el número de características, segmentos, destinos y modelos algorítmicos que puede crear para una cuenta. Los límites se aplican a estos elementos tanto si se crean en la interfaz de usuario como mediante programación a través de [!DNL API] métodos. Los límites de uso ayudan a proteger Audience Manager de procesos automatizados que podrían intentar poner en peligro nuestra interfaz de usuario o [!DNL API].

## Límites de ID Mapping {#id-mapping-limits}

En la tabla siguiente se enumeran los límites de [asignación de ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) para los ID de dispositivo. Una vez que un ID alcanza cualquiera de los límites siguientes, Audience Manager añade nuevas asignaciones de ID basadas en una lógica FIFO (primera entrada, primera salida), eliminando la asignación de ID almacenada más antigua y agregando la nueva. Consulte [Índice de ID](../../reference/ids-in-aam.md) en Audience Manager para obtener más información sobre los ID compatibles con Audience Manager.

| Asignación de ID | Límite máximo |
|-----------|-------------- |
| ID de Advertising de dispositivo ([DAID](../../reference/ids-in-aam.md)) a ID entre dispositivos ([DPUUID](../../reference/ids-in-aam.md)) | 100 ID de Advertising de dispositivo ([DAID](../../reference/ids-in-aam.md)) a 1 ID entre dispositivos ([DPUUID](../../reference/ids-in-aam.md)) |
| Id. entre dispositivos ([DPUUID](../../reference/ids-in-aam.md)) e ID de Advertising de dispositivo ([DAID](../../reference/ids-in-aam.md)) | 10 ID entre dispositivos ([DPUUID](../../reference/ids-in-aam.md)) a 1 ID de Advertising de dispositivo ([DAID](../../reference/ids-in-aam.md)), por cada [DPID](../../reference/ids-in-aam.md) |
| Cookie/ID de explorador a cookie/ID de explorador | 1000 ID de cookie/explorador a 1 ID de cookie/explorador |

## Límites de elementos {#item-limits}

En las tablas se enumeran los límites actuales por tipo de elemento. No puede crear características, segmentos, destinos o [!UICONTROL Algorithmic Models] nuevos si se alcanza un límite específico para uno de estos elementos. Si no alcanza el límite, debe eliminar un elemento antiguo para poder crear uno nuevo.

### Límites de rasgos

| Tipo de rasgo | Límite máximo |
| -------------------------- | ------------------------------------- |
| Características totales | 100.000 |
| Cualificaciones totales de rasgos | 150.000. Para obtener más información sobre la clasificación de características, consulte Límite de calificación de características en [Referencia de calificación de características](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit). |
| Algorítmico | 50 |
| Basado en reglas | 100.000 |
| Incorporado | 100.000 |
| Características de carpeta | 2.000 |

### Límites de segmentos

| Tipo de segmento | Límite máximo |
| -------------- | ------------- |
| Total de segmentos | 20.000 |

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
| Activo [!UICONTROL Look-Alike Models] | &#x200B;20. Audience Manager solo cuenta *modelos algorítmicos activos* respecto al límite. |
| [!UICONTROL Look-Alike Models] tamaño máximo de audiencia | 25.000.000.  Tenga en cuenta que este límite no se puede aumentar. Puede reducir el tamaño de la audiencia seleccionando menos fuentes de datos para el modelo o una ventana retrospectiva más corta. |
| Número máximo de rasgos excluidos para un(a) [!UICONTROL Look-Alike Model] | &#x200B;500. Consulte [Exclusión de características en el modelado algorítmico](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |
| Máximo [!UICONTROL Predictive Audiences Models] | 10 |
| Número máximo de personalidades de línea de base para [!UICONTROL Predictive Audiences Models] | 50 |

### Límites de carpetas

| Elemento | Límite máximo |
| ------------- | ------------------ |
| Carpetas de rasgos | 2.000.  La estructura de carpetas puede tener un máximo de 5 niveles. |

### Límites de señales derivadas

| Elemento | Límite máximo |
| --------------- | ------------- |
| Señales derivadas | 50.000. |

### Límite de cuentas de usuario de empresa

| Elemento | Límite máximo |
| ----------- | ------------- |
| Número máximo de cuentas de usuario para una compañía | MIL. |

## Monitorización del uso {#monitor-usage}

Puede ver el uso y los límites de su cuenta en **[!UICONTROL Administration > Limits]**. El acceso requiere permisos de administrador.

![imagen de límites de uso](assets/usage-limits.png)

## Aumentar límites de elementos {#increase-item-limits}

Los límites predeterminados enumerados aquí deben proporcionar suficiente capacidad para sus necesidades comerciales. Si su organización alcanza estos límites de forma constante, póngase en contacto con su representante de cuentas para discutir un aumento.
