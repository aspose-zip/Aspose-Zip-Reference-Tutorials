---
date: 2026-06-19
description: Aprenda como adicionar vários arquivos ao tar e compactar arquivos em
  tar.gz usando Aspose.Zip para .NET – uma maneira rápida e multiplataforma de criar
  arquivos TarGz.
keywords:
- add multiple files to tar
- compress files to tar.gz
- Aspose.Zip .NET
- tar archive .NET
- tar.gz creation
linktitle: Adicionar arquivos ao tar
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to add multiple files to tar and compress files to tar.gz
    using Aspose.Zip for .NET – a fast, cross‑platform way to build TarGz archives.
  headline: Add multiple files to tar and create tar.gz archive with Aspose.Zip for
    .NET
  type: TechArticle
- questions:
  - answer: Yes, it works with .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, and .NET
      5–10 projects.
    question: Is Aspose.Zip for .NET compatible with all .NET applications?
  - answer: Visit the [temporary‑license page](https://purchase.aspose.com/temporary-license/)
      to request a trial license.
    question: How can I obtain a temporary license for Aspose.Zip for .NET?
  - answer: The library is optimized for large files; there is no hard size limit
      other than the available system memory, and it can stream archives larger than
      100 GB.
    question: Are there any file‑size limitations?
  - answer: Use the community‑driven support forum [here](https://forum.aspose.com/c/zip/37)
      for help from Aspose engineers and other developers.
    question: Where can I get support?
  - answer: Absolutely—download the free trial from the [Aspose Zip releases page](https://releases.aspose.com/zip/net/).
    question: Can I try Aspose.Zip for .NET for free?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Adicionar vários arquivos ao tar e criar um arquivo tar.gz com Aspose.Zip para
  .NET
url: /pt/net/archive-extraction-and-formats/compress-to-tar-gz/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar vários arquivos a tar e criar arquivo tar.gz com Aspose.Zip para .NET

## Introdução

Em aplicações .NET modernas, **adicionar vários arquivos a tar** e depois **compactar arquivos em tar.gz** é uma necessidade frequente — seja para agrupar arquivos de log, preparar dados para armazenamento em nuvem ou criar pacotes de implantação para servidores Linux. Aspose.Zip para .NET fornece uma API limpa e de alto desempenho que permite construir um arquivo tar, adicionar qualquer número de arquivos e, opcionalmente, compactá‑lo em um arquivo tar.gz — tudo sem ferramentas externas. Neste guia percorreremos todo o fluxo de trabalho, desde a configuração do projeto até um `archive.tar.gz` pronto para produção.

## Respostas Rápidas
- **Qual biblioteca devo usar?** Aspose.Zip para .NET – suporta tar, tar.gz, zip e muitos outros formatos.  
- **Como adicionar vários arquivos a tar?** Chame `TarArchive.CreateEntry` para cada arquivo que deseja incluir.  
- **Posso compactar diretamente para tar.gz?** Sim — invoque `SaveGzipped` na instância `TarArchive`.  
- **Preciso de uma licença para produção?** É necessária uma licença válida da Aspose para uso não‑trial.  
- **Quais versões do .NET são suportadas?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 e .NET 5–10.

## O que é “adicionar vários arquivos a tar”?

Adicionar vários arquivos a um arquivo tar significa agrupar vários arquivos (e opcionalmente diretórios) em um único contêiner não compactado, preservando sua hierarquia e metadados originais. O arquivo `.tar` resultante pode ser posteriormente compactado com gzip para produzir um arquivo `tar.gz`, amplamente usado para distribuição e backup.

## Por que usar Aspose.Zip para compactar arquivos em tar.gz?

Aspose.Zip lida com todo o processo de tar e gzip na memória, eliminando a necessidade de utilitários nativos. Ele pode processar **arquivos de até 500 GB** sem carregar o arquivo inteiro na memória, graças à sua arquitetura baseada em streams. A biblioteca suporta **mais de 50 formatos de entrada e saída**, funciona em Windows, Linux e macOS, e oferece recursos adicionais como criptografia, proteção por senha e atributos de entrada personalizados — tudo a partir de uma única API .NET.

## Pré‑requisitos

- Experiência básica em desenvolvimento .NET.  
- Visual Studio (ou qualquer IDE preferida).  
- Aspose.Zip para .NET instalado – veja a documentação oficial [aqui](https://reference.aspose.com/zip/net/).  
- A biblioteca Aspose.Zip baixada a partir de [este link](https://releases.aspose.com/zip/net/).

## Importar Namespaces

No seu projeto .NET, importe os namespaces que expõem as classes relacionadas a tar:

```csharp
using System;
using Aspose.Zip.Tar;
```

## Como adicionar vários arquivos a tar usando Aspose.Zip para .NET

Usando Aspose.Zip, primeiro você carrega a pasta de origem, instancia um `TarArchive` e, em seguida, itera sobre cada arquivo, chamando `CreateEntry` para adicioná‑lo ao arquivo. Após todas as entradas serem adicionadas, você invoca `SaveGzipped` para gerar um `archive.tar.gz` compactado. Todo esse fluxo requer apenas algumas linhas de código .NET claro e tipado.

### Passo 1: Defina o Diretório do Documento

Defina a pasta que contém os arquivos que você deseja arquivar.

```csharp
string dataDir = "Your Document Directory";
```

> **Dica profissional:** Use `Path.Combine` ao construir caminhos para evitar problemas com separadores específicos da plataforma.  
> O método `Path.Combine` une com segurança nomes de diretórios e arquivos usando o separador apropriado para o sistema operacional.

### Passo 2: Criar um Arquivo TarGz

Agora criaremos o arquivo tar, adicionaremos entradas e o compactaremos em um fluxo fluente.

#### 2.1 Inicializar o TarArchive

A classe `TarArchive` é o objeto de nível superior do Aspose.Zip que representa um contêiner tar na memória. Instanciá‑lo prepara um arquivo vazio pronto para receber entradas.

```csharp
using (TarArchive archive = new TarArchive())
{
    // Entries will be added inside this block.
}
```

#### 2.2 Adicionar Arquivos – o núcleo de “adicionar vários arquivos a tar”

`CreateEntry` cria uma nova entrada dentro do arquivo tar. O método recebe o **nome da entrada** (o caminho dentro do tar) e o **caminho do arquivo de origem** no disco. Chame‑o repetidamente para adicionar quantos arquivos forem necessários.

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Cada chamada a `CreateEntry` adiciona um único arquivo; você pode percorrer uma coleção de diretórios para adicionar dezenas ou centenas de arquivos com código mínimo.

#### 2.3 Salvar como Tar Gzipped (como compactar arquivos em tar.gz)

`SaveGzipped` grava o conteúdo do tar em um fluxo gzip, produzindo um arquivo compacto `archive.tar.gz` pronto para distribuição ou armazenamento.

```csharp
archive.SaveGzipped(dataDir + "archive.tar.gz");
```

O método lida automaticamente com cabeçalhos e rodapés gzip, de modo que você obtém um tar.gz compatível com os padrões sem etapas adicionais.

## Casos de Uso Comuns

| Cenário | Por que “adicionar vários arquivos a tar” ajuda |
|----------|----------------------------------------|
| **Agregação de logs** | Agrupar logs diários em um único arquivo antes de enviá‑los para armazenamento em nuvem. |
| **Pacotes de implantação** | Criar pacotes tar.gz portáteis para servidores Linux a partir de um pipeline de build Windows. |
| **Backup de dados** | Preservar a hierarquia de pastas e metadados enquanto mantém o tamanho do backup baixo. |

## Problemas Comuns e Soluções

- **Erro de arquivo não encontrado** – Garanta que `dataDir` termine com o separador de caminho apropriado ou use `Path.Combine`.  
- **Arquivos grandes causam pressão de memória** – Use a sobrecarga baseada em stream de `CreateEntry` (`CreateEntry(string entryName, Stream source)`) para evitar carregar arquivos inteiros na memória.  
- **Saída gzip está corrompida** – Verifique se o `TarArchive` foi descartado (via um bloco `using`) antes de chamar `SaveGzipped`.  

## Perguntas Frequentes

**Q: O Aspose.Zip para .NET é compatível com todas as aplicações .NET?**  
A: Sim, funciona com .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 e projetos .NET 5–10.

**Q: Como posso obter uma licença temporária para Aspose.Zip para .NET?**  
A: Visite a [página de licença temporária](https://purchase.aspose.com/temporary-license/) para solicitar uma licença de avaliação.

**Q: Existem limitações de tamanho de arquivo?**  
A: A biblioteca é otimizada para arquivos grandes; não há limite rígido de tamanho além da memória do sistema disponível, e pode fazer streaming de arquivos maiores que 100 GB.

**Q: Onde posso obter suporte?**  
A: Use o fórum de suporte comunitário [aqui](https://forum.aspose.com/c/zip/37) para ajuda de engenheiros da Aspose e outros desenvolvedores.

**Q: Posso experimentar o Aspose.Zip para .NET gratuitamente?**  
A: Claro — baixe a versão de avaliação gratuita na [página de lançamentos do Aspose Zip](https://releases.aspose.com/zip/net/).

## Conclusão

Agora você sabe como **adicionar vários arquivos a tar**, criar um arquivo tar e **compactar arquivos em tar.gz** usando Aspose.Zip para .NET. Essa abordagem elimina dependências externas, dá controle total sobre o conteúdo do arquivo e escala para conjuntos de dados muito grandes. Explore recursos adicionais como criptografia, atributos de entrada personalizados e APIs de streaming para aprimorar ainda mais seu fluxo de arquivamento.

---

**Última atualização:** 2026-06-19  
**Testado com:** Aspose.Zip 24.11 for .NET  
**Autor:** Aspose

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Como compactar vários arquivos tar com Aspose.Zip para .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-lz/)
- [Adicionar arquivos a tar e criar arquivo tarxz com Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)
- [Como compactar tar e criar TarBz2 com Aspose.Zip para .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}