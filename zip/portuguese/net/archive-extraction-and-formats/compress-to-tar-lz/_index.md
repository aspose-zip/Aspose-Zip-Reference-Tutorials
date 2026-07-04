---
date: 2026-07-04
description: Aprenda a compactar vários arquivos tar usando Aspose.Zip para .NET e
  criar arquivos tar.lz de forma eficiente.
keywords:
- compress multiple files tar
- create tar.lz archive
- compress files to tar.lz
linktitle: Compactando para TarLz
schemas:
- author: Aspose
  dateModified: '2026-07-04'
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  headline: How to compress multiple files tar with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  name: How to compress multiple files tar with Aspose.Zip for .NET
  steps:
  - name: Compress a single file
    text: The first example shows the most basic scenario – adding one file to a TAR
      archive and then saving it as a **tar.lz** file. The `TarArchive` class represents
      a TAR container that can hold multiple files in a single archive. **Explanation**
      - `new TarArchive()` creates an empty TAR container. - `Crea
  - name: Compress multiple files in one archive
    text: Often you’ll need to bundle several files together. Just call `CreateEntry`
      for each file before saving. This demonstrates **add files to tar lz** and effectively
      **compress multiple files tar**. **Explanation** - The code follows the same
      pattern as Step 1, but adds a second entry (`lcet10.txt`). -
  - name: Specify your document directory
    text: Replace the placeholder with the actual path where your source files live.
      This path is used by the examples above. **Explanation** - Set `dataDir` to
      a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`. - Keeping the directory
      in a variable makes the code reusable and easier to maintain.
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET.
    question: What library should I use?
  - answer: About 5‑10 minutes for a basic example.
    question: How long does the implementation take?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes – just add more entries before saving.
    question: Can I compress multiple files at once?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Como compactar vários arquivos tar com Aspose.Zip para .NET
url: /pt/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como compactar vários arquivos tar com Aspose.Zip para .NET

Em desenvolvimento .NET moderno, empacotar arquivos de forma eficiente pode melhorar drasticamente o tamanho da implantação e os tempos de transferência de rede. **Compress multiple files tar** é um requisito frequente quando você precisa de um arquivo TAR leve, compactado com LZ, para backups, distribuição ou uploads na nuvem. Neste tutorial, percorreremos um **exemplo de compressão tar.lz** passo a passo usando a biblioteca Aspose.Zip, para que você possa criar rapidamente um **arquivo tar.lz** em suas próprias aplicações.

## Respostas Rápidas
- **Qual biblioteca devo usar?** Aspose.Zip for .NET.  
- **Quanto tempo leva a implementação?** Cerca de 5‑10 minutos para um exemplo básico.  
- **Preciso de uma licença?** Um teste gratuito funciona para testes; uma licença comercial é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Posso compactar vários arquivos de uma vez?** Sim – basta adicionar mais entradas antes de salvar.

## Como compactar vários arquivos tar com Aspose.Zip para .NET?
Carregue seus arquivos de origem, crie uma instância `TarArchive`, adicione cada arquivo com `CreateEntry` e finalize chamando `SaveLzipped`. A biblioteca trata a estrutura TAR e a compressão LZ internamente, de modo que você obtém um único arquivo `*.tar.lz` em apenas algumas linhas de código. Essa abordagem funciona no Windows, Linux e macOS sem dependências nativas.

## O que é compressão tar.lz?
`tar.lz` é um arquivo TAR que foi compactado usando o algoritmo LZMA (geralmente referido simplesmente como **LZ**). Ele combina a simplicidade de agrupar arquivos do TAR com a alta taxa de compressão do LZ, tornando‑o ideal para arquivos de backup, distribuição de pacotes ou qualquer cenário onde a largura de banda seja importante.

## Por que usar Aspose.Zip para .NET?
Aspose.Zip fornece uma solução pura‑gerenciada, multiplataforma, que cria arquivos TAR, ZIP e baseados em LZ sem ferramentas externas, suporta mais de 30 formatos de arquivo e oferece até 30 % mais compressão em arquivos grandes, além de oferecer exceções detalhadas para um tratamento de erros robusto. Também se integra perfeitamente a frameworks de logging .NET e fornece eventos de progresso detalhados.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

