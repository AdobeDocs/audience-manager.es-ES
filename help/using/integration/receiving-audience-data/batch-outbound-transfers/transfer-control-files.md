---
description: Los archivos de control de transferencia (.info) proporcionan información de metadatos sobre las transferencias de archivos para que los socios puedan comprobar que Audience Manager gestiona correctamente las transferencias de archivos.
seo-description: Los archivos de control de transferencia (.info) proporcionan información de metadatos sobre las transferencias de archivos para que los socios puedan comprobar que Audience Manager gestiona correctamente las transferencias de archivos.
seo-title: Archivos de transferencia y control para transferencias de archivos de registro
solution: Audience Manager
title: Archivos de transferencia y control para transferencias de archivos de registro
uuid: ef58213e-7b37-4c5a-8556-0de695706793
translation-type: tm+mt
source-git-commit: c5f9845a48d9d4432f38e9a0aaa256d89f9c1c11

---


# Archivos de transferencia y control para transferencias de archivos de registro {#transfer-control-files-for-log-file-transfers}

Los archivos de control de transferencia ([!DNL .info]) proporcionan información de metadatos sobre las transferencias de archivos para que los socios puedan comprobar que Audience Manager gestiona correctamente las transferencias de archivos.

[!DNL Audience Manager] envía un archivo de control de transferencia a un socio con cada transferencia de archivos. Debido a la naturaleza de varios subprocesos del [!DNL FTP] publicador, el archivo de control de transferencia se puede enviar antes de que los archivos reales terminen de transferirse.

Los metadatos del [!DNL .info] archivo permiten a los socios:

* Determinar cuándo se completa un ciclo completo de transferencia (se ha entregado el número total de archivos de la secuencia);
* Determinar si un archivo determinado de la secuencia es completo o correcto (examinando el tamaño del archivo en bytes y el número total de líneas);
* Validar el número de filas de los archivos sin procesar en comparación con el número de filas después de cargar los archivos en la base de datos en el extremo receptor (tamaño del archivo en líneas).

## Convenciones de nomenclatura de archivos {#file-naming-conventions}

El archivo transfer-control tiene el mismo nombre que la raíz del lote/secuencia con una extensión [!DNL .info] de archivo.

Por ejemplo, si el nombre del primer archivo de la secuencia es: [!DNL ftp_12345_67890_full_1500727351632-1.sync], el nombre del archivo de control sería [!DNL ftp_12345_67890_iter_1500727351632.info].

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
> Los números totales del lote son exclusivos del [!DNL .info] archivo mismo. Es decir, los totales no incluyen el [!DNL .info] archivo, su tamaño de byte ni su recuento de líneas.
>
> Los tamaños de bytes de los archivos y los recuentos de líneas incluyen todas las líneas/filas de encabezado y espaciador (en blanco). Para obtener el recuento de líneas/filas de datos reales, reste encabezados.
>
> Las líneas totales en el tamaño de lote y de byte total incluyen todas las filas de espacio y encabezado.