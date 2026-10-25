---
date: 2026-10-25
description: Aprenda cómo extraer la contraseña de zip y establecer el algoritmo de
  compresión al comprimir archivos tar con Aspose.Zip para .NET, mejorando la eficiencia
  del almacenamiento y la seguridad.
keywords:
- extract zip password
- set compression algorithm
- add folder archive
- tarbz2 vs targz
- aspose zip compress
lastmod: 2026-10-25
linktitle: Extracción de archivos y formatos
og_description: Aprenda cómo extraer la contraseña de zip y establecer el algoritmo
  de compresión al comprimir archivos tar con Aspose.Zip para .NET, mejorando la eficiencia
  del almacenamiento y la seguridad.
og_image_alt: 'Developer guide: extract zip password and compress tar archives using
  Aspose.Zip for .NET'
og_title: Extraer la contraseña de zip y comprimir archivos tar con Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  headline: Extract zip password and compress tar files with Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  name: Extract zip password and compress tar files with Aspose.Zip
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
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
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: Extraer la contraseña de zip y comprimir archivos tar con Aspose.Zip
url: /es/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extraer contraseña zip y comprimir archivos tar con Aspose.Zip

## Introducción

En esta guía descubrirás técnicas de **extract zip password**, aprenderás cómo establecer el algoritmo de compresión al crear archivos basados en tar y verás cómo crear TarGz, TarBz2 y otros formatos con Aspose.Zip para .NET. Ya sea que estés construyendo un servicio de copias de seguridad, un cliente de almacenamiento en la nube o una canalización de procesamiento de datos, dominar estas operaciones reduce los costos de almacenamiento, acelera las transferencias y protege los archivos sensibles.

## Respuestas rápidas
- **¿Qué es TarBz2?** Un archivo comprimido que combina el empaquetado TAR con compresión BZIP2 para obtener altas tasas de compresión.  
- **¿Por qué elegir Aspose.Zip para .NET?** Soporta más de 50 formatos de archivo y compresión, funciona en Windows, Linux y macOS, y mantiene el uso de memoria por debajo de 10 MB para archivos de varios cientos de megabytes.  
- **¿Puedo crear un archivo TarGz?** Sí – Aspose.Zip ofrece TarGz, TarLz, TarXz, TarZ y más.  
- **¿Cómo extraer un archivo zip protegido con contraseña?** Establece la propiedad `Password` en cada `ArchiveEntry` antes de llamar a `Extract`.  
- **¿Necesito una licencia para uso en producción?** Se requiere una licencia comercial para producción; hay una prueba gratuita disponible para evaluación.

## ¿Qué es la compresión tar?

La compresión tar combina el contenedor TAR con un algoritmo de compresión como BZIP2, GZIP, LZMA o XZ. El resultado es un único archivo (p. ej., `.tar.gz`, `.tar.bz2`) que puede descomprimirse en Linux, macOS y Windows. Preserva la jerarquía de directorios original, permite la extracción de acceso aleatorio y es ampliamente compatible con herramientas de línea de comandos y bibliotecas de programación, lo que lo hace ideal para la distribución multiplataforma y el almacenamiento de archivos.

## ¿Por qué usar Aspose.Zip para .NET para manejar estos formatos?

Aspose.Zip proporciona una API unificada y sin dependencias que soporta **50+** formatos de archivo y compresión, incluidos todos los tipos principales basados en tar. Su arquitectura de streaming procesa archivos de más de 10 GB manteniendo el uso de RAM por debajo de 10 MB, lo que lo hace ideal para cargas de trabajo de servidor de alto rendimiento.  

**Respuesta directa:** Usas Aspose.Zip porque te permite crear, comprimir y extraer archivos basados en tar y archivos zip protegidos con contraseña mediante una única API fluida, sin herramientas externas, mientras manejas archivos de varios gigabytes en modo de streaming eficiente en memoria.

## Requisitos previos
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, o .NET 5–10.  
- Paquete NuGet Aspose.Zip for .NET (`Install-Package Aspose.Zip`).  
- Familiaridad básica con I/O de archivos en C# y el sistema de proyectos .NET.

## Guía paso a paso

### Cómo comprimir archivos tar – respuesta directa
Crea una instancia `Archive`, añade los archivos que deseas empaquetar, establece `CompressionType.BZip2` (u otro algoritmo) y llama a `Save` con `ArchiveFormat.TarBz2`. La biblioteca escribe el contenedor TAR y lo comprime en una única pasada de streaming, de modo que nunca cargas todo el archivo en memoria.

### Paso 1: Elige el formato de archivo que necesitas
Decide qué formato basado en tar se ajusta mejor a tu compromiso entre compresión y velocidad:

- **TarBz2** – Mayor relación de compresión (≈30 % más pequeño que TarGz) pero más lento.  
- **TarGz** – Buen equilibrio entre velocidad y tamaño; ideal para la mayoría de los escenarios de almacenamiento en la nube.  
- **TarLz / TarXz** – Compresión muy alta con velocidad moderada, útil para almacenamiento de archivo.  
- **TarZ** – Formato heredado para compatibilidad con herramientas Unix más antiguas.

### Paso 2: Crea una nueva instancia `Archive`
`Archive` representa un único archivo de archivo y proporciona métodos para añadir entradas y guardar el archivo.  

La clase `Archive` gestiona el flujo de empaquetado y compresión, exponiendo métodos para añadir entradas y escribir el archivo final.

### Paso 3: Añadir archivos y carpetas
Puedes añadir todo un árbol de directorios con `AddAll` o añadir archivos individuales con `AddFile`.  

