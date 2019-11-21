---
description: Audience Manager se toma muy en serio la seguridad de los datos y la privacidad. Trabajamos para mantener nuestros sistemas seguros y proteger sus valiosos datos.
seo-description: Audience Manager se toma muy en serio la seguridad de los datos y la privacidad. Trabajamos para mantener nuestros sistemas seguros y proteger sus valiosos datos.
seo-title: Seguridad de datos en Audience Manager
solution: Audience Manager
title: Seguridad de datos en Audience Manager
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 1d606cf8ac8cf7b78a7ddf661e9a6d2ce32df71e

---


# Seguridad de datos en Audience Manager {#data-security}

Audience Manager se toma muy en serio la seguridad de los datos y la privacidad. Trabajamos para mantener nuestros sistemas seguros y proteger sus valiosos datos.

Las prácticas de seguridad de Audience Manager incluyen auditorías externas e internas, registro de actividades, capacitación y otros procedimientos diseñados para ayudar a proteger nuestros sistemas y sus valiosos datos. Creemos que un producto seguro ayuda a crear y mantener la confianza que los clientes depositan en nosotros.

En Audience Manager, pensamos en la seguridad en tres categorías principales:

| Tipo de seguridad | Proporciona Compatibilidad Con |
|---|---|
| **Seguridad de la información** | Prácticas de autenticación, cifrado y almacenamiento de datos a nivel empresarial |
| **Filtración/transparencia de datos** | Perspectiva profunda y procesable de las actividades en el sitio que constituyen o contribuyen a la fuga de datos |
| **Mejoras de procesos y políticas** | Clientes, trabajando con las optimizaciones del sector para la privacidad y la seguridad de los datos |

## Sistemas, capacitación y acceso {#systems-training-access}

Procesos que ayudan a mantener nuestro sistema y sus datos seguros.

**** Validación de seguridad externa:  Audience Manager comprueba la seguridad de forma anual y trimestral.

* Anual: Una vez al año, Audience Manager se somete a una prueba de penetración completa realizada por una empresa independiente de terceros. La prueba está diseñada para identificar vulnerabilidades de seguridad en la aplicación. Las pruebas incluyen el análisis de secuencias de comandos entre sitios, inyecciones SQL, manipulación de parámetros de formulario y otras vulnerabilidades a nivel de aplicación.
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

**** Datos PII:  Audience Manager prohíbe contractualmente a los clientes y socios de datos enviar información de PII a nuestro sistema. Además, el ID de usuario único (UUID) no contiene ni utiliza datos PII como parte del algoritmo de generación de ID.

**** Direcciones IP:  Audience Manager recopila direcciones IP. Las direcciones IP se utilizan en los procesos de procesamiento de datos y agregación de registros. También son necesarios para las búsquedas y la segmentación geográfica/de ubicación. Además, todas las direcciones IP de los archivos de registro retenidos se confunden en un plazo de 90 días.

## Partición de datos {#data-partitioning}

Procesos que ayudan a proteger los datos propiedad de clientes individuales.

**** Partición de datos de características:  Sus datos (características, ID, etc.) está dividido por el cliente. Esto ayuda a evitar la exposición accidental de información entre diferentes clientes. Por ejemplo, los datos de características de las cookies son particionados por el cliente y almacenados en un subdominio específico del cliente. Otro cliente de Audience Manager no puede leerlo ni utilizarlo accidentalmente. Además, los datos de características almacenados en el [!UICONTROL Profile Cache Servers (PCS)] también son divididos por el cliente. Esto evita que otros clientes utilicen accidentalmente sus datos en una llamada de evento u otra solicitud.

**** Partición de datos en informes:  Las ID de cliente forman parte de la clave de identificación en todas las tablas de informes y las consultas de informes se filtran por ID. Esto ayuda a evitar que los datos aparezcan en los informes de otro cliente de Audience Manager.

## Transferencias de servidor a servidor entrantes (S2S) {#inbound-s2s}

Adobe Audience Manager admite dos métodos principales para transferir archivos de datos integrados S2S a nuestros sistemas:

Ambos métodos están diseñados teniendo en cuenta la seguridad de nuestros datos de clientes y socios mientras los datos están en vuelo entre sus sistemas y nuestro sistema.

**** SFTP: Para la opción SFTP, la mayoría de los clientes decide enviar archivos a través del protocolo FTP seguro (SFTP), que utiliza el protocolo Secure Shell (SSH). Este método garantiza que los archivos se cifran mientras están en vuelo entre los sistemas del cliente y el sistema de Adobe. Para cada cliente, creamos una ubicación de buzón en la cárcel en nuestros servidores SFTP, que está ligada a una cuenta de usuario en ese sistema. Solo los usuarios privilegiados del sistema interno con credenciales del cliente pueden acceder a esta ubicación de la casilla de correo electrónico en la cárcel. Esta cárcel nunca es accesible a otros clientes.

**** Amazon Web Services S3 vía HTTPS: Para la opción de envío S3, recomendamos que todos los clientes configuren sus clientes S3 para utilizar el método de cifrado HTTPS para transferencias de archivos (este no es el predeterminado, por lo que debe configurarse explícitamente). La opción HTTPS es compatible tanto con la herramienta de línea de comandos s3cmd como con las bibliotecas S3 disponibles en todos los lenguajes de programación principales. Con esta opción HTTPS habilitada, los datos del cliente se cifran mientras se dirigen a nuestros sistemas. Para cada cliente, creamos un subdirectorio de bucket S3 independiente al que sólo se puede acceder mediante las credenciales de ese cliente y las de nuestros usuarios internos del sistema.

Para agregar codificación PGP a sus archivos de datos, consulte [Cifrado de PGP de archivos para tipos](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)de datos de entrada.

## Protección de datos escapando {#escaping-data}

Tenga en cuenta que [!DNL Audience Manager] no escapa a los datos salientes para protegerlos de posibles scripts entre sitios (XSS), etc. Es responsabilidad del cliente escapar de los datos entrantes.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] es un mecanismo de seguridad web de toda la industria que ayuda a protegerse contra el secuestro de cookies y los ataques de reducción de protocolo.

La directiva indica al explorador web que una vez que se realizó una llamada segura a un dominio determinado, no se debe permitir ninguna llamada ( [!DNL HTTPS][!DNL HTTP]) no segura posterior a ese dominio. Esto protege contra ataques de intermediarios, donde un atacante podría intentar reducir [!DNL HTTPS] las llamadas a [!DNL HTTP] llamadas no seguras".

Esta directiva mejora la seguridad de los datos entre los clientes y los servidores de Adobe [Edge](../../reference/system-components/components-edge.md) .

### Ejemplo {#hsts-example}

Supongamos que el `yourcompany.demdex.com` dominio envía tráfico al [!DNL DCS] a través de [!DNL HTTP]. [!DNL HSTS] actualiza las llamadas para usar [!DNL HTTPS] en su lugar, y todas [!DNL DCS] las llamadas posteriores procedentes de `yourcompany.demdex.com` se utilizarán [!DNL HTTPS] en lugar de [!DNL HTTP].

Consulte Seguridad de transporte [HTTP estricta - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) para obtener más información sobre HSTS.
