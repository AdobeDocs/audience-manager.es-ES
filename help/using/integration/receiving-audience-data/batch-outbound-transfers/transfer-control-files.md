---
description: Los archivos de control de transferencia (.info) proporcionan información de metadatos sobre las transferencias de archivos para que los socios puedan comprobar que el Audience Manager ha gestionado correctamente las transferencias de archivos.
seo-description: Los archivos de control de transferencia (.info) proporcionan información de metadatos sobre las transferencias de archivos para que los socios puedan comprobar que el Audience Manager ha gestionado correctamente las transferencias de archivos.
seo-title: Archivos de transferencia y control para transferencias de archivos de registro
solution: Audience Manager
title: Archivos de transferencia y control para transferencias de archivos de registro
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Transferencias de datos de salida
exl-id: 4fd1aab1-2dc2-4de9-97be-58e79825db40
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 6%

---

# Archivos de transferencia y control para transferencias de archivos de registro {#transfer-control-files-for-log-file-transfers}

Los archivos de control de transferencia ([!DNL .info]) proporcionan información de metadatos sobre las transferencias de archivos para que los socios puedan comprobar que el Audience Manager ha gestionado correctamente las transferencias de archivos.

[!DNL Audience Manager] envía un archivo de control de transferencia a un socio con cada transferencia de archivos. Debido a la naturaleza de subprocesos múltiples del editor [!DNL FTP], el archivo de control de transferencia puede enviarse antes de que los archivos reales terminen de transferirse.

Los metadatos del archivo [!DNL .info] permiten a los socios:

* Determinar cuándo se ha completado un ciclo completo de transferencia (el número total de archivos de la secuencia se han entregado);
* Determine si un archivo determinado de la secuencia es completo o correcto (examinando el tamaño del archivo en bytes y el número total de líneas);
* Valide el número de filas de archivos sin procesar frente al número de filas después de cargar los archivos en la base de datos en el extremo receptor (tamaño del archivo en líneas).

## Convenciones de nomenclatura de archivos {#file-naming-conventions}

El archivo de control de transferencia tiene el mismo nombre que la raíz del lote/secuencia con una extensión de archivo [!DNL .info].

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

>[!NOTE]
>
> Los números totales de lote son exclusivos del propio archivo [!DNL .info]. Es decir, los totales no incluyen el archivo [!DNL .info], su tamaño de byte ni su recuento de líneas.
>
> Los tamaños de bytes de los archivos y los recuentos de líneas incluyen todas las líneas/filas de encabezado y separador (en blanco). Para obtener el recuento de líneas/filas de datos reales, reste encabezados.
>
> Las líneas totales en lote y el tamaño total de bytes incluyen cualquier fila de espacio y encabezado.
