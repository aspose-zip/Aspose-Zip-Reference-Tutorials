---
date: 2025-12-17
description: Aprenda a extrair arquivos Xar e descompactar um arquivo Xar para uma
  pasta usando o Aspose.Zip para .NET. Siga este guia passo a passo.
linktitle: Decompress Xar to Folder
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Como Extrair Xar para Pasta Usando Aspose.Zip para .NET
url: /pt/net/file-decompression/decompress-xar-folder/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Extrair Xar para Pasta Usando Aspose.Zip para .NET

## Introdução

Se você é um desenvolvedor .NET procurando uma maneira confiável **como extrair xar**, Aspose.Zip para .NET oferece uma API limpa e de alto desempenho. Neste tutorial, percorreremos todo o processo de descompactar um arquivo Xar para uma pasta, explicaremos por que essa abordagem economiza tempo e mostraremos o código exato que você precisa executar.

## Respostas Rápidas
- **O que a biblioteca faz?** Ela lê e extrai arquivos Xar sem ferramentas externas.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6+.  
- **Preciso de licença?** Uma versão de avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Quanto tempo leva a implementação?** Normalmente menos de 10 minutos.  
- **Posso extrair para uma pasta personalizada?** Sim—basta especificar o caminho de destino em `ExtractToDirectory`.

## O que é “como extrair xar”?
Extrair um arquivo Xar significa ler o pacote compactado e gravar seus arquivos internos em um diretório no disco. Isso é útil quando você recebe pacotes XAR de instaladores macOS, utilitários de backup ou ferramentas de terceiros e precisa processar seu conteúdo em uma aplicação .NET.

## Por que usar Aspose.Zip para esta tarefa?
- **Zero dependências externas** – puro .NET, sem binários nativos.  
- **API baseada em streams** – funciona com arquivos, streams de memória ou streams de rede.  
- **Manipulação robusta de erros** – exceções detalhadas ajudam a solucionar arquivos corrompidos.  
- **Compatibilidade total com .NET** – funciona em runtimes Windows, Linux e macOS.

## Pré-requisitos

Antes de começarmos, certifique‑se de que você tem o seguinte:

- **Aspose.Zip for .NET** – integrado ao seu projeto. Você pode baixá‑lo [aqui](https://releases.aspose.com/zip/net/).  
- **Document Directory** – uma pasta na sua solução onde o arquivo `.xar` de exemplo e a saída extraída ficarão.

## Importar Namespaces

No seu projeto .NET, inclua os namespaces necessários para acessar a funcionalidade do Aspose.Zip:

```csharp
using System.IO;
using Aspose.Zip.Xar;
```

## Etapa 1: Defina Seu Document Directory

```csharp
string dataDir = "Your Document Directory";
```

Substitua `"Your Document Directory"` pelo caminho absoluto ou relativo que contém `sample.xar` e onde você deseja que a pasta de saída seja criada.

## Etapa 2: Descompactar Arquivo Xar

```csharp
//ExStart: DecompressXarArchive
using (FileStream fs = File.OpenRead(dataDir + "sample.xar"))
{
    using (XarArchive archive = new XarArchive(fs))
    {
        archive.ExtractToDirectory(dataDir + "DecompressXar_out");
    }
}
```

Este trecho abre o arquivo Xar, cria uma instância `XarArchive` e extrai **todo o arquivo xar descompactado** para `DecompressXar_out`. A operação é totalmente baseada em streams, portanto funciona de forma eficiente mesmo com pacotes grandes.

## Etapa 3: Executar o Código

Compile e execute sua aplicação. Após a execução, você encontrará uma nova pasta chamada `DecompressXar_out` dentro do seu document directory, contendo todos os arquivos que foram empacotados no arquivo `.xar` original.

## Problemas Comuns & Dicas

- **Arquivo não encontrado** – Certifique‑se de que o caminho em `File.OpenRead` aponta corretamente para `sample.xar`. Use `Path.Combine` para um tratamento de caminho mais seguro.  
- **Acesso negado** – Execute a aplicação com permissões de sistema de arquivos suficientes, especialmente ao gravar em diretórios protegidos.  
- **Arquivo corrompido** – Aspose.Zip lança `InvalidDataException`; verifique se o arquivo `.xar` de origem está íntegro.

## Perguntas Frequentes

**Q: O Aspose.Zip é compatível com as versões mais recentes do .NET framework?**  
A: Sim, o Aspose.Zip é atualizado regularmente para garantir compatibilidade com as versões mais recentes do .NET framework. Consulte a [documentação](https://reference.aspose.com/zip/net/) para detalhes específicos.

**Q: Posso experimentar o Aspose.Zip antes de comprar?**  
A: Absolutamente! Você pode baixar uma versão de avaliação gratuita [aqui](https://releases.aspose.com/).

**Q: Como posso obter suporte para o Aspose.Zip?**  
A: Para quaisquer dúvidas ou assistência, visite o [fórum Aspose.Zip](https://forum.aspose.com/c/zip/37).

**Q: Licenças temporárias estão disponíveis para o Aspose.Zip?**  
A: Sim, licenças temporárias podem ser obtidas [aqui](https://purchase.aspose.com/temporary-license/).

**Q: Onde posso comprar o Aspose.Zip para .NET?**  
A: Você pode comprar o Aspose.Zip para .NET [aqui](https://purchase.aspose.com/buy).

**Q: Posso extrair apenas arquivos específicos de um arquivo Xar?**  
A: Sim—use `archive.Entries` para enumerar os itens e chame `ExtractToFile` nos entries selecionados.

**Q: A biblioteca suporta arquivos Xar protegidos por senha?**  
A: Atualmente, arquivos Xar não suportam criptografia; se você encontrar um arquivo protegido, será necessário descriptografá‑lo antes de usar o Aspose.Zip.

---

**Última atualização:** 2025-12-17  
**Testado com:** Aspose.Zip 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}