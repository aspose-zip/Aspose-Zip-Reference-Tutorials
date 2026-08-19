---
date: 2026-07-18
description: Aprenda cómo agregar una carpeta al zip y agregar archivos al zip usando
  Aspose.Zip for .NET. Esta guía paso a paso muestra cómo comprimir archivos con FileInfo
  en proyectos ASP.NET.
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: Comprimir archivos usando FileInfo
og_description: Agregar carpeta al zip usando Aspose.Zip for .NET. Aprenda cómo crear
  un archivo zip, agregar archivos al zip y comprimir carpetas de manera eficiente
  en ASP.NET.
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: Agregar carpeta al zip – Comprimir archivos con Aspose.Zip for .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: Agregar carpeta al zip usando Aspose.Zip for .NET – Comprimir archivos con
  FileInfo
url: /es/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Añadir carpeta a zip usando Aspose.Zip para .NET

## Introducción

Si necesita **añadir carpeta a zip** de forma programática, Aspose.Zip para .NET ofrece una API limpia y de alto rendimiento que funciona en cualquier .NET (incluyendo ASP.NET). En este tutorial recorreremos la compresión de archivos con la clase `FileInfo`, le mostraremos cómo **añadir archivos a zip** y explicaremos por qué este enfoque es ideal para proyectos .NET modernos. También cubriremos los pasos exactos para **añadir carpeta a zip** para que pueda agrupar directorios completos en una sola operación. ¡Comencemos!

## Respuestas rápidas
- **¿Cuál es la forma más fácil de crear un archivo zip?** Use la clase `Archive` de Aspose.Zip junto con objetos `FileInfo`.  
- **¿Puedo añadir varios archivos a la vez?** Sí, solo cree un `FileInfo` para cada archivo y llame a `CreateEntry`.  
- **¿Necesito una licencia especial para ASP.NET?** Se requiere una licencia comercial de Aspose.Zip para producción; una prueba gratuita funciona para evaluación.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 y .NET 5–10.  
- **¿La API es segura para subprocesos?** Sí, siempre que cada subproceso trabaje con su propia instancia de `Archive`.

## Qué es un archivo Zip y por qué crear uno

Un archivo zip agrupa uno o más archivos en un único contenedor comprimido. Esto reduce el espacio de almacenamiento, acelera las transferencias de red y simplifica la distribución. Ya sea que esté entregando registros, exportando informes o empaquetando recursos para un cliente, saber **cómo crear archivos zip** de forma programática es una habilidad valiosa para cualquier desarrollador .NET.

## ¿Por qué usar Aspose.Zip para añadir archivos a zip?

Aspose.Zip ofrece una solución puramente .NET que elimina dependencias externas mientras brinda a los desarrolladores un control granular sobre la compresión, la codificación y la seguridad. Soporta archivos grandes, protección con contraseña y funciona de manera consistente en todas las versiones .NET compatibles, lo que lo convierte en una opción fiable tanto para aplicaciones heredadas como modernas.  

- **Cero dependencias externas** – implementación puramente .NET.  
- **Control total sobre el nivel de compresión y la codificación** (ASCII, UTF‑8, etc.).  
- **Soporta archivos de más de 4 GB** y protección con contraseña.  
- **API consistente en más de 50 versiones .NET** – desde .NET Framework 2.0 hasta .NET 10.  

## Requisitos previos

Antes de sumergirnos en el código, asegúrese de tener:

