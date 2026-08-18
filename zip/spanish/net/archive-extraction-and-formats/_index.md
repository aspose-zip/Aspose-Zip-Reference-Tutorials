---
date: 2026-06-19
description: Aprenda a comprimir archivos tar, crear archivos targz y extraer archivos
  zip protegidos con contraseña usando Aspose.Zip para .NET, mejorando la eficiencia
  de almacenamiento y la seguridad.
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: Extracción de archivos y formatos
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cómo comprimir archivos tar con Aspose.Zip para .NET
url: /es/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo comprimir archivos Tar con Aspose.Zip para .NET

## Introducción

En esta guía descubrirá **cómo comprimir archivos tar** usando Aspose.Zip para .NET, aprenderá a crear archivos TarGz y verá cómo extraer archivos zip protegidos con contraseña. El manejo eficiente de archivos es una habilidad esencial para los desarrolladores .NET modernos—ya sea que esté construyendo un servicio de copias de seguridad, un cliente de almacenamiento en la nube o una canalización de procesamiento de datos, dominar estos formatos reduce costos de almacenamiento, acelera las transferencias y mantiene seguros los datos sensibles.

## Respuestas rápidas
- **¿Qué es TarBz2?** Un archivo comprimido que combina el empaquetado TAR con compresión BZIP2 para obtener altas tasas de compresión.  
- **¿Por qué elegir Aspose.Zip para .NET?** Ofrece una API única y fluida para crear y extraer muchos formatos de archivo sin dependencias externas.  
- **¿Puedo crear un archivo TarGz?** Sí – Aspose.Zip admite TarGz, TarLz, TarXz, TarZ y más.  
- **¿Cómo extraigo un archivo zip protegido con contraseña?** Use la propiedad `Password` en el objeto `ArchiveEntry` al extraer.  
- **¿Necesito una licencia para uso en producción?** Se requiere una licencia comercial para producción; hay una prueba gratuita disponible para evaluación.

## Qué es la compresión Tar?
Tar (Tape Archive) es un formato contenedor que agrupa múltiples archivos y directorios en un único flujo sin compresión. Cuando se le aplica un algoritmo de compresión como BZIP2, GZip, LZMA o XZ, el resultado es un **archivo basado en tar** como `.tar.bz2`, `.tar.gz`, `.tar.lz`, etc. Estos formatos son ampliamente compatibles con Linux, macOS y Windows, lo que los hace ideales para el intercambio de datos multiplataforma.

## Por qué usar Aspose.Zip para .NET para manejar estos formatos?
Aspose.Zip proporciona una **API unificada y sin dependencias** que soporta más de 50 formatos de archivo y compresión, incluidos TarBz2, TarGz, TarLz, TarXz y TarZ. Funciona en Windows, Linux y macOS, y su arquitectura basada en streams mantiene el uso de memoria por debajo de 10 MB incluso para archivos de varios cientos de megabytes. La protección con contraseña está integrada, permitiendo cifrado por entrada sin bibliotecas adicionales.

## Requisitos previos
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, o .NET 5–10.  
- Paquete NuGet Aspose.Zip para .NET instalado (`Install-Package Aspose.Zip`).  
- Familiaridad básica con I/O de archivos en C# y el sistema de proyectos .NET.

## Guía paso a paso

### Cómo comprimir archivos Tar – Respuesta directa
`Archive` representa un archivo de archivo y proporciona métodos para añadir entradas y guardarlo.  
Cree una instancia `Archive`, añada los archivos que desea agrupar, establezca `CompressionType.BZip2` y llame a `Save` con `ArchiveFormat.TarBz2`. La biblioteca escribe el contenedor TAR y lo comprime en una única pasada de streaming, de modo que nunca carga todo el archivo en memoria.

### Paso 1: Elija el formato de archivo que necesita
Decida qué formato basado en tar se ajusta mejor a su compromiso entre compresión y velocidad:

- **TarBz2** – Mayor relación de compresión (≈30 % más pequeño que TarGz) pero más lento.  
- **TarGz** – Buen equilibrio entre velocidad y tamaño; ideal para la mayoría de los escenarios de almacenamiento en la nube.  
- **TarLz / TarXz** – Compresión muy alta con velocidad moderada, útil para almacenamiento de archivo.  
- **TarZ** – Formato heredado para compatibilidad con herramientas Unix más antiguas.

### Paso 2: Cree una nueva instancia `Archive`
`Archive` es el objeto de nivel superior que representa un único archivo de archivo en memoria.  

La clase `Archive` gestiona el flujo de empaquetado y compresión, exponiendo métodos para añadir entradas y escribir el archivo final.

### Paso 3: Añadir archivos y carpetas
Puede añadir todo un árbol de directorios con `AddAll` o añadir archivos individuales con `AddFile`. Preservar la jerarquía de carpetas original es tan simple como pasar la ruta del directorio base.

### Paso 4: Establezca el tipo de compresión deseado
`CompressionType` enumera los algoritmos soportados.  

`CompressionType` define el algoritmo (BZip2, GZip, LZMA, XZ, etc.) que se aplicará al flujo TAR durante el guardado.

