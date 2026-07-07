---
date: 2026-06-19
description: Aprenda a compactar arquivos tar, criar arquivos targz e extrair arquivos
  zip protegidos por senha usando Aspose.Zip para .NET – aumentando a eficiência de
  armazenamento e a segurança.
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: Extração de Arquivos e Formatos
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
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
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Como Compactar Arquivos Tar com Aspose.Zip para .NET
url: /pt/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Compactar Arquivos Tar com Aspose.Zip para .NET

## Introdução

Neste guia você descobrirá **como compactar arquivos tar** usando Aspose.Zip para .NET, aprenderá a criar arquivos TarGz e verá como extrair arquivos zip protegidos por senha. O manuseio eficiente de arquivos compactados é uma habilidade essencial para desenvolvedores .NET modernos — seja construindo um serviço de backup, um cliente de armazenamento em nuvem ou um pipeline de processamento de dados, dominar esses formatos reduz custos de armazenamento, acelera transferências e mantém dados sensíveis seguros.

## Respostas Rápidas
- **O que é TarBz2?** Um arquivo compactado que combina o empacotamento TAR com compressão BZIP2 para altas taxas de compressão.  
- **Por que escolher Aspose.Zip para .NET?** Ele oferece uma API única e fluente para criar e extrair diversos formatos de arquivo sem dependências externas.  
- **Posso criar um arquivo TarGz?** Sim – Aspose.Zip suporta TarGz, TarLz, TarXz, TarZ e mais.  
- **Como extraio um arquivo zip protegido por senha?** Use a propriedade `Password` no objeto `ArchiveEntry` ao extrair.  
- **Preciso de licença para uso em produção?** Uma licença comercial é necessária para produção; um teste gratuito está disponível para avaliação.

## O que é Compressão Tar?
Tar (Tape Archive) é um formato contêiner que agrupa múltiplos arquivos e diretórios em um único fluxo sem compressão. Quando você aplica um algoritmo de compressão como BZIP2, GZip, LZMA ou XZ, o resultado é um **arquivo baseado em tar** como `.tar.bz2`, `.tar.gz`, `.tar.lz`, etc. Esses formatos são amplamente suportados em Linux, macOS e Windows, tornando‑os ideais para troca de dados multiplataforma.

## Por que usar Aspose.Zip para .NET para manipular esses formatos?
Aspose.Zip fornece uma **API unificada e sem dependências** que suporta mais de 50 formatos de arquivo e compressão, incluindo TarBz2, TarGz, TarLz, TarXz e TarZ. Ele funciona em Windows, Linux e macOS, e sua arquitetura baseada em streams mantém o uso de memória abaixo de 10 MB mesmo para arquivos de várias centenas de megabytes. A proteção por senha está integrada, permitindo criptografia por entrada sem bibliotecas adicionais.

## Pré‑requisitos
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, ou .NET 5–10.  
- Pacote NuGet Aspose.Zip for .NET instalado (`Install-Package Aspose.Zip`).  
- Familiaridade básica com I/O de arquivos em C# e o sistema de projetos .NET.

## Guia Passo a Passo

### Como Compactar Arquivos Tar – Resposta Direta
`Archive` representa um arquivo de arquivamento e fornece métodos para adicionar entradas e salvá‑lo.  
Crie uma instância de `Archive`, adicione os arquivos que deseja agrupar, defina `CompressionType.BZip2` e chame `Save` com `ArchiveFormat.TarBz2`. A biblioteca grava o contêiner TAR e o comprime em uma única passagem de streaming, de modo que você nunca carrega o arquivo inteiro na memória.

### Etapa 1: Escolha o formato de arquivamento que você precisa
Decida qual formato baseado em tar melhor corresponde ao seu trade‑off entre compressão e velocidade:

- **TarBz2** – Maior taxa de compressão (≈30 % menor que TarGz) porém mais lento.  
- **TarGz** – Bom equilíbrio entre velocidade e tamanho; ideal para a maioria dos cenários de armazenamento em nuvem.  
- **TarLz / TarXz** – Compressão muito alta com velocidade moderada, útil para armazenamento de arquivos.  
- **TarZ** – Formato legado para compatibilidade com ferramentas Unix mais antigas.

### Etapa 2: Crie uma nova instância de `Archive`
`Archive` é o objeto de nível superior que representa um único arquivo de arquivamento na memória.  

A classe `Archive` gerencia o fluxo de empacotamento e compressão, expondo métodos para adicionar entradas e gravar o arquivo final.

### Etapa 3: Adicione arquivos e pastas
Você pode adicionar uma árvore de diretórios inteira com `AddAll` ou arquivos individuais com `AddFile`. Preservar a hierarquia original de pastas é tão simples quanto passar o caminho do diretório base.

### Etapa 4: Defina o tipo de compressão desejado
`CompressionType` enumera os algoritmos suportados.  

`CompressionType` define o algoritmo (BZip2, GZip, LZMA, XZ, etc.) que será aplicado ao fluxo TAR durante a gravação.

