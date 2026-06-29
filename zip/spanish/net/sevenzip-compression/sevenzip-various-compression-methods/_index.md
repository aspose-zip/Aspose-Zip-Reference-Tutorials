---
date: 2026-06-29
description: Aprenda cómo comprimir una carpeta a 7z con Aspose.Zip para .NET, cubriendo
  los métodos de compresión de 7z como LZMA2, BZip2 y Store. Perfecto para crear archivos
  7z de forma programática.
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip con varios métodos de compresión
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cómo comprimir una carpeta a 7z – Tutorial de Aspose.Zip para .NET
url: /es/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo comprimir una carpeta a 7z – Tutorial de Aspose.Zip para .NET

## Introducción

Si necesitas **compress folder to 7z** archivos de forma programática en una aplicación .NET, has llegado al lugar correcto. Aspose.Zip para .NET facilita la generación de archivos Seven Zip con cualquiera de los algoritmos de compresión compatibles, ya sea que quieras empaquetar un directorio completo para su distribución o simplemente necesites una solución fiable de **seven zip archive .net**. En esta guía recorreremos tres métodos de compresión populares—LZMA2, BZip2 y Store (sin compresión)—y te mostraremos exactamente cómo producir un archivo 7z en solo unas pocas líneas de código C#.

## Respuestas rápidas
- **¿Qué biblioteca debo usar?** Aspose.Zip para .NET proporciona el conjunto más completo de funciones Seven Zip.  
- **¿Qué método de compresión ofrece la mejor relación?** LZMA2 suele ofrecer la mayor compresión para datos mixtos.  
- **¿Puedo crear un 7z sin compresión?** Sí—utiliza el método Store (sin compresión).  
- **¿Necesito una licencia para desarrollo?** Hay una prueba gratuita disponible; se requiere una licencia para uso en producción.  
- **¿Es compatible con .NET 6/7?** Absolutamente—Aspose.Zip soporta .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 y .NET 5–10.

## ¿Cuáles son los métodos de compresión Seven Zip?

Seven Zip soporta varios algoritmos, cada uno optimizado para diferentes escenarios. **LZMA2** ofrece la mayor relación de compresión (a menudo 30‑40 % más pequeño que BZip2), **BZip2** brinda una compresión sólida con mayor compatibilidad con herramientas heredadas, y **Store** simplemente archiva los archivos sin reducirlos, preservando perfectamente las marcas de tiempo originales.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

- Conocimientos básicos de C# y Visual Studio.  
- La biblioteca Aspose.Zip para .NET instalada. Descárgala desde la página oficial de descargas **[here](https://releases.aspose.com/zip/net/)**.  
- Una carpeta (`dataDir`) que contenga los archivos que deseas archivar.

## Importar espacios de nombres

Primero, agrega los espacios de nombres requeridos a tu archivo C#:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Estas clases te dan acceso a la configuración de compresión y al manejo de archivos.

## Compresión LZMA2 – Cómo crear un 7z con la máxima relación

La clase `Archive` representa un archivo 7z que puede contener múltiples archivos.  
El algoritmo LZMA2 ofrece la mayor relación de compresión entre los métodos compatibles. Funciona dividiendo la entrada en bloques y aplicando una compresión de diccionario sofisticada. En Aspose.Zip estableces `CompressionMethod` a `CompressionMethod.Lzma2` en el objeto `Archive` antes de agregar archivos.

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **Consejo profesional:** LZMA2 funciona mejor cuando los archivos de origen son mayores de 1 MB. Para muchos archivos pequeños, BZip2 puede ser más rápido.

## Compresión BZip2 – Una opción equilibrada

La clase `Archive` representa un archivo 7z que puede contener múltiples archivos.  
BZip2 ofrece una compresión sólida con buena compatibilidad para herramientas más antiguas. Utiliza la transformación Burrows‑Wheeler y la codificación Huffman para reducir el tamaño. En Aspose.Zip seleccionas `CompressionMethod.BZip2` al configurar la instancia `Archive`, lo que equilibra velocidad y relación de compresión para la mayoría de archivos de texto y binarios.

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 ofrece una compresión sólida manteniendo una velocidad razonable, lo que lo convierte en una buena alternativa cuando LZMA2 no es compatible con el entorno de destino.

## Store (Sin compresión) – Cuando el tamaño no importa

La clase `Archive` representa un archivo 7z que puede contener múltiples archivos.  
El método Store crea un archivo sin comprimir los datos. Simplemente copia los archivos originales al contenedor 7z, preservando marcas de tiempo y la estructura de directorios. Para usarlo en Aspose.Zip, establece `CompressionMethod.Store` en el `Archive` antes de agregar los archivos que deseas empaquetar.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Utiliza el método Store si simplemente necesitas agrupar archivos sin alterar su tamaño—perfecto para preservar marcas de tiempo originales o cuando el archivo será descomprimido al instante.

## ¿Cómo agrego archivos a 7z?

Agrega archivos a un archivo 7z creando una instancia `Archive`, estableciendo el `CompressionMethod` deseado y llamando a `AddAllFiles(dataDir)`. El método escanea la carpeta especificada de forma recursiva, preservando la jerarquía de directorios dentro del archivo. Este enfoque te permite **compress folder to 7z** con una sola línea de código después de la configuración inicial.

## Casos de uso comunes

| Escenario | Método recomendado |
|----------|--------------------|
| Distribuir instaladores grandes | LZMA2 |
| Compartir registros con herramientas heredadas | BZip2 |
| Empaquetar archivos para extracción rápida | Store (no compression) |
| Necesitar **compress folder to 7z** al instante en un servicio web | LZMA2 (para la mejor relación) |

## Solución de problemas y consejos

- **¿Faltan archivos en el archivo?** Verifica que `dataDir` apunte al directorio correcto y que el proceso tenga permisos de lectura.  
- **¿El archivo no se abre en versiones antiguas de 7‑Zip?** Quédate con BZip2 o Store, ya que LZMA2 puede requerir bibliotecas de descompresión más recientes.  
- **¿Cuello de botella de rendimiento?** Para conjuntos de datos masivos, considera transmitir el archivo en lugar de cargar todas las entradas en memoria.

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Zip para .NET con cualquier tipo de archivo?**  
A: Sí, Aspose.Zip soporta una amplia gama de formatos de archivo, permitiéndote comprimir y descomprimir prácticamente cualquier tipo de archivo.

**Q: ¿Hay una prueba gratuita disponible para Aspose.Zip para .NET?**  
A: Sí, puedes obtener una prueba gratuita **[here](https://releases.aspose.com/)**.

**Q: ¿Dónde puedo encontrar la documentación de Aspose.Zip para .NET?**  
A: La referencia completa de la API está disponible **[here](https://reference.aspose.com/zip/net/)**.

**Q: ¿Cómo puedo obtener licencias temporales para Aspose.Zip para .NET?**  
A: Las licencias temporales se pueden obtener **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: ¿Dónde puedo obtener soporte para Aspose.Zip para .NET?**  
A: Puedes buscar soporte en el **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.

---

**Última actualización:** 2026-06-29  
**Probado con:** Aspose.Zip para .NET 24.12  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [comprimir archivos c# – Crear archivo 7z con Aspose.Zip para .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [Cómo comprimir una carpeta usando Aspose.Zip para .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [Cómo comprimir LZMA en Aspose.Zip para .NET](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}