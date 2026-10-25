---
date: 2026-10-25
description: Aprenda como extrair a senha de zip e definir o algoritmo de compressão
  ao compactar arquivos tar com Aspose.Zip para .NET, aumentando a eficiência de armazenamento
  e a segurança.
keywords:
- extract zip password
- set compression algorithm
- add folder archive
- tarbz2 vs targz
- aspose zip compress
lastmod: 2026-10-25
linktitle: Extração de Arquivos e Formatos
og_description: Aprenda como extrair a senha de zip e definir o algoritmo de compressão
  ao compactar arquivos tar com Aspose.Zip para .NET, aumentando a eficiência de armazenamento
  e a segurança.
og_image_alt: 'Developer guide: extract zip password and compress tar archives using
  Aspose.Zip for .NET'
og_title: Extrair senha de zip e compactar arquivos tar com Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  headline: Extract zip password and compress tar files with Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  name: Extract zip password and compress tar files with Aspose.Zip
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: Extrair senha de zip e compactar arquivos tar com Aspose.Zip
url: /pt/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrair senha de zip e compactar arquivos tar com Aspose.Zip

## Introdução

Neste guia você descobrirá técnicas de **extrair senha de zip**, aprenderá como definir o algoritmo de compressão ao criar arquivos baseados em tar e verá como construir TarGz, TarBz2 e outros formatos com Aspose.Zip para .NET. Seja você quem esteja construindo um serviço de backup, um cliente de armazenamento em nuvem ou um pipeline de processamento de dados, dominar essas operações reduz custos de armazenamento, acelera transferências e protege arquivos sensíveis.

## Respostas rápidas
- **O que é TarBz2?** Um arquivo compactado que combina o empacotamento TAR com compressão BZIP2 para altas taxas de compressão.  
- **Por que escolher Aspose.Zip para .NET?** Ele suporta mais de 50 formatos de arquivo e compressão, funciona em Windows, Linux e macOS, e mantém o uso de memória abaixo de 10 MB para arquivos de várias centenas de megabytes.  
- **Posso criar um arquivo TarGz?** Sim – Aspose.Zip oferece TarGz, TarLz, TarXz, TarZ e mais.  
- **Como extraio um arquivo zip protegido por senha?** Defina a propriedade `Password` em cada `ArchiveEntry` antes de chamar `Extract`.  
- **Preciso de licença para uso em produção?** Uma licença comercial é necessária para produção; um teste gratuito está disponível para avaliação.

## O que é compressão tar?

A compressão tar combina o contêiner TAR com um algoritmo de compressão como BZIP2, GZIP, LZMA ou XZ. O resultado é um único arquivo (por exemplo, `.tar.gz`, `.tar.bz2`) que pode ser descompactado no Linux, macOS e Windows. Ele preserva a hierarquia original de diretórios, permite extração de acesso aleatório e é amplamente suportado por ferramentas de linha de comando e bibliotecas de programação, tornando‑o ideal para distribuição multiplataforma e armazenamento arquivístico.

## Por que usar Aspose.Zip para .NET para lidar com esses formatos?

Aspose.Zip fornece uma API unificada, sem dependências, que suporta **mais de 50** formatos de arquivo e compressão, incluindo todos os principais tipos baseados em tar. Sua arquitetura de streaming processa arquivos maiores que 10 GB mantendo o uso de RAM abaixo de 10 MB, o que o torna ideal para cargas de trabalho de servidor de alta taxa de transferência.  

**Resposta direta:** Você usa Aspose.Zip porque ele permite criar, compactar e extrair arquivos baseados em tar e arquivos zip protegidos por senha com uma única API fluente, sem ferramentas externas, enquanto manipula arquivos de vários gigabytes de forma eficiente em memória.

## Pré-requisitos
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 ou .NET 5–10.  
- Pacote NuGet Aspose.Zip para .NET (`Install-Package Aspose.Zip`).  
- Familiaridade básica com I/O de arquivos em C# e o sistema de projetos .NET.

## Guia passo a passo

### Como compactar arquivos tar – resposta direta
Crie uma instância `Archive`, adicione os arquivos que deseja agrupar, defina `CompressionType.BZip2` (ou outro algoritmo) e chame `Save` com `ArchiveFormat.TarBz2`. A biblioteca grava o contêiner TAR e o compacta em uma única passagem de streaming, de modo que você nunca carrega o arquivo inteiro na memória.

### Etapa 1: Escolha o formato de arquivo que você precisa
Decida qual formato baseado em tar melhor corresponde ao seu trade‑off entre compressão e velocidade:

- **TarBz2** – Maior taxa de compressão (≈30 % menor que TarGz) mas mais lenta.  
- **TarGz** – Bom equilíbrio entre velocidade e tamanho; ideal para a maioria dos cenários de armazenamento em nuvem.  
- **TarLz / TarXz** – Compressão muito alta com velocidade moderada, útil para armazenamento arquivístico.  
- **TarZ** – Formato legado para compatibilidade com ferramentas Unix mais antigas.

### Etapa 2: Crie uma nova instância `Archive`
`Archive` representa um único arquivo de arquivo e fornece métodos para adicionar entradas e salvar o arquivo.  

A classe `Archive` gerencia o fluxo de empacotamento e compressão, expondo métodos para adicionar entradas e gravar o arquivo final.

### Etapa 3: Adicione arquivos e pastas
Você pode adicionar uma árvore de diretórios inteira com `AddAll` ou adicionar arquivos individuais com `AddFile`.  

