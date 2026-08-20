---
date: 2026-08-07
description: Aprenda como adicionar arquivos ao tar e gerar um arquivo TarBz2 em .NET
  usando Aspose.Zip. Guia passo a passo mostra a criação de tar, compressão Bzip2
  e dicas de boas práticas.
keywords:
- add files to tar
- tar bzip2 compression
- generate tarbz2 archive
- asp zip
- compress tar .net
lastmod: 2026-08-07
linktitle: Compactando para TarBz2
og_description: Adicionar arquivos ao tar e gerar um arquivo TarBz2 em .NET usando
  Aspose.Zip. Este guia cobre a criação de tar, compressão Bzip2 e dicas de solução
  de problemas.
og_image_alt: Developer guide showing how to add files to tar and compress to TarBz2
  with Aspose.Zip for .NET
og_title: Adicionar arquivos ao tar e criar um arquivo TarBz2 com Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-08-07'
  description: Learn how to add files to tar and generate a TarBz2 archive in .NET
    using Aspose.Zip. Step‑by‑step guide shows tar creation, Bzip2 compression and
    best‑practice tips.
  headline: Add files to tar and create a TarBz2 archive with Aspose.Zip
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
title: Adicionar arquivos ao tar e criar um arquivo TarBz2 com Aspose.Zip
url: /pt/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar arquivos a tar e criar um arquivo TarBz2 com Aspose.Zip

Neste tutorial você descobrirá **como adicionar arquivos a tar** em arquivos e transformá-los em um compacto arquivo **TarBz2** usando a biblioteca **Aspose.Zip** para .NET. Seja construindo uma ferramenta de backup, publicando pacotes de implantação ou precisando de um pacote leve para distribuição, os passos abaixo o guiarão na adição de arquivos a um contêiner tar, na aplicação da compressão Bzip2 e na produção de um arquivo pronto‑para‑compartilhar.

## Respostas rápidas
- **Qual biblioteca devo usar?** Aspose.Zip for .NET  
- **Quanto tempo leva a implementação?** About 5‑10 minutes  
- **Preciso de uma licença?** A temporary license is required for production; a free trial is available  
- **Posso compactar vários arquivos?** Yes – add as many entries as you like to the tar archive  
- **É compatível com .NET 6+?** Absolutely, Aspose.Zip supports .NET Framework and .NET Core/5/6  

## O que é um arquivo TarBz2?

Um arquivo TarBz2 combina o contêiner tradicional **tar** (que preserva a estrutura de diretórios e os metadados dos arquivos) com a compressão **Bzip2**, resultando em um pacote altamente compactado `.tar.bz2`. Esse formato é popular em sistemas semelhantes ao Unix porque oferece um bom equilíbrio entre taxa de compressão e velocidade de descompressão.

## Por que compactar arquivos em TarBz2 com Aspose.Zip?

Aspose.Zip pode gerar um arquivo TarBz2 em **duas chamadas de API** enquanto manipula streams de forma eficiente. Ele suporta **mais de 50 formatos de arquivo e compressão**, processa arquivos de até **2 GB** sem carregar todo o arquivo para a memória, e funciona em runtimes .NET para Windows, Linux e macOS. A biblioteca também oferece controle granular sobre nomes de entradas, timestamps e níveis de compressão, tornando-a ideal tanto para utilitários de console quanto para serviços web.

## Pré-requisitos

- **Aspose.Zip for .NET** – faça o download do pacote mais recente no site oficial: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document directory** – uma pasta que contém os arquivos que você deseja arquivar. Nos exemplos, referenciamos com a variável `dataDir`.

> **Pro tip:** Mantenha seus arquivos de origem em uma pasta dedicada para evitar a inclusão acidental de arquivos indesejados.

## Importar namespaces

Primeiro, importe os namespaces necessários para que você possa acessar as classes Tar e Bzip2 do Aspose.Zip.

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

