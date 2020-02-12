---
description: Como opción, puede cifrar archivos de datos con codificación PGP al enviarlos a Audience Manager.
seo-description: Como opción, puede cifrar archivos de datos con codificación PGP al enviarlos a Audience Manager.
seo-title: Cifrado PGP de archivo para tipos de datos de entrada
solution: Audience Manager
title: Cifrado PGP de archivo para tipos de datos de entrada
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
translation-type: tm+mt
source-git-commit: 8d2d841f8e94fd67c2165eb280b85ab18001d77e

---


# Cifrado PGP de archivo para tipos de datos de entrada{#file-pgp-encryption-for-inbound-data-types}

Como opción, puede cifrar archivos de datos con [!DNL PGP] codificación al enviarlos a Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>Actualmente no se admite el cifrado y la compresión en el mismo archivo de datos de entrada. Puede seleccionar cifrar o [comprimir](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) los archivos de entrada.
>
> Sin embargo, tenga en cuenta que el cifrado PGP incluye compresión incorporada.

Siga los pasos que se describen a continuación para cifrar los archivos de datos de entrada.

1. Descargue la clave [pública de](./assets/adobe_pgp.pub)Audience Manager.
1. Importe la clave pública en la tienda de confianza.

   Por ejemplo, si utiliza [!DNL GPG], el comando podría ser similar al siguiente:

   `gpg --import adobe_pgp.pub`

1. Valide que la clave se haya importado correctamente ejecutando el siguiente comando:

   `gpg --list-keys`

   Debería ver un mensaje similar al siguiente:

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

1. Cifre los datos de entrada mediante el siguiente comando:

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   Todos los datos cifrados deben utilizarse `.pgp` o `.gpg` como extensión de archivo (por ejemplo `ftp_dpm_100_123456789.sync.pgp` o `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager solo admite el algoritmo de cifrado de datos [!DNL Advanced Encryption Standard (AES)] . Audience Manager admite cualquier tamaño clave.
