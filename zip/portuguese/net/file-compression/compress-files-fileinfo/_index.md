---
date: 2026-02-05
description: Aprenda a compactar vários arquivos em C# e criar um arquivo zip .NET
  usando Aspose.Zip. Este guia passo a passo mostra como comprimir arquivos com FileInfo
  em projetos ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Como compactar vários arquivos em C# usando Aspose.Zip para .NET
url: /pt/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como compactar vários arquivos c# usando Aspise.Zip para .NET

## Introdução

Se você precisa **compactar vários arquivos c#** programaticamente, o Aspose.Zip para .NET oferece uma API limpa e de alto desempenho que funciona em qualquer .NET (incluindo ASP.NET). Neste tutorial, vamos percorrer a compressão de arquivos com a classe `FileInfo`, mostrar como **adicionar arquivos ao zip** e explicar por que essa abordagem é ideal para projetos .NET modernos. Vamos começar!

## Respostas Rápidas
- **Qual é a maneira mais fácil de criar um arquivo zip?** Use a classe `Archive` do Aspose.Zip junto com objetos `FileInfo`.  
- **Posso adicionar vários arquivos de uma vez?** Sim – basta criar um `FileInfo` para cada arquivo e chamar `CreateEntry`.  
- **Preciso de uma licença especial para ASP.NET?** Uma licença comercial do Aspose.Zip é necessária para produção; um teste gratuito funciona para avaliação.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **A API é thread‑safe?** Sim, desde que cada thread trabalhe com sua própria instância `Archive`.  
- **Como compactar arquivos c# sem carregá‑los na memória?** Use objetos `FileInfo` – eles transmitem os dados diretamente.  

## Como compactar vários arquivos c#
Um arquivo zip agrupa um ou mais arquivos em um único contêiner compactado. Isso reduz o espaço de armazenamento, acelera as transferências de rede e simplifica a distribuição. Seja entregando logs, exportando relatórios ou empacotando recursos para um cliente, saber **como compactar arquivos c#** programaticamente é uma habilidade valiosa para qualquer desenvolvedor .NET.

## Por que usar Aspose.Zip para adicionar arquivos ao Zip?
- **Zero dependências externas** – implementação pura em .NET.  
- **Controle total sobre o nível de compressão e codificação** (ASCII, UTF‑8, etc.).  
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

## Guia passo a passo

### Etapa 1: Configurar seu diretório de documentos

Primeiro, defina a pasta que contém os arquivos de origem. Substitua o placeholder pelo caminho absoluto ou relativo no seu sistema:

```csharp
string dataDir = "Your Document Directory";
```

> **Dica profissional:** Use `Path.Combine` para construir caminhos de forma multiplataforma.

### Etapa 2: Abrir um arquivo Zip para gravação

Crie um `FileStream` que aponta para o arquivo zip de saída. O stream é aberto no modo **Create**, que sobrescreve qualquer arquivo existente com o mesmo nome:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Etapa 3: Preparar objetos `FileInfo` para cada arquivo de origem

`FileInfo` fornece ao Aspose.Zip acesso direto aos arquivos físicos no disco. Crie uma instância por arquivo que você deseja compactar:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Por que usar `FileInfo`?** Ele evita carregar o arquivo inteiro na memória, o que é especialmente útil para arquivos grandes.

### Etapa 4: Criar o Archive e adicionar entradas

Instancie um objeto `Archive`, então chame `CreateEntry` para cada `FileInfo`. O primeiro argumento é o nome que o arquivo terá dentro do zip, o segundo argumento é o `FileInfo` de origem:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Etapa 5: Salvar o Archive Zip com a codificação desejada

Finalmente, persista o archive no `FileStream` que você abriu anteriormente. Aqui usamos codificação ASCII para os nomes das entradas, mas você pode mudar para UTF‑8 se seus nomes de arquivo contiverem caracteres não‑ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Quando os blocos `using` terminarem, os streams são fechados automaticamente e o arquivo zip está pronto para uso.

## Problemas comuns e soluções

| Problema | Causa | Solução |
|----------|-------|---------|
| **Arquivo zip vazio** | `FileInfo` aponta para um caminho inexistente | Verifique `dataDir` e os nomes dos arquivos; use `File.Exists` para checar antes de criar as entradas. |
| **Codificação de nome de arquivo incorreta** | Usando a codificação padrão com nomes não‑ASCII | Defina `Encoding = Encoding.UTF8` em `ArchiveSaveOptions`. |
| **OutOfMemoryException em arquivos grandes** | Carregando o arquivo inteiro na memória | `FileInfo` transmite o arquivo; certifique‑se de que não está lendo o arquivo em um array de bytes em outro lugar. |
| **Permissão negada** | Aplicação não tem permissão de escrita na pasta de saída | Execute o aplicativo com direitos adequados ou escolha um diretório gravável. |

## Perguntas Frequentes

**Q: Posso adicionar proteção por senha ao arquivo zip?**  
A: Sim. Após criar o `Archive`, defina `archive.Password = "yourPassword"` antes de chamar `Save`.

**Q: É possível atualizar um arquivo zip existente?**  
A: O Aspose.Zip suporta abrir um archive existente com `Archive.Open` e então adicionar novas entradas.

**Q: Como compactar arquivos em um controlador ASP.NET MVC?**  
A: O mesmo código funciona; apenas certifique‑se de que o stream de saída seja retornado como um `FileResult` ao cliente.

**Q: O Aspose.Zip suporta algoritmos de criptografia?**  
A: Ele suporta criptografia padrão ZipCrypto e AES‑256.

**Q: E se eu precisar compactar uma pasta recursivamente?**  
A: Percorra `Directory.GetFiles` (e subpastas) e crie um `FileInfo` para cada arquivo, então adicione‑os ao archive.

## Existing FAQ Section (kept unchanged)

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

Agora você sabe **como compactar vários arquivos c#** usando Aspose.Zip para .NET, como **adicionar arquivos ao zip**, e por que esse método é ideal para ASP.NET e outras aplicações .NET. Experimente diferentes níveis de compressão, codificações e opções de criptografia para adaptar o archive às suas necessidades exatas. Boa compactação!

---

**Última atualização:** 2026-02-05  
**Testado com:** Aspose.Zip for .NET 24.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}