### Etapa 5: Salve o arquivamento
`ArchiveFormat` é um conjunto de enumerações (por exemplo, `TarBz2`, `TarGz`) que indica ao gravador qual contêiner e compressão usar.  

Chamando `Save` o arquivo é escrito no disco usando o formato selecionado.

### Etapa 6: Extraindo arquivos com senhas
`ArchiveEntry` representa um único arquivo ou diretório dentro de um arquivamento.  

Para extrair um zip protegido por senha, abra o arquivamento, localize cada `ArchiveEntry`, atribua sua propriedade `Password` e chame `Extract`. Esse modelo de senha por entrada permite proteger arquivos individuais dentro de um único zip.

### Etapa 7: Verifique o resultado
Após a extração, compare os tamanhos dos arquivos e as somas de verificação SHA‑256 para confirmar que a ida‑e‑volta do arquivamento preservou a integridade dos dados.

## Casos de Uso Comuns
- **Utilitários de backup** – Armazene backups diários como `.tar.bz2` para reduzir custos de armazenamento em até 30 %.  
- **Troca de dados multiplataforma** – Formatos baseados em tar são nativamente compreendidos por ferramentas Linux, macOS e Windows.  
- **Distribuição segura** – Atribua senhas a entradas sensíveis, atendendo a requisitos de conformidade sem ferramentas de criptografia adicionais.

## Solução de Problemas & Dicas
- **Arquivos grandes** – Prefira a API de streaming (`Archive.CreateEntryFromFile`) para manter o uso de memória baixo.  
- **Incompatibilidade de senhas** – A senha definida em cada `ArchiveEntry` deve coincidir exatamente; caso contrário, uma `InvalidPasswordException` é lançada.  
- **Nível de compressão** – BZIP2 não expõe níveis personalizados; se precisar de controle mais fino, troque para LZMA (`CompressionType.LZMA`) ou XZ (`CompressionType.XZ`).  

## Perguntas Frequentes

**Q: Como crio um arquivo TarGz?**  
A: Defina `CompressionType.GZip` e use `ArchiveFormat.TarGz` ao chamar `Save`. Isso produz um arquivo `.tar.gz` em uma única etapa.

**Q: Posso extrair um arquivo protegido por senha sem conhecer a senha?**  
A: Não. Cada entrada deve receber a senha correta; a extração falha com `InvalidPasswordException` caso contrário.

**Q: O Aspose.Zip suporta extração de arquivos com senhas diferentes por entrada?**  
A: Sim. Atribua uma senha a cada `ArchiveEntry` individualmente antes de chamar `Extract`.

**Q: Qual formato oferece a melhor compressão?**  
A: TarBz2 normalmente gera o menor tamanho, seguido por TarLz e TarXz. TarGz oferece uma alternativa mais rápida e ainda eficaz.

**Q: Existe um limite para o número de arquivos que posso adicionar a um arquivamento TAR?**  
A: Praticamente nenhum, mas arquivamentos extremamente grandes (>10 GB) podem se beneficiar de divisão em múltiplas partes para facilitar o manuseio.

## Tutoriais de Extração de Arquivos e Formatos
### [File Compressing to TarBz2 with Aspose.Zip for .NET](./compress-to-tar-bz2/)
Aprenda a compactar arquivos no formato TarBz2 em .NET usando Aspose.Zip. Siga nosso guia passo a passo para compressão eficiente de arquivos.  
### [Compressing to TarGz with Aspose.Zip for .NET](./compress-to-tar-gz/)
Explore compressão de arquivos eficiente em .NET com Aspose.Zip. Compacte para TarGz sem esforço.  
### [Compressing to TarLz with Aspose.Zip for .NET](./compress-to-tar-lz/)
Compacte arquivos em .NET com Aspose.Zip de forma simples. Aprenda a criar arquivos TarLz passo a passo.  
### [Compressing to TarXz with Aspose.Zip for .NET](./compress-to-tar-xz/)
Aprenda a compactar arquivos para o formato TarXz em .NET usando Aspose.Zip. Siga nosso guia para armazenamento e transmissão eficientes.  
### [Compressing to TarZ with Aspose.Zip for .NET](./compress-to-tar-z/)
Explore a compressão passo a passo para TarZ usando Aspose.Zip para .NET. Manipulação de arquivos eficiente para seus projetos .NET.  
### [Extracting Archive Entries with Different Passwords in Aspose.Zip for .NET](./extract-archive-different-passwords/)
Aprenda a extrair entradas de arquivamento com senhas diferentes em Aspose.Zip para .NET. Aumente a segurança e flexibilidade em suas aplicações.

---

**Última atualização:** 2026-06-19  
**Testado com:** Aspose.Zip for .NET 24.11  
**Autor:** Aspose

## Tutoriais Relacionados

- [Create tar archive and add files to tar with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [How to compress tar and create TarBz2 with Aspose.Zip for .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Add files to tar and create tarxz archive with Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}