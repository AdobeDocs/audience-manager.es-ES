---
description: Audience Manager se toma muy en serio la seguridad de los datos y la privacidad. Trabajamos para mantener nuestros sistemas seguros y proteger sus valiosos datos.
seo-description: Audience Manager se toma muy en serio la seguridad de los datos y la privacidad. Trabajamos para mantener nuestros sistemas seguros y proteger sus valiosos datos.
seo-title: Seguridad de datos
solution: Audience Manager
title: Seguridad de datos
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: b76e905ec890dbe8270177d142dddb351438b039

---


# Seguridad de datos {#data-security}

Audience Manager se toma muy en serio la seguridad de los datos y la privacidad. Trabajamos para mantener nuestros sistemas seguros y proteger sus valiosos datos.

Las prácticas de seguridad de Audience Manager incluyen auditorías externas e internas, registro de actividades, capacitación y otros procedimientos diseñados para ayudar a proteger nuestros sistemas y sus valiosos datos. We believe a secure product helps build and maintain the trust customers place in us.

In Audience Manager, we think about security in three main categories:

| Security Type | Provides Support For |
|---|---|
| **Information security** | Enterprise-level authentication, encryption, and data storage practices |
| **Filtración/transparencia de datos** | Perspectiva profunda y procesable de las actividades en el sitio que constituyen o contribuyen a la fuga de datos |
| **Mejoras de procesos y políticas** | Clientes, trabajando con las mejores prácticas del sector para la privacidad y la seguridad de los datos |

## Systems, Training, and Access {#systems-training-access}

Procesos que ayudan a mantener nuestro sistema y sus datos seguros.

**** Validación de seguridad externa:  Audience Manager comprueba la seguridad de forma anual y trimestral.

* Yearly: Once a year, Audience Manager undergoes a full penetration test conducted by an independent third-party company. La prueba está diseñada para identificar vulnerabilidades de seguridad en la aplicación. Las pruebas incluyen el análisis de secuencias de comandos entre sitios, inyecciones SQL, manipulación de parámetros de formulario y otras vulnerabilidades a nivel de aplicación.
* Trimestral: Una vez cada trimestre, los equipos internos comprueban la existencia de vulnerabilidades de seguridad. These tests include network scans for open ports and service vulnerabilities.

**** Seguridad de los sistemas:  Para ayudar a mantener los datos seguros y privados, Audience Manager:

* Bloquea solicitudes de direcciones IP no autorizadas.
* Protege los datos detrás de servidores de seguridad, VPN y con almacenamiento en la nube privada virtual.
* Rastrea cambios en las bases de datos de información de control y cliente con registro de auditoría basado en desencadenadores. Estos registros rastrean todos los cambios a nivel de base de datos, incluyendo el ID de usuario y la dirección IP desde la cual se realizan los cambios.

**** Recursos de seguridad:  Audience Manager cuenta con un equipo de operaciones de red dedicado que supervisa los cortafuegos y los dispositivos de detección de intrusiones. Only key personnel have access to our security technology and data.

**Security Training:**  Internally, our commitment to security extends to developers who work on our product. Adobe provides formal training to developers on how to build secure applications and services.

**** Secure Access:  Audience Manager requires strong passwords to log on to the system. Consulte Requisitos [de contraseña](../../reference/password-requirements.md).

## Privacy and Personally Identifiable Information (PII) {#pii}

