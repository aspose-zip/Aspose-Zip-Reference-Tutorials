---
title: Criando Sete Arquivos Zip - Tutorial Aspose.Zip para .NET
linktitle: SevenZip com vários métodos de compactação
second_title: API Aspose.Zip .NET para compactação e arquivamento de arquivos
description: Aprenda a criar arquivos Seven Zip com Aspose.Zip for .NET usando diferentes métodos de compactação. Etapas fáceis para LZMA2, BZip2 e Store (sem compactação).
weight: 12
url: /pt/net/sevenzip-compression/sevenzip-various-compression-methods/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criando Sete Arquivos Zip - Tutorial Aspose.Zip para .NET


## Introdução

No domínio do desenvolvimento .NET, gerenciar e compactar arquivos é uma tarefa comum. Aspose.Zip for .NET fornece uma solução poderosa para trabalhar com arquivos compactados, oferecendo uma variedade de métodos de compactação. Neste tutorial, exploraremos como usar Aspose.Zip for .NET para criar arquivos Seven Zip com diferentes métodos de compactação.

## Pré-requisitos

Antes de mergulharmos no tutorial, certifique-se de ter o seguinte:

- Uma compreensão básica da programação C#.
- Visual Studio instalado em sua máquina.
-  Biblioteca Aspose.Zip para .NET. Você pode baixá-lo[aqui](https://releases.aspose.com/zip/net/).

## Importar namespaces

Comece importando os Namespaces necessários para o seu projeto C#. Use o seguinte trecho de código para começar:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## Compressão LZMA2

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

## Compressão BZip2

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

## Armazenar, sem compressão

```csharp
//Armazenar, sem compressão
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

## Conclusão

Neste tutorial, exploramos a versatilidade do Aspose.Zip for .NET na criação de arquivos Seven Zip com vários métodos de compactação. Se você precisa de altas taxas de compactação ou prefere nenhuma compactação, o Aspose.Zip oferece a flexibilidade para atender às suas necessidades.

## Perguntas frequentes

### Posso usar o Aspose.Zip for .NET com qualquer tipo de arquivo?
Sim, Aspose.Zip for .NET oferece suporte a uma ampla variedade de tipos de arquivos, permitindo compactar e descompactar vários formatos.

### Há uma avaliação gratuita disponível para Aspose.Zip for .NET?
 Sim, você pode obter um teste gratuito[aqui](https://releases.aspose.com/).

### Onde posso encontrar a documentação do Aspose.Zip para .NET?
 A documentação está disponível[aqui](https://reference.aspose.com/zip/net/).

### Como posso obter licenças temporárias do Aspose.Zip for .NET?
 Licenças temporárias podem ser obtidas[aqui](https://purchase.aspose.com/temporary-license/).

### Onde posso obter suporte para Aspose.Zip for .NET?
 Você pode procurar apoio no[Fórum Aspose.Zip](https://forum.aspose.com/c/zip/37).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