### Paso 5: Guardar el archivo
`ArchiveFormat` es un conjunto de enumeraciones (p. ej., `TarBz2`, `TarGz`) que indica al escritor qué contenedor y compresión usar.  

Al llamar a `Save` se escribe el archivo en disco usando el formato seleccionado.

### Paso 6: Extraer archivos con contraseñas
`ArchiveEntry` representa una única entrada de archivo o directorio dentro de un archivo.  

Para extraer un zip protegido con contraseña, abra el archivo, localice cada `ArchiveEntry`, asigne su propiedad `Password` y llame a `Extract`. Este modelo de contraseña por entrada le permite proteger archivos individuales dentro de un mismo zip.

### Paso 7: Verificar el resultado
Después de la extracción, compare los tamaños de archivo y los checksums SHA‑256 para confirmar que el ciclo del archivo preservó la integridad de los datos.

## Casos de uso comunes
- **Utilidades de copia de seguridad** – Almacene copias de seguridad diarias como `.tar.bz2` para reducir costos de almacenamiento hasta en un 30 %.  
- **Intercambio de datos multiplataforma** – Los formatos basados en Tar son comprendidos nativamente por herramientas de Linux, macOS y Windows.  
- **Distribución segura** – Asigne contraseñas a entradas sensibles, cumpliendo requisitos de cumplimiento sin herramientas de cifrado adicionales.

## Solución de problemas y consejos
- **Archivos grandes** – Prefiera la API de streaming (`Archive.CreateEntryFromFile`) para mantener bajo el uso de memoria.  
- **Desajustes de contraseña** – La contraseña establecida en cada `ArchiveEntry` debe coincidir exactamente; de lo contrario se lanza `InvalidPasswordException`.  
- **Nivel de compresión** – BZIP2 no expone niveles personalizados; si necesita un control más fino, cambie a LZMA (`CompressionType.LZMA`) o XZ (`CompressionType.XZ`).  

## Preguntas frecuentes

**Q:** ¿Cómo crear un archivo TarGz?  
**A:** Establezca `CompressionType.GZip` y use `ArchiveFormat.TarGz` al llamar a `Save`. Esto produce un archivo `.tar.gz` en un solo paso.

**Q:** ¿Puedo extraer un archivo protegido con contraseña sin conocer la contraseña?  
**A:** No. Cada entrada debe recibir la contraseña correcta; la extracción falla con `InvalidPasswordException` de lo contrario.

**Q:** ¿Aspose.Zip admite la extracción de archivos con diferentes contraseñas por entrada?  
**A:** Sí. Asigne una contraseña a cada `ArchiveEntry` individualmente antes de llamar a `Extract`.

**Q:** ¿Qué formato ofrece la mejor compresión?  
**A:** TarBz2 suele producir el tamaño más pequeño, seguido de TarLz y TarXz. TarGz ofrece una alternativa más rápida y aún eficaz.

**Q:** ¿Hay un límite al número de archivos que puedo añadir a un archivo TAR?  
**A:** Prácticamente ninguno, pero los archivos extremadamente grandes (>10 GB) pueden beneficiarse de dividirse en varias partes para facilitar su manejo.

## Tutoriales de extracción de archivos y formatos
### [Compresión de archivos a TarBz2 con Aspose.Zip para .NET](./compress-to-tar-bz2/)
Aprenda a comprimir archivos al formato TarBz2 en .NET usando Aspose.Zip. Siga nuestra guía paso a paso para una compresión de archivos eficiente.  
### [Compresión a TarGz con Aspose.Zip para .NET](./compress-to-tar-gz/)
Explore la compresión de archivos eficiente en .NET con Aspose.Zip. Comprima a TarGz sin esfuerzo.  
### [Compresión a TarLz con Aspose.Zip para .NET](./compress-to-tar-lz/)
Comprima archivos en .NET con Aspose.Zip sin complicaciones. Aprenda a crear archivos TarLz paso a paso.  
### [Compresión a TarXz con Aspose.Zip para .NET](./compress-to-tar-xz/)
Aprenda a comprimir archivos al formato TarXz en .NET usando Aspose.Zip. Siga nuestra guía para un almacenamiento y transmisión eficientes.  
### [Compresión a TarZ con Aspose.Zip para .NET](./compress-to-tar-z/)
Explore la compresión paso a paso a TarZ usando Aspose.Zip para .NET. Manejo de archivos eficiente para sus proyectos .NET.  
### [Extracción de entradas de archivo con diferentes contraseñas en Aspose.Zip para .NET](./extract-archive-different-passwords/)
Aprenda a extraer entradas de archivo con diferentes contraseñas en Aspose.Zip para .NET. Mejore la seguridad y flexibilidad en sus aplicaciones.

---

**Última actualización:** 2026-06-19  
**Probado con:** Aspose.Zip para .NET 24.11  
**Autor:** Aspose

## Tutoriales relacionados

- [Crear archivo tar y añadir archivos a tar con Aspose.Zip para .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Cómo comprimir tar y crear TarBz2 con Aspose.Zip para .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Añadir archivos a tar y crear archivo tarxz con Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}