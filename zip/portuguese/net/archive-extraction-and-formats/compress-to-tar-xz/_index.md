---
date: 2026-02-05
description: Aprenda como adicionar arquivos a tar e criar arquivos tarxz no .NET
  usando Aspose.Zip. Este guia mostra como compactar arquivos em tarxz com alta eficiência.
linktitle: Compressing to TarXz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Adicionar arquivos ao tar, criar arquivo tarxz .NET com Aspose.Zip
url: /pt/net/archive-extraction-and-formats/compress-to-tar-xz/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como adicionar arquivos ao tar, criar arquivo tarxz .NET com Aspise.Zip

## Introdução

Se você precisa **adicionar arquivos ao tar** e depois compactá‑los em um arquivo tarxz usando .NET, o Aspose.Zip para .NET torna o processo simples e confiável. Seja empacotando logs, arquivos de configuração ou quaisquer outros recursos para armazenamento ou transmissão, compactar para o formato TarXz oferece uma alta taxa de compressão enquanto preserva a estrutura familiar do tar. Neste tutorial, percorreremos as etapas exatas — completas com trechos de código — para que você possa integrar a criação de tarxz em suas aplicações .NET com confiança.

## Respostas Rápidas
- **Qual é a classe principal?** `TarArchive` de `Aspose.Zip.Tar`
- **Como compactar tarxz?** Use `SaveXzCompressed` após adicionar entradas
- **Versões .NET suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6
- **Licença necessária?** Sim, uma licença válida do Aspose.Zip para produção
- **Tempo típico de implementação?** ~5‑10 minutos

## O que é um arquivo TarXz?

Um **arquivo TarXz** combina o contêiner Unix tradicional `tar` com compressão XZ. A parte tar agrupa vários arquivos em um único fluxo, enquanto o XZ fornece compressão forte e sem perdas. Este formato é popular para distribuir código‑fonte, backups e grandes conjuntos de dados porque preserva a estrutura de diretórios e gera tamanhos de arquivo menores que tar ou zip simples.

## Por que adicionar arquivos ao tar e compactar para tarxz com Aspose.Zip?

- **Alta taxa de compressão** – XZ costuma comprimir 30‑50 % menor que gzip.  
- **Compatibilidade multiplataforma** – Arquivos TarXz podem ser abertos no Linux, macOS e Windows.  
- **API simples** – Aspose.Zip abstrai os detalhes de baixo nível, permitindo que você se concentre na lógica de negócio.  
- **Sem ferramentas externas** – Tudo roda dentro do seu processo .NET, perfeito para nuvem ou pipelines de CI.  

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- **Aspose.Zip para .NET** instalado (download da documentação oficial [Aspose.Zip documentation](https://reference.aspose.com/zip/net/)).  
- Uma pasta contendo os arquivos que você deseja arquivar. Nos exemplos abaixo, esta pasta é referenciada pela variável `dataDir`.  
- Uma licença válida do Aspose.Zip (opcional para avaliação, necessária para produção).

## Importar Namespaces

Primeiro, importe os namespaces que expõem a funcionalidade TarXz.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Como adicionar arquivos ao tar usando Aspose.Zip

### Passo 1: Inicializar um `TarArchive`

Crie uma nova instância de `TarArchive` que armazenará os arquivos que você deseja compactar.

```csharp
using (TarArchive archive = new TarArchive())
{
```

> **Dica profissional:** A instrução `using` garante que o arquivo seja descartado corretamente, liberando quaisquer recursos não gerenciados.

### Passo 2: Adicionar arquivos ao arquivo

Adicione cada arquivo que deseja incluir. Neste exemplo, adicionamos dois arquivos de texto, mas você pode adicionar quantas entradas precisar.

```csharp
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

> **Por que isso importa:** Adicionar entradas antes da compressão permite que o Aspose.Zip construa primeiro o contêiner tar e, em seguida, aplique a compressão XZ em uma única etapa.

### Passo 3: Salvar o arquivo com compressão XZ

Finalmente, grave o arquivo tar no disco usando compressão XZ. O arquivo resultante terá a extensão `.tar.xz`.

```csharp
    archive.SaveXzCompressed(dataDir + "archive.tar.xz");
}
```

> **Resultado:** Agora você tem um arquivo `archive.tar.xz` totalmente compactado que pode ser transferido, armazenado ou descompactado em qualquer plataforma que suporte TarXz.

## Problemas Comuns & Soluções

| Problema | Causa | Correção |
|----------|-------|----------|
| **Exceção “File not found”** | Caminho `dataDir` incorreto | Verifique se o caminho do diretório termina com uma barra invertida (`\`) ou use `Path.Combine`. |
| **Uso elevado de memória** | Arquivos muito grandes sendo compactados na memória | Use `TarArchive` em modo streaming (`Sobrecarga SaveXzCompressed` que aceita um `Stream`). |
| **Licença não aplicada** | Arquivo de licença ausente | Carregue a licença na inicialização da aplicação: `new Aspose.Zip.License().SetLicense("Aspose.Zip.lic");` |

## Perguntas Frequentes

**Q: O Aspose.Zip é compatível com todos os ambientes .NET?**  
A: Sim, o Aspose.Zip funciona com .NET Framework 4.5+, .NET Core 3.1+, e .NET 5/6+. Consulte a [documentação](https://reference.aspose.com/zip/net/) para detalhes.

**Q: Como posso obter uma licença temporária para o Aspose.Zip?**  
A: Você pode solicitar uma licença temporária na [página de licença temporária da Aspose](https://purchase.aspose.com/temporary-license/).

**Q: Existem exemplos adicionais para outros formatos de arquivo?**  
A: Claro—explore o conjunto completo de exemplos na [referência da API Aspose.Zip](https://reference.aspose.com/zip/net/).

**Q: Onde posso obter ajuda ou discutir problemas?**  
A: Participe da conversa no [fórum Aspose.Zip](https://forum.aspose.com/c/zip/37) para suporte da comunidade e respostas oficiais.

**Q: Posso testar o Aspose.Zip gratuitamente antes de comprar?**  
A: Sim, um teste gratuito está disponível na [página de download do Aspose.Zip](https://releases.aspose.com/zip/net).

## Conclusão

Seguindo as etapas acima, você agora sabe **como adicionar arquivos ao tar** e **criar arquivos tarxz** usando Aspose.Zip em .NET. Essa abordagem fornece um pacote compacto e portátil que pode ser integrado perfeitamente a qualquer fluxo de trabalho .NET — seja construindo uma utilidade desktop, um serviço web ou um pipeline CI/CD automatizado.

---

**Última atualização:** 2026-02-05  
**Testado com:** Aspose.Zip for .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}