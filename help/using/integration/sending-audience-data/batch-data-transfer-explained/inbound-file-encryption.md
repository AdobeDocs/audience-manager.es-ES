---
description: Como opción, puede cifrar archivos de datos con cifrado PGP al enviarlos a Audience Manager.
seo-description: As an option, you can encrypt data files with PGP encryption when sending them to Audience Manager.
seo-title: File PGP Encryption for Inbound Data Types
solution: Audience Manager
title: Cifrado PGP de archivo para tipos de datos de entrada
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
TQID: https://experienceleague.adobe.com/eUhGeYNzSeQxjQ0VWydB8vnmgFh9GnWQQ3VmAG73w-k
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 165
ht-degree: 0%

---

# Cifrado PGP de archivo para tipos de datos de entrada{#file-pgp-encryption-for-inbound-data-types}

Puede cifrar archivos de datos con cifrado de [!DNL PGP] al enviarlos a Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>El cifrado [!DNL PGP] incluye la compresión de archivos. Al enviar [!DNL PGP] archivos de entrada cifrados, asegúrese de no [comprimirlos](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) con gzip (`.gz`).
>
>[!DNL PGP] archivos de entrada cifrados que también están [comprimidos](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) no son válidos en Audience Manager.

Siga los pasos descritos a continuación para cifrar los archivos de datos de entrada.

1. Descargar la [clave pública de Audience Manager](./assets/adobe_pgp.pub).
2. Importe la clave pública a su almacén de confianza.

   Por ejemplo, si usa [!DNL GPG], el comando podría ser similar al siguiente:

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

   Todos los datos cifrados deben usar `.pgp` o `.gpg` como extensión de archivo (por ejemplo, `ftp_dpm_100_123456789.sync.pgp` o `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager solo admite el algoritmo de cifrado de datos [!DNL Advanced Encryption Standard (AES)]. Audience Manager admite cualquier tamaño de clave.
