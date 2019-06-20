---
description: Audience Manager tiene muy en serio la seguridad de los datos y la privacidad. Trabajamos para mantener nuestros sistemas seguros y proteger sus valiosos datos.
seo-description: Audience Manager tiene muy en serio la seguridad de los datos y la privacidad. Trabajamos para mantener nuestros sistemas seguros y proteger sus valiosos datos.
seo-title: Seguridad de datos
solution: Audience Manager
title: Seguridad de datos
uuid: 33 ad 19 ca -4690-4 d 97-853 b -1882 d 7 d 4 ac 01
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Security {#data-security}

Audience Manager tiene muy en serio la seguridad de los datos y la privacidad. Trabajamos para mantener nuestros sistemas seguros y proteger sus valiosos datos.

Las prácticas de seguridad de Audience Manager incluyen auditorías internas y externas, registro de actividades, capacitación y otros procedimientos diseñados para proteger nuestros sistemas y sus valiosos datos. Creemos que un producto seguro ayuda a crear y mantener la confianza de los clientes en nosotros.

En Audience Manager, pensamos en la seguridad en tres categorías principales:

| Tipo de seguridad | Proporciona compatibilidad con |
|---|---|
| **Seguridad de información** | Prácticas de autenticación, codificación y almacenamiento de datos de nivel empresarial |
| **Pérdida/transparencia de datos** | Perspectiva profunda y procesable sobre las actividades en el sitio que constituyen o contribuyen a la fuga de datos |
| **Mejoras de proceso/política** | Clientes, trabajando con las optimizaciones del sector para privacidad y seguridad de datos |

## Systems, Training, and Access {#systems-training-access}

Procesos que ayudan a mantener el sistema y los datos seguros.

**Validación de seguridad externa:** Audience Manager comprueba la seguridad por año y por trimestre.

* Anual: Una vez al año, Audience Manager realiza una prueba de penetración completa llevada a cabo por una empresa independiente de terceros. La prueba está diseñada para identificar vulnerabilidades de seguridad en la aplicación. Las pruebas incluyen digitalización de secuencias de comandos entre sitios, inyecciones SQL, manipulación de parámetros de formulario y otras vulnerabilidades a nivel de aplicación.
* Trimestral: Una vez cada trimestre, los equipos internos comprueban si existen vulnerabilidades de seguridad. Estas pruebas incluyen búsqueda de red para puertos abiertos y vulnerabilidades de servicio.

**Seguridad de sistemas:** Para ayudar a mantener los datos seguros y privados, Audience Manager:

* Bloquea solicitudes de direcciones IP no autorizadas.
* Protege los datos detrás de los servidores de seguridad, los VPNS y el almacenamiento virtual en nube virtual.
* Realiza un seguimiento de los cambios en las bases de datos del cliente y de la información de control con registro de auditoría basado en activadores. Estos registros rastrean todos los cambios en el nivel de base de datos, incluido el ID de usuario y la dirección IP desde la que se realizan los cambios.

**Recursos de seguridad:** Audience Manager dispone de un equipo de operaciones de red dedicado que supervisa los servidores de seguridad y los dispositivos de detección de intrusión. Solo el personal clave tiene acceso a nuestra tecnología de seguridad y a los datos.

**Capacitación en seguridad:** Internamente, nuestro compromiso con la seguridad se extiende a los desarrolladores que trabajan en nuestro producto. Adobe proporciona formación formal a los desarrolladores sobre cómo crear aplicaciones y servicios seguros.

**Acceso seguro:** Audience Manager requiere contraseñas sólidas para iniciar sesión en el sistema. See [password requirements](../../reference/password-requirements.md).

## Privacy and Personally Identifiable Information (PII) {#pii}

Procesos que ayudan a mantener la información personal segura. For additional privacy information, see the [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

**Datos PII:** Audience Manager prohíbe a los clientes y a los socios de datos enviar información PII en nuestro sistema. Además, el ID de usuario único (UUID) no contiene ni utiliza datos PII como parte del algoritmo de generación de ID.

**Direcciones IP:** Audience Manager recopila direcciones IP. Las direcciones IP se utilizan en procesos de procesamiento de datos y de agregación de registros. También son necesarios para las búsquedas y los objetivos geográficos y de ubicación. Además, todas las direcciones IP de los archivos de registro retenidos se confunden en un plazo de 90 días.

## Data Partitioning {#data-partitioning}

Procesos que ayudan a proteger los datos propiedad de clientes individuales.

**Partición de datos de características:** Sus datos (características, ID, etc.) la particiona el cliente. Esto ayuda a evitar la exposición de información accidental entre distintos clientes. Por ejemplo, los datos de características en las cookies se particionan por cliente y se almacenan en un subdominio específico del cliente. No puede ser leída ni utilizada accidentalmente por otro cliente de Audience Manager. Furthermore, trait data stored in the [!UICONTROL Profile Cache Servers (PCS)] is also partitioned by customer. Esto evita que otros clientes utilicen accidentalmente los datos en una llamada de evento u otra solicitud.

**Partición de datos en informes:** Los ID de cliente forman parte de la clave de identificación de todas las tablas de informes y las consultas de informes se filtran por ID. Esto ayuda a evitar que los datos aparezcan en los informes de otro cliente de Audience Manager.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager admite dos métodos principales para transferir archivos de datos conectados a S 2 S a nuestros sistemas:

Ambos métodos están diseñados teniendo en cuenta la seguridad de los datos de nuestros socios y socios mientras los datos están en vuelo entre sus sistemas y nuestro sistema.

**SFTP:** Para la opción SFTP, la mayoría de los clientes elige entregar archivos a través del protocolo Secure FTP (SFTP), que utiliza el protocolo Shell seguro (SSH). Este método garantiza que los archivos estén cifrados mientras están en vuelo entre los sistemas del cliente y el sistema de Adobe. Para cada cliente, creamos una ubicación de soltar solapada en nuestros servidores SFTP, que está ligada a una cuenta de usuario en ese sistema. Solo los usuarios de sistemas internos privilegiados y privilegiados del cliente pueden acceder a esta ubicación de soltar en el menú desplegable. Esta cárcel nunca se puede acceder a otros clientes.

**Amazon Web Services S 3 a través de HTTPS:** Para la opción de entrega S 3, recomendamos que todos los clientes configuren sus clientes S 3 para utilizar el método de codificación HTTPS para transferencias de archivos (este no es el predeterminado, por lo que debe configurarse de forma explícita). La opción HTTPS es compatible tanto con la herramienta de línea de comandos s 3 cmd como con las bibliotecas S 3 disponibles en todos los lenguajes de programación principales. Cuando esta opción HTTPS está activada, los datos del cliente están cifrados mientras están en vuelo a nuestros sistemas. Para cada cliente, creamos un subdirectorio de bucket S 3 independiente a los que solo puedan acceder las credenciales de ese cliente y los de nuestros usuarios del sistema interno.

To add PGP encryption to your data files, see [File PGP Encryption for Inbound Data Types](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Protecting Data by Escaping {#escaping-data}

Note that [!DNL Audience Manager] does not escape outgoing data to secure it against possible cross-site scripting (XSS), etc. El cliente tiene la responsabilidad de escapar los datos entrantes.
