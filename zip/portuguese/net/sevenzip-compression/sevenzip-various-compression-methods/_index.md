---
date: 2026-06-29
description: Aprenda a compactar pasta para 7z com Aspose.Zip para .NET, abordando
  os métodos de compressão do 7-Zip como LZMA2, BZip2 e Store. Perfeito para criar
  arquivos 7z programaticamente.
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip com Vários Métodos de Compressão
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Como Compactar Pasta para 7z – Tutorial Aspose.Zip para .NET
url: /pt/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Compactar Pasta em 7z – Aspose.Zip para .NET Tutorial

## Introdução

Se você precisa **compactar pasta em 7z** programaticamente em uma aplicação .NET, está no lugar certo. Aspose.Zip para .NET facilita a geração de arquivos Seven Zip com qualquer um dos algoritmos de compressão suportados, seja para agrupar um diretório inteiro para distribuição ou simplesmente precisar de uma solução confiável de **arquivo seven zip .net**. Neste guia, percorreremos três métodos de compressão populares — LZMA2, BZip2 e Store (sem compressão) — e mostraremos exatamente como produzir um arquivo 7z em apenas algumas linhas de código C#.

## Respostas Rápidas
- **Qual biblioteca devo usar?** Aspose.Zip para .NET fornece o conjunto mais completo de recursos Seven Zip.  
- **Qual método de compressão oferece a melhor taxa?** LZMA2 geralmente fornece a maior compressão para dados mistos.  
- **Posso criar um 7z sem compressão?** Sim — use o método Store (sem compressão).  
- **Preciso de licença para desenvolvimento?** Um teste gratuito está disponível; uma licença é necessária para uso em produção.  
- **Isso é compatível com .NET 6/7?** Absolutamente — Aspose.Zip suporta .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 e .NET 5–10.

## Quais São os Métodos de Compressão Seven Zip?

Seven Zip suporta vários algoritmos, cada um otimizado para diferentes cenários. **LZMA2** oferece a maior taxa de compressão (geralmente 30‑40 % menor que BZip2), **BZip2** fornece compressão sólida com amplo suporte a ferramentas legadas, e **Store** simplesmente arquiva arquivos sem reduzi-los, preservando perfeitamente os timestamps originais.

## Pré-requisitos

Antes de começarmos, certifique-se de que você tem:

- Conhecimento básico de C# e Visual Studio.  
- A biblioteca Aspose.Zip para .NET instalada. Baixe-a na página oficial de download **[aqui](https://releases.aspose.com/zip/net/)**.  
- Uma pasta (`dataDir`) contendo os arquivos que você deseja arquivar.

## Importar Namespaces

Primeiro, adicione os namespaces necessários ao seu arquivo C#:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Essas classes dão acesso às configurações de compressão e ao gerenciamento de arquivos.

## Compressão LZMA2 – Como Criar um 7z com a Máxima Taxa de Compressão

A classe `Archive` representa um arquivo 7z que pode conter múltiplos arquivos.  
O algoritmo LZMA2 fornece a maior taxa de compressão entre os métodos suportados. Ele funciona dividindo a entrada em blocos e aplicando uma compressão de dicionário sofisticada. No Aspose.Zip, você define `CompressionMethod` como `CompressionMethod.Lzma2` no objeto `Archive` antes de adicionar arquivos.

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **Dica profissional:** LZMA2 funciona melhor quando os arquivos de origem têm mais de 1 MB. Para muitos arquivos pequenos, BZip2 pode ser mais rápido.

## Compressão BZip2 – Uma Escolha Equilibrada

A classe `Archive` representa um arquivo 7z que pode conter múltiplos arquivos.  
BZip2 oferece compressão sólida com boa compatibilidade para ferramentas mais antigas. Ele usa a transformação Burrows‑Wheeler e codificação Huffman para reduzir o tamanho. No Aspose.Zip, você seleciona `CompressionMethod.BZip2` ao configurar a instância `Archive`, o que equilibra velocidade e taxa de compressão para a maioria dos arquivos de texto e binários.

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 oferece compressão sólida mantendo velocidade razoável, sendo uma boa alternativa quando LZMA2 não é suportado pelo ambiente de destino.

## Store (Sem Compressão) – Quando o Tamanho Não Importa

A classe `Archive` representa um arquivo 7z que pode conter múltiplos arquivos.  
O método Store cria um arquivo sem comprimir os dados. Ele simplesmente copia os arquivos originais para o contêiner 7z, preservando timestamps e a estrutura de diretórios. Para usá-lo no Aspose.Zip, defina `CompressionMethod.Store` no `Archive` antes de adicionar os arquivos que deseja agrupar.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Use o método Store se você simplesmente precisar agrupar arquivos sem alterar seu tamanho — perfeito para preservar timestamps originais ou quando o arquivo será descompactado em tempo real.

## Como adicionar arquivos ao 7z?

Adicione arquivos a um arquivo 7z criando uma instância `Archive`, definindo o `CompressionMethod` desejado e chamando `AddAllFiles(dataDir)`. O método escaneia a pasta especificada recursivamente, preservando a hierarquia de diretórios dentro do arquivo. Essa abordagem permite que você **compacte pasta em 7z** com uma única linha de código após a configuração inicial.

## Casos de Uso Comuns

| Cenário | Método Recomendado |
|----------|--------------------|
| Distribuir instaladores grandes | LZMA2 |
| Compartilhar logs com ferramentas legadas | BZip2 |
| Empacotar arquivos para extração rápida | Store (sem compressão) |
| Precisa **compactar pasta em 7z** em tempo real em um serviço web | LZMA2 (para melhor taxa) |

## Solução de Problemas e Dicas

- **Arquivos ausentes no arquivo?** Verifique se `dataDir` aponta para o diretório correto e se o processo tem permissões de leitura.  
- **O arquivo falha ao abrir em versões antigas do 7‑Zip?** Use BZip2 ou Store, pois LZMA2 pode exigir bibliotecas de descompressão mais recentes.  
- **Gargalo de desempenho?** Para conjuntos de dados massivos, considere transmitir o arquivo em vez de carregar todas as entradas na memória.

## Perguntas Frequentes

**P: Posso usar Aspose.Zip para .NET com qualquer tipo de arquivo?**  
R: Sim, Aspose.Zip suporta uma ampla variedade de formatos de arquivo, permitindo compactar e descompactar praticamente qualquer tipo de arquivo.

**P: Existe uma versão de teste gratuita disponível para Aspose.Zip para .NET?**  
R: Sim, você pode obter uma versão de teste gratuita **[aqui](https://releases.aspose.com/)**.

**P: Onde posso encontrar a documentação do Aspose.Zip para .NET?**  
R: A referência completa da API está disponível **[aqui](https://reference.aspose.com/zip/net/)**.

**P: Como posso obter licenças temporárias para Aspose.Zip para .NET?**  
R: Licenças temporárias podem ser obtidas **[aqui](https://purchase.aspose.com/temporary-license/)**.

**P: Onde posso obter suporte para Aspose.Zip para .NET?**  
R: Você pode buscar suporte no **[fórum Aspose.Zip](https://forum.aspose.com/c/zip/37)**.

---

**Last Updated:** 2026-06-29  
**Tested With:** Aspose.Zip for .NET 24.12  
**Author:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [compactar arquivos c# – Criar arquivo 7z com Aspose.Zip para .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [Como Compactar Pasta Usando Aspose.Zip para .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [Como Compactar LZMA no Aspose.Zip para .NET](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}