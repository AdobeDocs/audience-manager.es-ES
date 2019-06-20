---
description: Los archivos de control de transferencia (.info) proporcionan información de metadatos sobre las transferencias de archivos para que los socios puedan comprobar que Audience Manager gestiona las transferencias de archivos correctamente.
seo-description: Los archivos de control de transferencia (.info) proporcionan información de metadatos sobre las transferencias de archivos para que los socios puedan comprobar que Audience Manager gestiona las transferencias de archivos correctamente.
seo-title: Transferir archivos de control para transferencias de archivos de registro
solution: Audience Manager
title: Transferir archivos de control para transferencias de archivos de registro
uuid: ef 58213 e -7 b 37-4 c 5 a -8556-0 de 695706793
translation-type: tm+mt
source-git-commit: c5f9845a48d9d4432f38e9a0aaa256d89f9c1c11

---


# Transfer-Control Files for Log File Transfers {#transfer-control-files-for-log-file-transfers}

Transfer-control ([!DNL .info]) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.

[!DNL Audience Manager] envía un archivo de control de transferencia a un socio con cada transferencia de archivos. Due to the multi-thread nature of the [!DNL FTP] publisher, the transfer-control file might be sent before the actual files are finished transferring.

The metadata in the [!DNL .info] file lets partners:

* Determine cuándo se completa un ciclo de transferencia completo (se ha entregado el número total de archivos de la secuencia);
* Determine si un archivo determinado de la secuencia se completa o es correcto (examinando el tamaño del archivo en bytes y el número total de líneas);
* Al validar el número de filas en archivos sin procesar, se ve el número de filas después de que los archivos se hayan cargado en la base de datos en el final (tamaño del archivo en líneas).

## File Naming Conventions {#file-naming-conventions}

The transfer-control file has the same name as the root of the batch/sequence with a [!DNL .info] file extension.s

For example, if the first file in the sequence were named: [!DNL ftp_12345_67890_full_1500727351632-1.sync], the control file would be named [!DNL ftp_12345_67890_iter_1500727351632.info].

## Formato del archivo {#file-format}

```
{
  Files: [
    {
      FileByteSize: 293029329,
      FileLineCount: 36893908,
      FileName: "ftp_12345_67890_full_1500727351632-1.sync.gz",
      FileSequenceNumber: 1,
      md5: "983g634be2ad5263c6a6c4958bf61d9f"
    },
    {
      FileByteSize: 293039238,
      FileLineCount: 36895184,
      FileName: "ftp_12345_67890_full_1500727351632-2.sync.gz",
      FileSequenceNumber: 2,
      md5: "6sn9907c8e78cfd78409622e7b55a984"
    },
    {
      FileByteSize: 293050833,
      FileLineCount: 36896787,
      FileName: "ftp_12345_67890_full_1500727351632-3.sync.gz",
      FileSequenceNumber: 3,
      md5: "7cdfb8e74cd6cec1jy6vel21ccb4a962"
    },
    {
      FileByteSize: 218425764,
      FileLineCount: 27498226,
      FileName: "ftp_12345_67890_full_1500727351632-4.sync.gz",
      FileSequenceNumber: 4,
      md5: "7hs53149f8a2444457g968f04cbbdee5"
    }
  ],
  Totals: {
    FileName: "ftp_12345_67890_full_1500727351632.sync",
    TotalByteSize: 1097545164,
    TotalNumberFiles: 4,
    TotalNumberLines: 138184105
    }
}
```

>[NOTA]
>
> The batch total numbers are exclusive of the [!DNL .info] file itself. That is, the totals do not include the [!DNL .info] file, its byte size, or its line count.
>
> Los tamaños de bytes de archivos y recuentos de líneas incluyen las líneas y filas de encabezado y espaciador (en blanco). Para obtener el recuento de líneas o filas de datos reales, reste los encabezados.
>
> Las líneas totales por lote y tamaño total de bytes incluyen cualquier encabezado y filas de espacio.