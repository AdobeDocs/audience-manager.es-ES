---
description: Audience Manager se toma muy en serio la seguridad de los datos y la privacidad. Trabajamos para mantener nuestros sistemas seguros y proteger sus valiosos datos.
seo-description: Audience Manager se toma muy en serio la seguridad de los datos y la privacidad. Trabajamos para mantener nuestros sistemas seguros y proteger sus valiosos datos.
seo-title: Seguridad de datos en Audience Manager
solution: Audience Manager
title: Seguridad de datos en Audience Manager
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 98%

---


# Seguridad de datos en Audience Manager {#data-security}

Audience Manager se toma muy en serio la seguridad de los datos y la privacidad. Trabajamos para mantener nuestros sistemas seguros y proteger sus valiosos datos.

Las prácticas de seguridad de Audience Manager incluyen auditorías externas e internas, registro de actividades, formación y otros procedimientos diseñados para ayudar a proteger nuestros sistemas y sus valiosos datos. Creemos que un producto seguro ayuda a crear y mantener la confianza que los clientes depositan en nosotros.

En Audience Manager, pensamos en la seguridad en tres categorías principales:

| Tipo de seguridad | Compatible con |
|---|---|
| **Seguridad de la información** | Prácticas de autenticación, cifrado y almacenamiento de datos a nivel empresarial |
| **Filtración de datos/transparencia** | Perspectiva completa y procesable de las actividades en el sitio que ayudan o contribuyen a la pérdida de datos |
| **Mejoras de procesos y políticas** | Clientes, trabajando de acuerdo con las prácticas recomendadas del sector en cuanto a privacidad y seguridad de los datos |

## Sistemas, formación y acceso {#systems-training-access}

Procesos que ayudan a mantener nuestro sistema y sus datos seguros.

**Validación de seguridad externa:** Audience Manager comprueba su seguridad de forma anual y trimestral.

* Anual: Una vez al año, Audience Manager se somete a una prueba de penetración completa realizada por una compañía independiente. La prueba está diseñada para identificar vulnerabilidades de seguridad en la aplicación. Las pruebas incluyen el análisis de secuencias de comandos entre sitios, inyecciones SQL, manipulación de parámetros de formulario y otras vulnerabilidades a nivel de aplicación.
* Trimestral: Una vez cada trimestre, los equipos internos comprueban la existencia de vulnerabilidades de seguridad. Estas pruebas incluyen análisis de red para detectar puertos abiertos y vulnerabilidades en el servicio.

**Seguridad de los sistemas:** Para ayudar a mantener los datos seguros y privados, Audience Manager:

* Bloquea solicitudes de direcciones IP no autorizadas.
* Protege los datos detrás de servidores de seguridad, VPN y con el almacenamiento de Virtual Private Cloud.
* Rastrea cambios en las bases de datos de información de control y clientes con registros de auditoría basados en activadores. Estos registros rastrean todos los cambios a nivel de base de datos, incluido el ID de usuario y la dirección IP desde la cual se realizan los cambios.

**Recursos de seguridad:** Audience Manager cuenta con un equipo de operaciones de red dedicado que supervisa los servidores de seguridad y los dispositivos de detección de intrusiones. Solo el personal clave tiene acceso a nuestra tecnología y datos de seguridad.

**Formación en seguridad:** Internamente, nuestro compromiso con la seguridad se extiende a los desarrolladores que trabajan en nuestro producto. Adobe proporciona formación formal a los desarrolladores sobre cómo crear aplicaciones y servicios seguros.

**Acceso seguro:** Audience Manager requiere contraseñas sólidas para iniciar sesión en el sistema. Consulte [Requisitos de contraseña](../../reference/password-requirements.md).

## Privacidad e información de identificación personal (PII) {#pii}

