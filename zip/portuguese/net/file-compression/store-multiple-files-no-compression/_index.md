---
date: 2025-12-10
description: Aprenda a armazenar arquivos sem compressão usando Aspose.Zip para .NET.
  Este guia mostra como criar um zip sem compressão, salvar arquivos no zip e gerenciar
  arquivos de forma eficiente.
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Como armazenar arquivos sem compressão com Aspose.Zip para .NET
url: /pt/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como armazenar arquivos sem compressão com Aspose.Zip para .NET

No desenvolvimento moderno em .NET, **como armazenar arquivos** de forma eficiente pode fazer uma grande diferença no desempenho e nos custos de armazenamento. Quando você precisa manter os arquivos exatamente como estão — sem nenhuma compressão — Aspose.Zip para .NET oferece uma API limpa e direta. Neste tutorial vamos percorrer os passos para criar um arquivo ZIP sem compressão, salvar arquivos no ZIP e integrar a solução em sua aplicação.

## Respostas rápidas
- **O que significa “zip sem compressão”?** É um arquivo ZIP onde cada entrada é armazenada usando o método “store”, deixando os bytes originais do arquivo intactos.  
- **Por que evitar compressão?** Para acelerar a criação do arquivo, preservar os tamanhos originais dos arquivos para processamento posterior ou atender a requisitos regulatórios que proíbem a alteração dos dados.  
- **Qual classe do Aspose.Zip trata disso?** `ArchiveEntrySettings` combinada com `StoreCompressionSettings`.  
- **Preciso de licença?** Um teste gratuito funciona para testes; uma licença comercial é necessária para produção.  
- **Versões .NET suportadas?** .NET Framework, .NET Core, .NET 5/6/7 e posteriores.

## O que é armazenar vários arquivos sem compressão?
Armazenar vários arquivos sem compressão significa adicionar cada arquivo a um contêiner ZIP usando o método de compressão *store*. Os arquivos permanecem byte‑por‑byte idênticos aos originais, o que é ideal quando você deseja arquivamento rápido ou precisa manter os dados inalterados.

## Por que usar Aspose.Zip para arquivos sem compressão?
- **Velocidade:** Nenhum algoritmo de compressão intensivo em CPU é executado.  
- **Tamanho previsível:** O tamanho do arquivo ZIP equivale à soma dos arquivos originais mais a sobrecarga mínima do ZIP.  
- **Compatibilidade:** O ZIP resultante funciona com qualquer utilitário padrão de descompactação.  
- **Flexibilidade:** Você ainda pode misturar entradas comprimidas e não comprimidas no mesmo arquivo, se necessário.

## Pré‑requisitos
- **Aspose.Zip para .NET** – integrado ao seu projeto. Consulte a [documentação oficial](https://reference.aspose.com/zip/net/) para etapas de instalação.  
- **Ambiente de desenvolvimento .NET** – Visual Studio, VS Code ou qualquer IDE de sua preferência.  
- **Diretório de documentos** – uma pasta em sua máquina contendo os arquivos que você deseja arquivar (por exemplo, “Your Document Directory”).

## Importar namespaces
Antes de escrever qualquer código, importe os namespaces necessários para que o compilador saiba onde encontrar as classes Aspose.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## Etapa 1: Definir o diretório de documentos
Defina o caminho onde seus arquivos de origem estão localizados. Substitua o placeholder pelo caminho real da pasta em seu sistema.

```csharp
string dataDir = "Your Document Directory";
```

## Etapa 2: Criar arquivo Zip sem compressão
O núcleo do tutorial – criamos uma instância de `Archive` configurada com `StoreCompressionSettings`. Isso indica ao Aspose.Zip para *armazenar* (ou seja, não comprimir) cada entrada.

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **Dica profissional:** Se precisar **salvar arquivos no zip** comprimindo alguns e deixando outros sem compressão, crie instâncias separadas de `ArchiveEntrySettings` para cada arquivo e adicione‑as ao mesmo `Archive`.

## Problemas comuns e soluções
| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| **Arquivo não encontrado** | Caminho `dataDir` incorreto ou extensão de arquivo ausente. | Verifique o caminho e assegure que os arquivos existam. Use `Path.Combine` para concatenação mais segura. |
| **Acesso negado** | O processo não tem permissão para ler os arquivos de origem ou gravar o ZIP. | Execute a aplicação com direitos adequados ou escolha uma pasta com permissão de escrita. |
| **Tamanho inesperado do arquivo no ZIP** | O arquivo foi criado com compressão padrão. | Garanta que `new StoreCompressionSettings()` seja passado para `ArchiveEntrySettings`. |

## Perguntas frequentes

**P: Posso comprimir tipos de arquivo específicos enquanto armazeno outros sem compressão?**  
R: Sim, você pode criar diferentes `ArchiveEntrySettings` para cada arquivo e misturar entradas comprimidas e não comprimidas no mesmo arquivo.

**P: O Aspose.Zip para .NET é compatível com .NET Core e .NET 5/6?**  
R: Absolutamente. A biblioteca suporta .NET Framework, .NET Core, .NET Standard e as versões mais recentes do .NET.

**P: Como devo tratar exceções durante o processo de arquivamento?**  
R: Envolva o código de arquivamento em um bloco `try‑catch` e registre os detalhes da exceção. Isso garante falhas controladas e facilita a depuração.

**P: O Aspose.Zip suporta arquivamento multi‑thread?**  
R: Sim, você pode processar vários arquivos em paralelo e adicioná‑los ao arquivo, mas lembre‑se de que o objeto `Archive` em si não é thread‑safe; sincronize o acesso ao adicioná‑los.

**P: Posso integrar o Aspose.Zip em um projeto existente sem grandes alterações de código?**  
R: Definitivamente. A API foi projetada para uso simples de “drop‑in”. Consulte a [documentação oficial](https://reference.aspose.com/zip/net/) para orientações de migração.

---

**Última atualização:** 2025-12-10  
**Testado com:** Aspose.Zip para .NET 24.12 (mais recente na data de escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}