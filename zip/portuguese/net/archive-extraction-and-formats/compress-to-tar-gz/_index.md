---
date: 2026-01-28
description: Learn how to create tar.gz archive, add files to tar and compress using
  Aspose.Zip for .NET – a fast, reliable way to archive files.
linktitle: Add files to tar
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Criar arquivo tar.gz e adicionar arquivos ao tar com Aspose.Zip para .NET
url: /pt/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar arquivos a tar e criar TarGz com Aspose.Zip para .NET

## Introdução

Em aplicações .NET modernas, **add files to tar** de forma rápida e confiável é um requisito comum — seja para empacotar logs, preparar dados para armazenamento em nuvem ou criar pacotes de implantação. Aspose.Zip para .NET oferece uma API limpa e de alto desempenho para **add files to tar**, e então comprimir o arquivo para o formato amplamente usado **tar.gz**. Neste tutorial você aprenderá exatamente como **create tar.gz archive** do zero, passo a passo, usando a biblioteca Aspose.Zip .NET.

## Respostas Rápidas
- **Qual biblioteca devo usar?** Aspose.Zip for .NET  
- **Como adiciono arquivos a tar?** Use `TarArchive.CreateEntry` para cada arquivo.  
- **Posso comprimir diretamente para tar.gz?** Sim — chame `SaveGzipped`.  
- **Preciso de licença para produção?** Uma licença válida da Aspose é necessária para uso não‑trial.  
- **Versões .NET suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que é “add files to tar”?
Adicionar arquivos a um arquivo tar significa agrupar múltiplos arquivos em um único contêiner não comprimido. O formato tar preserva estruturas de diretórios e metadados dos arquivos, tornando‑o ideal para arquivamento antes da compressão opcional (por exemplo, gzip) para **create tar.gz archive**.

## Por que usar Aspose.Zip para comprimir arquivos em tar.gz?
- **Sem ferramentas externas** – tudo roda dentro do seu código .NET.  
- **Alto desempenho** – API baseada em streams lida eficientemente com arquivos grandes.  
- **Multiplataforma** – funciona no Windows, Linux e macOS.  
- **Conjunto rico de recursos** – suporta criptografia, proteção por senha e atributos de entrada personalizados.  

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- Experiência básica em desenvolvimento .NET.  
- Visual Studio (ou qualquer IDE preferida).  
- Aspose.Zip for .NET instalado – veja a documentação oficial [aqui](https://reference.aspose.com/zip/net/).  
- A biblioteca Aspose.Zip baixada a partir de [este link](https://releases.aspose.com/zip/net/).

## Importar Namespaces

No seu projeto .NET, importe os namespaces que expõem as classes relacionadas a tar:

```csharp
using System;
using Aspose.Zip.Tar;
```

## Como criar um arquivo tar.gz com Aspose.Zip para .NET

### Passo 1: Defina Seu Diretório de Documentos

Primeiro, aponte o código para a pasta que contém os arquivos que você deseja arquivar.

```csharp
string dataDir = "Your Document Directory";
```

> **Dica profissional:** Use `Path.Combine` ao construir caminhos para evitar problemas com separadores específicos da plataforma.

### Passo 2: Inicializar o TarArchive

Crie uma instância de `TarArchive` que armazenará as entradas.

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

### Passo 3: Adicionar Arquivos – o núcleo de “add files to tar”

Dentro do bloco `using`, adicione cada arquivo que você deseja incluir no arquivo.

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Cada chamada `CreateEntry` recebe o **nome da entrada** (como o arquivo aparecerá dentro do tar) e o **caminho do arquivo de origem** no disco.

### Passo 4: Salvar como um Tar Gzipped (como compress files to tar.gz)

Finalmente, escreva o conteúdo do tar em um stream gzip para produzir um compacto `archive.tar.gz`.

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

`SaveGzipped` lida tanto com o empacotamento tar quanto com a compressão gzip em uma única chamada fluente.

## Casos de Uso Comuns

| Cenário | Por que “add files to tar” ajuda |
|----------|------------------------------|
| **Agregação de logs** | Agrupe logs diários em um único arquivo antes de enviá‑los para armazenamento em nuvem. |
| **Pacotes de implantação** | Crie pacotes tar.gz portáteis para servidores Linux a partir de um pipeline de build Windows. |
| **Backup de dados** | Preserve a hierarquia de pastas e metadados mantendo o tamanho do backup baixo. |

## Problemas Comuns e Soluções

- **Erro de arquivo não encontrado** – Certifique‑se de que `dataDir` termina com o separador de caminho apropriado ou use `Path.Combine`.  
- **Arquivos grandes causam pressão de memória** – Use sobrecargas baseadas em stream (`CreateEntry` com um `Stream`) para evitar carregar arquivos inteiros na memória.  
- **Saída gzip está corrompida** – Verifique se o arquivo está fechado (`bloco using`) antes de chamar `SaveGzipped`.  

## Perguntas Frequentes

**Q: O Aspose.Zip para .NET é compatível com todas as aplicações .NET?**  
A: Sim, funciona com projetos .NET Framework, .NET Core e .NET 5/6/7.

**Q: Como posso obter uma licença temporária para Aspose.Zip para .NET?**  
A: Visite a [página de licença temporária](https://purchase.aspose.com/temporary-license/) para solicitar uma licença de avaliação.

**Q: Existem limitações de tamanho de arquivo?**  
A: A biblioteca é otimizada para arquivos grandes; não há limite rígido de tamanho além da memória disponível no sistema.

**Q: Onde posso obter suporte?**  
A: Use o fórum de suporte comunitário [aqui](https://forum.aspose.com/c/zip/37) para ajuda de engenheiros da Aspose e outros desenvolvedores.

**Q: Posso experimentar o Aspose.Zip para .NET gratuitamente?**  
A: Claro — baixe a avaliação gratuita na [página de lançamentos do Aspose Zip](https://releases.aspose.com/zip/net).

## Conclusão

Agora você aprendeu **how to add files to tar**, criar um arquivo tar e comprimi‑lo para **tar.gz** usando Aspose.Zip para .NET. Essa abordagem elimina dependências externas, oferece controle granular sobre o conteúdo do arquivo e escala para grandes conjuntos de dados. Sinta‑se à vontade para explorar recursos adicionais do Aspose.Zip, como criptografia, atributos de entrada personalizados e APIs de streaming para aprimorar ainda mais seu fluxo de trabalho de arquivamento.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2026-01-28  
**Testado com:** Aspose.Zip 24.11 for .NET  
**Autor:** Aspose