---
date: 2026-02-15
description: Aprenda a compactar vários arquivos em C# com Aspose.Zip para .NET usando
  compressão paralela. Guia passo a passo, exemplos de código e dicas para arquivos
  rápidos e escaláveis.
linktitle: Using Parallelism to Zip Multiple Files in C#
second_title: Aspose.Zip .NET API – zip multiple files c# with Parallel Processing
title: Como zipar vários arquivos em C# usando compressão paralela do Aspose.Zip
url: /pt/net/file-compression/using-parallelism-compress-files/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# compactar vários arquivos c# com compressão paralela Aspose.Zip

## Introdução

Se você precisa **compactar vários arquivos c#** de forma rápida e eficiente, aproveitar o processamento paralelo é o caminho a seguir. Em aplicações .NET modernas, criar grandes arquivos zip pode se tornar um gargalo—especialmente ao lidar com dezenas ou centenas de arquivos. Aspose.Zip para .NET elimina esse ponto crítico ao oferecer **compressão zip paralela** incorporada que distribui o trabalho por todos os núcleos de CPU disponíveis. Neste tutorial vamos percorrer todo o processo: desde a configuração do ambiente até a gravação de um arquivo zip com paralelismo habilitado.

## Respostas Rápidas
- **O que é compressão zip paralela?** Ela comprime vários arquivos ao mesmo tempo, usando múltiplas threads para reduzir o tempo total de processamento.  
- **Qual biblioteca .NET a suporta?** Aspose.Zip para .NET fornece uma API simples para compressão paralela.  
- **Preciso de licença para produção?** Sim—uma licença completa é necessária; uma licença temporária está disponível para testes.  
- **Posso adicionar arquivos ao zip em tempo real?** Absolutamente—use `Archive.CreateEntry` para cada arquivo que desejar incluir.  
- **É compatível com .NET 6/7?** Sim, a API funciona em todas as runtimes .NET modernas.

## O que é compactar vários arquivos c#?
`compactar vários arquivos c#` refere‑se à prática de criar um único arquivo ZIP que contém muitos arquivos individuais, usando código C#. Quando você combina isso com **compressão zip paralela**, a biblioteca processa cada arquivo em uma thread separada, reduzindo drasticamente o tempo necessário para gerar o arquivo final.

## Por que usar Aspose.Zip para compressão paralela?
- **Velocidade:** Aproveita ao máximo CPUs multi‑core, frequentemente entregando compressão 2‑3× mais rápida que abordagens sequenciais.  
- **Escalabilidade:** Lida com grandes lotes de arquivos sem aumento linear no tempo de processamento.  
- **Simplicidade:** API de alto nível abstrai o threading, permitindo que você foque na lógica de negócio.  
- **Flexibilidade:** Funciona com qualquer versão .NET (Framework, Core, .NET 5/6/7) e integra‑se perfeitamente a projetos existentes.

## Pré‑requisitos

Antes de prosseguirmos, certifique‑se de que você tem:

- Conhecimento básico de C# e desenvolvimento .NET.  
- Aspose.Zip para .NET instalado. Você pode baixá‑lo **[aqui](https://releases.aspose.com/zip/net/)**.  
- Uma licença temporária ou completa (a licença temporária é suficiente para este tutorial).  

## Importar Namespaces

Primeiro, traga os namespaces necessários para o seu arquivo C# para que o compilador saiba onde encontrar as classes que você usará.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Etapa 1: Configurar o Diretório de Documentos

Defina a pasta que contém os arquivos que você deseja compactar. Esse caminho é armazenado na variável `dataDir`.

```csharp
string dataDir = "Your Document Directory";
```

## Etapa 2: Inicializar o Processo de Compressão

Abra um novo arquivo ZIP para gravação. A instrução `using` garante que o fluxo de arquivo seja descartado corretamente após a operação.

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## Etapa 3: Ler e Compactar Arquivos em Paralelo

Abra cada arquivo de origem que você pretende adicionar ao arquivo. Neste exemplo trabalhamos com dois textos clássicos, mas você pode **adicionar arquivos ao zip** para qualquer número de documentos.

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## Etapa 4: Criar Entradas no Arquivo

Crie uma instância `Archive` e adicione cada arquivo como uma entrada separada. É aqui que ocorre a etapa de **criar arquivo zip c#**.

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## Etapa 5: Definir o Critério de Paralelismo

Configure a compressão para ser executada em paralelo definindo `ParallelOptions`. O sinalizador `ParallelCompressInMemory` indica ao Aspose.Zip que sempre use processamento paralelo.

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## Etapa 6: Salvar o Arquivo Compactado

Por fim, grave o arquivo no disco com as opções desejadas, incluindo codificação, um comentário e as configurações paralelas definidas anteriormente.

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

> **Dica profissional:** Se você estiver compactando arquivos muito grandes, considere definir `ParallelOptions.MaxDegreeOfParallelism` para um valor menor que o número de processadores lógicos. Isso ajuda a manter seu servidor responsivo sob carga.

### Casos de Uso Comuns

- **Relatórios em lote:** Gere um pacote zip de relatórios CSV diários para sistemas downstream.  
- **Arquivamento de documentos:** Armazene grandes coleções de PDFs, imagens ou logs em um único arquivo para backup.  
- **APIs de exportação de dados:** Retorne um arquivo zip contendo múltiplos arquivos de dados ao cliente em uma única resposta HTTP.

## Problemas Comuns & Dicas

- **Pressão de memória em arquivos enormes:** Em vez de carregar um arquivo inteiro na memória, faça streaming em blocos ou use o modo `ParallelCompressInMemory` seletivamente.  
- **Segurança de threads:** A API Aspose.Zip é thread‑safe para modo paralelo, mas evite modificar o mesmo `FileStream` fora da biblioteca enquanto a compressão estiver em execução.  
- **Ajuste de desempenho:** Experimente `ParallelOptions.MaxDegreeOfParallelism` se precisar limitar o uso de CPU em servidores compartilhados.  

## Perguntas Frequentes

**P: Posso usar Aspose.Zip para .NET junto com outras bibliotecas de compressão?**  
R: Sim, o Aspose.Zip pode coexistir com outras bibliotecas .NET; basta manter seus namespaces distintos.

**P: Existe uma licença temporária disponível para fins de teste?**  
R: Sim, você pode obter uma licença temporária para testes em **[aqui](https://purchase.aspose.com/temporary-license/)**.

**P: Onde posso pedir ajuda se encontrar problemas?**  
R: Visite o **[fórum Aspose.Zip](https://forum.aspose.com/c/zip/37)** para suporte da comunidade e discussões.

**P: Onde encontro mais exemplos de código e documentação detalhada da API?**  
R: Explore a **[documentação Aspose.Zip](https://reference.aspose.com/zip/net/)** para exemplos abrangentes.

**P: Como faço a compra de uma licença completa do Aspose.Zip?**  
R: Você pode adquirir o Aspose.Zip para .NET **[aqui](https://purchase.aspose.com/buy)**.

---

**Última atualização:** 2026-02-15  
**Testado com:** Aspose.Zip 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}