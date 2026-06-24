---
date: 2026-06-24
description: Aprenda como compactar LZMA no Aspose.Zip para .NET, otimizando o armazenamento
  e a eficiência da transferência de dados.
keywords:
- how to compress lzma
- LZMA compression .NET
- Aspose.Zip archive
linktitle: Compactar para Lzma
schemas:
- author: Aspose
  dateModified: '2026-06-24'
  description: Learn how to compress LZMA in Aspose.Zip for .NET, optimizing storage
    and data transfer efficiency.
  headline: How to Compress LZMA in Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes. Call `archive.AddFile()` for each file before invoking `archive.Save()`.
    question: Can I compress multiple files into a single LZMA archive?
  - answer: The `LzmaArchive` class uses the default compression level, which provides
      a good balance between speed and size. Advanced settings are available through
      the `LzmaEncoder` if you need fine‑tuned control.
    question: Is there a way to set compression level for LZMA?
  - answer: Absolutely. The LZMA format is platform‑agnostic, so the archive can be
      decompressed on any OS with an LZMA‑compatible tool.
    question: Will the resulting .lzma file work on non‑Windows platforms?
  - answer: Use the `LzmaArchive` constructor with the archive path, then call `ExtractToDirectory()`
      to extract its contents.
    question: How do I decompress an LZMA archive using Aspose.Zip?
  - answer: Yes. You can work with streams by passing `Stream` objects to `SetSource()`
      and `Save()` methods.
    question: Does Aspose.Zip support streaming compression to avoid loading whole
      files into memory?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Como Compactar LZMA no Aspose.Zip para .NET
url: /pt/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Compactar LZMA no Aspose.Zip para .NET

## Introdução

Neste tutorial, você aprenderá **como compactar LZMA** no Aspose.Zip para .NET, uma habilidade crucial para otimizar o espaço de armazenamento e melhorar a eficiência da transferência de dados. LZMA (algoritmo Lempel‑Ziv‑Markov chain) produz arquivos até 70 % menores em comparação com o ZIP tradicional, mantendo descompressão rápida, tornando-o ideal para cenários com largura de banda limitada.

## Respostas Rápidas
- **Qual biblioteca é necessária?** Aspose.Zip for .NET  
- **Qual algoritmo este guia cobre?** LZMA compression  
- **Preciso de uma licença?** Uma licença temporária é suficiente para testes; uma licença completa é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, e .NET 5–10  
- **Quanto tempo leva a implementação?** Normalmente menos de 10 minutos para um arquivo básico.

## O que é compressão LZMA?

LZMA é um algoritmo de compressão sem perdas de alta taxa que usa compressão por dicionário e codificação por intervalo. Ele pode reduzir arquivos de texto em 30‑70 % mantendo a velocidade de descompressão comparável ao ZIP. Para grandes conjuntos de dados, LZMA reduz custos de armazenamento e acelera transferências de rede sem sacrificar a integridade dos dados.

## Por que usar Aspose.Zip para LZMA?

Aspose.Zip suporta **5 algoritmos de compressão** (ZIP, Deflate, BZIP2, LZMA e ZSTD) e pode lidar com arquivos de até **4 GB** sem carregar o arquivo inteiro na memória. A biblioteca processa documentos com centenas de páginas em menos de **2 segundos** em um servidor típico, oferecendo desempenho e escalabilidade.

## Pré-requisitos

Antes de começar, certifique-se de que você tem o seguinte:

- Aspose.Zip for .NET: Certifique-se de que a biblioteca Aspose.Zip está instalada. Você pode encontrar a documentação [aqui](https://reference.aspose.com/zip/net/).
- Diretório de Documentos: Escolha ou crie uma pasta que contenha os arquivos que você deseja compactar.

## Importar Namespaces

Adicione os namespaces necessários no topo do seu arquivo C# para que você possa acessar a funcionalidade LZMA do Aspose.Zip:

```csharp
using System;
using Aspose.Zip.LZMA;
```

## Como definir a pasta de origem para compressão?

Especifique a pasta que contém os arquivos que você pretende arquivar. Fornecer um diretório de origem dedicado garante que apenas os arquivos desejados sejam processados, reduz o risco de incluir dados indesejados e simplifica o gerenciamento de caminhos ao trabalhar com múltiplas tarefas de compressão no mesmo projeto.

```csharp
string dataDir = "Your Document Directory";
```

## Como compactar um arquivo usando LZMA?

`LzmaArchive` é a classe do Aspose.Zip para criar e gerenciar arquivos LZMA.

Crie uma instância de `LzmaArchive`, aponte-a para o arquivo de origem e chame `Save` para gerar o arquivo `.lzma`. Esse padrão de duas linhas executa todo o fluxo de compressão, gerenciando streams internamente e produzindo um arquivo compacto pronto para distribuição ou armazenamento.

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

## Como posso confirmar que a compressão foi bem-sucedida?

`Console.WriteLine` escreve uma linha de texto no console de saída padrão.

Depois que o arquivo for salvo, exiba uma mensagem curta de confirmação usando `Console.WriteLine`. Esse feedback imediato ajuda os desenvolvedores a verificar que a etapa de compressão foi concluída sem erros, simplifica a depuração durante builds automatizados e fornece informações de status claras quando a rotina é integrada a aplicações ou scripts maiores.

```csharp
Console.WriteLine("Successfully Compressed a File");
```

## Problemas Comuns e Soluções

- **Arquivo não encontrado** – Verifique se a string de caminho usa barras invertidas duplas (`\\`) ou uma string literal (`@"C:\Path"`).  
- **Memória insuficiente** – Aspose.Zip transmite dados em streams, mas arquivos extremamente grandes podem exigir o aumento do limite de memória do processo.  
- **Licença não aplicada** – Certifique-se de chamar `License license = new License(); license.SetLicense("Aspose.Total.NET.lic");` antes de qualquer operação do Aspose.Zip.

## Perguntas Frequentes

**Q: Posso compactar vários arquivos em um único arquivo LZMA?**  
A: Sim. Chame `archive.AddFile()` para cada arquivo antes de invocar `archive.Save()`.

**Q: Existe uma maneira de definir o nível de compressão para LZMA?**  
A: A classe `LzmaArchive` usa o nível de compressão padrão, que oferece um bom equilíbrio entre velocidade e tamanho. Configurações avançadas estão disponíveis através do `LzmaEncoder` se você precisar de controle fino.

**Q: O arquivo .lzma resultante funcionará em plataformas não‑Windows?**  
A: Absolutamente. O formato LZMA é independente de plataforma, portanto o arquivo pode ser descompactado em qualquer SO com uma ferramenta compatível com LZMA.

**Q: Como descompactar um arquivo LZMA usando Aspose.Zip?**  
A: Use o construtor `LzmaArchive` com o caminho do arquivo, então chame `ExtractToDirectory()` para extrair seu conteúdo.

**Q: O Aspose.Zip suporta compressão em streaming para evitar carregar arquivos inteiros na memória?**  
A: Sim. Você pode trabalhar com streams passando objetos `Stream` para os métodos `SetSource()` e `Save()`.

---

**Última atualização:** 2026-06-24  
**Testado com:** Aspose.Zip for .NET (última versão no momento da escrita)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Como Compactar Arquivos com Aspose.Zip para .NET](/zip/net/file-compression/compress-file/)
- [Como Abrir Arquivo GZip e Outras Técnicas de Compressão com Aspose.Zip para .NET](/zip/net/other-compression-techniques/)
- [compactar arquivos c# – Criar arquivo 7z com Aspose.Zip para .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}