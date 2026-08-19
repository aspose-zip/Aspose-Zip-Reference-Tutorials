---
date: 2026-07-18
description: Aprenda como adicionar pasta ao zip e adicionar arquivos ao zip usando
  Aspose.Zip para .NET. Este guia passo a passo mostra como compactar arquivos com
  FileInfo em projetos ASP.NET.
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: Compactar Arquivos usando FileInfo
og_description: Adicionar pasta ao zip usando Aspose.Zip para .NET. Aprenda como criar
  um arquivo zip, adicionar arquivos ao zip e compactar pastas de forma eficiente
  em ASP.NET.
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: Adicionar Pasta ao Zip – Compactar Arquivos com Aspose.Zip para .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: Adicionar Pasta ao Zip Usando Aspose.Zip para .NET – Compactar Arquivos com
  FileInfo
url: /pt/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Pasta ao Zip Usando Aspose.Zip para .NET

## Introdução

Se você precisar **add folder to zip** programaticamente, o Aspose.Zip para .NET oferece uma API limpa e de alto desempenho que funciona em qualquer .NET (incluindo ASP.NET). Neste tutorial, vamos percorrer a compressão de arquivos com a classe `FileInfo`, mostrar como **add files to zip**, e explicar por que essa abordagem é ideal para projetos .NET modernos. Também cobriremos os passos exatos para **add folder to zip** para que você possa agrupar diretórios inteiros em uma única operação. Vamos começar!

## Respostas Rápidas
- **Qual é a maneira mais fácil de criar um arquivo zip?** Use a classe `Archive` do Aspose.Zip junto com objetos `FileInfo`.  
- **Posso adicionar vários arquivos de uma vez?** Sim – basta criar um `FileInfo` para cada arquivo e chamar `CreateEntry`.  
- **Preciso de uma licença especial para ASP.NET?** É necessária uma licença comercial do Aspose.Zip para produção; um teste gratuito funciona para avaliação.  
- **Quais versões do .NET são suportadas?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 e .NET 5–10.  
- **A API é thread‑safe?** Sim, desde que cada thread trabalhe com sua própria instância `Archive`.

## O que é um Arquivo Zip e Por Que Criar Um?
Um arquivo zip agrupa um ou mais arquivos em um único contêiner comprimido. Isso reduz o espaço de armazenamento, acelera as transferências de rede e simplifica a distribuição. Seja entregando logs, exportando relatórios ou empacotando recursos para um cliente, saber **how to create zip archive** programaticamente é uma habilidade valiosa para qualquer desenvolvedor .NET.

## Por Que Usar Aspose.Zip para Adicionar Arquivos ao Zip?
Aspose.Zip fornece uma solução puramente .NET que elimina dependências externas enquanto oferece aos desenvolvedores controle granular sobre compressão, codificação e segurança. Ele suporta arquivos grandes, proteção por senha e funciona de forma consistente em todas as versões .NET suportadas, tornando‑se uma escolha confiável tanto para aplicações legadas quanto modernas.  

- **Zero dependências externas** – implementação pura .NET.  
- **Controle total sobre o nível de compressão e codificação** (ASCII, UTF‑8, etc.).  
- **Suporta arquivos maiores que 4 GB** e proteção por senha.  
- **API consistente em mais de 50 versões .NET** – do .NET Framework 2.0 até .NET 10.  

## Pré‑requisitos

Antes de mergulharmos no código, certifique‑se de que você tem:

