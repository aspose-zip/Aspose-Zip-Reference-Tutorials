---
date: 2026-10-31
description: Aprenda a criar um arquivo tar e compactá‑lo em um arquivo TarBz2 no
  .NET usando Aspose.Zip. Guia passo a passo mostra a criação de tar, compressão Bzip2
  e dicas de boas práticas.
images:
- /net/archive-extraction-and-formats/compress-to-tar-bz2/og-image.png
keywords:
- create tar archive
- add files to tar
- compress multiple files
- tar bzip2 compression
- add files tar
lastmod: 2026-10-31
linktitle: Compactando para TarBz2
og_description: Aprenda a criar um arquivo tar e compactá‑lo em um arquivo TarBz2
  usando Aspose.Zip para .NET. Guia passo a passo cobre a criação de tar, compressão
  Bzip2 e dicas de boas práticas.
og_image_alt: Developer guide showing how to create tar archive and compress to TarBz2
  using Aspose.Zip for .NET
og_title: Como criar um arquivo tar e compactar para TarBz2 com .NET
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to create tar archive and compress it to a TarBz2 file in
    .NET using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression
    and best‑practice tips.
  headline: Create tar archive and compress to TarBz2 with .NET
  type: TechArticle
- questions:
  - answer: Yes. It works with .NET Framework, .NET Core, .NET 5/6 and newer runtimes.
    question: Is Aspose.Zip compatible with all .NET applications?
  - answer: Absolutely. Call `CreateEntry` for each file before saving the archive.
    question: Can I compress multiple files simultaneously?
  - answer: 'Detailed docs are available in the **Aspose.Zip .NET API reference**:
      [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).'
    question: Where can I find additional documentation?
  - answer: 'You can **request a temporary license** here: [request a temporary license](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for Aspose.Zip?
  - answer: 'Yes, **download a trial version from Aspose releases**: [download a trial
      version](https://releases.aspose.com/).'
    question: Is there a free trial available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- add files to tar
- Aspose.Zip
- .NET compression
- TarBz2 archive
title: Como criar um arquivo tar e compactar para TarBz2 com .NET
url: /pt/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar um arquivo tar e compactar para TarBz2 com .NET

Neste tutorial você aprenderá **como criar arquivos de arquivo tar** e, em seguida, compactá‑los em um pacote **TarBz2** compacto usando a biblioteca **Aspose.Zip** para .NET. Seja você quem está construindo uma ferramenta de backup, preparando pacotes de implantação ou precisa de um formato de distribuição leve, os passos abaixo mostram como adicionar arquivos a um contêiner tar, aplicar compressão Bzip2 e gravar o arquivo final `.tar.bz2`.

## Respostas rápidas
- **Qual biblioteca devo usar?** Aspose.Zip para .NET  
- **Quanto tempo leva a implementação?** Cerca de 5‑10 minutos  
- **Preciso de licença?** Uma licença temporária é necessária para produção; há uma versão de avaliação gratuita  
- **Posso compactar vários arquivos?** Sim – adicione quantas entradas quiser ao arquivo tar  
- **É compatível com .NET 6+?** Absolutamente, o Aspose.Zip suporta .NET Framework e .NET Core/5/6  

## O que é um arquivo TarBz2?

Um arquivo TarBz2 combina o contêiner tradicional **tar** (que preserva a estrutura de diretórios e metadados dos arquivos) com compressão **Bzip2**, resultando em um pacote `.tar.bz2` altamente compactado. Esse formato é popular em sistemas tipo Unix porque oferece um bom equilíbrio entre taxa de compressão e velocidade de descompressão.

## Por que compactar arquivos para TarBz2 com Aspose.Zip?

O Aspose.Zip pode gerar um arquivo TarBz2 em **duas chamadas de API** enquanto manipula streams de forma eficiente. Ele suporta **mais de 50 formatos de arquivo e compressão**, processa arquivos de até **2 GB** sem carregar todo o arquivo na memória e funciona nos runtimes .NET para Windows, Linux e macOS. A biblioteca também oferece controle granular sobre nomes de entradas, timestamps e níveis de compressão, tornando‑a ideal tanto para utilitários de console quanto para serviços web.

## Pré‑requisitos

- **Aspose.Zip para .NET** – baixe o pacote mais recente no site oficial: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Diretório de documentos** – uma pasta que contém os arquivos que você deseja arquivar. Nos exemplos, referenciamos isso com a variável `dataDir`.

> **Dica profissional:** Mantenha seus arquivos fonte em uma pasta dedicada para evitar a inclusão acidental de arquivos indesejados.

## Importar namespaces

Primeiro, importe os namespaces necessários para acessar as classes Tar e Bzip2 do Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Etapa 1: definir o diretório de documentos

Defina o caminho que aponta para a pasta que contém os arquivos que você deseja arquivar.

```csharp
string dataDir = "Your Document Directory";
```

> Substitua `"Your Document Directory"` pelo caminho absoluto ou relativo da sua pasta de origem.

## Etapa 2: adicionar arquivos ao tar e criar um arquivo TarBz2

A classe `TarArchive` representa um contêiner tar em memória, enquanto `Bzip2Archive` compacta streams usando o algoritmo Bzip2.  
O método `CreateEntry` adiciona uma nova entrada de arquivo ao arquivo tar.

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **adiciona arquivos ao tar** – você pode chamar esse método para cada arquivo que precisar no arquivo.  
- `bz2.SetSource(archive)` indica ao arquivo Bzip2 para compactar todo o stream tar.  
- `bz2.Save(...)` grava o arquivo final **TarBz2** no disco.

**Dica:** Para **adicionar arquivos ao tar** em lote, basta repetir `archive.CreateEntry` para cada arquivo antes de chamar `bz2.Save`.

## Como adicionar arquivos ao tar?

Carregue o diretório de origem, crie uma instância `TarArchive`, adicione cada arquivo com `CreateEntry`, então envolva o stream tar em um `Bzip2Archive` e chame `Save`. Esse padrão de duas etapas adiciona qualquer número de arquivos e produz um arquivo `.tar.bz2` em um fluxo fluente único, eliminando a necessidade de arquivos temporários ou ferramentas externas.

## Problemas comuns & soluções

| Problema | Motivo | Solução |
|----------|--------|---------|
| **Erro “File not found”** | Caminho `dataDir` incorreto ou extensão de arquivo ausente | Verifique o caminho completo e assegure‑se de que o arquivo exista. |
| **Arquivo vazio** | Nenhuma entrada adicionada antes de `bz2.Save` | Adicione ao menos uma chamada `CreateEntry`. |
| **Permissão negada** | Aplicação não tem permissão de gravação na pasta de saída | Execute o aplicativo com direitos adequados ou escolha um diretório gravável. |

## Perguntas frequentes

**P: O Aspose.Zip é compatível com todos os aplicativos .NET?**  
R: Sim. Funciona com .NET Framework, .NET Core, .NET 5/6 e runtimes mais recentes.

**P: Posso compactar vários arquivos simultaneamente?**  
R: Absolutamente. Chame `CreateEntry` para cada arquivo antes de salvar o arquivo.

**P: Onde posso encontrar documentação adicional?**  
R: Documentação detalhada está disponível na **referência da API Aspose.Zip .NET**: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**P: Como obtenho uma licença temporária para o Aspose.Zip?**  
R: Você pode **solicitar uma licença temporária** aqui: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**P: Existe uma versão de avaliação gratuita?**  
R: Sim, **baixe uma versão de avaliação dos lançamentos Aspose**: [download a trial version](https://releases.aspose.com/).

Você também pode [download a      trial version](https://releases.aspose.com/).

## Conclusão

Agora você sabe **como criar um arquivo tar**, compactar o stream tar com Bzip2 e gerar um **arquivo TarBz2** usando Aspose.Zip para .NET. A abordagem é rápida, eficiente em memória e funciona em todas as plataformas .NET modernas. Sinta‑se à vontade para experimentar conjuntos de arquivos maiores, nomes de entrada personalizados ou integrar o código em seus próprios pipelines de backup ou implantação.

Se encontrar algum desafio, a comunidade Aspose.Zip está pronta para ajudar — basta acessar o **fórum de suporte Aspose.Zip**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Última atualização:** 2026-10-31  
**Testado com:** Aspose.Zip para .NET (última versão)  
**Autor:** Aspose  

## Tutoriais relacionados

- [Create tar archive and add files to tar with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Add files to tar and create tarxz archive with Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Add files to tar and compress to TarZ with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}