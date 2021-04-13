---
description: Como opción, puede cifrar archivos de datos con cifrado PGP al enviarlos al Audience Manager.
seo-description: Como opción, puede cifrar archivos de datos con cifrado PGP al enviarlos al Audience Manager.
seo-title: Cifrado PGP de archivo para tipos de datos de entrada
solution: Audience Manager
title: Cifrado PGP de archivo para tipos de datos de entrada
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Transferencias de datos de entrada
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 12%

---

# Cifrado PGP de archivo para tipos de datos de entrada{#file-pgp-encryption-for-inbound-data-types}

Puede cifrar archivos de datos con cifrado [!DNL PGP] al enviarlos al Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] el cifrado incluye la compresión de archivos. Al enviar [!DNL PGP] archivos de entrada cifrados, asegúrese de no [comprimirlos](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) mediante gzip (`.gz`).
>
>[!DNL PGP] los archivos de entrada cifrados que también se  [](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) comprimen no son válidos en el Audience Manager.

Siga los pasos descritos a continuación para cifrar archivos de datos entrantes.

1. Descargue la [clave pública del Audience Manager](./assets/adobe_pgp.pub).
2. Importe la clave pública en la tienda de confianza.

   Por ejemplo, si utiliza [!DNL GPG], el comando podría ser similar al siguiente:

   `gpg --import adobe_pgp.pub`

3. Valide que la clave se haya importado correctamente ejecutando el siguiente comando:

   `gpg --list-keys`

   Debería ver un mensaje similar al siguiente:

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. Cifre los datos de entrada mediante el siguiente comando:

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   Todos los datos cifrados deben utilizar `.pgp` o `.gpg` como extensión del archivo (p. ej. `ftp_dpm_100_123456789.sync.pgp` o `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager solo admite el algoritmo de cifrado de datos [!DNL Advanced Encryption Standard (AES)] . Audience Manager admite cualquier tamaño de clave.
