---
date: 2025-12-05
description: Aprenda a crear archivos zip y agregar archivos al zip usando Aspose.Zip
  para .NET. Esta guía paso a paso muestra cómo comprimir archivos con FileInfo en
  proyectos ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cómo crear un archivo Zip usando Aspose.Zip para .NET – Comprimir archivos
  con FileInfo
url: /es/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un archivo Zip usando Aspose.Zip para .NET

## Introducción

Si necesitas **crear un archivo zip** de forma programática, Aspose.Zip para .NET te ofrece una API limpia y de alto rendimiento que funciona en cualquier aplicación .NET (incluyendo ASP.NET). En este tutorial recorreremos la compresión de archivos con la clase `FileInfo`, te mostraremos cómo **añadir archivos al zip** y explicaremos por qué este enfoque es ideal para proyectos .NET modernos. ¡Comencemos!

## Respuestas rápidas
- **¿Cuál es la forma más fácil de crear un archivo zip?** Usa la clase `Archive` de Aspose.Zip junto con objetos `FileInfo`.  
- **¿Puedo añadir varios archivos a la vez?** Sí, solo crea un `FileInfo` para cada archivo y llama a `CreateEntry`.  
- **¿Necesito una licencia especial para ASP.NET?** Se requiere una licencia comercial de Aspose.Zip para producción; una prueba gratuita sirve para evaluación.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **¿La API es segura para sub‑hilos?** Sí, siempre que cada sub‑hilo trabaje con su propia instancia de `Archive`.

## ¿Qué es un archivo Zip y por qué crear uno?
Un archivo zip agrupa uno o más archivos en un único contenedor comprimido. Esto reduce el espacio de almacenamiento, acelera las transferencias de red y simplifica la distribución. Ya sea que entregues registros, exportes informes o empaquetes recursos para un cliente, saber **cómo crear archivos zip** de forma programática es una habilidad valiosa para cualquier desarrollador .NET.

## ¿Por qué usar Aspose.Zip para añadir archivos al zip?
- **Cero dependencias externas** – implementación pura en .NET.  
- **Control total sobre el nivel de compresión y la codificación** (ASCII, UTF‑8, etc.).  
- **Soporta archivos grandes** (> 4 GB) y protección con contraseña.  
- **API consistente en .NET Framework, .NET Core y .NET 5+**.

## Requisitos previos

Antes de sumergirnos en el código, asegúrate de tener:

1. **Aspose.Zip para .NET** instalado. Descarga el paquete más reciente desde la [página de descarga de Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Una carpeta en tu máquina que contenga los archivos que deseas comprimir (por ejemplo, `alice29.txt` y `fields.c`).  

## Importar espacios de nombres

En cualquier archivo C# donde trabajes con archivos zip, agrega las siguientes instrucciones `using`:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Estos espacios de nombres te dan acceso a la clase `Archive`, opciones de guardado y utilidades estándar de I/O.

## Guía paso a paso

### Paso 1: Configurar el directorio de documentos

Primero, define la carpeta que contiene los archivos de origen. Reemplaza el marcador de posición con la ruta absoluta o relativa en tu sistema:

```csharp
string dataDir = "Your Document Directory";
```

> **Consejo profesional:** Usa `Path.Combine` para construir rutas de forma multiplataforma.

### Paso 2: Abrir un archivo Zip para escritura

Crea un `FileStream` que apunte al archivo zip de salida. El flujo se abre en modo **Create**, lo que sobrescribe cualquier archivo existente con el mismo nombre:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Paso 3: Preparar objetos `FileInfo` para cada archivo de origen

`FileInfo` brinda a Aspose.Zip acceso directo a los archivos físicos en disco. Crea una instancia por cada archivo que quieras comprimir:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **¿Por qué usar `FileInfo`?** Evita cargar todo el archivo en memoria, lo cual es especialmente útil para archivos grandes.

### Paso 4: Crear el archivo y añadir entradas

Instancia un objeto `Archive`, luego llama `CreateEntry` para cada `FileInfo`. El primer argumento es el nombre que tendrá el archivo dentro del zip, el segundo argumento es el `FileInfo` de origen:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Paso 5: Guardar el archivo Zip con la codificación deseada

Finalmente, persiste el archivo en el `FileStream` que abriste antes. Aquí usamos codificación ASCII para los nombres de entrada, pero puedes cambiar a UTF‑8 si tus nombres de archivo contienen caracteres no ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Cuando los bloques `using` finalizan, los flujos se cierran automáticamente y el archivo zip está listo para usarse.

## Problemas comunes y soluciones

| Problema | Causa | Solución |
|----------|-------|----------|
| **Archivo zip vacío** | `FileInfo` apunta a una ruta inexistente | Verifica `dataDir` y los nombres de archivo; usa `File.Exists` para comprobar antes de crear entradas. |
| **Codificación de nombre de archivo incorrecta** | Uso de la codificación predeterminada con nombres no ASCII | Establece `Encoding = Encoding.UTF8` en `ArchiveSaveOptions`. |
| **OutOfMemoryException con archivos grandes** | Cargar todo el archivo en memoria | `FileInfo` transmite el archivo; asegúrate de no leerlo en un arreglo de bytes en otro lugar. |
| **Permiso denegado** | La aplicación no tiene permiso de escritura en la carpeta de salida | Ejecuta la aplicación con los derechos adecuados o elige un directorio con permisos de escritura. |

## Preguntas frecuentes

**P: ¿Puedo añadir protección con contraseña al archivo zip?**  
R: Sí. Después de crear el `Archive`, asigna `archive.Password = "yourPassword"` antes de llamar a `Save`.

**P: ¿Es posible actualizar un archivo zip existente?**  
R: Aspose.Zip permite abrir un archivo existente con `Archive.Open` y luego añadir nuevas entradas.

**P: ¿Cómo comprimo archivos en un controlador ASP.NET MVC?**  
R: El mismo código funciona; solo asegúrate de que el flujo de salida se envíe como `FileResult` al cliente.

**P: ¿Aspose.Zip soporta algoritmos de cifrado?**  
R: Soporta los algoritmos estándar ZipCrypto y AES‑256.

**P: ¿Qué hago si necesito comprimir una carpeta de forma recursiva?**  
R: Recorre `Directory.GetFiles` (y subcarpetas) y crea un `FileInfo` para cada archivo, luego añádelos al archivo.

## Sección de FAQ existente (sin cambios)

### FAQ's

#### Q1: ¿Es Aspose.Zip compatible con todos los tipos de archivo?

A1: Aspose.Zip soporta una amplia gama de tipos de archivo, garantizando versatilidad en la compresión.

#### Q2: ¿Puedo usar Aspose.Zip para proyectos comerciales?

A2: ¡Absolutamente! Visita nuestra [página de compra](https://purchase.aspose.com/buy) para explorar opciones de licencia.

#### Q3: ¿Cómo puedo obtener soporte para Aspose.Zip?

A3: Únete a nuestra comunidad en el [foro de Aspose.Zip](https://forum.aspose.com/c/zip/37) para asistencia y discusiones.

#### Q4: ¿Hay una prueba gratuita disponible?

A4: Sí, puedes obtener tu [prueba gratuita aquí](https://releases.aspose.com/).

#### Q5: ¿Cómo puedo obtener una licencia temporal para Aspose.Zip?

A5: Visita [este enlace](https://purchase.aspose.com/temporary-license/) para información sobre cómo obtener una licencia temporal.

## Conclusión

Ahora sabes **cómo crear archivos zip** usando Aspose.Zip para .NET, **cómo añadir archivos al zip**, y por qué este método es ideal para ASP.NET y otras aplicaciones .NET. Experimenta con diferentes niveles de compresión, codificaciones y opciones de cifrado para adaptar el archivo a tus necesidades exactas. ¡Feliz compresión!

---

**Última actualización:** 2025-12-05  
**Probado con:** Aspose.Zip para .NET 24.12 (última)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}