## Etapa 2: adicionar arquivos a tar e criar um arquivo TarBz2

`TarArchive` representa um contêiner tar em memória que pode conter múltiplas entradas de arquivos.  
`Bzip2Archive` compacta um stream usando o algoritmo Bzip2.  
O método `CreateEntry` adiciona um arquivo ao arquivo tar como uma nova entrada.

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

- `CreateEntry` **adds files to tar** – você pode chamar este método para cada arquivo que precisar no arquivo.  
- `bz2.SetSource(archive)` indica ao arquivo Bzip2 para compactar todo o stream tar.  
- `bz2.Save(...)` grava o arquivo final **TarBz2** no disco.

**Dica:** Para **adicionar arquivos a tar** em massa, basta repetir `archive.CreateEntry` para cada arquivo antes de chamar `bz2.Save`.

## Como adicionar arquivos a tar?

Carregue o diretório de origem, crie uma instância `TarArchive`, adicione cada arquivo com `CreateEntry`, então envolva o stream tar em um `Bzip2Archive` e chame `Save`. Esse padrão de duas etapas adiciona qualquer número de arquivos e produz um arquivo `.tar.bz2` em um fluxo fluente único, eliminando a necessidade de arquivos temporários ou ferramentas externas.

## Problemas comuns & soluções

| Problema | Motivo | Correção |
|----------|--------|----------|
| **Erro de arquivo não encontrado** | Caminho `dataDir` incorreto ou extensão de arquivo ausente | Verifique o caminho completo e assegure que o arquivo exista. |
| **Arquivo vazio** | Nenhuma entrada adicionada antes de `bz2.Save` | Adicione ao menos uma chamada `CreateEntry`. |
| **Permissão negada** | Aplicação não tem permissão de escrita na pasta de saída | Execute o aplicativo com direitos apropriados ou escolha um diretório gravável. |

## Perguntas frequentes

**Q: O Aspose.Zip é compatível com todas as aplicações .NET?**  
A: Sim. Funciona com .NET Framework, .NET Core, .NET 5/6 e runtimes mais recentes.

**Q: Posso compactar vários arquivos simultaneamente?**  
A: Absolutamente. Chame `CreateEntry` para cada arquivo antes de salvar o arquivo.

**Q: Onde posso encontrar documentação adicional?**  
A: Documentação detalhada está disponível na **referência da API Aspose.Zip .NET**: [Aspose.Zip .NET API reference](https://reference.aspose.com/zip/net/).

**Q: Como obtenho uma licença temporária para Aspose.Zip?**  
A: Você pode **solicitar uma licença temporária** aqui: [request a temporary license](https://purchase.aspose.com/temporary-license/).

**Q: Existe uma versão de avaliação gratuita disponível?**  
A: Sim, **baixe uma versão de avaliação nos lançamentos da Aspose**: [download a trial version](https://releases.aspose.com/).

## Conclusão

Agora você sabe **como adicionar arquivos a tar**, compactar o stream tar com Bzip2 e gerar um arquivo **TarBz2** usando Aspose.Zip para .NET. A abordagem é rápida, eficiente em memória e funciona em todas as plataformas .NET modernas. Sinta-se à vontade para experimentar conjuntos de arquivos maiores, nomes de entradas personalizados ou integrar o código em seus próprios pipelines de backup ou implantação.

Se você encontrar algum desafio, a comunidade Aspose.Zip está pronta para ajudar—basta acessar o **fórum de suporte do Aspose.Zip**: [Aspose.Zip support forum](https://forum.aspose.com/c/zip/37).

---

**Última atualização:** 2026-08-07  
**Testado com:** Aspose.Zip for .NET (latest release)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Criar arquivo tar e adicionar arquivos a tar com Aspose.Zip para .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Adicionar arquivos a tar e criar arquivo tarxz com Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Adicionar arquivos a tar e compactar para TarZ com Aspose.Zip para .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-z/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}