---
date: 2026-02-23
description: Aprenda como adicionar arquivos a um tar e compactar arquivos em um arquivo
  tarxz .NET usando Aspose.Zip. Siga este guia passo a passo para armazenamento e
  transmissão eficientes.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Adicionar arquivos ao tar e criar arquivo tarxz com Aspose.Zip
url: /pt/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar arquivos ao tar e criar arquivo tarxz com Aspose.Zip

## Introdução

Se você precisa **adicionar arquivos ao tar** e então **criar um arquivo tarxz .net**, o Aspose.Zip para .NET torna o processo simples e confiável. Seja empacotando logs, arquivos de configuração ou quaisquer outros recursos para armazenamento ou transmissão, comprimir no formato TarXz oferece uma alta taxa de compressão enquanto preserva a estrutura familiar do tar. Neste tutorial percorreremos os passos exatos—com trechos de código—para que você possa integrar a criação de tarxz em suas aplicações .NET com confiança.

## Respostas rápidas
- **Qual é a classe principal?** `TarArchive` de `Aspose.Zip.Tar`
- **Como comprimir tarxz?** Use `SaveXzCompressed` após adicionar as entradas
- **Versões .NET suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **É necessária licença?** Sim, uma licença válida do Aspose.Zip para produção
- **Tempo típico de implementação?** ~5‑10 minutos

## O que é um arquivo TarXz?

Um **arquivo TarXz** combina o contêiner Unix tradicional `tar` com compressão XZ. A parte tar agrupa múltiplos arquivos em um único fluxo, enquanto o XZ fornece compressão forte e sem perdas. Este formato é popular para distribuir código‑fonte, backups e grandes conjuntos de dados porque mantém a estrutura de diretórios e gera arquivos menores que tar ou zip simples.

## Por que criar arquivo tarxz .net com Aspose.Zip?

- **Alta taxa de compressão** – XZ costuma comprimir 30‑50 % mais que gzip.  
- **Compatibilidade multiplataforma** – Arquivos TarXz podem ser abertos no Linux, macOS e Windows.  
- **API simples** – Aspose.Zip abstrai os detalhes de baixo nível, permitindo que você foque na lógica de negócio.  
- **Sem ferramentas externas** – Tudo roda dentro do seu processo .NET, ideal para nuvem ou pipelines de CI.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- **Aspose.Zip para .NET** instalado (baixe na documentação oficial do [Aspose.Zip](https://reference.aspose.com/zip/net/)).  
- Uma pasta contendo os arquivos que deseja arquivar. Nos exemplos abaixo, essa pasta é referenciada pela variável `dataDir`.  
- Uma licença válida do Aspose.Zip (opcional para avaliação, obrigatória para produção).

## Importar namespaces

Primeiro, importe os namespaces que expõem a funcionalidade TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Como adicionar arquivos ao tar usando Aspose.Zip

A seguir está o guia passo a passo que mostra exatamente como você **adiciona arquivos ao tar** antes de comprimi‑los.

### Etapa 1: Inicializar um `TarArchive`

Crie uma nova instância de `TarArchive` que armazenará os arquivos que você deseja comprimir.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Dica:** A instrução `using` garante que o arquivo seja descartado corretamente, liberando quaisquer recursos não gerenciados.

### Etapa 2: Adicionar arquivos ao arquivo

Adicione cada arquivo que deseja incluir. Neste exemplo adicionamos dois arquivos de texto, mas você pode inserir quantas entradas precisar.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Por que isso importa:** Adicionar entradas antes da compressão permite que o Aspose.Zip construa o contêiner tar primeiro e, em seguida, aplique a compressão XZ em uma única etapa.

### Etapa 3: Salvar o arquivo com compressão XZ

Por fim, grave o arquivo tar no disco usando compressão XZ. O arquivo resultante terá a extensão `.tar.xz`.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Resultado:** Você agora possui um arquivo `archive.tar.xz` totalmente comprimido que pode ser transferido, armazenado ou descompactado em qualquer plataforma que suporte TarXz.

## Como comprimir arquivos tarxz com Aspose.Zip

O processo mostrado acima é essencialmente **como comprimir arquivos tarxz**: primeiro você adiciona arquivos a um contêiner tar (`add files to tar`) e então invoca `SaveXzCompressed`. Essa abordagem de chamada única elimina a necessidade de ferramentas externas de linha de comando e mantém tudo dentro do seu código .NET.

## Problemas comuns & soluções

| Problema | Causa | Solução |
|----------|-------|---------|
| **Exceção “File not found”** | Caminho `dataDir` incorreto | Verifique se o caminho termina com barra invertida (`\`) ou use `Path.Combine`. |
| **Uso elevado de memória** | Arquivos muito grandes sendo comprimidos na memória | Use `TarArchive` em modo streaming (sobrecarga de `SaveXzCompressed` que aceita um `Stream`). |
| **Licença não aplicada** | Arquivo de licença ausente | Carregue a licença na inicialização da aplicação: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Perguntas frequentes

**P: O Aspose.Zip é compatível com todos os ambientes .NET?**  
R: Sim, o Aspose.Zip funciona com .NET Framework 4.5+, .NET Core 3.1+, e .NET 5/6+. Consulte a [documentação](https://reference.aspose.com/zip/net/) para detalhes.

**P: Como posso obter uma licença temporária para o Aspose.Zip?**  
R: Você pode solicitar uma licença temporária na [página de licença temporária da Aspose](https://purchase.aspose.com/temporary-license/).

**P: Existem exemplos adicionais para outros formatos de arquivo?**  
R: Absolutamente—explore o conjunto completo de exemplos na [referência da API Aspose.Zip](https://reference.aspose.com/zip/net/).

**P: Onde posso obter ajuda ou discutir problemas?**  
R: Participe da conversa no [fórum Aspose.Zip](https://forum.aspose.com/c/zip/37) para suporte da comunidade e respostas oficiais.

**P: Posso testar o Aspose.Zip gratuitamente antes de comprar?**  
R: Sim, um teste gratuito está disponível na [página de download do Aspose.Zip](https://releases.aspose.com/zip/net).

## Conclusão

Seguindo os passos acima, você agora sabe **como adicionar arquivos ao tar** e **comprimir arquivos tarxz**, e, mais importante, **como criar um arquivo tarxz .net** usando Aspose.Zip. Essa abordagem fornece um pacote compacto e portátil que pode ser integrado perfeitamente a qualquer fluxo de trabalho .NET—seja desenvolvendo um utilitário desktop, um serviço web ou um pipeline CI/CD automatizado.

---

**Última atualização:** 2026-02-23  
**Testado com:** Aspose.Zip para .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}