---
description: Audience Manager establece un límite máximo de características, segmentos, destinos y modelos algorítmicos que puede crear para una cuenta. Los límites se aplican a estos elementos tanto si se crean en la interfaz de usuario como si son programados mediante métodos API. Los límites de uso ayudan a proteger Audience Manager desde procesos automatizados que pueden intentar poner en peligro nuestras API o interfaz de usuario.
seo-description: Audience Manager establece un límite máximo de características, segmentos, destinos y modelos algorítmicos que puede crear para una cuenta. Los límites se aplican a estos elementos tanto si se crean en la interfaz de usuario como si son programados mediante métodos API. Los límites de uso ayudan a proteger Audience Manager desde procesos automatizados que pueden intentar poner en peligro nuestras API o interfaz de usuario.
seo-title: Límites de uso
solution: Audience Manager
title: Límites de uso
keywords: Asignación de ID, asignaciones de ID, asignaciones de cookies
uuid: 50 ca 4647-0 b 5 c -409 c -89 fa -4 fa 1799 b 3222
translation-type: tm+mt
source-git-commit: d893998e9e59dbce64195a167e267c6f7ed16f90

---


# Límites de uso {#usage-limits}

Audience Manager establece un límite máximo de características, segmentos, destinos y modelos algorítmicos que puede crear para una cuenta. Los límites se aplican a estos elementos tanto si se crean en la interfaz de usuario como si son programados mediante [!DNL API] métodos. Los límites de uso ayudan a proteger Audience Manager desde procesos automatizados que pueden intentar poner en peligro nuestra [!DNL API]interfaz de usuario o s.

## Límites de asignación de ID {#id-mapping-limits}

La tabla siguiente enumera los límites [de asignación](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) de ID para los ID de dispositivos. Cuando un ID alcance alguno de los límites siguientes, Audience Manager agrega nuevas asignaciones de ID basadas en una lógica [!DNL FIFO] (primer, primer out), eliminando la asignación de ID almacenada más antigua y agrega la nueva. Consulte [Índice de ID](../../reference/ids-in-aam.md) en Audience Manager para obtener más detalles sobre los ID admitidos por Audience Manager.

| Asignación de ID | Límite máximo |
|-----------|-------------- |
| ID de publicidad de dispositivo (DAID) en ID entre dispositivos (ID de CRM) | 100 ID de publicidad de dispositivo (DAID) a 1 ID de dispositivo múltiple (ID de CRM) |
| ID entre dispositivos (ID de CRM) al ID de publicidad de dispositivo (DAID) | 10 ID entre dispositivos (ID de CRM) a 1 ID de publicidad de dispositivo (DAID) |
| ID de cookie y explorador a ID de cookie/navegador | 1000 ID de cookies y exploradores a 1 cookie/ID de explorador |

## Límites de elementos {#item-limits}

Las tablas enumeran los límites actuales por tipo de elemento. No se pueden crear nuevas características, segmentos, destinos ni [!UICONTROL Algorithmic Models] si se alcanza un límite específico para uno de estos elementos. Si llega a un límite, debe eliminar un elemento anterior para poder crear uno nuevo.

### Límites de características

| Tipo de característica | Límite máximo |
| -------------------------- | ------------------------------------- |
| Características totales | 100,000 |
| Requisitos totales de características | 150,000. Para obtener más información sobre la cualificación de características, consulte Límite de cualificación de características en [Referencia de características de características](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit). |
| Algorítmico | 50 |
| Basado en reglas | 100,000 |
| Onbogged | 100,000 |
| Características de carpeta | 2,000 |

### Límites de segmentos

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

### Límites del modelo algorítmico

| Elemento | Límite máximo |
| -------- | ----- |
| Modelos algorítmicos activos | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| Modelos algorítmicos máximos de audiencia | 25,000,000.  Tenga en cuenta que no se puede aumentar este límite. Puede reducir los tamaños de audiencia seleccionando menos fuentes de datos para el modelo o seleccionando una ventana de retroceso más corta. |
| Número máximo de características excluidas para un modelo | 500. Consulte [Exclusión de rasgos en el modelado algorítmico](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |

### Límites de carpetas

| Elemento | Límite máximo |
| ------------- | ------------------ |
| Carpetas de características | 2,000.  La estructura de carpetas puede ser máxima de 5 niveles. |

### Límites de señales derivadas

| Elemento | Límite máximo |
| --------------- | ------------- |
| Señales derivadas | 50 000. |

### Límite de cuentas de usuario de la empresa

| Elemento | Límite máximo |
| ----------- | ------------- |
| Número máximo de cuentas de usuario para una empresa | 1000. |

## Uso del monitor {#monitor-usage}

Para ver el uso y los límites de su cuenta, vaya **[!UICONTROL Administration > Limits]** a. El acceso requiere permisos de administrador.

![límite de uso de imagen](assets/usage-limits.png)

## Aumentar límites de elementos {#increase-item-limits}

Los límites predeterminados enumerados aquí deben proporcionar suficiente capacidad como para sus necesidades comerciales. Si su organización supera constantemente estos límites, comuníquese con el representante de cuentas para analizar un aumento.