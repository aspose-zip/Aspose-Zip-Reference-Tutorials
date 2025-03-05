---
title: Compactar arquivos usando FileInfo em Aspose.Zip para .NET
linktitle: Compactar arquivos usando FileInfo
second_title: API Aspose.Zip .NET para compactação e arquivamento de arquivos
description: Aprenda a compactar arquivos usando fileinfo com Aspose.Zip para .NET. Siga nosso guia passo a passo para um gerenciamento eficiente de arquivos.
type: docs
weight: 11
url: /pt/net/file-compression/compress-files-fileinfo/
---
## Introdução

Bem-vindo ao nosso guia completo sobre compactação de arquivos usando Aspose.Zip para .NET! Se você deseja otimizar o armazenamento ou transmissão de arquivos, Aspose.Zip é a solução ideal. Neste tutorial, orientaremos você no processo de compactação de arquivos usando a classe FileInfo, fornecendo um guia passo a passo detalhado. Vamos mergulhar!

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:

1.  Aspose.Zip para .NET: Certifique-se de ter a biblioteca Aspose.Zip instalada. Você pode baixá-lo no[local na rede Internet](https://releases.aspose.com/zip/net/).

2. Diretório de documentos: Configure um diretório em seu sistema para armazenar os arquivos que deseja compactar.

## Importar namespaces

No seu projeto .NET, inclua os namespaces necessários:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

## Etapa 1: configure seu diretório de documentos

Primeiramente, defina o diretório onde seus documentos estão armazenados. Você pode usar o seguinte código:

```csharp
string dataDir = "Your Document Directory";
```

## Etapa 2: compactar arquivos usando FileInfo

 Agora, vamos entrar no cerne do processo. Usaremos o`FileInfo` class junto com Aspose.Zip para compactar arquivos. Siga esses passos:

### Etapa 2.1: Abra um arquivo Zip

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Etapa 2.2: Criar objetos FileInfo

 Criar`FileInfo` objetos para os arquivos que você deseja compactar:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

### Etapa 2.3: Criar arquivo e adicionar entradas

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Etapa 2.4: Salve o arquivo Zip

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Parabéns! Você compactou arquivos com sucesso usando a classe FileInfo em Aspose.Zip for .NET.

## Conclusão

Neste tutorial, exploramos como compactar arquivos com eficiência usando Aspose.Zip para .NET. Seguindo essas etapas, você pode aprimorar seus recursos de gerenciamento de arquivos e otimizar o uso de espaço. Experimente diferentes tipos e tamanhos de arquivo para aproveitar todo o potencial do Aspose.Zip.

## Perguntas frequentes

### Q1: O Aspose.Zip é compatível com todos os tipos de arquivo?

A1: Aspose.Zip suporta uma ampla variedade de tipos de arquivos, garantindo versatilidade na compactação.

### Q2: Posso usar Aspose.Zip para projetos comerciais?

 A2: Com certeza! Visite nosso[página de compra](https://purchase.aspose.com/buy) para explorar opções de licenciamento.

### Q3: Como posso obter suporte para Aspose.Zip?

 A3: Junte-se à nossa comunidade no[Fórum Aspose.Zip](https://forum.aspose.com/c/zip/37) para assistência e discussões.

### Q4: Existe um teste gratuito disponível?

 A4: Sim, você pode pegar seu[teste gratuito aqui](https://releases.aspose.com/).

### P5: Como posso obter uma licença temporária do Aspose.Zip?

 A5: Visita[esse link](https://purchase.aspose.com/temporary-license/) para obter informações sobre como obter uma licença temporária.