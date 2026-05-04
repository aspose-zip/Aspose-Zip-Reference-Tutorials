---
date: 2026-02-28
description: Aprenda como adicionar pasta ao zip e adicionar arquivos ao zip usando
  Aspose.Zip para .NET. Este guia passo a passo mostra como compactar arquivos com
  FileInfo em projetos ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Como adicionar pasta ao ZIP usando Aspose.Zip para .NET – Compactar arquivos
  com FileInfo
url: /pt/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Adicionar Pasta a um Zip Usando Aspose.Zip para .NET

## Introdução

Se você precisa **criar um arquivo zip** programaticamente, o Aspose.Zip para .NET oferece uma API limpa e de alto desempenho que funciona em qualquer aplicação .NET (incluindo ASP.NET). Neste tutorial vamos percorrer a compressão de arquivos com a classe `FileInfo`, mostrar como **adicionar arquivos ao zip**, e explicar por que essa abordagem é ideal para projetos .NET modernos. Também abordaremos como **adicionar pasta ao zip** para que você possa agrupar diretórios inteiros em um único passo. Vamos começar!

## Respostas Rápidas
- **Qual é a maneira mais fácil de criar um arquivo zip?** Use a classe `Archive` do Aspose.Zip junto com objetos `FileInfo`.  
- **Posso adicionar vários arquivos de uma vez?** Sim – basta criar um `FileInfo` para cada arquivo e chamar `CreateEntry`.  
- **Preciso de uma licença especial para ASP.NET?** É necessária uma licença comercial do Aspose.Zip para produção; uma avaliação gratuita funciona para testes.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **A API é thread‑safe?** Sim, desde que cada thread trabalhe com sua própria instância de `Archive`.

## O que é um Arquivo Zip e Por Que Criar Um?
Um arquivo zip agrupa um ou mais arquivos em um único contêiner compactado. Isso reduz o espaço de armazenamento, acelera transferências de rede e simplifica a distribuição. Seja entregando logs, exportando relatórios ou empacotando ativos para um cliente, saber **como criar arquivos zip** programaticamente é uma habilidade valiosa para qualquer desenvolvedor .NET.

## Por Que Usar Aspose.Zip para Adicionar Arquivos ao Zip?
- **Zero dependências externas** – implementação pura em .NET.  
- **Controle total sobre o nível de compressão e codificação** (ASCII, UTF‑8, etc.).  
- **Suporta arquivos grandes** (> 4 GB) e proteção por senha.  
- **API consistente entre .NET Framework, .NET Core e .NET 5+**.

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

### Etapa 3: Preparar Objetos `FileInfo` para Cada Arquivo de Origem

`FileInfo` fornece ao Aspose.Zip acesso direto aos arquivos físicos no disco. Crie uma instância por arquivo que você deseja compactar:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Por que usar `FileInfo`?** Ele evita carregar o arquivo inteiro na memória, o que é especialmente útil para arquivos grandes.

### Etapa 4: Criar o Arquivo e Adicionar Entradas

Instancie um objeto `Archive`, então chame `CreateEntry` para cada `FileInfo`. O primeiro argumento é o nome que o arquivo terá dentro do zip, o segundo argumento é o `FileInfo` de origem:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Etapa 5: Salvar o Arquivo Zip com a Codificação Desejada

Finalmente, persista o arquivo no `FileStream` que você abriu anteriormente. Aqui usamos codificação ASCII para os nomes das entradas, mas você pode mudar para UTF‑8 se seus nomes de arquivo contiverem caracteres não‑ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Quando os blocos `using` terminam, os streams são fechados automaticamente e o arquivo zip está pronto para uso.

## Como Adicionar Pasta ao Zip Usando Aspose.Zip

Se você precisa **adicionar pasta ao zip** em vez de arquivos individuais, o processo é simples:

1. **Enumerar a pasta** com `DirectoryInfo.GetFiles` (e opcionalmente `GetDirectories` para recursão).  
2. **Criar um `FileInfo`** para cada arquivo encontrado.  
3. **Chamar `CreateEntry`** com um caminho relativo que inclua o nome da pasta, por exemplo, `"MyFolder/Report.pdf"`.  

Como a API trabalha com `FileInfo`, você nunca precisa carregar arquivos inteiros na memória, tornando‑a segura para diretórios grandes. Essa técnica também funciona para **zip multiple files asp.net** em cenários onde você gera um conjunto de relatórios dinamicamente e precisa entregá‑lo como um único arquivo.

## Problemas Comuns & Soluções

| Problema | Causa | Correção |
|----------|-------|----------|
| **Arquivo zip vazio** | O `FileInfo` aponta para um caminho inexistente | Verifique `dataDir` e os nomes dos arquivos; use `File.Exists` para checar antes de criar as entradas. |
| **Codificação de nome de arquivo incorreta** | Uso da codificação padrão com nomes não‑ASCII | Defina `Encoding = Encoding.UTF8` em `ArchiveSaveOptions`. |
| **OutOfMemoryException em arquivos grandes** | Carregamento de todo o arquivo na memória | `FileInfo` faz streaming do arquivo; garanta que você não esteja lendo o arquivo em um array de bytes em outro lugar. |
| **Permissão negada** | Aplicação não tem permissão de escrita na pasta de saída | Execute o aplicativo com direitos adequados ou escolha um diretório gravável. |

### Perguntas Frequentes

#### P1: O Aspose.Zip é compatível com todos os tipos de arquivo?

R1: O Aspose.Zip suporta uma ampla variedade de tipos de arquivo, garantindo versatilidade na compressão.

#### P2: Posso usar o Aspose.Zip em projetos comerciais?

R2: Com certeza! Visite nossa [página de compra](https://purchase.aspose.com/buy) para explorar as opções de licenciamento.

#### P3: Como posso obter suporte para o Aspose.Zip?

R3: Participe da nossa comunidade no [fórum do Aspose.Zip](https://forum.aspose.com/c/zip/37) para obter assistência e participar de discussões.

#### P4: Existe uma versão de avaliação gratuita disponível?

R4: Sim, você pode obter sua [versão de avaliação gratuita aqui](https://releases.aspose.com/).

#### Q5: Como posso obter uma licença temporária do Aspose.Zip?

R5: Visite [este link](https://purchase.aspose.com/temporary-license/) para obter informações sobre como obter uma licença temporária.

## Conclusão

Agora você sabe **como adicionar pasta ao zip** e **como criar arquivos zip** usando Aspose.Zip para .NET, como **adicionar arquivos ao zip**, e por que esse método é ideal para ASP.NET e outras aplicações .NET. Experimente diferentes níveis de variação, codificações e opções de criptografia para adaptar o arquivo às suas necessidades específicas. Boa avaliação!

---

**Última atualização:** 28/02/2026
**Testado com:** Aspose.Zip para .NET 24.12 (mais recente)
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}