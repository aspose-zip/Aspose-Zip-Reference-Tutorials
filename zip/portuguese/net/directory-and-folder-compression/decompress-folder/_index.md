---
date: 2025-12-01
description: Aprenda a compactar um diretório em zip e extrair um zip para um diretório
  usando Aspose.Zip para .NET – um guia completo de compressão zip .NET e criação
  de arquivo zip .NET.
language: pt
linktitle: Decompressing a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Compactar Diretório em Zip e Descompactar – Aspose.Zip para .NET
url: /net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Compactar Diretório em Zip e Descompactar – Aspose.Zip para .NET

Se você precisa **compactar diretório em zip** e depois extrair esse arquivo em uma aplicação .NET, você está no lugar certo. Neste tutorial vamos percorrer todo o fluxo de trabalho—começando com a criação de um arquivo zip, e depois mostrando um processo limpo, passo a passo de descompactação usando Aspose.Zip para .NET. Ao final, você terá um padrão reutilizável para compressão zip em projetos .NET e uma compreensão sólida de como descompactar no estilo .NET.

## Respostas Rápidas
- **O que significa “compactar diretório em zip”?** Significa transformar o conteúdo de uma pasta em um único .zip file.  
- **Como faço para extrair zip para diretório?** Use o método `Archive.ExtractToDirectory` como mostrado no guia.  
- **Quais versões do .NET são suportadas?** Todas as versões modernas do .NET Framework, .NET Core e .NET 5/6+.  
- **É necessária uma licença para produção?** Sim, uma licença comercial do Aspose.Zip é necessária para uso não‑trial.  
- **Posso automatizar isso em pipelines CI/CD?** Absolutamente—basta adicionar o mesmo código aos seus scripts de build.

## O que é “compactar diretório em zip”?
Compactar um diretório em zip agrupa todos os arquivos e subpastas em um único arquivo compactado. Isso reduz o tamanho de armazenamento, simplifica a transferência e é uma forma padrão de empacotar recursos para implantação.

## Por que usar Aspose.Zip para .NET?
Aspose.Zip oferece uma API **pure‑managed** que funciona sem dependências nativas, suporta arquivos grandes e fornece recursos de compressão zip de alto desempenho .NET. Também lida com casos extremos, como arquivos protegidos por senha e nomes de arquivos Unicode, prontamente.

## Pré‑requisitos
- **Biblioteca Aspose.Zip para .NET** instalada (faça o download [aqui](https://releases.aspose.com/zip/net/)).  
- Uma pasta no disco que você deseja arquivar – defina seu caminho na variável `dataDir`.  
- Ambiente de desenvolvimento .NET (Visual Studio, VS Code ou qualquer IDE de sua preferência).

## Importar Namespaces
First, bring the required namespaces into scope:

```csharp
using Aspose.Zip;
using System.IO;
```

## Etapa 1: Compactar Diretório em Zip
Vamos criar um arquivo zip a partir do diretório que você planeja descompactar mais tarde. O helper `CompressDirectory.Run()` faz o trabalho pesado.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Dica profissional:** O exemplo `CompressDirectory` empacota todos os arquivos em `dataDir` em `CompressDirectory_out.zip`. Sinta-se à vontade para renomear o arquivo de saída de acordo com suas convenções de nomenclatura.

## Etapa 2: Descompactar a Pasta (Como descompactar .NET)

### Etapa 2.1: Abrir o Arquivo Zip
Abra o arquivo gerado com um `FileStream`. Isso prepara o arquivo para leitura.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

### Etapa 2.2: Criar Instância do Archive
Instancie o objeto `Archive`, que representa o contêiner zip.

```csharp
    using (var archive = new Archive(zipFile))
    {
```

### Etapa 2.3: Extrair para Diretório
Finalmente, extraia o conteúdo para uma nova pasta. Esta é a etapa de **extrair zip para diretório**.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

Parabéns! Você compactou com sucesso um **diretório em zip** e depois **extraiu o zip para um diretório** usando Aspose.Zip para .NET. Essa abordagem garante a integridade dos dados enquanto mantém o código conciso e legível.

## Problemas Comuns & Soluções
| Sintoma | Causa Provável | Correção |
|---------|----------------|----------|
| `UnauthorizedAccessException` ao extrair | A pasta de destino está somente leitura ou em uso | Certifique-se de que o caminho de destino seja gravável e não esteja bloqueado |
| Pasta de saída vazia após a extração | Caminho do zip de origem incorreto | Verifique novamente se `dataDir + "CompressDirectory_out.zip"` aponta para o arquivo correto |
| Arquivos grandes causam OutOfMemoryException | Usando o tamanho de buffer padrão em arquivos muito grandes | Use `ArchiveOptions` para aumentar o tamanho do buffer ou transmita os arquivos em blocos |

## Perguntas Frequentes

**Q: Posso usar Aspose.Zip para .NET com qualquer tipo de arquivo?**  
A: Sim, o Aspose.Zip suporta todos os tipos de arquivo—texto, binário, imagens, PDFs, o que você precisar.

**Q: O Aspose.Zip é adequado para aplicações em grande escala?**  
A: Absolutamente. Foi projetado para cenários de compressão zip de alto desempenho .NET, lidando com arquivos de vários gigabytes com baixo consumo de memória.

**Q: Onde posso encontrar documentação abrangente para Aspose.Zip para .NET?**  
A: Explore a documentação detalhada [aqui](https://reference.aspose.com/zip/net/).

**Q: Posso experimentar o Aspose.Zip antes de comprar?**  
A: Sim, um teste gratuito está disponível na [página de download do Aspose.Zip](https://releases.aspose.com/).

**Q: Como posso obter suporte para Aspose.Zip para .NET?**  
A: Visite o [fórum do Aspose.Zip](https://forum.aspose.com/c/zip/37) para ajuda da comunidade e assistência oficial.

---

**Última Atualização:** 2025-12-01  
**Testado com:** Aspose.Zip 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}