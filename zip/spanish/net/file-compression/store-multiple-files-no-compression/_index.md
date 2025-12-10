---
date: 2025-12-10
description: Aprenda a almacenar archivos sin compresión usando Aspose.Zip para .NET.
  Esta guía le muestra cómo crear un zip sin comprimir, guardar archivos en el zip
  y gestionar los archivos de forma eficiente.
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cómo almacenar archivos sin comprimir con Aspose.Zip para .NET
url: /es/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo almacenar archivos sin comprimir con Aspose.Zip para .NET

En el desarrollo moderno de .NET, **cómo almacenar archivos** de manera eficiente puede marcar una gran diferencia en el rendimiento y los costos de almacenamiento. Cuando necesitas mantener los archivos tal cual—sin ninguna compresión—Aspose.Zip para .NET ofrece una API limpia y sencilla. En este tutorial recorreremos los pasos para crear un archivo ZIP sin comprimir, guardar archivos en ZIP e integrar la solución en tu aplicación.

## Respuestas rápidas
- **¿Qué significa “zip sin comprimir”?** Es un archivo ZIP donde cada entrada se almacena usando el método “store”, dejando los bytes originales del archivo sin tocar.  
- **¿Por qué evitar la compresión?** Para acelerar el archivado, preservar los tamaños originales de los archivos para procesamiento posterior, o cumplir con requisitos regulatorios que prohíben la alteración de datos.  
- **¿Qué clase de Aspose.Zip maneja esto?** `ArchiveEntrySettings` combinada con `StoreCompressionSettings`.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Versiones de .NET compatibles?** .NET Framework, .NET Core, .NET 5/6/7 y posteriores.

## ¿Qué es almacenar varios archivos sin compresión?
Almacenar varios archivos sin compresión significa agregar cada archivo a un contenedor ZIP usando el método de compresión *store*. Los archivos permanecen idénticos byte a byte a los originales, lo cual es ideal cuando deseas un archivado rápido o necesitas mantener los datos sin cambios.

## ¿Por qué usar Aspose.Zip para archivos sin comprimir?
- **Velocidad:** No se ejecutan algoritmos de compresión intensivos en CPU.  
- **Tamaño predecible:** El tamaño del archivo es la suma de los archivos originales más una sobrecarga mínima de ZIP.  
- **Compatibilidad:** El ZIP resultante funciona con cualquier utilidad estándar de descompresión.  
- **Flexibilidad:** aún puedes mezclar entradas comprimidas y sin comprimir en el mismo archivo si es necesario.

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

## Paso 2: Crear un archivo ZIP sin compresión
El núcleo del tutorial: creamos una instancia de `Archive` configurada con `StoreCompressionSettings`. Esto indica a Aspose.Zip que *almacene* (es decir, no comprima) cada entrada.

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
R: Envuelve el código de archivado en un bloque `try‑catch` y registra los detalles de la excepción. Esto garantiza una falla controlada y una depuración más sencilla.

**P: ¿Aspose.Zip admite archivado multihilo?**  
R: Sí, puedes procesar varios archivos en paralelo y agregarlos al archivo, pero recuerda que el objeto `Archive` en sí no es seguro para hilos; sincroniza el acceso al agregar entradas.

**P: ¿Puedo integrar Aspose.Zip en un proyecto existente sin cambios de código importantes?**  
R: Definitivamente. La API está diseñada para un uso simple de inserción directa. Consulta la [documentación](https://reference.aspose.com/zip/net/) oficial para obtener orientación de migración.

---

**Última actualización:** 2025-12-10  
**Probado con:** Aspose.Zip for .NET 24.12 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}