---
date: 2026-02-28
description: Aprenda cómo agregar una carpeta a un zip y agregar archivos a un zip
  usando Aspose.Zip para .NET. Esta guía paso a paso muestra cómo comprimir archivos
  con FileInfo en proyectos ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cómo agregar una carpeta a un zip usando Aspose.Zip para .NET – Comprimir archivos
  con FileInfo
url: /es/net/file-compression/compress-files-fileinfo/
weight: 11
---

.

Let's do translation.

I'll write Spanish.

Be careful with bullet points: keep markdown.

Also keep URLs unchanged.

Let's produce.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar una carpeta a un Zip usando Aspose.Zip para .NET

## Introducción

Si necesitas **crear un archivo zip** de forma programática, Aspose.Zip para .NET te ofrece una API limpia y de alto rendimiento que funciona en cualquier aplicación .NET (incluyendo ASP.NET). En este tutorial recorreremos la compresión de archivos con la clase `FileInfo`, te mostraremos cómo **agregar archivos a zip**, y explicaremos por qué este enfoque es ideal para proyectos .NET modernos. También cubriremos cómo **agregar una carpeta a zip** para que puedas empaquetar directorios completos en un solo paso. ¡Comencemos!

## Respuestas rápidas
- **¿Cuál es la forma más fácil de crear un archivo zip?** Usa la clase `Archive` de Aspose.Zip junto con objetos `FileInfo`.  
- **¿Puedo agregar varios archivos a la vez?** Sí, solo crea un `FileInfo` para cada archivo y llama a `CreateEntry`.  
- **¿Necesito una licencia especial para ASP.NET?** Se requiere una licencia comercial de Aspose.Zip para producción; una prueba gratuita funciona para evaluación.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **¿Es la API segura para subprocesos?** Sí, siempre que cada subproceso trabaje con su propia instancia de `Archive`.

## ¿Qué es un archivo Zip y por qué crear uno?
Un archivo zip agrupa uno o más archivos en un único contenedor comprimido. Esto reduce el espacio de almacenamiento, acelera las transferencias de red y simplifica la distribución. Ya sea que entregues registros, exportes informes o empaquetes recursos para un cliente, saber **cómo crear archivos zip** de forma programática es una habilidad valiosa para cualquier desarrollador .NET.

## ¿Por qué usar Aspose.Zip para agregar archivos a zip?
- **Cero dependencias externas** – implementación pura en .NET.  
- **Control total sobre el nivel de compresión y la codificación** (ASCII, UTF‑8, etc.).  
- **Soporta archivos grandes** (> 4 GB) y protección con contraseña.  
- **API consistente entre .NET Framework, .NET Core y .NET 5+**.

## Requisitos previos

Antes de sumergirnos en el código, asegúrate de tener:

