---
date: 2026-05-30
description: Aprenda como adicionar arquivos ao tar e compactá‑los para TarZ usando
  Aspose.Zip para .NET – um guia passo a passo para um manuseio eficiente de arquivos
  .NET.
keywords:
- add files to tar
- add directory to tar
- compress folders to tar
- compress files .net
linktitle: Compactando para TarZ
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to add files to tar and compress them to TarZ using Aspose.Zip
    for .NET – a step‑by‑step guide for efficient .NET file handling.
  headline: Add files to tar and compress to TarZ with Aspose.Zip for .NET
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
title: Adicionar arquivos ao tar e compactar para TarZ com Aspose.Zip para .NET
url: /pt/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar arquivos a tar e compactar para TarZ com Aspise.Zip para .NET

## Introdução

Se você precisar **add files to tar** e então compactar o arquivo para o formato TarZ, Aspose.Zip para .NET torna todo o processo simples. Neste tutorial, percorreremos cada passo — desde a configuração do seu projeto até a criação de um arquivo tar, a adição de arquivos e, finalmente, a gravação de um arquivo .tar.z compactado. Ao final, você terá um trecho reutilizável que pode ser inserido em qualquer aplicação .NET, seja lidando com alguns arquivos de configuração ou com uma árvore de diretórios inteira.

## Respostas Rápidas
- **Qual biblioteca lida com a criação de tar?** Aspose.Zip for .NET  
- **Quantas linhas de código?** About 15 lines (excluding comments)  
- **Preciso de licença para teste?** A free trial is available; a license is required for production.  
- **Versões .NET suportadas?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET 5–10  
- **Posso compactar pastas, não apenas arquivos?** Yes – you can add entire directories with a loop.  

## O que é **add files to tar**?
A operação **add files to tar** agrupa arquivos selecionados em um único contêiner tar não compactado, preservando a hierarquia de diretórios e metadados.  
Carregar arquivos em um arquivo tar é o primeiro passo antes de qualquer compressão adicional, como TarZ, porque o formato tar fornece um pacote determinístico e independente de plataforma que os algoritmos de compressão podem processar de forma eficiente.

## Por que adicionar arquivos a tar antes de compactar para TarZ?
Criar primeiro um contêiner tar isola a lógica de empacotamento da etapa de compressão, o que gera três benefícios mensuráveis. Ao separar essas fases, você obtém um arquivo previsível e repetível que pode ser compactado independentemente, facilitando a medição de taxas de compressão e a reutilização do mesmo tar para diferentes algoritmos de compressão.  
1. **Portabilidade** – Um arquivo `.tar` pode ser descompactado em qualquer sistema tipo Unix sem bibliotecas adicionais.  
2. **Velocidade** – A criação do tar é essencialmente uma operação de cópia de fluxo; a compressão Z subsequente foca apenas na redução de tamanho, tipicamente reduzindo 30‑70 % dos dados originais.  
3. **Compatibilidade** – Muitas ferramentas legadas (por exemplo, `tar`, `gzip`) esperam um `.tar` antes de aplicar compressão estilo gzip, exatamente o que a extensão `.tar.z` representa.

### Por que isso importa para desenvolvedores .NET
Usar um contêiner tar permite que seu código .NET permaneça simples e determinístico. Você pode gerar o arquivo em memória, transmiti‑lo diretamente para uma resposta ou armazená‑lo em disco sem lidar com arquivos zip temporários. Esse padrão é especialmente útil para pipelines de construção, agregação de logs ou quando você precisa enviar um conjunto de arquivos de configuração para um serviço baseado em Linux.

## Pré‑requisitos

Antes de mergulharmos no código, certifique‑se de que você tem:

- **Aspose.Zip for .NET** instalado. Baixe‑o do site oficial [here](https://releases.aspose.com/zip/net/).  
- Uma pasta na sua máquina que contém os arquivos que você deseja arquivar. Substitua o caminho placeholder pelo seu diretório real.

## Importar Namespaces

Adicione as declarações `using` necessárias no topo do seu arquivo C#:

```csharp
using System;
using Aspose.Zip.Tar;
```

> **Dica profissional:** Use `Path.Combine` se precisar construir caminhos dinamicamente; isso evita a falta de separadores de caminho em diferentes sistemas operacionais.

## Como adicionar arquivos a tar usando Aspose.Zip para .NET?

Carregue o diretório de origem, crie uma instância `TarArchive`, adicione cada arquivo (ou sub‑diretório inteiro) e, finalmente, chame `Save` com a flag de compressão TarZ. Esse fluxo de ponta a ponta requer apenas algumas linhas de código e funciona em todos os runtimes .NET suportados.

### Âncora de definição
A classe `TarArchive` é o objeto central do Aspose.Zip que representa um contêiner tar que você pode preencher com entradas.

### Guia passo a passo

### Passo 1: Defina seu diretório de documentos

```csharp
string dataDir = "Your Document Directory";
```

> **Por que este passo é importante:** `dataDir` funciona como o local base para cada arquivo que você adicionará. Mantê‑lo em uma única variável torna o código fácil de manter e reutilizar em vários arquivos.

### Passo 2: Crie um arquivo Tar e adicione arquivos

#### 2.1: Crie a instância do arquivo Tar

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

> O bloco `using` garante que o objeto `TarArchive` seja descartado corretamente, liberando quaisquer manipuladores de arquivo ou buffers de memória.

#### 2.2: Adicione arquivos ao arquivo  

`CreateEntry` adiciona um arquivo ao arquivo tar, especificando seu nome e fluxo de conteúdo.  

Dentro do bloco `using`, adicione cada arquivo que deseja incluir:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Você pode repetir `CreateEntry` para quantos arquivos precisar, ou percorrer um diretório para adicioná‑los programaticamente. Por exemplo, um loop `foreach (var file in Directory.GetFiles(dataDir))` permitiria lidar com um número arbitrário de arquivos preservando seus caminhos relativos.

#### 2.3: Salve o arquivo TarZ compactado  

`Save` grava o arquivo no disco e aplica o formato de compressão selecionado.  

Depois de adicionar todas as entradas, compacte o arquivo tar para o formato `.tar.z`:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

O arquivo resultante `archive.tar.z` ficará na mesma pasta especificada em `dataDir`. Agora você pode enviar este pacote único e compactado para qualquer sistema que entenda TarZ.

## Problemas Comuns e Soluções

| Problema | Razão | Correção |
|----------|-------|----------|
| **Arquivo não encontrado** | Caminho errado ou extensão de arquivo ausente | Verifique se `dataDir` termina com um separador de caminho e se os nomes dos arquivos estão corretos. |
| **Acesso negado** | Permissões insuficientes na pasta de destino | Execute a aplicação com direitos adequados ou escolha um diretório gravável. |
| **Arquivo compactado maior que o esperado** | Arquivos originais já estão compactados (ex.: imagens, vídeos) | TarZ funciona melhor em arquivos de texto ou logs; considere deixar os arquivos já compactados como estão. |

### Armadilhas comuns a observar
- **Barra final ausente** – Se `dataDir` não terminar com `\` ou `/`, a concatenação de strings produzirá um caminho inválido.  
- **Diretórios grandes** – Adicionar milhares de arquivos pode consumir memória; considere transmitir entradas ou usar a sobrecarga `TarArchive` que grava diretamente em um fluxo de arquivo.  
- **Problemas de codificação** – Nomes de arquivos não‑ASCII podem precisar de tratamento explícito de codificação; Aspose.Zip respeita UTF‑8 por padrão, mas verifique na plataforma de destino.  

## Perguntas Frequentes

**Q: Posso compactar pastas inteiras com Aspose.Zip para .NET?**  
A: Absolutamente. Use um loop `Directory.GetFiles` e chame `CreateEntry` para cada arquivo, preservando os caminhos relativos.

**Q: Existe uma versão de avaliação disponível para Aspose.Zip para .NET?**  
A: Sim, você pode explorar as funcionalidades do Aspose.Zip para .NET baixando a avaliação gratuita [here](https://releases.aspose.com/).

**Q: Onde posso encontrar documentação abrangente para Aspose.Zip para .NET?**  
A: A documentação está disponível [here](https://reference.aspose.com/zip/net/), fornecendo detalhes sobre os recursos e uso da biblioteca.

**Q: Como posso obter suporte para Aspose.Zip para .NET?**  
A: Visite o [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) para buscar ajuda, compartilhar experiências e conectar‑se com a comunidade.

**Q: Posso obter uma licença temporária para Aspose.Zip para .NET?**  
A: Sim, se precisar de uma licença temporária, você pode obter uma [here](https://purchase.aspose.com/temporary-license/).

## Conclusão

Agora você aprendeu como **add files to tar** e compactar o resultado em um arquivo TarZ usando Aspose.Zip para .NET. Essa abordagem fornece um pacote limpo e portátil que pode ser facilmente transferido, armazenado ou processado adicionalmente. Sinta‑se à vontade para adaptar o trecho para processar diretórios em lote, integrá‑lo em pipelines de construção ou combiná‑lo com outros componentes Aspose para fluxos de trabalho de documentos mais avançados.

---

**Última atualização:** 2026-05-30  
**Testado com:** Aspose.Zip for .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
