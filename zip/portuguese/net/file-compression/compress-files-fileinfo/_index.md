---
date: 2025-12-05
description: Aprenda como criar arquivos zip e adicionar arquivos ao zip usando Aspose.Zip
  para .NET. Este guia passo a passo mostra como compactar arquivos com FileInfo em
  projetos ASP.NET.
language: pt
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Como criar um arquivo Zip usando Aspose.Zip para .NET – Compactar arquivos
  com FileInfo
url: /net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Criar Arquivo Zip Usando Aspose.Zip para .NET

## Introdução

Se você precisa **criar um arquivo zip** programaticamente, o Aspose.Zip para .NET oferece uma API limpa e de alto desempenho que funciona em qualquer aplicação .NET (incluindo ASP.NET). Neste tutorial vamos percorrer a compressão de arquivos com a classe `FileInfo`, mostrar como **adicionar arquivos ao zip** e explicar por que essa abordagem é ideal para projetos .NET modernos. Vamos começar!

## Respostas Rápidas
- **Qual a maneira mais fácil de criar um arquivo zip?** Use a classe `Archive` do Aspose.Zip junto com objetos `FileInfo`.  
- **Posso adicionar vários arquivos de uma vez?** Sim – basta criar um `FileInfo` para cada arquivo e chamar `CreateEntry`.  
- **Preciso de licença especial para ASP.NET?** Uma licença comercial do Aspose.Zip é necessária para produção; um trial gratuito funciona para avaliação.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **A API é thread‑safe?** Sim, desde que cada thread trabalhe com sua própria instância de `Archive`.

## O que é um Arquivo Zip e Por Que Criar Um?
Um arquivo zip agrupa um ou mais arquivos em um único contêiner compactado. Isso reduz o espaço de armazenamento, acelera transferências de rede e simplifica a distribuição. Seja entregando logs, exportando relatórios ou empacotando recursos para um cliente, saber **como criar arquivos zip** programaticamente é uma habilidade valiosa para qualquer desenvolvedor .NET.

## Por Que Usar Aspose.Zip para Adicionar Arquivos ao Zip?
- **Zero dependências externas** – implementação pura em .NET.  
- **Controle total sobre nível de compressão e codificação** (ASCII, UTF‑8, etc.).  
- **Suporta arquivos grandes** (> 4 GB) e proteção por senha.  
- **API consistente entre .NET Framework, .NET Core e .NET 5+**.

## Pré‑requisitos

Antes de mergulharmos no código, certifique‑se de que você tem:

1. **Aspose.Zip para .NET** instalado. Baixe o pacote mais recente na [página de download do Aspose.Zip](https://releases.aspose.com/zip/net/).  
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

### Passo 1: Configurar o Diretório de Documentos

Primeiro, defina a pasta que contém os arquivos de origem. Substitua o placeholder pelo caminho absoluto ou relativo no seu sistema:

```csharp
string dataDir = "Your Document Directory";
```

> **Dica profissional:** Use `Path.Combine` para montar caminhos de forma multiplataforma.

### Passo 2: Abrir um Arquivo Zip para Escrita

Crie um `FileStream` que aponta para o arquivo zip de saída. O é aberto no modo **Create**, que sobrescreve qualquer arquivo existente com o mesmo nome:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Passo 3: Preparar Objetos `FileInfo` para Cada Arquivo Fonte

`FileInfo` fornece ao Aspose.Zip acesso direto aos arquivos físicos no disco. Crie uma instância por arquivo que você deseja compactar:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Por que usar `FileInfo`?** Ele evita carregar o arquivo inteiro na memória, o que é especialmente útil para arquivos grandes.

### Passo 4: Criar o Arquivo e Adicionar Entradas

Instancie um objeto `Archive` e, em seguida, chame `CreateEntry` para cada `FileInfo`. O primeiro argumento é o nome que o arquivo terá dentro do zip, o segundo argumento é o `FileInfo` de origem:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Passo 5: Salvar o Arquivo Zip com a Codificação Desejada

Por fim, persista o arquivo no `FileStream` que você abriu anteriormente. Aqui usamos codificação ASCII para os nomes das entradas, mas você pode mudar para UTF‑8 se seus nomes contiverem caracteres não‑ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Quando os blocos `using` terminarem, os streams são fechados automaticamente e o arquivo zip fica pronto para uso.

## Problemas Comuns & Soluções

| Problema | Causa | Solução |
|----------|-------|---------|
| **Arquivo zip vazio** | `FileInfo` aponta para um caminho inexistente | Verifique `dataDir` e os nomes dos arquivos; use `File.Exists` para checar antes de criar as entradas. |
| **Codificação de nome de arquivo incorreta** | Uso da codificação padrão com nomes não‑ASCII | Defina `Encoding = Encoding.UTF8` em `ArchiveSaveOptions`. |
| **OutOfMemoryException em arquivos grandes** | Carregamento do arquivo inteiro na memória | `FileInfo` faz streaming do arquivo; garanta que você não esteja lendo o arquivo para um array de bytes em outro ponto. |
| **Permissão negada** | Aplicação não tem permissão de escrita na pasta de saída | Execute a aplicação com direitos adequados ou escolha um diretório gravável. |

## Perguntas Frequentes

**P: Posso adicionar proteção por senha ao arquivo zip?**  
R: Sim. Após criar o `Archive`, defina `archive.Password = "yourPassword"` antes de chamar `Save`.

**P: É possível atualizar um arquivo zip existente?**  
R: O Aspose.Zip permite abrir um arquivo existente com `Archive.Open` e então adicionar novas entradas.

**P: Como comprimir arquivos em um controlador ASP.NET MVC?**  
R: O mesmo código funciona; apenas certifique‑se de que o stream de saída seja retornado como um `FileResult` ao cliente.

**P: O Aspose.Zip suporta algoritmos de criptografia?**  
R: Ele suporta ZipCrypto padrão e criptografia AES‑256.

**P: E se eu precisar compactar uma pasta recursivamente?**  
R: Percorra `Directory.GetFiles` (e sub‑pastas) e crie um `FileInfo` para cada arquivo, então adicione‑os ao arquivo.

## Seção de FAQ Existente (mantida inalterada)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## Conclusão

Agora você sabe **como criar arquivos zip** usando Aspose.Zip para .NET, como **adicionar arquivos ao zip** e por que esse método é ideal para ASP.NET e outras aplicações .NET. Experimente diferentes níveis de compressão, codificações e opções de criptografia para adequar o arquivo às suas necessidades exatas. Boa compactação!

---

**Última atualização:** 2025-12-05**Testado com:** Aspose.Zip para .NET 24.12 (mais recente)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}