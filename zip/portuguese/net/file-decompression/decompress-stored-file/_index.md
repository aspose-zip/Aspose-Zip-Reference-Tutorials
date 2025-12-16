---
date: 2025-12-16
description: Aprenda como criar arquivos zip sem compressão e extrair vários arquivos
  zip usando Aspose.Zip para .NET. Este guia aborda como abrir um zip, ler a entrada
  do zip e as etapas de extração de zip em C#.
linktitle: Decompressing a Stored File
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Criar Zip sem compressão e descompactar arquivos – Aspose.Zip
url: /pt/net/file-decompression/decompress-stored-file/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Descompactando um Arquivo Armazenado usando Aspose.Zip para .NET

## Introdução

Em aplicações .NET modernas, **create zip without compression** é uma técnica útil quando você precisa de arquivamento rápido sem a sobrecarga da redução de dados. Aspose.Zip para .NET facilita tanto a criação desses arquivos quanto a **extract multiple zip files** posteriormente. Neste tutorial você verá como abrir um zip, ler os dados de uma entrada zip e executar uma operação de **C# extract zip** passo a passo.

## Respostas Rápidas
- **O que é “create zip without compression”?** Significa adicionar arquivos a um arquivo ZIP usando o método “store”, que deixa os dados inalterados.
- **Qual biblioteca trata isso no .NET?** Aspose.Zip para .NET.
- **Preciso de licença para executar o exemplo?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.
- **Posso extrair vários arquivos de uma vez?** Sim – o tutorial mostra como **extract multiple zip files** em um loop.
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## O que é “create zip without compression”?
Quando você cria um arquivo ZIP com o método de compressão **store**, cada arquivo é adicionado exatamente como está. Isso resulta em um arquivo maior comparado a ZIPs comprimidos, mas a operação é muito mais rápida e os bytes originais permanecem intactos – ideal para cenários onde velocidade ou integridade dos dados são mais importantes que o tamanho.

## Por que usar Aspose.Zip para .NET?
- **Controle total** sobre o nível de compressão (store vs. deflate).  
- **API simples** para ler entradas, abrir arquivos zip e extrair dados.  
- **Suporte multiplataforma** para .NET Framework, .NET Core e .NET 5+.

## Pré‑requisitos

Antes de iniciarmos este tutorial, certifique‑se de que você possui os seguintes pré‑requisitos:

- Biblioteca Aspose.Zip para .NET: Baixe e instale a biblioteca Aspose.Zip para .NET. Você pode encontrar a biblioteca [aqui](https://releases.aspose.com/zip/net/).

- Diretório de Documentos: Crie um diretório em seu sistema onde você armazenará os arquivos necessários para este tutorial.

## Importar Namespaces

Para começar, vamos importar os namespaces necessários para o nosso projeto:

```csharp
using Aspose.Zip;
using System.IO;
```

## Como Criar Zip Sem Compressão

Primeiro precisamos de um arquivo ZIP que use o método **store** (ou seja, sem compressão). O código de exemplo abaixo cria esse arquivo e é fornecido pela Aspose.Zip como um método auxiliar. Executá‑lo gerará `StoreMultipleFilesWithoutCompression_out.zip` em seu diretório de documentos.

```csharp
StoreMultipleFilesWithoutCompression.Run();
```

> **Dica profissional:** O método auxiliar define internamente `CompressionMethod.Store` para cada entrada, garantindo que o arquivo seja criado sem qualquer compressão de dados.

## Como Abrir Zip e Extrair Vários Arquivos

Agora que temos um ZIP armazenado, vamos ver **how to open zip** e extrair os arquivos.

### Etapa 2.1: Abrindo o Arquivo Zip

```csharp
string dataDir = "Your Document Directory";

using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Open))
{
    using (Archive archive = new Archive(zipFile))
    {
```

O objeto `Archive` representa o ZIP aberto e fornece acesso a cada entrada por meio da coleção `Entries`.

### Etapa 2.2: Criando Arquivos Extraídos

```csharp
        using (var extracted = File.Create(dataDir + "alice_extracted_store_out.txt"))
        {
            using (var decompressed = archive.Entries[0].Open())
            {
                byte[] buffer = new byte[8192];
                int bytesRead;

                // Reading from decompressed stream to extracting file.
                while (0 < (bytesRead = decompressed.Read(buffer, 0, buffer.Length)))
                {
                    extracted.Write(buffer, 0, bytesRead);
                }
            }
        }
```

Aqui nós **read zip entry** 0, copiamos seus bytes para um novo arquivo e fechamos os streams automaticamente graças às instruções `using`.

### Etapa 2.3: Repetindo o Processo para Outro Arquivo

```csharp
        using (var extracted = File.Create(dataDir + "asyoulik_extracted_store_out.txt"))
        {
            using (var decompressed = archive.Entries[1].Open())
            {
                byte[] buffer = new byte[8192];
                int bytesRead;

                // Reading from decompressed stream to extracting file.
                while (0 < (bytesRead = decompressed.Read(buffer, 0, buffer.Length)))
                {
                    extracted.Write(buffer, 0, bytesRead);
                }
            }
        }
    }
}
```

Ao iterar sobre `archive.Entries`, você pode **extract multiple zip files** (ou múltiplas entradas) com apenas algumas linhas de código.

## Problemas Comuns e Soluções

| Problema | Causa | Solução |
|----------|-------|---------|
| `FileNotFoundException` ao abrir o ZIP | Caminho `dataDir` incorreto | Verifique se `dataDir` termina com barra ou use `Path.Combine`. |
| Arquivo extraído está vazio | Buffer não descarregado | O bloco `using` descarrega automaticamente; assegure‑se de ler o stream até que `bytesRead` seja 0 (conforme mostrado). |
| Exceção de licença | Execução sem licença válida | Aplique uma licença de avaliação ou permanente antes da implantação. |

## Perguntas Frequentes

### Q1: O Aspose.Zip para .NET é compatível com todos os frameworks .NET?

**A:** Sim, o Aspose.Zip para .NET foi projetado para ser compatível com diversos frameworks .NET, oferecendo flexibilidade aos desenvolvedores.

### Q2: Posso usar o Aspose.Zip para .NET em projetos comerciais e não comerciais?

**A:** Sim, o Aspose.Zip para .NET pode ser usado tanto em projetos comerciais quanto não comerciais. Consulte a [página de compra](https://purchase.aspose.com/buy) para detalhes de licenciamento.

### Q3: Como posso obter suporte para o Aspose.Zip para .NET?

**A:** Para suporte, visite o [fórum Aspose.Zip](https://forum.aspose.com/c/zip/37), onde uma comunidade de desenvolvedores e especialistas pode ajudá‑lo.

### Q4: Existe uma avaliação gratuita disponível para o Aspose.Zip para .NET?

**A:** Sim, você pode explorar os recursos do Aspose.Zip para .NET obtendo uma avaliação gratuita [aqui](https://releases.aspose.com/).

### Q5: Posso obter uma licença temporária para fins de teste?

**A:** Sim, você pode obter uma licença temporária para testes visitando [este link](https://purchase.aspose.com/temporary-license/).

### Q6: Como leio uma entrada zip sem extrair todo o arquivo?

**A:** Use `archive.Entries[index].Open()` para obter um stream de uma entrada específica, então leia os bytes necessários, como demonstrado no código acima.

### Q7: Qual a melhor forma de **extract multiple zip files** em um loop?

**A:** Itere sobre `archive.Entries` com um loop `foreach`, abrindo o stream de cada entrada e gravando-o em um arquivo de destino, similar ao padrão mostrado nas Etapas 2.2 e 2.3.

## Conclusão

Dominar **create zip without compression** e o processo subsequente de extração é essencial para aplicações .NET de alto desempenho. Aspose.Zip para .NET oferece uma API limpa e intuitiva para **how to open zip**, ler cada **zip entry** e executar uma operação de **C# extract zip** com código mínimo. Seguindo este guia, você aprendeu a gerar um arquivo armazenado, abri‑lo e extrair seu conteúdo de forma eficiente.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2025-12-16  
**Testado com:** Aspose.Zip para .NET 24.12  
**Autor:** Aspose  

---