`AddAll` adiciona uma árvore de diretórios inteira ao arquivo, preservando sua estrutura.  
`AddFile` adiciona um único arquivo ao arquivo. Preservar a hierarquia original de pastas é tão simples quanto passar o caminho do diretório base.

### Etapa 4: Defina o tipo de compressão desejado
O enum `CompressionType` especifica o algoritmo de compressão aplicado ao fluxo TAR.  

`CompressionType` enumera os algoritmos suportados (BZip2, GZip, LZMA, XZ, etc.) que serão aplicados durante a gravação.

### Etapa 5: Salve o arquivo
O enum `ArchiveFormat` seleciona a combinação de contêiner e compressão para o arquivo de saída.  

Chamar `Save` grava o arquivo no disco usando o formato selecionado.

### Etapa 6: Extraindo arquivos com senhas
`ArchiveEntry` representa uma única entrada de arquivo ou diretório dentro de um arquivo.  

Para extrair um zip protegido por senha, abra o arquivo, localize cada `ArchiveEntry`, atribua sua propriedade `Password` e chame `Extract`. A propriedade `Password` define a senha de descriptografia para uma entrada zip. Esse modelo de senha por entrada permite proteger arquivos individuais dentro de um único zip.

### Etapa 7: Verifique o resultado
Após a extração, compare os tamanhos dos arquivos e as somas de verificação SHA‑256 para confirmar que o ciclo de ida‑e‑volta preservou a integridade dos dados.

## Casos de uso comuns
- **Utilitários de backup** – Armazene backups diários como `.tar.bz2` para reduzir custos de armazenamento em até 30 %.  
- **Troca de dados multiplataforma** – Formatos baseados em tar são compreendidos nativamente por ferramentas Linux, macOS e Windows.  
- **Distribuição segura** – Atribua senhas a entradas sensíveis, atendendo a requisitos de conformidade sem ferramentas de criptografia adicionais.

## Solução de problemas e dicas
- **Arquivos grandes** – Use a API de streaming (`Archive.CreateEntryFromFile`) para manter o uso de memória baixo.  
- **Incompatibilidade de senhas** – A senha definida em cada `ArchiveEntry` deve coincidir exatamente; caso contrário, uma `InvalidPasswordException` é lançada.  
- **Nível de compressão** – BZIP2 não expõe níveis personalizados; se precisar de controle mais fino, troque para LZMA (`CompressionType.LZMA`) ou XZ (`CompressionType.XZ`).  

## Perguntas frequentes

**Q: Como crio um arquivo TarGz?**  
A: Defina `CompressionType.GZip` e use `ArchiveFormat.TarGz` ao chamar `Save`. Isso produz um arquivo `.tar.gz` em uma única etapa.

**Q: Posso extrair um arquivo protegido por senha sem conhecer a senha?**  
A: Não. Cada entrada deve receber a senha correta; a extração falha com uma `InvalidPasswordException` caso contrário.

**Q: O Aspose.Zip suporta a extração de arquivos com senhas diferentes por entrada?**  
A: Sim. Atribua uma senha a cada `ArchiveEntry` individualmente antes de chamar `Extract`.

**Q: Qual formato oferece a melhor compressão?**  
A: TarBz2 normalmente gera o menor tamanho, seguido por TarLz e TarXz. TarGz oferece uma alternativa mais rápida e ainda eficaz.

**Q: Existe um limite para o número de arquivos que posso adicionar a um arquivo TAR?**  
A: Praticamente nenhum, mas arquivos extremamente grandes (>10 GB) podem se beneficiar de serem divididos em várias partes para facilitar o manuseio.

## Tutoriais de extração de arquivos e formatos

### [Compressão de arquivos para TarBz2 com Aspose.Zip para .NET](./compress-to-tar-bz2/)
Aprenda como compactar arquivos para o formato TarBz2 em .NET usando Aspose.Zip. Siga nosso guia passo a passo para compressão eficiente de arquivos.  
### [Compressão para TarGz com Aspose.Zip para .NET](./compress-to-tar-gz/)
Explore compressão eficiente de arquivos em .NET com Aspose.Zip. Compacte para TarGz sem esforço.  
### [Compressão para TarLz com Aspose.Zip para .NET](./compress-to-tar-lz/)
Compacte arquivos em .NET com Aspose.Zip de forma simples. Aprenda a criar arquivos TarLz passo a passo.  
### [Compressão para TarXz com Aspose.Zip para .NET](./compress-to-tar-xz/)
Aprenda a compactar arquivos para o formato TarXz em .NET usando Aspose.Zip. Siga nosso guia para armazenamento e transmissão eficientes.  
### [Compressão para TarZ com Aspose.Zip para .NET](./compress-to-tar-z/)
Explore a compressão passo a passo para TarZ usando Aspose.Zip para .NET. Manipulação de arquivos eficiente para seus projetos .NET.  
### [Extraindo entradas de arquivo com senhas diferentes no Aspose.Zip para .NET](./extract-archive-different-passwords/)
Aprenda como extrair entradas de arquivo com senhas diferentes no Aspose.Zip para .NET. Aumente a segurança e flexibilidade em suas aplicações.

## Tutoriais relacionados

- [Criar arquivo tar e adicionar arquivos ao tar com Aspose.Zip para .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Como compactar tar e criar TarBz2 com Aspose.Zip para .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Adicionar arquivos ao tar e criar arquivo tarxz com Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

---

**Última atualização:** 2026-10-25  
**Testado com:** Aspose.Zip para .NET 24.11  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}