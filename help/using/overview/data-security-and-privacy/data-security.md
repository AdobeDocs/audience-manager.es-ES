---
description: Audience Manager se toma muy en serio la seguridad de los datos y la privacidad. Trabajamos para mantener nuestros sistemas seguros y proteger sus valiosos datos.
seo-description: Audience Manager se toma muy en serio la seguridad de los datos y la privacidad. Trabajamos para mantener nuestros sistemas seguros y proteger sus valiosos datos.
seo-title: Seguridad de datos
solution: Audience Manager
title: Seguridad de datos
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 91444ad943fcd020c83e522922d67ef400bf8824

---


# Seguridad de datos {#data-security}

Audience Manager se toma muy en serio la seguridad de los datos y la privacidad. Trabajamos para mantener nuestros sistemas seguros y proteger sus valiosos datos.

Las prácticas de seguridad de Audience Manager incluyen auditorías externas e internas, registro de actividades, capacitación y otros procedimientos diseñados para ayudar a proteger nuestros sistemas y sus valiosos datos. Creemos que un producto seguro ayuda a crear y mantener la confianza que los clientes depositan en nosotros.

En Audience Manager, pensamos en la seguridad en tres categorías principales:

| Tipo de seguridad | Provides Support For |
|---|---|
| **Seguridad de la información** | Enterprise-level authentication, encryption, and data storage practices |
| **Data leakage/transparency** | Deep and actionable insight into on-site activities that constitute or contribute to data leakage |
| **Process/policy enhancements** | Clients, by working with industry best practices for privacy and data security |

## Systems, Training, and Access {#systems-training-access}

Processes that help keep our system and your data secure.

**External Security Validation:**  Audience Manager tests security on an annual and quarterly basis.

* Yearly: Once a year, Audience Manager undergoes a full penetration test conducted by an independent third-party company. La prueba está diseñada para identificar vulnerabilidades de seguridad en la aplicación. The tests include scanning for cross-site scripting, SQL injections, form parameter manipulation, and other application-level vulnerabilities.
* Quarterly: Once each quarter, internal teams check for security vulnerabilities. These tests include network scans for open ports and service vulnerabilities.

**** Systems Security:  To help keep data safe and private, Audience Manager:

* Bloquea solicitudes de direcciones IP no autorizadas.
* Protects data behind firewalls, VPNs, and with Virtual Private Cloud storage.
* Rastrea cambios en las bases de datos de información de control y cliente con registro de auditoría basado en desencadenadores. Estos registros rastrean todos los cambios a nivel de base de datos, incluyendo el ID de usuario y la dirección IP desde la cual se realizan los cambios.

**** Recursos de seguridad:  Audience Manager cuenta con un equipo de operaciones de red dedicado que supervisa los cortafuegos y los dispositivos de detección de intrusiones. Sólo el personal clave tiene acceso a nuestra tecnología y datos de seguridad.

**** Capacitación en seguridad:  Internamente, nuestro compromiso con la seguridad se extiende a los desarrolladores que trabajan en nuestro producto. Adobe proporciona formación formal a los desarrolladores sobre cómo crear aplicaciones y servicios seguros.

**** Acceso seguro:  Audience Manager requiere contraseñas sólidas para iniciar sesión en el sistema. Consulte Requisitos [de contraseña](../../reference/password-requirements.md).

## Privacidad e información de identificación personal (PII) {#pii}

Procesos que ayudan a mantener la seguridad de la información personal. Para obtener información de privacidad adicional, consulte el Centro de privacidad de [Adobe](https://www.adobe.com/privacy/advertising-services.html).

**** Datos PII:  Audience Manager prohíbe contractualmente a los clientes y socios de datos enviar información PII a nuestro sistema. Además, el ID de usuario único (UUID) no contiene ni utiliza datos PII como parte del algoritmo de generación de ID.

**** Direcciones IP:  Audience Manager recopila direcciones IP. Las direcciones IP se utilizan en los procesos de procesamiento de datos y agregación de registros. También son necesarios para las búsquedas y la segmentación geográfica/de ubicación. Además, todas las direcciones IP de los archivos de registro retenidos se confunden en un plazo de 90 días.

## Partición de datos {#data-partitioning}

Procesos que ayudan a proteger los datos propiedad de clientes individuales.

**** Partición de datos de características:  Sus datos (características, ID, etc.) está dividido por el cliente. Esto ayuda a evitar la exposición accidental de información entre diferentes clientes. Por ejemplo, los datos de características de las cookies son particionados por el cliente y almacenados en un subdominio específico del cliente. Otro cliente de Audience Manager no puede leerlo ni utilizarlo accidentalmente. Además, los datos de características almacenados en el [!UICONTROL Profile Cache Servers (PCS)] también son divididos por el cliente. Esto evita que otros clientes utilicen accidentalmente sus datos en una llamada de evento u otra solicitud.

**** Partición de datos en informes:  Las ID de cliente forman parte de la clave de identificación en todas las tablas de informes y las consultas de informes se filtran por ID. Esto ayuda a evitar que los datos aparezcan en los informes de otro cliente de Audience Manager.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager supports two main methods of transferring S2S on-boarded data files to our systems:

Both methods are designed with the security of our customer and partner data in mind while data is in flight between their systems and our system.

**** SFTP: For the SFTP option, most customers choose to deliver files via the Secure FTP (SFTP) protocol, which uses the Secure Shell (SSH) protocol. This method ensures that files are encrypted while in flight between the customer's systems and Adobe's system. For each customer, we create a jailed drop-box location on our SFTP servers, which is tied to a user account on that system. Solo los usuarios privilegiados del sistema interno con credenciales del cliente pueden acceder a esta ubicación de la casilla de correo electrónico en la cárcel. This jail is never accessible to other customers.

**** Amazon Web Services S3 via HTTPS: For the S3 delivery option, we recommend that all customers configure their S3 clients to use the HTTPS encryption method for file transfers (this is not the default, so it must be explicitly configured). La opción HTTPS es compatible tanto con la herramienta de línea de comandos s3cmd como con las bibliotecas S3 disponibles en todos los lenguajes de programación principales. Con esta opción HTTPS habilitada, los datos del cliente se cifran mientras se dirigen a nuestros sistemas. For each customer, we create a separate S3 bucket sub-directory that can be accessed only by that customer's credentials and those of our internal system users.

To add PGP encryption to your data files, see File PGP Encryption for Inbound Data Types.[](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)

## Protecting Data by Escaping {#escaping-data}

Note that  does not escape outgoing data to secure it against possible cross-site scripting (XSS), etc. [!DNL Audience Manager] It is the responsibility of the client to escape incoming data.

## HTTP Strict-Transport-Security (#hsts)

[!DNL HTTP Strict-Transport-Security (HSTS)] es un mecanismo de políticas de seguridad web que ayuda a proteger contra el secuestro de cookies y los ataques de reducción de protocolo al no permitir [!DNL HTTP] el tráfico y actualizar de forma transparente todo [!DNL HTTP] el tráfico a [!DNL HTTPS].

This policy improves data security between clients and Adobe Edge servers.

### Ejemplo {#hsts-example}

Al intentar acceder a `http://bank.demdex.com`, [!DNL HSTS] automáticamente se actualizará la solicitud a `https://bank.demdex.com`, en caso de que el explorador no solicite automáticamente el [!DNL HTTPS] dominio.

Consulte Seguridad de transporte [HTTP estricta - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) para obtener más información sobre HSTS.