Procesos que ayudan a mantener la seguridad de la información personal. Para obtener información de privacidad adicional, consulte el [Centro de privacidad de Adobe](https://www.adobe.com/es/privacy/advertising-services.html).

**Datos PII:** Audience Manager prohíbe por contrato a los clientes y socios de datos enviar información PII a nuestro sistema. Además, el ID de usuario único (UUID) no contiene ni utiliza datos PII como parte del algoritmo de generación de ID.

**Direcciones IP:** Audience Manager recopila direcciones IP. Las direcciones IP se utilizan en los procesos de procesamiento de datos y agregación de registros. También son necesarios para las búsquedas y la segmentación geográfica/de ubicación. Además, todas las direcciones IP de los archivos de registro retenidos se ofuscan en un plazo de 90 días.

## Partición de datos {#data-partitioning}

Procesos que ayudan a proteger los datos propiedad de clientes individuales.

**Partición de datos de características:**  sus datos ([!UICONTROL traits], ID, etc.) por cliente. Esto ayuda a evitar la exposición accidental de información entre diferentes clientes. Por ejemplo, los datos de rasgos de las cookies se dividen por cliente y se almacenan en un subdominio específico del cliente. Otro cliente de Audience Manager no podrá leer estos datos ni utilizarlos accidentalmente. Además, los datos de rasgos almacenados en los [!UICONTROL Profile Cache Servers (PCS)] también se dividen por cliente. Esto evita que otros clientes utilicen accidentalmente sus datos en una llamada de evento u otra solicitud.

**Partición de datos en informes:** Los ID de cliente forman parte de la clave de identificación en todas las tablas de los informes y las consultas de informes se filtran por su ID. Esto ayuda a evitar que los datos aparezcan en los informes de otro cliente de Audience Manager.

## Transferencias de servidor a servidor entrantes (S2S) {#inbound-s2s}

Adobe Audience Manager admite dos métodos principales para transferir archivos de datos integrados S2S a nuestros sistemas:

Ambos métodos están diseñados teniendo en cuenta la seguridad de nuestros datos de clientes y socios mientras los datos están en tránsito entre sus sistemas y nuestro sistema.

**SFTP:** Para la opción SFTP, la mayoría de los clientes decide enviar archivos a través del protocolo FTP seguro (SFTP), que utiliza el protocolo Secure Shell (SSH). Este método garantiza que los archivos se cifren mientras se envían entre los sistemas del cliente y el de Adobe. Para cada cliente, creamos una ubicación de buzón cerrada en nuestros servidores SFTP, que está ligada a una cuenta de usuario en ese sistema. Solo los usuarios privilegiados del sistema interno con credenciales del cliente pueden acceder a esta ubicación cerrada compartida. Ningún otro cliente puede acceder a esta ubicación cerrada.

**[!UICONTROL Amazon Web Services S3]mediante HTTPS:** Para la opción de envío de S3, recomendamos que todos los clientes configuren sus clientes S3 de forma que utilicen el método de codificación HTTPS para transferencias de archivos (este no es el predeterminado, por lo que debe configurarse explícitamente). La opción HTTPS es compatible tanto con la herramienta de línea de comandos s3cmd como con las bibliotecas S3 disponibles en todos los lenguajes de programación principales. Con esta opción HTTPS habilitada, los datos del cliente se cifran mientras se dirigen a nuestros sistemas. Para cada cliente, creamos un subdirectorio de compartimentos S3 independiente al que solo se puede acceder mediante las credenciales de ese cliente y las de nuestros usuarios internos del sistema.

Para agregar un cifrado PGP a sus archivos de datos, consulte [Cifrado de PGP de archivos para tipos de datos de entrada](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Protección de datos mediante procesos de escape {#escaping-data}

Tenga en cuenta que [!DNL Audience Manager] no escapa los datos salientes para protegerlos de posibles scripts entre sitios (XSS), etc. Es responsabilidad del cliente aplicar el escape en los datos entrantes.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] es un mecanismo de seguridad web del sector que ayuda a protegerse contra el secuestro de cookies y los ataques de reducción de protocolos.

La directiva indica al explorador web que una vez que se realizó una llamada segura [!DNL HTTPS] a un dominio determinado, no se debe permitir ninguna llamada no segura ([!DNL HTTP]) posterior a ese dominio. Esto protege contra ataques de intermediarios, donde un atacante podría intentar reducir las llamadas a [!DNL HTTPS] a llamadas [!DNL HTTP] no seguras”.

Esta directiva mejora la seguridad de los datos entre los clientes y los servidores de Adobe [Edge](../../reference/system-components/components-edge.md).

### Ejemplo {#hsts-example}

Supongamos que el dominio `yourcompany.demdex.com` envía tráfico a [!DNL DCS] mediante [!DNL HTTP]. [!DNL HSTS] actualiza las llamadas para usar [!DNL HTTPS] en su lugar, y todas las llamadas [!DNL DCS] posteriores procedentes de `yourcompany.demdex.com` utilizarán [!DNL HTTPS] en lugar de [!DNL HTTP].

Consulte [HTTP Strict Transport Security - Wikipedia](https://es.wikipedia.org/wiki/HTTP_Strict_Transport_Security) para obtener más información sobre HSTS.
