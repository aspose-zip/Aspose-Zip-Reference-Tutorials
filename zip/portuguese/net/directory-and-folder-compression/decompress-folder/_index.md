---
date: 2026-04-09
description: Aprenda como compactar um diretório em zip e extrair um zip para um diretório
  usando Aspose.Zip para .NET. Este guia aborda a compactação de pastas programaticamente
  e o manuseio de arquivos zip no .NET.
keywords:
- compress directory to zip
- zip folder programmatically
- extract zip to directory
- extract zip archive .net
linktitle: Descompactando uma pasta
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Como Compactar Pasta – Comprimir Diretório com Aspose.Zip
url: /pt/net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Compactar Pasta – Comprimir Diretório com Aspose.Zip para .NET

Se você está procurando uma solução clara, **compress directory to zip**, em uma aplicação .NET, chegou ao lugar certo. Neste tutorial percorreremos todo o fluxo — primeiro faremos **compress directory to zip**, depois mostraremos os passos exatos para **extract zip to directory** (também conhecido como descompactar pasta). Ao final, você terá um padrão reutilizável e programático para operações de zip de pasta que funciona em .NET Framework, .NET Core e .NET 5/6+.

## Respostas Rápidas
- **What does “compress directory to zip” mean?** Significa transformar o conteúdo de uma pasta em um único .zip file.  
- **How do I extract zip to directory?** Use o método `Archive.ExtractToDirectory` conforme mostrado no guide.  
- **Which .NET versions are supported?** Todas as versões modernas do .NET Framework, .NET Core e .NET 5/6+ versions.  
- **Is a license required for production?** Sim, uma licença comercial Aspose.Zip é necessária para non‑trial use.  
- **Can I automate this in CI/CD pipelines?** Absolutamente — basta add the same code to your build scripts.

## O que é “compress directory to zip”?
**Compress directory to zip** simplesmente significa pegar cada arquivo e sub‑folder dentro de um diretório e empacotá‑los em um único compressed archive. Isso reduz o tamanho de storage, speeds up transfers, e cria um portable package para deployment.

## Por que usar Aspose.Zip para .NET?
Aspose.Zip fornece uma API **pure‑managed** que não requer native DLLs, suporta massive archives, e lida automaticamente com edge cases como **zip archive password protection** e Unicode file names. Também é otimizada para performance, tornando‑a ideal quando você precisa zip folder programmatically em high‑throughput scenarios.

## Pré‑requisitos
- **Aspose.Zip for .NET** library installed (download it [here](https://releases.aspose.com/zip/net/)).  
- Uma pasta no disco que você deseja archive – set its path in the `dataDir` variable.  
- Ambiente de desenvolvimento .NET (Visual Studio, VS Code, or any IDE you prefer).

## Importar Namespaces
First, bring the required namespaces into scope:

```csharp
using Aspose.Zip;
using System.IO;
```

## compress directory to zip – Guia passo a passo

### Etapa 1: Zip folder programmatically
Vamos criar um zip file a partir do diretório que você planeja decompress later. O helper `CompressDirectory.Run()` does the heavy lifting.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Pro tip:** O exemplo `CompressDirectory` packs every file in `dataDir` into `CompressDirectory_out.zip`. Feel free to rename the output file to match your naming conventions.

### Etapa 2: extract zip to directory – Como unzip folder in .NET

#### Etapa 2.1: Abrir o Zip File
Abra o generated archive com um `FileStream`. This prepares the file for reading.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

#### Etapa 2.2: Criar Instância de Archive
Instancie o `Archive` object, which represents the zip container.

```csharp
    using (var archive = new Archive(zipFile))
    {
```

#### Etapa 2.3: extract zip archive .net
Finalmente, extract the contents to a new folder. This is the **extract zip to directory** step.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

## Por que isso importa
- **Consistency:** Usar a mesma library para both compressing and extracting guarantees compatible archive formats.  
- **Performance:** Aspose.Zip streams data efficiently, so even multi‑gigabyte archives are handled with low memory overhead.  
- **Security:** Built‑in support for password protection means you can secure the zip archive without extra code.

## Casos de Uso Comuns
- **Automated backups** – zip a logs folder nightly and store it in cloud storage.  
- **Deployment packages** – bundle static web assets before publishing to a server.  
- **Data exchange** – send a collection of files between services as a single archive.

## Problemas Comuns & Soluções
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `UnauthorizedAccessException` when extracting | Target folder is read‑only or in use | Ensure the destination path is writable and not locked |
| Empty output folder after extraction | Wrong source zip path | Double‑check `dataDir + "CompressDirectory_out.zip"` points to the correct file |
| Large files cause OutOfMemoryException | Using default buffer size on very large archives | Use `ArchiveOptions` to increase buffer size or stream files in chunks |

## Perguntas Frequentes

**Q: Posso usar Aspose.Zip para .NET com qualquer tipo de arquivo?**  
A: Sim, Aspose.Zip supports all file types—text, binary, images, PDFs, you name it.

**Q: O Aspose.Zip é adequado para aplicações em grande escala?**  
A: Absolutely. It’s designed for high‑performance zip compression .NET scenarios, handling multi‑gigabyte archives with low memory overhead.

**Q: Onde posso encontrar documentação abrangente para Aspose.Zip para .NET?**  
A: Explore the detailed docs [here](https://reference.aspose.com/zip/net/).

**Q: Posso experimentar o Aspose.Zip antes de comprar?**  
A: Sim, a free trial is available at the [Aspose.Zip download page](https://releases.aspose.com/).

**Q: Como posso obter suporte para Aspose.Zip para .NET?**  
A: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for community help and official assistance.

---

**Última atualização:** 2026-04-09  
**Testado com:** Aspose.Zip 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}