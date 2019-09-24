---
description: Audience Manager se toma muy en serio la seguridad de los datos y la privacidad. We work to keep our systems secure and protect your valuable data.
seo-description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-title: Seguridad de datos
solution: Audience Manager
title: Seguridad de datos
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 9e1abb305c66a4adf6a42a7873144222491692f9

---


# Seguridad de datos {#data-security}

Audience Manager se toma muy en serio la seguridad de los datos y la privacidad. Trabajamos para mantener nuestros sistemas seguros y proteger sus valiosos datos.

Las prácticas de seguridad de Audience Manager incluyen auditorías externas e internas, registro de actividades, capacitación y otros procedimientos diseñados para ayudar a proteger nuestros sistemas y sus valiosos datos. Creemos que un producto seguro ayuda a crear y mantener la confianza que los clientes depositan en nosotros.

In Audience Manager, we think about security in three main categories:

| Tipo de seguridad | Provides Support For |
|---|---|
| **Information security** | Enterprise-level authentication, encryption, and data storage practices |
| **Data leakage/transparency** | Deep and actionable insight into on-site activities that constitute or contribute to data leakage |
| **Process/policy enhancements** | Clients, by working with industry best practices for privacy and data security |

## Systems, Training, and Access {#systems-training-access}

Processes that help keep our system and your data secure.

**** External Security Validation:  Audience Manager tests security on an annual and quarterly basis.

* Yearly: Once a year, Audience Manager undergoes a full penetration test conducted by an independent third-party company. La prueba está diseñada para identificar vulnerabilidades de seguridad en la aplicación. Las pruebas incluyen el análisis de secuencias de comandos entre sitios, inyecciones SQL, manipulación de parámetros de formulario y otras vulnerabilidades a nivel de aplicación.
* Trimestral: Una vez cada trimestre, los equipos internos comprueban la existencia de vulnerabilidades de seguridad. Estas pruebas incluyen análisis de red para detectar puertos abiertos y vulnerabilidades de servicio.

**** Seguridad de los sistemas:  Para ayudar a mantener los datos seguros y privados, Audience Manager:

* Bloquea solicitudes de direcciones IP no autorizadas.
* Protege los datos detrás de servidores de seguridad, VPN y con almacenamiento en la nube privada virtual.
* Rastrea cambios en las bases de datos de información de control y cliente con registro de auditoría basado en desencadenadores. Estos registros rastrean todos los cambios a nivel de base de datos, incluyendo el ID de usuario y la dirección IP desde la cual se realizan los cambios.

**** Recursos de seguridad:  Audience Manager cuenta con un equipo de operaciones de red dedicado que supervisa los cortafuegos y los dispositivos de detección de intrusiones. Sólo el personal clave tiene acceso a nuestra tecnología y datos de seguridad.

**** Capacitación en seguridad:  Internamente, nuestro compromiso con la seguridad se extiende a los desarrolladores que trabajan en nuestro producto. Adobe proporciona formación formal a los desarrolladores sobre cómo crear aplicaciones y servicios seguros.

**** Acceso seguro:  Audience Manager requiere contraseñas sólidas para iniciar sesión en el sistema. Consulte Requisitos [de contraseña](../../reference/password-requirements.md).

## Privacidad e información de identificación personal (PII) {#pii}

Procesos que ayudan a mantener la seguridad de la información personal. Para obtener información de privacidad adicional, consulte el Centro de privacidad de [Adobe](https://www.adobe.com/privacy/advertising-services.html).

**** Datos PII:  Audience Manager prohíbe contractualmente a los clientes y socios de datos enviar información PII a nuestro sistema. Additionally, the Unique User ID (UUID) does not contain or use PII data as part of the ID-generation algorithm.

**** IP Addresses:  Audience Manager does collect IP addresses. Las direcciones IP se utilizan en los procesos de procesamiento de datos y agregación de registros. También son necesarios para las búsquedas y la segmentación geográfica/de ubicación. Además, todas las direcciones IP de los archivos de registro retenidos se confunden en un plazo de 90 días.

## Data Partitioning {#data-partitioning}

Procesos que ayudan a proteger los datos propiedad de clientes individuales.

**** Partición de datos de características:  Sus datos (características, ID, etc.) está dividido por el cliente. Esto ayuda a evitar la exposición accidental de información entre diferentes clientes. Por ejemplo, los datos de características de las cookies son particionados por el cliente y almacenados en un subdominio específico del cliente. Otro cliente de Audience Manager no puede leerlo ni utilizarlo accidentalmente. Además, los datos de características almacenados en el [!UICONTROL Profile Cache Servers (PCS)] también son divididos por el cliente. This prevents other clients from accidentally using your data in an event call or other request.

**** Partición de datos en informes:  Las ID de cliente forman parte de la clave de identificación en todas las tablas de informes y las consultas de informes se filtran por ID. This helps prevent your data from appearing in the reports of another Audience Manager customer.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager supports two main methods of transferring S2S on-boarded data files to our systems:

Both methods are designed with the security of our customer and partner data in mind while data is in flight between their systems and our system.

**** SFTP: For the SFTP option, most customers choose to deliver files via the Secure FTP (SFTP) protocol, which uses the Secure Shell (SSH) protocol. This method ensures that files are encrypted while in flight between the customer's systems and Adobe's system. Para cada cliente, creamos una ubicación de buzón en la cárcel en nuestros servidores SFTP, que está ligada a una cuenta de usuario en ese sistema. Only the customer's credentialed and privileged internal system users can access this jailed drop-box location. This jail is never accessible to other customers.

**** Amazon Web Services S3 via HTTPS: For the S3 delivery option, we recommend that all customers configure their S3 clients to use the HTTPS encryption method for file transfers (this is not the default, so it must be explicitly configured). La opción HTTPS es compatible tanto con la herramienta de línea de comandos s3cmd como con las bibliotecas S3 disponibles en todos los lenguajes de programación principales. Con esta opción HTTPS habilitada, los datos del cliente se cifran mientras se dirigen a nuestros sistemas. Para cada cliente, creamos un subdirectorio de bucket S3 independiente al que sólo se puede acceder mediante las credenciales de ese cliente y las de nuestros usuarios internos del sistema.

Para agregar codificación PGP a sus archivos de datos, consulte [Cifrado de PGP de archivos para tipos](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)de datos de entrada.

## Protección de datos escapando {#escaping-data}

Tenga en cuenta que [!DNL Audience Manager] no escapa a los datos salientes para protegerlos de posibles scripts entre sitios (XSS), etc. Es responsabilidad del cliente escapar de los datos entrantes.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] es un mecanismo de políticas de seguridad web que ayuda a proteger contra el secuestro de cookies y los ataques de reducción de protocolo al no permitir [!DNL HTTP] el tráfico y actualizar de forma transparente todo [!DNL HTTP] el tráfico a [!DNL HTTPS].

Esta directiva mejora la seguridad de los datos entre los clientes y los servidores de Adobe Edge.

### Ejemplo {#hsts-example}

Al intentar acceder a `http://bank.demdex.com`, [!DNL HSTS] automáticamente se actualizará la solicitud a `https://bank.demdex.com`, en caso de que el explorador no solicite automáticamente el [!DNL HTTPS] dominio.

Consulte Seguridad de transporte [HTTP estricta - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) para obtener más información sobre HSTS.
