---
date: 2026-05-30
description: Aprenda como criar zip sem compressão em .NET com Aspose.Zip para .NET.
  Este guia mostra como compactar arquivos sem compressão, armazenar arquivos sem
  compressão e gerenciar arquivos de forma eficiente.
keywords:
- zip without compression
- generate zip archive .net
- Aspose.Zip uncompressed
linktitle: Armazenar vários arquivos sem compressão
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
title: Criar zip sem compressão em .NET usando Aspose.Zip
url: /pt/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar zip sem compressão em .NET usando Aspose.Zip

No desenvolvimento moderno em .NET, **criar um zip sem compressão** pode melhorar drasticamente a velocidade de arquivamento e manter os tamanhos dos arquivos previsíveis. Quando você precisa **compactar arquivos sem compressão** — por exemplo, para atender a regras regulatórias, acelerar o processamento subsequente ou garantir que a sequência original de bytes permaneça intacta — Aspose.Zip para .NET oferece uma API limpa e direta. Neste tutorial vamos percorrer os passos exatos para criar um arquivo ZIP não comprimido, adicionar arquivos e integrar a solução em sua aplicação.

## Respostas rápidas
- **O que significa “zip sem compressão”?** É um arquivo ZIP onde cada entrada é armazenada usando o método “store”, deixando os bytes originais do arquivo intactos.  
- **Por que evitar compressão?** Para acelerar o arquivamento, preservar os tamanhos originais dos arquivos para processamento posterior ou atender a requisitos regulatórios que proíbem a alteração de dados.  
- **Qual classe do Aspose.Zip lida com isso?** `ArchiveEntrySettings` combinada com `StoreCompressionSettings`.  
- **Preciso de licença?** Um teste gratuito funciona para testes; uma licença comercial é necessária para produção.  
- **Versões .NET suportadas?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 e .NET 5–10.  

## O que é zip sem compressão?
**Zip sem compressão** é um arquivo ZIP onde cada entrada de arquivo usa o método *store*, ou seja, os dados são copiados literalmente para o arquivo sem aplicar nenhum algoritmo de compressão. Isso resulta em um arquivo cujo tamanho é essencialmente a soma dos arquivos originais mais alguns bytes de overhead do ZIP.

## Por que usar Aspose.Zip para arquivos zip sem compressão?
Aspose.Zip é otimizado para arquivamento de alto desempenho, permitindo que você armazene arquivos instantaneamente sem a sobrecarga dos algoritmos de compressão. Ele garante compatibilidade total com ZIP, permite misturar entradas armazenadas e comprimidas e fornece uma API simples que abstrai estruturas de ZIP de baixo nível, tornando a implementação rápida e confiável.

## Pré‑requisitos
- **Aspose.Zip for .NET** – integrado ao seu projeto. Consulte a [documentação](https://reference.aspose.com/zip/net/) oficial para etapas de instalação.  
- **Ambiente de desenvolvimento .NET** – Visual Studio, VS Code ou qualquer IDE de sua preferência.  
- **Diretório de documentos** – uma pasta na sua máquina contendo os arquivos que você deseja arquivar (por exemplo, “Your Document Directory”).

## Importar namespaces
Antes de escrever qualquer código, importe os namespaces necessários para que o compilador saiba onde encontrar as classes Aspose.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## Etapa 1: Definir diretório de documentos
Defina o caminho onde seus arquivos de origem estão localizados. Substitua o placeholder pelo caminho real da pasta no seu sistema.

```csharp
string dataDir = "Your Document Directory";
```

## Etapa 2: Criar arquivo Zip sem compressão
O núcleo do tutorial – criamos uma instância de `Archive` configurada com `StoreCompressionSettings`. `Archive` representa um contêiner ZIP que pode conter múltiplas entradas. `StoreCompressionSettings` especifica que uma entrada deve ser armazenada sem compressão. Isso indica ao Aspose.Zip para *armazenar* (ou seja, não comprimir) cada entrada.

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

> **Dica profissional:** Se precisar **salvar arquivos em zip** comprimindo alguns e deixando outros sem compressão, crie instâncias separadas de `ArchiveEntrySettings` para cada arquivo e adicione‑as ao mesmo `Archive`.

## Como criar zip sem compressão em .NET?
Carregue seus arquivos de origem, instancie um objeto `Archive` e adicione cada arquivo usando `ArchiveEntrySettings` com `new StoreCompressionSettings()`. Toda a operação requer apenas três linhas de código e é executada em tempo linear em relação ao tamanho total dos arquivos, proporcionando a experiência de arquivamento mais rápida possível.

### Passo a passo
1. **Criar o arquivo** – instancie `Archive` com um fluxo de destino ou caminho de arquivo.  
2. **Configurar as definições da entrada** – para cada arquivo, crie um objeto `ArchiveEntrySettings` e atribua `new StoreCompressionSettings()` à sua propriedade `Compression`.  
3. **Adicionar entradas** – chame `archive.Add(entrySettings)` para cada arquivo e finalize com `archive.Save()`.

## Problemas comuns e soluções
| Problema | Por que acontece | Correção |
|----------|------------------|----------|
| **Arquivo não encontrado** | Caminho `dataDir` incorreto ou extensão de arquivo ausente. | Verifique o caminho e assegure que os arquivos existam. Use `Path.Combine` para concatenação mais segura. |
| **Acesso negado** | O processo não tem permissão para ler os arquivos de origem ou gravar o ZIP. | Execute a aplicação com direitos adequados ou escolha uma pasta com permissão de gravação. |
| **Tamanho inesperado no ZIP** | O arquivo foi criado com compressão padrão. | Garanta que `new StoreCompressionSettings()` seja passado para `ArchiveEntrySettings`. |

## Perguntas frequentes

**Q: Posso comprimir tipos de arquivo específicos enquanto armazeno outros sem compressão?**  
A: Sim, você pode criar diferentes `ArchiveEntrySettings` para cada arquivo e misturar entradas comprimidas e não comprimidas no mesmo arquivo.

**Q: O Aspose.Zip para .NET é compatível com .NET Core e .NET 5/6?**  
A: Absolutamente. A biblioteca suporta .NET Framework, .NET Core, .NET Standard e as versões mais recentes do .NET.

**Q: Como devo tratar exceções durante o processo de arquivamento?**  
A: Envolva o código de arquivamento em um bloco `try‑catch` e registre os detalhes da exceção. Isso garante falhas controladas e facilita a depuração.

**Q: O Aspose.Zip suporta arquivamento multithread?**  
A: Sim, você pode processar vários arquivos em paralelo e adicioná‑los ao arquivo, mas lembre‑se de que o objeto `Archive` não é thread‑safe; sincronize o acesso ao adicioná‑los.

**Q: Posso integrar o Aspose.Zip em um projeto existente sem grandes alterações de código?**  
A: Definitivamente. A API foi projetada para uso simples de “arrastar‑e‑soltar”. Consulte a [documentação](https://reference.aspose.com/zip/net/) oficial para orientações de migração.

---

**Última atualização:** 2026-05-30  
**Testado com:** Aspose.Zip for .NET (última versão na data de escrita)  
**Autor:** Aspose

## Tutoriais relacionados

- [Criar arquivo Zip .NET – Compressão de arquivos com Aspose.Zip](/zip/net/file-compression/)
- [zip múltiplos arquivos c# – Compressão sem esforço com Aspose.Zip para .NET](/zip/net/file-compression/compress-multiple-files/)
- [Criar Zip sem compressão & Descompactar arquivos – Aspose.Zip](/zip/net/file-decompression/decompress-stored-file/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}