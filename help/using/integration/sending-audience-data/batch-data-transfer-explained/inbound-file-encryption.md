---
description: Como opción, puede codificar archivos de datos con codificación PGP al enviarlos a Audience Manager.
seo-description: Como opción, puede codificar archivos de datos con codificación PGP al enviarlos a Audience Manager.
seo-title: Codificación PGP de archivo para tipos de datos entrantes
solution: Audience Manager
title: Codificación PGP de archivo para tipos de datos entrantes
uuid: 89 caace 1-0259-48 fc -865 b-d 525 ec 7822 f 7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# File PGP Encryption for Inbound Data Types{#file-pgp-encryption-for-inbound-data-types}

As an option, you can encrypt data files with [!DNL PGP] encryption when sending them to Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>Actualmente no admitimos cifrado ni compresión en el mismo archivo de datos de entrada. You can select to either encrypt or [compress](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) your inbound files.

Siga los pasos descritos a continuación para codificar los archivos de datos de entrada.

1. Download the [Audience Manager public key](./assets/adobe_pgp.pub).
1. Importe la clave pública a su tienda de confianza.

   For example, if you use [!DNL GPG], the command could be similar to the following:

   `gpg --import adobe_pgp.pub`

1. Valide que la clave se haya importado correctamente ejecutando el comando siguiente:

   `gpg --list-keys`

   Debería ver un mensaje similar al siguiente:

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

1. Codifique los datos de entrada utilizando el comando siguiente:

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   All encrypted data must use `.pgp` or `.gpg` as the file extension (e.g. `ftp_dpm_100_123456789.sync.pgp` or `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager supports only the [!DNL Advanced Encryption Standard (AES)] data-encryption algorithm. Audience Manager admite cualquier tamaño clave.