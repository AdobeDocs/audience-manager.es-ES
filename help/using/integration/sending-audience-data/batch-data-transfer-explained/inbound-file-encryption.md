---
description: Como opción, puede cifrar archivos de datos con cifrado PGP al enviarlos al Audience Manager.
seo-description: As an option, you can encrypt data files with PGP encryption when sending them to Audience Manager.
seo-title: File PGP Encryption for Inbound Data Types
solution: Audience Manager
title: Cifrado PGP de archivo para tipos de datos de entrada
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 8%

---

# Cifrado PGP de archivo para tipos de datos de entrada{#file-pgp-encryption-for-inbound-data-types}

Puede cifrar archivos de datos con [!DNL PGP] cifrado al enviarlos al Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] el cifrado incluye la compresión de archivos. Al enviar [!DNL PGP] los archivos de entrada cifrados garantizan que no [comprimir](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) usando gzip (`.gz`).
>
>[!DNL PGP] archivos de entrada cifrados que también son [comprimido](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) no son válidos en el Audience Manager.

Siga los pasos descritos a continuación para cifrar los archivos de datos de entrada.

1. Descargue la [clave pública del Audience Manager](./assets/adobe_pgp.pub).
2. Importe la clave pública a su almacén de confianza.

   Por ejemplo, si utiliza [!DNL GPG], el comando podría ser similar al siguiente:

   `gpg --import adobe_pgp.pub`

3. Compruebe que la clave se haya importado correctamente ejecutando el siguiente comando:

   `gpg --list-keys`

   Debería ver un mensaje similar al siguiente:

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. Cifre los datos de entrada con el siguiente comando:

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   Todos los datos cifrados deben utilizar `.pgp` o `.gpg` como la extensión del archivo (p. ej. `ftp_dpm_100_123456789.sync.pgp` o `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >El Audience Manager solo admite [!DNL Advanced Encryption Standard (AES)] algoritmo de cifrado de datos. El Audience Manager admite cualquier tamaño de clave.
