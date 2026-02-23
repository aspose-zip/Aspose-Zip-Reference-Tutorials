---
date: 2026-02-23
description: Aprenda a compactar vários arquivos em tar usando Aspose.Zip para .NET
  e criar arquivos tar.lz de forma eficiente.
linktitle: Compressing to TarLz
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Como compactar vários arquivos tar com Aspose.Zip para .NET
url: /pt/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

 need to keep shortcodes at top and bottom unchanged.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como compactar vários arquivos tar com Aspose.Zip para .NET

No desenvolvimento moderno em .NET, empacotar arquivos de forma eficiente pode melhorar drasticamente o tamanho da implantação e os tempos de transferência de rede. **Compress multiple files tar** é uma necessidade frequente quando você precisa de um arquivo TAR leve, compactado com LZ para backups, distribuição ou uploads para a nuvem. Neste tutorial, percorreremos um exemplo claro, passo a passo, de **compressão tar.lz** usando a biblioteca Aspose.Zip, para que você possa criar rapidamente um **arquivo tar.lz** em suas próprias aplicações.

## Respostas rápidas
- **Qual biblioteca devo usar?** Aspose.Zip para .NET.  
- **Quanto tempo leva a implementação?** Cerca de 5‑10 minutos para um exemplo básico.  
- **Preciso de licença?** Uma avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Posso compactar vários arquivos de uma vez?** Sim – basta adicionar mais entradas antes de salvar.

## Como compactar vários arquivos tar
Esta seção aborda diretamente a palavra‑chave principal e mostra os passos exatos para **compress multiple files tar** usando Aspose.Zip. A abordagem funciona para qualquer número de arquivos, e você pode adaptá‑la facilmente à sua própria estrutura de pastas.

## O que é compressão tar.lz?
`tar.lz` é um arquivo TAR que foi compactado usando o algoritmo LZMA (geralmente referido simplesmente como **LZ**). Ele combina a simplicidade de agrupar arquivos do TAR com a alta taxa de compressão do LZ, tornando‑o ideal para arquivos de backup, distribuição de pacotes ou qualquer cenário onde a largura de banda seja importante.

## Por que usar Aspose.Zip para .NET?
Aspose.Zip abstrai os detalhes de baixo nível da criação de arquivos, oferecendo uma API limpa e orientada a objetos. Você obtém:

* **Zero dependências externas** – implementação pura em .NET.  
* **Suporte multiplataforma** – funciona no Windows, Linux e macOS.  
* **Compressão LZ integrada** – sem necessidade de instalar ferramentas nativas adicionais.  
* **Tratamento robusto de erros** – exceções são descritivas, facilitando a depuração.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

- Biblioteca **Aspose.Zip para .NET** – faça o download [aqui](https://releases.aspose.com/zip/net/).  
- Uma pasta que contém os arquivos que você deseja arquivar. O caminho para essa pasta será armazenado na variável `dataDir` (você a definirá na Etapa 3).

## Importar namespaces
Adicione os namespaces necessários para que o compilador saiba onde encontrar as classes que usaremos.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Como criar um arquivo tar.lz – Guia passo a passo

### Etapa 1: Compactar um único arquivo
O primeiro exemplo mostra o cenário mais básico – adicionar um arquivo a um arquivo TAR e então salvá‑lo como um **tar.lz**.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Explicação**

- `new TarArchive()` cria um contêiner TAR vazio.  
- `CreateEntry` adiciona o arquivo `alice29.txt` da sua `dataDir`.  
- `SaveLzipped` grava o arquivo no disco e aplica a compressão LZ, produzindo `archive.tar.lz`.

### Etapa 2: Compactar vários arquivos em um único arquivo
Frequentemente você precisará agrupar vários arquivos. Basta chamar `CreateEntry` para cada arquivo antes de salvar. Isso demonstra **add files to tar lz** e efetivamente **compress multiple files tar**.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

**Explicação**

- O código segue o mesmo padrão da Etapa 1, mas adiciona uma segunda entrada (`lcet10.txt`).  
- Você pode repetir `CreateEntry` quantas vezes precisar; a biblioteca gerencia a estrutura interna do TAR automaticamente.

### Etapa 3: Especificar o diretório dos seus documentos
Substitua o placeholder pelo caminho real onde seus arquivos de origem estão localizados. Esse caminho é usado pelos exemplos acima.

```csharp
string dataDir = "Your Document Directory";
```

**Explicação**

- Defina `dataDir` para um caminho de pasta totalmente qualificado, por exemplo, `@"C:\MyFiles\"`.  
- Manter o diretório em uma variável torna o código reutilizável e mais fácil de manter.

## Armadilhas comuns & solução de problemas
| Sintoma | Causa provável | Solução |
|---------|----------------|--------|
| `FileNotFoundException` ao executar o exemplo | `dataDir` aponta para uma pasta inexistente ou o nome do arquivo está escrito incorretamente | Verifique o caminho e os nomes dos arquivos; use `Path.Combine` para maior segurança. |
| Arquivo de saída tem **0 KB** | `archive.SaveLzipped` foi chamado antes de adicionar quaisquer entradas | Garanta que ao menos uma chamada a `CreateEntry` preceda `SaveLzipped`. |
| A compressão parece lenta | Arquivos grandes com tamanho de buffer padrão | Considere processar os arquivos em blocos ou usar I/O assíncrono se o desempenho for crítico. |

## Conclusão
Agora você sabe **como compress tar.lz** arquivos usando Aspose.Zip para .NET, seja lidando com um único documento ou com uma coleção de arquivos. Este **exemplo de compressão tar.lz** demonstra uma maneira limpa e pronta para produção de **criar arquivos tar lz** que podem ser facilmente transferidos ou armazenados.

## Perguntas Frequentes

**Q:** Posso compactar arquivos de qualquer tamanho usando Aspose.Zip para .NET?  
**A:** Sim, a biblioteca lida tanto com arquivos pequenos quanto muito grandes; apenas assegure que você tenha memória e espaço em disco suficientes para a estrutura temporária do TAR.

**Q:** O código é compatível com a versão mais recente do Aspose.Zip?  
**A:** O exemplo tem como alvo a versão atual; mantenha sempre o pacote NuGet atualizado para correções de bugs e novos recursos.

**Q:** Existem considerações de licenciamento?  
**A:** Uma licença comercial é necessária para uso em produção. Consulte os detalhes de licenciamento no [site da Aspose](https://purchase.aspose.com/buy).

**Q:** Posso usar isso em um projeto comercial?  
**A:** Absolutamente – depois de obter uma licença válida, você pode incorporar a biblioteca em qualquer aplicação comercial.

**Q:** Onde posso obter ajuda se encontrar problemas?  
**A:** Visite o [fórum Aspose.Zip](https://forum.aspose.com/c/zip/37) para suporte da comunidade e assistência oficial.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2026-02-23  
**Testado com:** Aspose.Zip para .NET (última versão)  
**Autor:** Aspose  

---