Procesos que ayudan a mantener la seguridad de la información personal. Para obtener información de privacidad adicional, consulte el Centro de privacidad de [Adobe](https://www.adobe.com/privacy/advertising-services.html).

**** Datos PII:  Audience Manager prohíbe contractualmente a los clientes y socios de datos enviar información PII a nuestro sistema. Además, el ID de usuario único (UUID) no contiene ni utiliza datos PII como parte del algoritmo de generación de ID.

**** Direcciones IP:  Audience Manager recopila direcciones IP. Las direcciones IP se utilizan en los procesos de procesamiento de datos y agregación de registros. También son necesarios para las búsquedas y la segmentación geográfica/de ubicación. Además, todas las direcciones IP de los archivos de registro retenidos se confunden en un plazo de 90 días.

## Partición de datos {#data-partitioning}

Procesos que ayudan a proteger los datos propiedad de clientes individuales.

**** Partición de datos de características:  Sus datos (características, ID, etc.) está dividido por el cliente. Esto ayuda a evitar la exposición accidental de información entre diferentes clientes. Por ejemplo, los datos de características de las cookies son particionados por el cliente y almacenados en un subdominio específico del cliente. Otro cliente de Audience Manager no puede leerlo ni utilizarlo accidentalmente. Furthermore, trait data stored in the  is also partitioned by customer. [!UICONTROL Profile Cache Servers (PCS)] This prevents other clients from accidentally using your data in an event call or other request.

**** Data Partitioning in Reports:  Client IDs are part of the identifying key in all reporting tables and report queries are filtered by ID. Esto ayuda a evitar que los datos aparezcan en los informes de otro cliente de Audience Manager.

## Transferencias de servidor a servidor entrantes (S2S) {#inbound-s2s}

Adobe Audience Manager admite dos métodos principales para transferir archivos de datos integrados S2S a nuestros sistemas:

Both methods are designed with the security of our customer and partner data in mind while data is in flight between their systems and our system.

**** SFTP: For the SFTP option, most customers choose to deliver files via the Secure FTP (SFTP) protocol, which uses the Secure Shell (SSH) protocol. Este método garantiza que los archivos se cifran mientras están en vuelo entre los sistemas del cliente y el sistema de Adobe. For each customer, we create a jailed drop-box location on our SFTP servers, which is tied to a user account on that system. Solo los usuarios privilegiados del sistema interno con credenciales del cliente pueden acceder a esta ubicación de la casilla de correo electrónico en la cárcel. Esta cárcel nunca es accesible a otros clientes.

**** Amazon Web Services S3 vía HTTPS: Para la opción de envío S3, recomendamos que todos los clientes configuren sus clientes S3 para utilizar el método de cifrado HTTPS para transferencias de archivos (este no es el predeterminado, por lo que debe configurarse explícitamente). La opción HTTPS es compatible tanto con la herramienta de línea de comandos s3cmd como con las bibliotecas S3 disponibles en todos los lenguajes de programación principales. Con esta opción HTTPS habilitada, los datos del cliente se cifran mientras se dirigen a nuestros sistemas. Para cada cliente, creamos un subdirectorio de bucket S3 independiente al que sólo se puede acceder mediante las credenciales de ese cliente y las de nuestros usuarios internos del sistema.

Para agregar codificación PGP a sus archivos de datos, consulte [Cifrado de PGP de archivos para tipos](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)de datos de entrada.

## Protección de datos escapando {#escaping-data}

Tenga en cuenta que [!DNL Audience Manager] no escapa a los datos salientes para protegerlos de posibles scripts entre sitios (XSS), etc. Es responsabilidad del cliente escapar de los datos entrantes.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] es un mecanismo de seguridad web de toda la industria que ayuda a protegerse contra el secuestro de cookies y los ataques de reducción de protocolo.

The policy instructs the web browser that once a secure  call was made to a given domain, no subsequent unsecure calls () should be allowed to that domain. [!DNL HTTPS][!DNL HTTP] This protects against man-in-the-middle attacks, where an attacker might try to downgrade  calls to unsecured  calls.”[!DNL HTTPS][!DNL HTTP]

This policy improves data security between clients and Adobe Edge servers.[](../../reference/system-components/components-edge.md)

### Ejemplo {#hsts-example}

When trying to access ,  will automatically upgrade the request to  , in case the browser doesn’t automatically request the  domain.`http://bank.demdex.com`[!DNL HSTS]`https://bank.demdex.com`[!DNL HTTPS]

See HTTP Strict Transport Security - Wikipedia for more information about HSTS.[](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
