---
date: 2026-11-18
description: Aprenda a criar arquivos tar e compactá‑los para TarZ usando Aspose.Zip
  para .NET – um guia passo a passo para manipulação eficiente de arquivos .NET.
keywords:
- how to create tar
- add files to tar
- add directory to tar
- archive files to tar
- compress files .net
lastmod: 2026-11-18
linktitle: Compactando para TarZ
og_description: Aprenda a criar arquivos tar e compactá‑los para TarZ usando Aspose.Zip
  para .NET. Este guia orienta você na adição de arquivos, diretórios e compressão
  eficiente.
og_image_alt: 'Guide: create tar and compress to TarZ using Aspose.Zip for .NET'
og_title: Como criar tar e compactar para TarZ com Aspose.Zip para .NET
schemas:
- author: Aspose
  dateModified: '2026-11-18'
  description: Learn how to create tar archives and compress them to TarZ using Aspose.Zip
    for .NET – a step‑by‑step guide for efficient .NET file handling.
  headline: How to create tar and compress to TarZ with Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Absolutely. Use a `Directory.GetFiles` loop and call `CreateEntry` for
      each file, preserving relative paths.
    question: Can I compress entire folders with Aspose.Zip for .NET?
  - answer: Yes, you can explore the capabilities of Aspose.Zip for .NET by downloading
      the free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Zip for .NET?
  - answer: The documentation is available [here](https://reference.aspose.com/zip/net/),
      providing detailed insights into the library's features and usage.
    question: Where can I find comprehensive documentation for Aspose.Zip for .NET?
  - answer: Visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) to seek
      assistance, share experiences, and connect with the community.
    question: How can I get support for Aspose.Zip for .NET?
  - answer: Yes, if you need a temporary license, you can obtain one [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: Como criar tar e compactar para TarZ com Aspose.Zip para .NET
url: /pt/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar arquivos a tar e compactar para TarZ com Aspose.Zip para .NET

## Introdução

Se você precisa **adicionar arquivos a tar** e depois compactar o arquivo para o formato TarZ, o Aspose.Zip para .NET torna todo o processo indolor. Neste tutorial percorreremos cada passo — desde a configuração do seu projeto até a criação de um arquivo tar, a adição de arquivos e, finalmente, a gravação de um arquivo .tar.z compactado. Ao final, você terá um trecho reutilizável que pode ser inserido em qualquer aplicação .NET, seja para lidar com alguns arquivos de configuração ou com uma árvore de diretórios inteira.

## Respostas rápidas
- **Qual biblioteca lida com a criação de tar?** Aspose.Zip for .NET  
- **Quantas linhas de código?** Cerca de 15 linhas (excluindo comentários)  
- **Preciso de licença para teste?** Um teste gratuito está disponível; uma licença é necessária para produção.  
- **Versões .NET suportadas?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 e .NET 5–10  
- **Posso compactar pastas, não apenas arquivos?** Sim – você pode adicionar diretórios inteiros com um loop.

## O que é **add files to tar**?
**Add files to tar** é o processo de agrupar arquivos selecionados em um único contêiner tar não compactado, preservando a hierarquia de diretórios e metadados. O formato tar cria um pacote determinístico e independente de plataforma que algoritmos de compressão subsequentes podem processar de forma eficiente, tornando-o ideal para distribuição multiplataforma.

## Como criar arquivos tar com Aspose.Zip para .NET?

A classe `TarArchive` representa um contêiner tar que pode conter múltiplas entradas de arquivo. Carregue o diretório de origem, instancie um `TarArchive`, adicione cada arquivo (ou um subdiretório inteiro) e, por fim, chame `Save` com a flag de compressão TarZ. O processo é direto, requer apenas algumas linhas de código e funciona de forma consistente em todos os runtimes .NET suportados, incluindo .NET Framework e .NET Core.

A classe `TarArchive` é o objeto central do Aspose.Zip que representa um contêiner tar que você pode popular com entradas. Usá‑la permite gerar arquivos tar completamente em memória, transmiti‑los diretamente para uma resposta ou gravá‑los no disco sem arquivos zip temporários.

## Por que adicionar arquivos a tar antes de compactar para TarZ?

Criar primeiro um contêiner tar isola o empacotamento da compressão, o que gera três benefícios mensuráveis. Ao separar essas etapas, você obtém um arquivo previsível e repetível que pode ser compactado independentemente, facilitando a medição de taxas de compressão e a reutilização do mesmo tar para diferentes algoritmos de compressão.

1. **Portabilidade** – Um arquivo `.tar` pode ser descompactado em qualquer sistema tipo Unix sem bibliotecas adicionais.  
2. **Velocidade** – A criação do tar é essencialmente uma operação de cópia de fluxo; a compressão Z subsequente foca apenas em reduzir o tamanho, tipicamente reduzindo **30‑70 %** dos dados originais.  
3. **Compatibilidade** – Muitas ferramentas legadas (por exemplo, `tar`, `gzip`) esperam um `.tar` antes de aplicar compressão estilo gzip, exatamente o que a extensão `.tar.z` representa.

### Por que isso importa para desenvolvedores .NET
Usar um contêiner tar permite que seu código .NET permaneça simples e determinístico. Você pode gerar o arquivo em memória, transmiti‑lo diretamente para uma resposta ou armazená‑lo no disco sem lidar com arquivos zip temporários. Esse padrão é especialmente útil para pipelines de build, agregação de logs ou quando você precisa enviar um conjunto de arquivos de configuração para um serviço baseado em Linux.

## Pré‑requisitos

Antes de mergulharmos no código, certifique‑se de que você tem:

- **Aspose.Zip for .NET** instalado. Baixe‑o do site oficial [here](https://releases.aspose.com/zip/net/).  
- Uma pasta na sua máquina que contém os arquivos que você deseja arquivar. Substitua o caminho placeholder pelo seu diretório real.

## Importar namespaces

Adicione as instruções `using` necessárias no topo do seu arquivo C#:

```csharp
using System;
using Aspose.Zip.Tar;
```

> **Dica profissional:** Use `Path.Combine` se precisar montar caminhos dinamicamente; isso evita separadores de caminho ausentes em diferentes SOs.

## Como adicionar arquivos a tar usando Aspose.Zip para .NET?

O método `CreateEntry` adiciona uma nova entrada de arquivo ao arquivo tar com um nome especificado e um fluxo de conteúdo. Carregue o diretório de origem, crie uma instância `TarArchive`, adicione cada arquivo (ou sub‑diretório inteiro) e, por fim, chame `Save` com a flag de compressão TarZ. Esse fluxo permanece conciso, tipicamente com menos de 20 linhas, e funciona em todos os runtimes .NET suportados, proporcionando uma maneira confiável de empacotar e compactar dados.

O método `Save` grava o arquivo no disco e, opcionalmente, aplica compressão.  

### Âncora de definição
A classe `TarArchive` é o objeto central do Aspose.Zip que representa um contêiner tar que você pode popular com entradas.

### Guia passo a passo

#### Etapa 1: Defina seu diretório de documentos

```csharp
string dataDir = "Your Document Directory";
```

> **Por que esta etapa é importante:** `dataDir` atua como o local base para cada arquivo que você adicionará. Mantê‑lo em uma única variável facilita a manutenção e a reutilização do código em múltiplos arquivos.

#### Etapa 2: Crie um arquivo Tar e adicione arquivos

##### 2.1: Crie a instância do arquivo Tar

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> O bloco `using` garante que o objeto `TarArchive` seja descartado corretamente, liberando quaisquer manipuladores de arquivo ou buffers de memória.

##### 2.2: Adicione arquivos ao arquivo  

`CreateEntry` adiciona um arquivo ao arquivo tar, especificando seu nome e fluxo de conteúdo.  

Dentro do bloco `using`, adicione cada arquivo que deseja incluir:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Você pode repetir `CreateEntry` quantas vezes precisar, ou percorrer um diretório em um loop para adicioná‑los programaticamente. Por exemplo, um loop `foreach (var file in Directory.GetFiles(dataDir))` permitiria lidar com um número arbitrário de arquivos preservando seus caminhos relativos.

##### 2.3: Salve o arquivo TarZ compactado  

`Save` grava o arquivo no disco e aplica o formato de compressão selecionado.  

Após adicionar todas as entradas, compacte o arquivo tar para o formato `.tar.z`:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

O arquivo resultante `archive.tar.z` ficará na mesma pasta especificada em `dataDir`. Agora você pode distribuir esse único pacote compactado para qualquer sistema que entenda TarZ.

## Problemas comuns e soluções

| Problema | Motivo | Correção |
|----------|--------|----------|
| **Arquivo não encontrado** | Caminho errado ou extensão de arquivo ausente | Verifique se `dataDir` termina com um separador de caminho e se os nomes de arquivos estão corretos. |
| **Acesso negado** | Permissões insuficientes na pasta de destino | Execute a aplicação com direitos apropriados ou escolha um diretório gravável. |
| **Arquivo compactado maior que o esperado** | Arquivos originais já estão compactados (por exemplo, imagens, vídeos) | TarZ funciona melhor em arquivos de texto ou logs; considere deixar os arquivos já compactados como estão. |

### Armadilhas comuns a observar
- **Barra final ausente** – Se `dataDir` não terminar com `\` ou `/`, a concatenação de strings produzirá um caminho inválido.  
- **Diretórios grandes** – Adicionar milhares de arquivos pode consumir memória; considere transmitir entradas ou usar a sobrecarga do `TarArchive` que grava diretamente em um fluxo de arquivo.  
- **Problemas de codificação** – Nomes de arquivos não‑ASCII podem precisar de tratamento explícito de codificação; Aspose.Zip respeita UTF‑8 por padrão, mas verifique na plataforma de destino.

## Perguntas frequentes

**P: Posso compactar pastas inteiras com Aspose.Zip para .NET?**  
R: Absolutamente. Use um loop `Directory.GetFiles` e chame `CreateEntry` para cada arquivo, preservando os caminhos relativos.

**P: Existe uma versão de teste disponível para Aspose.Zip para .NET?**  
R: Sim, você pode explorar as capacidades do Aspose.Zip para .NET baixando a versão de teste gratuita [aqui](https://releases.aspose.com/).

**P: Onde posso encontrar documentação abrangente para Aspose.Zip para .NET?**  
R: A documentação está disponível [aqui](https://reference.aspose.com/zip/net/), oferecendo insights detalhados sobre os recursos e o uso da biblioteca.

**P: Como posso obter suporte para Aspose.Zip para .NET?**  
R: Visite o [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) para buscar assistência, compartilhar experiências e conectar‑se com a comunidade.

**P: Posso obter uma licença temporária para Aspose.Zip para .NET?**  
R: Sim, se precisar de uma licença temporária, você pode obtê‑la [aqui](https://purchase.aspose.com/temporary-license/).

## Conclusão

Você aprendeu agora como **adicionar arquivos a tar** e compactar o resultado para um arquivo TarZ usando Aspose.Zip para .NET. Essa abordagem fornece um pacote limpo e portátil que pode ser facilmente transferido, armazenado ou processado posteriormente. Sinta‑se à vontade para adaptar o trecho para processar lotes de diretórios, integrá‑lo em pipelines de build ou combiná‑lo com outros componentes Aspose para fluxos de trabalho de documentos mais ricos.

---

**Last Updated:** 2026-11-18  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose

## Tutoriais relacionados

- [Adicionar vários arquivos a tar e criar arquivo tar.gz com Aspose.Zip para .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Como compactar vários arquivos tar com Aspose.Zip para .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)
- [Extração de Arquivo e Formatos](/zip/net/archive-extraction-and-formats/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}