`AddAll` añade todo un árbol de directorios al archivo, preservando su estructura.  
`AddFile` añade un solo archivo al archivo. Preservar la jerarquía de carpetas original es tan simple como pasar la ruta del directorio base.

### Paso 4: Establecer el tipo de compresión deseado
El enumerado `CompressionType` especifica el algoritmo de compresión aplicado al flujo TAR.  

`CompressionType` enumera los algoritmos compatibles (BZip2, GZip, LZMA, XZ, etc.) que se aplicarán durante el guardado.

### Paso 5: Guardar el archivo
El enumerado `ArchiveFormat` selecciona la combinación de contenedor y compresión para el archivo de salida.  

Al llamar a `Save` se escribe el archivo en disco usando el formato seleccionado.

### Paso 6: Extraer archivos con contraseñas
`ArchiveEntry` representa una única entrada de archivo o directorio dentro de un archivo.  

Para extraer un zip protegido con contraseña, abre el archivo, localiza cada `ArchiveEntry`, asigna su propiedad `Password` y llama a `Extract`. La propiedad `Password` establece la contraseña de descifrado para una entrada zip. Este modelo de contraseña por entrada te permite proteger archivos individuales dentro de un solo zip.

### Paso 7: Verificar el resultado
Después de la extracción, compara los tamaños de los archivos y los checksums SHA‑256 para confirmar que el ciclo de archivo preservó la integridad de los datos.

## Casos de uso comunes
- **Backup utilities** – Almacena copias de seguridad diarias como `.tar.bz2` para reducir los costos de almacenamiento hasta en un 30 %.  
- **Cross‑platform data exchange** – Los formatos basados en tar son entendidos nativamente por herramientas de Linux, macOS y Windows.  
- **Secure distribution** – Asigna contraseñas a entradas sensibles, cumpliendo requisitos de cumplimiento sin herramientas de cifrado adicionales.

## Solución de problemas y consejos
- **Large archives** – Usa la API de streaming (`Archive.CreateEntryFromFile`) para mantener bajo el uso de memoria.  
- **Password mismatches** – La contraseña establecida en cada `ArchiveEntry` debe coincidir exactamente; de lo contrario se lanza `InvalidPasswordException`.  
- **Compression level** – BZIP2 no expone niveles personalizados; si necesitas un control más fino, cambia a LZMA (`CompressionType.LZMA`) o XZ (`CompressionType.XZ`).  

## Preguntas frecuentes

**Q: ¿Cómo crear un archivo TarGz?**  
A: Establece `CompressionType.GZip` y usa `ArchiveFormat.TarGz` al llamar a `Save`. Esto produce un archivo `.tar.gz` en un solo paso.

**Q: ¿Puedo extraer un archivo protegido con contraseña sin conocer la contraseña?**  
A: No. Cada entrada debe recibir la contraseña correcta; la extracción falla con `InvalidPasswordException` de lo contrario.

**Q: ¿Aspose.Zip admite la extracción de archivos con diferentes contraseñas por entrada?**  
A: Sí. Asigna una contraseña a cada `ArchiveEntry` individualmente antes de llamar a `Extract`.

**Q: ¿Qué formato ofrece la mejor compresión?**  
A: TarBz2 suele producir el tamaño más pequeño, seguido de TarLz y TarXz. TarGz ofrece una alternativa más rápida y aún eficaz.

**Q: ¿Existe un límite al número de archivos que puedo añadir a un archivo TAR?**  
A: Prácticamente ninguno, pero los archivos extremadamente grandes (>10 GB) pueden beneficiarse de dividirse en varias partes para un manejo más sencillo.

## Tutoriales de extracción de archivos y formatos
### [Compresión de archivos a TarBz2 con Aspose.Zip para .NET](./compress-to-tar-bz2/)
Aprende a comprimir archivos al formato TarBz2 en .NET usando Aspose.Zip. Sigue nuestra guía paso a paso para una compresión de archivos eficiente.  
### [Compresión a TarGz con Aspose.Zip para .NET](./compress-to-tar-gz/)
Explora la compresión eficiente de archivos en .NET con Aspose.Zip. Comprime a TarGz sin esfuerzo.  
### [Compresión a TarLz con Aspose.Zip para .NET](./compress-to-tar-lz/)
Comprime archivos en .NET con Aspose.Zip de manera sencilla. Aprende a crear archivos TarLz paso a paso.  
### [Compresión a TarXz con Aspose.Zip para .NET](./compress-to-tar-xz/)
Aprende a comprimir archivos al formato TarXz en .NET usando Aspose.Zip. Sigue nuestra guía para un almacenamiento y transmisión eficientes.  
### [Compresión a TarZ con Aspose.Zip para .NET](./compress-to-tar-z/)
Explora la compresión paso a paso a TarZ usando Aspose.Zip para .NET. Manejo de archivos eficiente para tus proyectos .NET.  
### [Extracción de entradas de archivo con diferentes contraseñas en Aspose.Zip para .NET](./extract-archive-different-passwords/)
Aprende a extraer entradas de archivo con distintas contraseñas en Aspose.Zip para .NET. Mejora la seguridad y flexibilidad en tus aplicaciones.

## Tutoriales relacionados

- [Crear archivo tar y añadir archivos a tar con Aspose.Zip para .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Cómo comprimir tar y crear TarBz2 con Aspose.Zip para .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Añadir archivos a tar y crear archivo tarxz con Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

---

**Última actualización:** 2026-10-25  
**Probado con:** Aspose.Zip for .NET 24.11  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}