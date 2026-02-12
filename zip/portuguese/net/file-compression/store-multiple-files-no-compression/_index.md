---
date: 2026-02-12
description: Aprenda a criar arquivos zip sem compressão no .NET com Aspose.Zip para
  .NET. Este guia mostra como compactar arquivos sem compressão, armazenar arquivos
  sem compressão e gerenciar arquivos de forma eficiente.
linktitle: Storing Multiple Files Without Compression
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Criar zip não compactado .NET usando Aspose.Zip para .NET
url: /pt/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar zip não compactado .net com Aspose.Zip para .NET

No desenvolvimento moderno em .NET, **criar um zip não compactado .net** pode melhorar drasticamente a velocidade de arquivamento e manter os tamanhos dos arquivos previsíveis. Quando você precisa **compactar arquivos sem compressão** — por exemplo, para atender a regras regulatórias ou acelerar o processamento subsequente — Aspose.Zip para .NET oferece uma API limpa e direta. Neste tutorial, percorreremos os passos exatos para criar um arquivo ZIP não compactado, adicionar arquivos e integrar a solução em sua aplicação.

## Respostas rápidas
- **O que significa “zip não compactado”?** É um arquivo ZIP onde cada entrada é armazenada usando o método “store”, deixando os bytes originais do arquivo intactos.  
- **Por que evitar compressão?** Para acelerar o arquivamento, preservar os tamanhos originais dos arquivos para processamento subsequente ou atender a requisitos regulatórios que proíbem a alteração de dados.  
- **Qual classe do Aspose.Zip lida com isso?** `ArchiveEntrySettings` combinada com `StoreCompressionSettings`.  
- **Preciso de licença?** Uma avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Versões .NET suportadas?** .NET Framework, .NET Core, .NET 5/6/7 e posteriores.  

## O que é criar zip não compactado .net?
Criar um ZIP não compactado significa adicionar cada arquivo a um contêiner ZIP usando o método de compressão *store*. Os arquivos permanecem byte a byte idênticos aos originais, o que é ideal quando você deseja um arquivamento rápido ou precisa manter os dados inalterados.

## Por que usar Aspose.Zip para arquivos zip sem compressão?
- **Velocidade:** Nenhum algoritmo de compressão intensivo em CPU é executado.  
- **Tamanho previsível:** O tamanho do arquivo é igual à soma dos arquivos originais mais a sobrecarga mínima do ZIP.  
- **Compatibilidade:** O ZIP resultante funciona com qualquer utilitário padrão de descompactação.  
- **Flexibilidade:** Você ainda pode misturar entradas compactadas e não compactadas no mesmo arquivo, se necessário.

## Pré-requisitos
- **Aspose.Zip for .NET** – integrado ao seu projeto. Consulte a [documentação](https://reference.aspose.com/zip/net/) oficial para etapas de instalação.  
- **Ambiente de desenvolvimento .NET** – Visual Studio, VS Code ou qualquer IDE de sua preferência.  
- **Diretório de documentos** – uma pasta na sua máquina contendo os arquivos que você deseja arquivar (por exemplo, “Your Document Directory”).

## Importar Namespaces
Antes de escrever qualquer código, importe os namespaces necessários para que o compilador saiba onde encontrar as classes da Aspose.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## Etapa 1: Definir Diretório de Documentos
Defina o caminho onde seus arquivos de origem estão localizados. Substitua o placeholder pela pasta real no seu sistema.

```csharp
string dataDir = "Your Document Directory";
```

## Etapa 2: Criar Arquivo Zip Sem Compressão
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

> **Dica profissional:** Se você precisar **salvar arquivos em zip** enquanto comprime alguns e deixa outros sem compressão, crie instâncias separadas de `ArchiveEntrySettings` para cada arquivo e adicione-as ao mesmo `Archive`.

## Problemas Comuns e Soluções
| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| **Arquivo não encontrado** | Caminho `dataDir` incorreto ou extensão de arquivo ausente. | Verifique o caminho e assegure que os arquivos existam. Use `Path.Combine` para concatenação mais segura. |
| **Acesso negado** | O processo não tem permissão para ler os arquivos de origem ou gravar o ZIP. | Execute a aplicação com direitos adequados ou escolha uma pasta com permissão de gravação. |
| **Tamanho de arquivo inesperado no ZIP** | O arquivo foi criado com compressão padrão. | Garanta que `new StoreCompressionSettings()` seja passado para `ArchiveEntrySettings`. |

## Perguntas Frequentes

**Q: Posso comprimir tipos de arquivo específicos enquanto armazeno outros sem compressão?**  
A: Sim, você pode criar diferentes `ArchiveEntrySettings` para cada arquivo e misturar entradas compactadas e não compactadas no mesmo arquivo.

**Q: O Aspose.Zip para .NET é compatível com .NET Core e .NET 5/6?**  
A: Absolutamente. A biblioteca suporta .NET Framework, .NET Core, .NET Standard e as versões mais recentes do .NET.

**Q: Como devo tratar exceções durante o processo de arquivamento?**  
A: Envolva o código de arquivamento em um bloco `try‑catch` e registre os detalhes da exceção. Isso garante falha graciosa e facilita a depuração.

**Q: O Aspose.Zip suporta arquivamento multi‑thread?**  
A: Sim, você pode processar vários arquivos em paralelo e adicioná‑los ao arquivo, mas lembre‑se de que o objeto `Archive` não é thread‑safe; sincronize o acesso ao adicionar entradas.

**Q: Posso integrar o Aspose.Zip em um projeto existente sem grandes alterações de código?**  
A: Definitivamente. A API foi projetada para uso simples de drop‑in. Consulte a [documentação](https://reference.aspose.com/zip/net/) oficial para orientações de migração.

---

**Última atualização:** 2026-02-12  
**Testado com:** Aspose.Zip for .NET (mais recente na época da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}