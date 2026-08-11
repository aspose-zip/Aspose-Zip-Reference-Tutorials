---
date: 2026-05-30
description: Aprenda cómo crear zip sin compresión en .NET con Aspose.Zip para .NET.
  Esta guía le muestra cómo crear archivos zip sin compresión, almacenar archivos
  sin comprimir y gestionar archivos de forma eficiente.
keywords:
- zip without compression
- generate zip archive .net
- Aspose.Zip uncompressed
linktitle: Almacenar varios archivos sin compresión
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  headline: Create zip without compression in .NET using Aspose.Zip
  type: TechArticle
- description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  name: Create zip without compression in .NET using Aspose.Zip
  steps:
  - name: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
    text: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
  - name: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
    text: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
  - name: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
    text: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
  type: HowTo
- questions:
  - answer: Yes, you can create different `ArchiveEntrySettings` for each file and
      mix compressed and uncompressed entries in the same archive.
    question: Can I compress specific file types while storing others without compression?
  - answer: Absolutely. The library supports .NET Framework, .NET Core, .NET Standard,
      and the latest .NET versions.
    question: Is Aspose.Zip for .NET compatible with .NET Core and .NET 5/6?
  - answer: Wrap the archiving code in a `try‑catch` block and log the exception details.
      This ensures graceful failure and easier debugging.
    question: How should I handle exceptions during the archiving process?
  - answer: Yes, you can process multiple files in parallel and add them to the archive,
      but remember that the `Archive` object itself is not thread‑safe; synchronize
      access when adding entries.
    question: Does Aspose.Zip support multi‑threaded archiving?
  - answer: Definitely. The API is designed for simple drop‑in usage. Refer to the
      official [documentation](https://reference.aspose.com/zip/net/) for migration
      guidance.
    question: Can I integrate Aspose.Zip into an existing project without major code
      changes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Crear zip sin compresión en .NET usando Aspose.Zip
url: /es/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear zip sin compresión en .NET usando Aspose.Zip

En el desarrollo moderno de .NET, **crear un zip sin compresión** puede mejorar drásticamente la velocidad de archivado y mantener los tamaños de archivo predecibles. Cuando necesitas **archivar archivos sin compresión** —por ejemplo, para cumplir con normas regulatorias, acelerar el procesamiento posterior, o garantizar que la secuencia original de bytes permanezca intacta— Aspose.Zip para .NET ofrece una API limpia y directa. En este tutorial recorreremos los pasos exactos para crear un archivo ZIP sin comprimir, agregar archivos e integrar la solución en tu aplicación.

## Respuestas rápidas
- **¿Qué significa “zip sin comprimir”?** Es un archivo ZIP donde cada entrada se almacena usando el método “store”, dejando los bytes originales del archivo sin tocar.  
- **¿Por qué evitar la compresión?** Para acelerar el archivado, preservar los tamaños originales de los archivos para el procesamiento posterior, o cumplir con requisitos regulatorios que prohíben la alteración de datos.  
- **¿Qué clase de Aspose.Zip maneja esto?** `ArchiveEntrySettings` combinada con `StoreCompressionSettings`.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Versiones de .NET compatibles?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 y .NET 5–10.  

## Qué es zip sin compresión?
**Zip sin compresión** es un archivo ZIP donde cada entrada de archivo usa el método *store*, lo que significa que los datos se copian literalmente al archivo sin aplicar ningún algoritmo de compresión. Esto da como resultado un archivo cuyo tamaño es esencialmente la suma de los archivos originales más unos pocos bytes de sobrecarga ZIP.

## Por qué usar Aspose.Zip para archivos zip sin compresión?
Aspose.Zip está optimizado para archivado de alto rendimiento, permitiéndote almacenar archivos instantáneamente sin la sobrecarga de los algoritmos de compresión. Garantiza compatibilidad total con ZIP, te permite mezclar entradas almacenadas y comprimidas, y ofrece una API sencilla que abstrae las estructuras ZIP de bajo nivel, haciendo la implementación rápida y fiable.

## Requisitos previos
- **Aspose.Zip for .NET** – integrado en tu proyecto. Consulta la [documentación](https://reference.aspose.com/zip/net/) oficial para los pasos de instalación.  
- **Entorno de desarrollo .NET** – Visual Studio, VS Code o cualquier IDE que prefieras.  
- **Directorio de documentos** – una carpeta en tu máquina que contiene los archivos que deseas archivar (p. ej., “Your Document Directory”).

## Importar espacios de nombres
Antes de escribir cualquier código, importa los espacios de nombres requeridos para que el compilador sepa dónde encontrar las clases de Aspose.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## Paso 1: Establecer el directorio de documentos
Define la ruta donde se encuentran tus archivos fuente. Reemplaza el marcador de posición con la carpeta real en tu sistema.

```csharp
string dataDir = "Your Document Directory";
```

## Paso 2: Crear archivo Zip sin compresión
El núcleo del tutorial: creamos una instancia de `Archive` configurada con `StoreCompressionSettings`. `Archive` representa un contenedor ZIP que puede contener múltiples entradas. `StoreCompressionSettings` especifica que una entrada debe almacenarse sin compresión. Esto indica a Aspose.Zip que *almacene* (es decir, no comprima) cada entrada.

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **Consejo profesional:** Si necesitas **guardar archivos en zip** mientras comprimes algunos y dejas otros sin comprimir, crea instancias separadas de `ArchiveEntrySettings` para cada archivo y añádelas al mismo `Archive`.

## ¿Cómo crear zip sin compresión en .NET?
Carga tus archivos fuente, instancia un objeto `Archive` y agrega cada archivo usando `ArchiveEntrySettings` con `new StoreCompressionSettings()`. Toda la operación requiere solo tres líneas de código y se ejecuta en tiempo lineal respecto al tamaño total de los archivos, brindándote la experiencia de archivado más rápida posible.

### Guía paso a paso
1. **Crear el archivo** – instancia `Archive` con un flujo objetivo o ruta de archivo.  
2. **Configurar la configuración de entrada** – para cada archivo, crea un objeto `ArchiveEntrySettings` y asigna `new StoreCompressionSettings()` a su propiedad `Compression`.  
3. **Agregar entradas** – llama a `archive.Add(entrySettings)` para cada archivo, luego finaliza con `archive.Save()`.

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| **Archivo no encontrado** | Ruta `dataDir` incorrecta o falta la extensión del archivo. | Verifica la ruta y asegura que los archivos existan. Usa `Path.Combine` para una concatenación más segura. |
| **Acceso denegado** | El proceso no tiene permiso para leer los archivos fuente o escribir el ZIP. | Ejecuta la aplicación con los derechos adecuados o elige una carpeta con acceso de escritura. |
| **Tamaño de archivo inesperado en ZIP** | El archivo se creó con compresión predeterminada. | Asegúrate de que `new StoreCompressionSettings()` se pase a `ArchiveEntrySettings`. |

## Preguntas frecuentes

**P: ¿Puedo comprimir tipos de archivo específicos mientras almaceno otros sin compresión?**  
R: Sí, puedes crear diferentes `ArchiveEntrySettings` para cada archivo y mezclar entradas comprimidas y sin comprimir en el mismo archivo.

**P: ¿Es Aspose.Zip para .NET compatible con .NET Core y .NET 5/6?**  
R: Absolutamente. La biblioteca soporta .NET Framework, .NET Core, .NET Standard y las versiones más recientes de .NET.

**P: ¿Cómo debo manejar excepciones durante el proceso de archivado?**  
R: Envuelve el código de archivado en un bloque `try‑catch` y registra los detalles de la excepción. Esto asegura una falla controlada y una depuración más fácil.

**P: ¿Aspose.Zip soporta archivado multihilo?**  
R: Sí, puedes procesar varios archivos en paralelo y agregarlos al archivo, pero recuerda que el objeto `Archive` no es seguro para hilos; sincroniza el acceso al agregar entradas.

**P: ¿Puedo integrar Aspose.Zip en un proyecto existente sin cambios de código importantes?**  
R: Definitivamente. La API está diseñada para un uso sencillo de tipo drop‑in. Consulta la [documentación](https://reference.aspose.com/zip/net/) oficial para obtener orientación de migración.

**Última actualización:** 2026-05-30  
**Probado con:** Aspose.Zip for .NET (última versión al momento de escribir)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}