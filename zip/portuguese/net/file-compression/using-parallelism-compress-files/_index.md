---
{}
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# compactar vários arquivos c# com Aspose.Zip Compressão Paralela

## Introdução

Se você precisa **zip multiple files c#** de forma rápida e eficiente, aproveitar o processamento paralelo é o caminho a seguir. Em aplicações .NET modernas, criar arquivos zip grandes pode se tornar um gargalo—especialmente ao lidar com dezenas ou centenas de arquivos. Aspose.Zip para .NET elimina esse ponto crítico ao oferecer **parallel zip compression** incorporada que distribui o trabalho por todos os núcleos de CPU disponíveis. Neste tutorial vamos percorrer todo o processo: desde a configuração do ambiente até a gravação de um arquivo zip com paralelismo habilitado, e também mostraremos como **create zip archive c#** que funciona suavemente no .NET Core.

## Respostas Rápidas
- **What is parallel zip compression?** Compacta vários arquivos ao mesmo tempo, usando múltiplas threads para reduzir o tempo total de processamento.  
- **Which .NET library supports it?** Aspose.Zip para .NET fornece uma API simples para compressão paralela.  
- **Do I need a license for production?** Sim—é necessária uma licença completa; uma licença temporária está disponível para testes.  
- **Can I add files to zip on the fly?** Absolutamente—use `Archive.CreateEntry` para cada arquivo que desejar incluir.  
- **Is it compatible with .NET 6/7?** Sim, a API funciona em todas as runtimes .NET modernas.

## O que é compactar vários arquivos c#?
`zip multiple files c#` refere‑se à prática de criar um único arquivo ZIP que contém muitos arquivos individuais, usando código C#. Quando você combina isso com **parallel zip compression**, a biblioteca processa cada arquivo em uma thread separada, reduzindo drasticamente o tempo necessário para produzir o arquivo final.

## Por que usar Aspose.Zip para compressão paralela?
A compressão paralela permite aproveitar cada núcleo de uma máquina multiprocessador, frequentemente entregando **2‑3× mais rapidez** em comparação com uma abordagem de thread única. Ela também escala de forma elegante: adicionar mais arquivos não aumenta linearmente o tempo de execução, e a API gerencia as threads para você, permitindo que se concentre na lógica de negócio.  

- **Speed:** Utiliza todos os processadores lógicos, reduzindo o tempo de criação do zip em até 70 % em cargas típicas.  
- **Scalability:** Lida com lotes de 500+ arquivos sem aumento proporcional no tempo de CPU.  
- **Simplicity:** Métodos de alto nível ocultam a complexidade de `System.Threading.Tasks`.  
- **Flexibility:** Suporta .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 e .NET 5–10, incluindo .NET 6/7 para serviços nativos em nuvem.

## Pré-requisitos

Antes de começarmos, certifique‑se de que você tem:

- Conhecimento básico de C# e desenvolvimento .NET.  
- Aspose.Zip para .NET instalado. Você pode baixá‑lo **[aqui](https://releases.aspose.com/zip/net/)**.  
- Uma licença temporária ou completa (a licença temporária é suficiente para este tutorial).  

## Importar Namespaces

O namespace `Aspose.Zip` contém todos os tipos necessários para trabalhar com arquivos ZIP.  

```csharp
using Aspose.Zip;
using System.IO;
using System.Threading.Tasks;
```

Primeiro, importe os namespaces necessários no seu arquivo C# para que o compilador saiba onde encontrar as classes que você usará.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Etapa 1: Configurar o Diretório de Documentos

Defina a pasta que contém os arquivos que você deseja compactar. Esse caminho é armazenado na variável `dataDir`, que pode apontar para qualquer localização no disco.

```csharp
string dataDir = @"C:\MyFiles\ToCompress";
```

```csharp
string dataDir = "Your Document Directory";
```

## Etapa 2: Inicializar o Processo de Compressão

Abra um novo arquivo ZIP para gravação. A instrução `using` garante que o fluxo de arquivo seja descartado corretamente após a operação, evitando vazamentos de manipuladores de arquivo.

```csharp
using (FileStream zipStream = new FileStream("output.zip", FileMode.Create))
{
    // Archive instance will be created inside the using block
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## Etapa 3: Ler e Compactar Arquivos em Paralelo

`Parallel.ForEach` executa um laço foreach cujas iterações podem ser executadas simultaneamente em múltiplas threads.  

Abra cada arquivo fonte que você pretende adicionar ao arquivo. Neste exemplo trabalhamos com dois textos clássicos, mas você pode **add files to zip** para qualquer número de documentos. O laço `Parallel.ForEach` distribui o trabalho entre as threads automaticamente.

```csharp
var files = Directory.GetFiles(dataDir);
Parallel.ForEach(files, filePath =>
{
    // Read and add each file inside the parallel loop
});
```

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

A classe `Archive` é o objeto de nível superior do Aspose.Zip que representa o contêiner ZIP que você está construindo.  

`CreateEntry` cria uma nova entrada no arquivo ZIP para um arquivo especificado. Cada chamada a `CreateEntry` adiciona uma nova entrada de arquivo ao ZIP.

```csharp
Archive archive = new Archive(zipStream);
archive.CreateEntry(fileName, fileStream);
```

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## Etapa 5: Definir Critério de Paralelismo

`ParallelOptions` é um tipo .NET que controla como os loops paralelos são executados.  

Configure a compressão para ser executada em paralelo definindo `ParallelOptions`. O sinalizador `ParallelCompressInMemory` indica ao Aspose.Zip para sempre usar processamento paralelo, enquanto `MaxDegreeOfParallelism` permite limitar o número de threads concorrentes.

```csharp
ParallelOptions options = new ParallelOptions
{
    MaxDegreeOfParallelism = Environment.ProcessorCount // use all cores
};
archive.ParallelCompressInMemory = true;
archive.ParallelOptions = options;
```

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## Etapa 6: Salvar o Arquivo Compactado

Por fim, grave o arquivo no disco com as opções desejadas, incluindo codificação, um comentário e as configurações paralelas definidas anteriormente. O método `Save` finaliza o arquivo ZIP.

```csharp
archive.Save();
```

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

> **Pro tip:** Se você estiver compactando arquivos muito grandes, considere definir `ParallelOptions.MaxDegreeOfParallelism` para um valor menor que o número de processadores lógicos. Isso ajuda a manter seu servidor responsivo sob carga.

### Casos de Uso Comuns

- **Relatórios em lote:** Gere um pacote zip de relatórios CSV diários para sistemas downstream.  
- **Arquivamento de documentos:** Armazene grandes coleções de PDFs, imagens ou logs em um único arquivo para backup.  
- **APIs de exportação de dados:** Retorne um arquivo zip contendo múltiplos arquivos de dados para um cliente em uma única resposta HTTP.  

## Problemas Comuns & Dicas

- **Pressão de memória em arquivos enormes:** Em vez de carregar um arquivo inteiro na memória, faça streaming do arquivo em blocos ou use o modo `ParallelCompressInMemory` seletivamente.  
- **Segurança de threads:** A API Aspose.Zip é thread‑safe para modo paralelo, mas evite modificar o mesmo `FileStream` fora da biblioteca enquanto a compressão está em execução.  
- **Ajuste de desempenho:** Experimente `ParallelOptions.MaxDegreeOfParallelism` se precisar limitar o uso de CPU em servidores compartilhados.  

## Perguntas Frequentes

**Q: Posso usar Aspose.Zip para .NET junto com outras bibliotecas de compressão?**  
**A:** Sim, o Aspose.Zip pode coexistir com outras bibliotecas .NET; basta manter seus namespaces distintos.

**Q: Existe uma licença temporária disponível para fins de teste?**  
**A:** Sim, você pode obter uma licença temporária para teste **[aqui](https://purchase.aspose.com/temporary-license/)**.

**Q: Onde posso pedir ajuda se encontrar problemas?**  
**A:** Visite o **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)** para suporte da comunidade e discussões.

**Q: Onde encontro mais exemplos de código e documentação detalhada da API?**  
**A:** Explore a **[Aspose.Zip documentation](https://reference.aspose.com/zip/net/)** para exemplos abrangentes.

**Q: Como compro uma licença completa do Aspose.Zip?**  
**A:** Você pode comprar o Aspose.Zip para .NET **[aqui](https://purchase.aspose.com/buy)**.

---

**Last Updated:** 2026-06-09  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [compactar vários arquivos c# – Compressão sem Esforço com Aspose.Zip para .NET](/zip/net/file-compression/compress-multiple-files/)
- [Como Criar Arquivo Zip e Adicionar Arquivo ao Zip Usando Aspose.Zip para .NET](/zip/net/file-compression/compress-single-file/)
- [Compactar Vários Arquivos com Criptografia no Aspose.Zip .NET](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}