1. **Aspose.Zip para .NET** instalado. Descargue el paquete más reciente desde la [página de descarga de Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Una carpeta en su máquina que contenga los archivos que desea comprimir (p. ej., `alice29.txt` y `fields.c`).  

## Importar espacios de nombres

En cualquier archivo C# donde trabajará con archivos zip, agregue las siguientes sentencias `using`:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Estos espacios de nombres le dan acceso a la clase `Archive`, opciones de guardado y las utilidades estándar de E/S.

## Guía paso a paso

### Paso 1: Configurar su directorio de documentos

Primero, defina la carpeta que contiene los archivos de origen. Reemplace el marcador de posición con la ruta absoluta o relativa en su sistema:

```csharp
string dataDir = "Your Document Directory";
```

> **Consejo profesional:** Use `Path.Combine` para construir rutas de forma multiplataforma.

### Paso 2: Abrir un archivo zip para escritura

Crear un `FileStream` que apunte al archivo zip de salida. El flujo se abre en modo **Create**, que sobrescribe cualquier archivo existente con el mismo nombre:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Paso 3: Preparar objetos `FileInfo` para cada archivo de origen

`FileInfo` brinda a Aspose.Zip acceso directo a los archivos físicos en disco. Cree una instancia por cada archivo que desee comprimir:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **¿Por qué usar `FileInfo`?** Evita cargar todo el archivo en memoria, lo cual es especialmente útil para archivos grandes.

### Paso 4: Crear el archivo y añadir entradas

La clase `Archive` es el objeto central de Aspose.Zip que representa un contenedor zip en memoria. Instancie un objeto `Archive`, luego llame a `CreateEntry` para cada `FileInfo`. El primer argumento es el nombre que el archivo tendrá dentro del zip, el segundo argumento es el `FileInfo` de origen:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

El método `CreateEntry` añade una nueva entrada de archivo al archivo, vinculando el nombre de la entrada con el `FileInfo` de origen para que los datos se transmitan directamente desde el disco cuando se guarde el archivo.

### Paso 5: Guardar el archivo zip con la codificación deseada

Finalmente, persista el archivo en el `FileStream` que abrió anteriormente. Aquí usamos codificación ASCII para los nombres de entrada, pero puede cambiar a UTF‑8 si sus nombres de archivo contienen caracteres no ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Cuando los bloques `using` finalizan, los flujos se cierran automáticamente y el archivo zip está listo para usarse.

## ¿Cómo añadir una carpeta a zip usando Aspose.Zip?

Cargue el directorio objetivo, enumere cada archivo y añada cada uno con una ruta relativa que incluya el nombre de la carpeta. Este enfoque le permite **añadir carpeta a zip** sin listar manualmente cada archivo. Al preservar la jerarquía de carpetas en los nombres de entrada, el archivo resultante puede extraerse con la estructura de directorios original intacta, lo cual es esencial para muchos escenarios de despliegue.

1. Use `DirectoryInfo` para apuntar a la carpeta que desea comprimir.  
2. Llame a `GetFiles("*", SearchOption.AllDirectories)` para obtener todos los archivos de forma recursiva.  
3. Para cada archivo, cree un `FileInfo` y llame a `CreateEntry` con una ruta como `"MyFolder/Report.pdf"`.  

Debido a que la API trabaja con `FileInfo`, transmite cada archivo directamente desde el disco, manteniendo bajo el uso de memoria incluso para carpetas que contienen cientos de megabytes.

## Problemas comunes y soluciones

| Problema | Causa | Solución |
|----------|-------|----------|
| **Empty zip file** | `FileInfo` points to a non‑existent path | Verify `dataDir` and file names; use `File.Exists` to check before creating entries. |
| **Incorrect filename encoding** | Using the default encoding with non‑ASCII names | Set `Encoding = Encoding.UTF8` in `ArchiveSaveOptions`. |
| **OutOfMemoryException on large files** | Loading whole file into memory | `FileInfo` streams the file; ensure you are not reading the file into a byte array elsewhere. |
| **Permission denied** | Application lacks write permission for the output folder | Run the app with appropriate rights or choose a writable directory. |

## Preguntas frecuentes

**P: ¿Puedo añadir una carpeta completa a un archivo zip en una sola llamada?**  
R: No existe un método de una sola llamada, pero enumerar los archivos con `DirectoryInfo` y añadir cada uno mediante `CreateEntry` logra el mismo resultado de manera eficiente.

**P: ¿Aspose.Zip soporta protección con contraseña?**  
R: Sí, puede establecer una contraseña en el objeto `Archive` antes de guardar para cifrar todo el archivo.

**P: ¿Qué tan grande puede ser un archivo zip que Aspose.Zip maneje?**  
R: La biblioteca procesa archivos de más de 4 GB y puede crear archivos que superen los 10 GB sin cargar todo el archivo en memoria.

**P: ¿La API es compatible con .NET 6 y .NET 8?**  
R: Absolutamente. Aspose.Zip soporta .NET 5 a través de .NET 10, cubriendo todas las versiones LTS actuales.

**P: ¿Qué niveles de compresión están disponibles?**  
R: Puede elegir `CompressionLevel.NoCompression`, `Fast`, `Normal` o `Maximum` para equilibrar velocidad y tamaño.

## Recursos adicionales

- Descargar el paquete más reciente de Aspose.Zip: [página de descarga de Aspose.Zip](https://releases.aspose.com/zip/net/)  
- Comprar una licencia para uso en producción: [página de compra](https://purchase.aspose.com/buy)  
- Obtener ayuda de la comunidad: [foro de Aspose.Zip](https://forum.aspose.com/c/zip/37)  
- Probar Aspose.Zip gratis: [prueba gratuita aquí](https://releases.aspose.com/)  
- Obtener una licencia temporal para evaluación: [este enlace](https://purchase.aspose.com/temporary-license/)

## Conclusión

Ahora sabe **cómo añadir carpeta a zip** y **cómo crear archivos zip** usando Aspose.Zip para .NET, cómo **añadir archivos a zip**, y por qué este método es ideal para ASP.NET y otras aplicaciones .NET. Experimente con diferentes niveles de compresión, codificaciones y opciones de cifrado para adaptar el archivo a sus necesidades exactas. ¡Feliz compresión!

---

**Last Updated:** 2026-07-18  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Cómo comprimir una carpeta usando Aspose.Zip para .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [Comprimir varios archivos c# – Compresión sin esfuerzo con Aspose.Zip para .NET](/zip/net/file-compression/compress-multiple-files/)
- [Crear archivo Zip .NET – Compresión de archivos con Aspose.Zip](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}