- **Biblioteca Aspose.Zip para .NET** – faça o download [aqui](https://releases.aspose.com/zip/net/).  
- Uma pasta que contém os arquivos que você deseja arquivar. O caminho para essa pasta será armazenado na variável `dataDir` (você a definirá na Etapa 3).

## Importar Namespaces
Adicione os namespaces necessários para que o compilador saiba onde encontrar as classes que usaremos.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Como criar um arquivo tar.lz – Guia passo a passo

### Etapa 1: Compactar um único arquivo
O primeiro exemplo mostra o cenário mais básico – adicionar um arquivo a um arquivo TAR e então salvá‑lo como um **tar.lz**.

A classe `TarArchive` representa um contêiner TAR que pode conter vários arquivos em um único arquivo.

**Explicação**

- `new TarArchive()` cria um contêiner TAR vazio.  
- `CreateEntry` adiciona o arquivo `alice29.txt` do seu `dataDir`.  
- `SaveLzipped` grava o arquivo no disco e aplica compressão LZ, produzindo `archive.tar.lz`.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Etapa 2: Compactar vários arquivos em um único arquivo
Frequentemente você precisará agrupar vários arquivos juntos. Basta chamar `CreateEntry` para cada arquivo antes de salvar. Isso demonstra **add files to tar lz** e efetivamente **compress multiple files tar**.

**Explicação**

- O código segue o mesmo padrão da Etapa 1, mas adiciona uma segunda entrada (`lcet10.txt`).  
- Você pode repetir `CreateEntry` quantas vezes precisar; a biblioteca lida automaticamente com a estrutura interna do TAR.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Etapa 3: Especificar o diretório dos documentos
Substitua o marcador de posição pelo caminho real onde seus arquivos de origem estão localizados. Esse caminho é usado pelos exemplos acima.

**Explicação**

- Defina `dataDir` para um caminho de pasta totalmente qualificado, por exemplo, `@"C:\MyFiles\"`.  
- Manter o diretório em uma variável torna o código reutilizável e mais fácil de manter.

```csharp
string dataDir = "Your Document Directory";
```

## Armadilhas comuns e solução de problemas
| Sintoma | Causa provável | Correção |
|---------|----------------|----------|
| `FileNotFoundException` ao executar o exemplo | `dataDir` aponta para uma pasta inexistente ou o nome do arquivo está escrito errado | Verifique o caminho e os nomes dos arquivos; use `Path.Combine` para segurança. |
| O arquivo de saída tem **0 KB** | `archive.SaveLzipped` foi chamado antes de adicionar quaisquer entradas | Garanta que ao menos uma chamada `CreateEntry` preceda `SaveLzipped`. |
| A compressão parece lenta | Arquivos grandes com tamanho de buffer padrão | Considere processar arquivos em blocos ou usar I/O assíncrono se o desempenho for crítico. |

## Conclusão
Agora você sabe **como compactar arquivos tar.lz** usando Aspose.Zip para .NET, seja lidando com um único documento ou uma coleção de arquivos. Este **exemplo de compressão tar.lz** demonstra uma forma limpa e pronta para produção de **criar arquivos tar lz** que podem ser facilmente transferidos ou armazenados. Você pode compactar arquivos para tar.lz usando a mesma API chamando `SaveLzipped` após adicionar todas as entradas desejadas.

## Perguntas Frequentes

**Q:** Posso compactar arquivos de qualquer tamanho usando Aspose.Zip para .NET?  
**A:** Sim, a biblioteca lida tanto com arquivos pequenos quanto muito grandes; apenas certifique‑se de ter memória e espaço em disco suficientes para a estrutura temporária do TAR.

**Q:** O código é compatível com a versão mais recente do Aspose.Zip?  
**A:** O exemplo tem como alvo a versão atual; mantenha sempre o pacote NuGet atualizado para correções de bugs e novos recursos.

**Q:** Existem considerações de licenciamento?  
**A:** Uma licença comercial é necessária para uso em produção. Veja os detalhes de licenciamento no [site da Aspose](https://purchase.aspose.com/buy).

**Q:** Posso usar isso em um projeto comercial?  
**A:** Absolutamente – depois de obter uma licença válida, você pode incorporar a biblioteca em qualquer aplicação comercial.

**Q:** Onde posso obter ajuda se encontrar problemas?  
**A:** Visite o [fórum Aspose.Zip](https://forum.aspose.com/c/zip/37) para suporte da comunidade e assistência oficial.

---

**Última atualização:** 2026-07-04  
**Testado com:** Aspose.Zip for .NET (última versão)  
**Autor:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Criar arquivo tar e adicionar arquivos ao tar com Aspose.Zip para .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Como compactar tar e criar TarBz2 com Aspose.Zip para .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Adicionar arquivos ao tar e criar arquivo tarxz com Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}