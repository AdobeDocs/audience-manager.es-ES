---
description: Este artículo explica cómo configurar Audiencias adaptadas para Twitter tanto para integraciones nuevas como existentes.
seo-description: Este artículo explica cómo configurar Audiencias adaptadas para Twitter tanto para integraciones nuevas como existentes.
seo-title: Configurar audiencias adaptadas para Twitter como destino basado en dispositivos autoservicio
solution: Audience Manager
title: Configurar audiencias adaptadas para Twitter como destino basado en dispositivos autoservicio
translation-type: tm+mt
source-git-commit: 96717384ebb82056f330312b0f99fb97086a2e05

---


# Configurar [!DNL Twitter Tailored Audiences] como destino basado en dispositivo autoservicio {#configure-twitter}

Este artículo explica cómo configurar [Audiencias adaptadas para Twitter](https://business.twitter.com/en/targeting/tailored-audiences.html) tanto para integraciones nuevas como existentes.

## Requisitos previos {#prerequisites}

Antes de configurar [!DNL Twitter Tailored Audiences] el destino, asegúrese de revisar los siguientes requisitos previos de Twitter que necesita cumplir.

1. Su [!DNL Twitter Ads] cuenta debe ser calificada para publicidad. Las cuentas nuevas [!DNL Twitter Ads] no son elegibles para la publicidad en las dos primeras semanas después de crearlas.
2. La cuenta de usuario de Twitter a la que autorizó el acceso en Audience Manager debe tener habilitado el permiso [de administrador de audiencia](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) asociado.
3. Si [está actualizando la integración de Twitter existente a la administración de autoservicio](#update-existing-twitter-integrations), su cuenta de usuario de Twitter debe habilitar el permiso [de administrador](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) de publicidad.



## Agregar [!DNL Twitter Tailored Audiences] un nuevo destino {#add-new-twitter-destination}

Esta sección describe los pasos que debe seguir al configurar un nuevo destino basado en dispositivo para [!DNL Twitter Tailored Audiences]. Este escenario supone que no tiene ningún destino existente [!DNL Twitter Tailored Audiences] configurado por medio de su consultor de Adobe ni del Servicio de atención al cliente.

### Paso 1. Autenticar con [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Antes de agregar el destino basado en dispositivo, debe vincular Audience Manager y [!DNL Twitter Tailored Audiences] su cuenta. A continuación se muestra cómo hacer esto:

1. Inicie sesión en su cuenta de Audience Manager y vaya **[!DNL Administration > Integrated Accounts]** a. Si tiene una integración configurada previamente con una plataforma de destino, debería verlo en esta página. De lo contrario, la página está vacía.
2. Haga clic en **[!DNL Add Account]**.
3. Seleccione [!DNL Twitter Tailored Audiences] y haga clic **[!DNL Confirm]** para que se le redirija a la página de autenticación. ![plataformas integradas](assets/dbd-integrated-platforms.png)
4. Una vez que haya autenticado, se le redirigirá a Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic **[!DNL Confirm]** en.

### Paso 2: Crear un nuevo destino basado en dispositivo {#step2-create-new-destination}

Una vez vinculado Audience Manager y su [!DNL Twitter Tailored Audiences], puede crear el nuevo destino. A continuación se muestra cómo hacer esto:

>[!NOTE]
>
>No puede cambiar el nombre de un destino existente basado en dispositivo. Asegúrese de proporcionar un nombre que le ayude a identificar el destino correctamente.

1. Inicie sesión en su cuenta de Audience Manager, vaya a **[!DNL Audience Data > Destinations]** y haga clic **[!DNL Create Destination]** en.
2. En **[!DNL Basic Information]** la sección, introduzca un **[!DNL Name]** y **[!DNL Description]** para el nuevo destino y utilice los ajustes siguientes: ![configurar](assets/dbd-new-basic.png)
3. Haga clic en **[!DNL Next]**.
4. Elija las etiquetas de exportación [de datos](/help/using/features/data-export-controls.md#controls-labels) que desee definir para este destino.
5. Haga clic en **[!DNL Save]**.
6. En **[!DNL Segment Mappings]** la sección, seleccione los segmentos de audiencia que desee enviar a este destino.
7. Guarde el destino.

## Actualizar integraciones de Twitter existentes a administración de autoservicio {#update-existing-twitter-integrations}

Para mejorar la experiencia del usuario y optimizar el proceso de configuración, vamos a actualizar [!DNL Twitter Tailored Audiences] la integración a un modelo de autoservicio, donde puede realizar la configuración usted mismo, desde la interfaz de usuario de Audience Manager. Esta sección describe los pasos que debe seguir para actualizar la integración existente de Twitter.

>[!IMPORTANT]
>
>Los pasos que se describen a continuación solo se aplican si tiene una integración existente, [!DNL Twitter Tailored Audiences]configurada por un asesor de Audience Manager o por el Servicio de atención al cliente. El proceso de actualización completa del destino al modelo de autoservicio puede tardar hasta cinco días hábiles. Mientras tanto, el destino aún está activo y Audience Manager sigue enviando audiencias al mismo.
> Consulte el número 3 de [Requisitos previos](#prerequisites) antes de migrar al [!DNL Twitter Tailored Audiences] modelo de autoservicio.

Siga los pasos a continuación para migrar [!DNL Twitter Tailored Audiences] el destino existente al modelo de autoservicio.

1. Inicie sesión en su cuenta de Audience Manager y vaya **[!DNL Administration > Integrated Accounts]** a.
2. Haga clic en **[!DNL Add Account]**.
3. Seleccione [!DNL Twitter Tailored Audiences] y haga clic **[!DNL Confirm]** para que se le redirija a la página de autenticación. ![plataformas integradas](assets/dbd-integrated-platforms.png)
4. Una vez que haya autenticado con su cuenta de Twitter, se le redirigirá a Audience Manager, donde debería ver las cuentas de anunciante asociadas. Seleccione la cuenta del anunciante que desee utilizar y haga clic **[!DNL Confirm]** en.

## Consideraciones de asignación de segmentos {#segment-mapping-considerations}

Cuando asigne segmentos de audiencia a Twitter, asegúrese de cumplir los siguientes requisitos de nomenclatura de segmentos:

* Proporcione nombres de asignación de segmentos legibles en lenguaje natural. Recomendamos utilizar el mismo nombre que utilizó para los segmentos de Audience Manager.
* No utilice comas en nombres de asignación de segmentos y segmentos.

**Ejemplo**

* Correcto segmento o nombre de asignación: " US y compradores europeos ";
* Nombre de segmento o segmento incorrecto: " EE. UU., Europa 5 h 0 pP 3 rs ".

>[!IMPORTANT]
>
>No puede cambiar los nombres de segmentos asignados previamente. Audience Manager usa los nombres de segmento para identificar correctamente los segmentos en la integración.