1. **Aspose.Zip para .NET** instalado. Descarga el paquete más reciente desde la [página de descarga de Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Una carpeta en tu máquina que contenga los archivos que deseas comprimir (por ejemplo, `alice29.txt` y `fields.c`).  

## Importar espacios de nombres

En cualquier archivo C# donde trabajes con archivos zip, agrega las siguientes sentencias `using`:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Estos espacios de nombres te dan acceso a la clase `Archive`, opciones de guardado y utilidades estándar de I/O.

## Guía paso a paso

### Paso 1: Configura tu directorio de documentos

Primero, define la carpeta que contiene los archivos fuente. Reemplaza el marcador de posición con la ruta absoluta o relativa en tu sistema:

```csharp
string dataDir = "Your Document Directory";
```

> **Consejo profesional:** Usa `Path.Combine` para construir rutas de forma multiplataforma.

### Paso 2: Abre un archivo Zip para escritura

Crea un `FileStream` que apunte al archivo zip de salida. El flujo se abre en modo **Create**, lo que sobrescribe cualquier archivo existente con el mismo nombre:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Paso 3: Prepara objetos `FileInfo` para cada archivo fuente

`FileInfo` le da a Aspose.Zip acceso directo a los archivos físicos en disco. Crea una instancia por cada archivo que quieras comprimir:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **¿Por qué usar `FileInfo`?** Evita cargar todo el archivo en memoria, lo cual es especialmente útil para archivos grandes.

### Paso 4: Crea el archivo y agrega entradas

Instancia un objeto `Archive`, luego llama a `CreateEntry` para cada `FileInfo`. El primer argumento es el nombre que tendrá el archivo dentro del zip, el segundo argumento es el `FileInfo` de origen:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Paso 5: Guarda el archivo Zip con la codificación deseada

Finalmente, persiste el archivo en el `FileStream` que abriste antes. Aquí usamos codificación ASCII para los nombres de entrada, pero puedes cambiar a UTF‑8 si tus nombres de archivo contienen caracteres no ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Cuando los bloques `using` finalizan, los flujos se cierran automáticamente y el archivo zip está listo para usarse.

## Cómo agregar una carpeta a Zip usando Aspose.Zip

Si necesitas **agregar una carpeta a zip** en lugar de archivos individuales, el proceso es sencillo:

1. **Enumera la carpeta** con `DirectoryInfo.GetFiles` (y opcionalmente `GetDirectories` para recursividad).  
2. **Crea un `FileInfo`** para cada archivo descubierto.  
3. **Llama a `CreateEntry`** con una ruta relativa que incluya el nombre de la carpeta, por ejemplo, `"MiCarpeta/Reporte.pdf"`.  

Como la API trabaja con `FileInfo`, nunca tendrás que cargar archivos completos en memoria, lo que la hace segura para directorios grandes. Esta técnica también funciona para escenarios de **zip multiple files asp.net** donde generas un conjunto de informes al vuelo y necesitas entregarlo como un único archivo.

## Problemas comunes y soluciones

| Problema | Causa | Solución |
|----------|-------|----------|
| **Archivo zip vacío** | `FileInfo` apunta a una ruta inexistente | Verifica `dataDir` y los nombres de archivo; usa `File.Exists` para comprobar antes de crear entradas. |
| **Codificación de nombre de archivo incorrecta** | Usar la codificación predeterminada con nombres no ASCII | Establece `Encoding = Encoding.UTF8` en `ArchiveSaveOptions`. |
| **OutOfMemoryException con archivos grandes** | Cargar todo el archivo en memoria | `FileInfo` transmite el archivo; asegúrate de no leer el archivo en un arreglo de bytes en otro lugar. |
| **Permiso denegado** | La aplicación no tiene permiso de escritura en la carpeta de salida | Ejecuta la app con los derechos adecuados o elige un directorio con permisos de escritura. |

## Preguntas frecuentes

**P: ¿Puedo agregar protección con contraseña al archivo zip?**  
R: Sí. Después de crear el `Archive`, establece `archive.Password = "yourPassword"` antes de llamar a `Save`.

**P: ¿Es posible actualizar un archivo zip existente?**  
R: Aspose.Zip permite abrir un archivo existente con `Archive.Open` y luego agregar nuevas entradas.

**P: ¿Cómo comprimo archivos en un controlador ASP.NET MVC?**  
R: El mismo código funciona; solo asegúrate de que el flujo de salida se devuelva como un `FileResult` al cliente.

**P: ¿Aspose.Zip soporta algoritmos de cifrado?**  
R: Soporta ZipCrypto estándar y cifrado AES‑256.

**P: ¿Qué pasa si necesito comprimir una carpeta de forma recursiva?**  
R: Recorre `Directory.GetFiles` (y subcarpetas) y crea un `FileInfo` para cada archivo, luego añádelos al archivo.

## Preguntas frecuentes adicionales

**P: ¿Cómo creo un archivo zip .net para conjuntos de datos grandes?**  
R: Usa objetos `FileInfo` para transmitir datos y establece `CompressionLevel` en `ArchiveSaveOptions` para obtener el mejor rendimiento.

**P: ¿Puedo usar Aspose.Zip en una API web .NET Core (zip files asp.net core)?**  
R: Absolutamente – la biblioteca es totalmente compatible con .NET Core 3.1 y versiones posteriores.

**P: ¿Existe una forma de agregar una carpeta a zip sin escribir un bucle personalizado?**  
R: Aspose.Zip no tiene un método único “add folder”, pero iterar con `DirectoryInfo` es liviano y te brinda control total sobre los nombres de entrada.

**P: ¿La protección con contraseña del archivo zip afecta la velocidad de compresión?**  
R: Habilitar el cifrado añade una pequeña sobrecarga, pero el impacto es mínimo para la mayoría de los casos.

**P: ¿Qué licencia se requiere para despliegue comercial?**  
R: Se necesita una licencia paga de Aspose.Zip para producción; una prueba gratuita puede usarse para desarrollo y pruebas.

## Sección de FAQ existente (sin cambios)

### FAQ's

#### Q1: Is Aspose.Zip compatible con todos los tipos de archivo?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## Conclusión

Ahora sabes **cómo agregar una carpeta a zip** y **cómo crear archivos zip** usando Aspose.Zip para .NET, cómo **agregar archivos a zip**, y por qué este método es ideal para ASP.NET y otras aplicaciones .NET. Experimenta con diferentes niveles de compresión, codificaciones y opciones de cifrado para adaptar el archivo a tus necesidades exactas. ¡Feliz compresión!

---

**Última actualización:** 2026-02-28  
**Probado con:** Aspose.Zip para .NET 24.12 (última)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}