1. **Aspose.Zip for .NET** instalado. Baixe o pacote mais recente na [Aspose.Zip download page](https://releases.aspose.com/zip/net/).  
2. Uma pasta na sua máquina contendo os arquivos que você deseja compactar (por exemplo, `alice29.txt` e `fields.c`).  

## Importar Namespaces

Em qualquer arquivo C# onde você trabalhará com arquivos zip, adicione as seguintes instruções `using`:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Esses namespaces dão acesso à classe `Archive`, opções de salvamento e utilitários padrão de I/O.

## Guia Passo a Passo

### Etapa 1: Configurar Seu Diretório de Documentos

Primeiro, defina a pasta que contém os arquivos de origem. Substitua o placeholder pelo caminho absoluto ou relativo no seu sistema:

```csharp
string dataDir = "Your Document Directory";
```

> **Dica profissional:** Use `Path.Combine` para construir caminhos de forma multiplataforma.

### Etapa 2: Abrir um Arquivo Zip para Escrita

Crie um `FileStream` que aponta para o arquivo zip de saída. O stream é aberto no modo **Create**, que sobrescreve qualquer arquivo existente com o mesmo nome:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Etapa 3: Preparar Objetos `FileInfo` para Cada Arquivo Fonte

`FileInfo` fornece ao Aspose.Zip acesso direto aos arquivos físicos no disco. Crie uma instância por arquivo que você deseja compactar:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Por que usar `FileInfo`?** Ele evita carregar o arquivo inteiro na memória, o que é especialmente útil para arquivos grandes.

### Etapa 4: Criar o Arquivo e Adicionar Entradas

A classe `Archive` é o objeto central do Aspose.Zip que representa um contêiner zip na memória. Instancie um objeto `Archive` e, em seguida, chame `CreateEntry` para cada `FileInfo`. O primeiro argumento é o nome que o arquivo terá dentro do zip, o segundo argumento é o `FileInfo` de origem:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

O método `CreateEntry` adiciona uma nova entrada de arquivo ao arquivo, vinculando o nome da entrada ao `FileInfo` de origem, de modo que os dados sejam transmitidos diretamente do disco quando o arquivo for salvo.

### Etapa 5: Salvar o Arquivo Zip com a Codificação Desejada

Finalmente, persista o arquivo no `FileStream` que você abriu anteriormente. Aqui usamos codificação ASCII para os nomes das entradas, mas você pode mudar para UTF‑8 se seus nomes de arquivo contiverem caracteres não‑ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Quando os blocos `using` terminarem, os streams são fechados automaticamente e o arquivo zip está pronto para uso.

## Como Adicionar Pasta ao Zip Usando Aspose.Zip?

Carregue o diretório de destino, enumere cada arquivo e adicione cada um com um caminho relativo que inclua o nome da pasta. Essa abordagem permite **add folder to zip** sem listar manualmente cada arquivo. Ao preservar a hierarquia de pastas nos nomes das entradas, o arquivo resultante pode ser extraído com a estrutura de diretórios original intacta, o que é essencial para muitos cenários de implantação.

1. Use `DirectoryInfo` para apontar para a pasta que você deseja compactar.  
2. Chame `GetFiles("*", SearchOption.AllDirectories)` para recuperar todos os arquivos de forma recursiva.  
3. Para cada arquivo, crie um `FileInfo` e chame `CreateEntry` com um caminho como `"MyFolder/Report.pdf"`.

## Problemas Comuns & Soluções

| Problema | Causa | Correção |
|----------|-------|----------|
| **Arquivo zip vazio** | `FileInfo` aponta para um caminho inexistente | Verifique `dataDir` e os nomes dos arquivos; use `File.Exists` para checar antes de criar as entradas. |
| **Codificação de nome de arquivo incorreta** | Usando a codificação padrão com nomes não‑ASCII | Defina `Encoding = Encoding.UTF8` em `ArchiveSaveOptions`. |
| **OutOfMemoryException em arquivos grandes** | Carregando o arquivo inteiro na memória | `FileInfo` transmite o arquivo; certifique‑se de que não está lendo o arquivo em um array de bytes em outro lugar. |
| **Permissão negada** | Aplicação não tem permissão de escrita para a pasta de saída | Execute o aplicativo com direitos adequados ou escolha um diretório gravável. |

## Perguntas Frequentes

**Q: Posso adicionar uma pasta inteira a um arquivo zip em uma única chamada?**  
A: Não existe um método de chamada única, mas enumerar arquivos com `DirectoryInfo` e adicionar cada um via `CreateEntry` alcança o mesmo resultado de forma eficiente.

**Q: O Aspose.Zip suporta proteção por senha?**  
A: Sim, você pode definir uma senha no objeto `Archive` antes de salvar para criptografar todo o arquivo.

**Q: Qual o tamanho máximo de um arquivo zip que o Aspose.Zip pode manipular?**  
A: A biblioteca processa arquivos maiores que 4 GB e pode criar arquivos que excedem 10 GB sem carregar todo o arquivo na memória.

**Q: A API é compatível com .NET 6 e .NET 8?**  
A: Absolutamente. Aspose.Zip suporta .NET 5 até .NET 10, cobrindo todas as versões LTS atuais.

**Q: Quais níveis de compressão estão disponíveis?**  
A: Você pode escolher `CompressionLevel.NoCompression`, `Fast`, `Normal` ou `Maximum` para equilibrar velocidade e tamanho.

## Recursos Adicionais

- Baixe o pacote mais recente do Aspose.Zip: [Aspose.Zip download page](https://releases.aspose.com/zip/net/)  
- Compre uma licença para uso em produção: [purchase page](https://purchase.aspose.com/buy)  
- Obtenha ajuda da comunidade: [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)  
- Experimente o Aspose.Zip gratuitamente: [free trial here](https://releases.aspose.com/)  
- Obtenha uma licença temporária para avaliação: [this link](https://purchase.aspose.com/temporary-license/)

## Conclusão

Agora você sabe **how to add folder to zip** e **how to create zip archive** usando Aspose.Zip para .NET, como **add files to zip**, e por que esse método é ideal para ASP.NET e outras aplicações .NET. Experimente diferentes níveis de compressão, codificações e opções de criptografia para adaptar o arquivo exatamente às suas necessidades. Boa compressão!

---

**Última Atualização:** 2026-07-18  
**Testado com:** Aspose.Zip for .NET 24.12 (latest)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Como Compactar Pasta Usando Aspose.Zip para .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [compactar múltiplos arquivos c# – Compressão sem Esforço com Aspose.Zip para .NET](/zip/net/file-compression/compress-multiple-files/)
- [Criar Arquivo Zip .NET – Compressão de Arquivos com Aspose.Zip](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}