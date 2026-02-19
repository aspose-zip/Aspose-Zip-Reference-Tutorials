---
date: 2026-02-07
description: Aprenda a compactar pastas no .NET comprimindo um diretório em zip e
  extraindo-o de volta. Este guia mostra como compactar pastas usando Aspose.Zip para
  .NET.
linktitle: Decompressing a Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Como Compactar Pasta – Comprimir Diretório com Aspose.Zip
url: /pt/net/directory-and-folder-compression/decompress-folder/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Compactar uma Pasta – Comprimir Diretório com Aspose.Zip para .NET

Se você está procurando uma solução clara de **como compactar uma pasta** em uma aplicação .NET, chegou ao lugar certo. Neste tutorial vamos percorrer todo o fluxo—primeiro **compactaremos o diretório em zip**, depois mostraremos os passos exatos para **extrair zip para diretório** (ou seja, como descompactar uma pasta). Ao final, você terá um padrão reutilizável e programático para operações de zip de pastas que funciona em .NET Framework, .NET Core e .NET 5/6+.

## Respostas Rápidas
- **O que significa “compactar diretório em zip”?** Significa transformar o conteúdo de uma pasta em um único arquivo .zip.  
- **Como eu extraio zip para diretório?** Use o método `Archive.ExtractToDirectory` conforme mostrado no guia.  
- **Quais versões do .NET são suportadas?** Todas as versões modernas do .NET Framework, .NET Core e .NET 5/6+.  
- **É necessária uma licença para produção?** Sim, uma licença comercial do Aspose.Zip é necessária para uso que não seja de avaliação.  
- **Posso automatizar isso em pipelines CI/CD?** Absolutamente—basta adicionar o mesmo código aos seus scripts de build.

## O que é “como compactar uma pasta”?
**Como compactar uma pasta** simplesmente significa pegar cada arquivo e sub‑pasta dentro de um diretório e empacotá‑los em um único arquivo compactado. Isso reduz o tamanho de armazenamento, acelera transferências e cria um pacote portátil para implantação.

## Por que usar Aspose.Zip para .NET?
Aspose.Zip fornece uma API **pure‑managed** que não requer DLLs nativas, suporta arquivos de grande volume e lida automaticamente com casos especiais como **proteção por senha de arquivos zip** e nomes de arquivos Unicode. Também é otimizado para desempenho, tornando‑o ideal quando você precisa compactar pastas programaticamente em cenários de alta taxa de transferência.

## Pré‑requisitos
- Biblioteca **Aspose.Zip para .NET** instalada (faça o download [aqui](https://releases.aspose.com/zip/net/)).  
- Uma pasta no disco que você deseja arquivar – defina seu caminho na variável `dataDir`.  
- Ambiente de desenvolvimento .NET (Visual Studio, VS Code ou qualquer IDE de sua preferência).

## Importar Namespaces
Primeiro, traga os namespaces necessários para o escopo:

```csharp
using Aspose.Zip;
using System.IO;
```

## Guia Passo a Passo

### Passo 1: Compactar Diretório em Zip (compactar pasta programaticamente)
Criaremos um arquivo zip a partir do diretório que você planeja descompactar depois. O helper `CompressDirectory.Run()` faz o trabalho pesado.

```csharp
string dataDir = "Your Document Directory";
CompressDirectory.Run();
```

> **Dica:** O exemplo `CompressDirectory` empacota todos os arquivos em `dataDir` dentro de `CompressDirectory_out.zip`. Sinta‑se à vontade para renomear o arquivo de saída conforme suas convenções de nomenclatura.

### Passo 2: Descompactar a Pasta – Como Descompactar uma Pasta em .NET

#### Passo 2.1: Abrir o Arquivo Zip
Abra o arquivo gerado com um `FileStream`. Isso prepara o arquivo para leitura.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Open))
{
```

#### Passo 2.2: Criar Instância do Archive
Instancie o objeto `Archive`, que representa o contêiner zip.

```csharp
    using (var archive = new Archive(zipFile))
    {
```

#### Passo 2.3: Extrair para Diretório
Por fim, extraia o conteúdo para uma nova pasta. Este é o passo de **extrair zip para diretório**.

```csharp
        archive.ExtractToDirectory(dataDir + "DecompressFolder_out");
    }
}
```

## Por que Isso Importa
- **Consistência:** Usar a mesma biblioteca tanto para compactar quanto para extrair garante formatos de arquivo compatíveis.  
- **Desempenho:** Aspose.Zip transmite dados de forma eficiente, de modo que até arquivos de vários gigabytes são manipulados com baixo consumo de memória.  
- **Segurança:** Suporte nativo a proteção por senha significa que você pode proteger o arquivo zip sem código adicional.

## Casos de Uso Comuns
- **Backups automatizados** – compacte uma pasta de logs diariamente e armazene-a na nuvem.  
- **Pacotes de implantação** – agrupe ativos estáticos da web antes de publicar em um servidor.  
- **Troca de dados** – envie uma coleção de arquivos entre serviços como um único arquivo.

## Problemas Comuns & Soluções
| Sintoma | Causa Provável | Solução |
|---------|----------------|---------|
| `UnauthorizedAccessException` ao extrair | Pasta de destino está somente‑leitura ou em uso | Garanta que o caminho de destino seja gravável e não esteja bloqueado |
| Pasta de saída vazia após a extração | Caminho do zip de origem incorreto | Verifique se `dataDir + "CompressDirectory_out.zip"` aponta para o arquivo correto |
| Arquivos grandes causam OutOfMemoryException | Uso do tamanho de buffer padrão em arquivos muito grandes | Use `ArchiveOptions` para aumentar o tamanho do buffer ou transmita arquivos em blocos |

## Perguntas Frequentes

**P: Posso usar Aspose.Zip para .NET com qualquer tipo de arquivo?**  
R: Sim, Aspose.Zip suporta todos os tipos de arquivo—texto, binário, imagens, PDFs, o que for.

**P: Aspose.Zip é adequado para aplicações em grande escala?**  
R: Absolutamente. Foi projetado para cenários de compressão zip de alto desempenho em .NET, lidando com arquivos de vários gigabytes com baixo consumo de memória.

**P: Onde encontro a documentação completa do Aspose.Zip para .NET?**  
R: Explore a documentação detalhada [aqui](https://reference.aspose.com/zip/net/).

**P: Posso testar o Aspose.Zip antes de comprar?**  
R: Sim, há uma avaliação gratuita na [página de download do Aspose.Zip](https://releases.aspose.com/).

**P: Como obtenho suporte para Aspose.Zip para .NET?**  
R: Visite o [fórum do Aspose.Zip](https://forum.aspose.com/c/zip/37) para ajuda da comunidade e assistência oficial.

---

**Última atualização:** 2026-02-07  
**Testado com:** Aspose.Zip 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}