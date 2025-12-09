---
date: 2025-11-29
description: Aprenda como adicionar arquivos a um tar e compactá‑los em TarZ usando
  Aspose.Zip para .NET – um guia passo a passo para um manuseio eficiente de arquivos
  .NET.
linktitle: Compressing to TarZ
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Adicionar arquivos ao tar e compactar para TarZ com Aspose.Zip para .NET
url: /pt/net/archive-extraction-and-formats/compress-to-tar-z/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar arquivos a tar e compactar para TarZ com Aspose.Zip para .NET

## Introdução

Se você precisa **adicionar arquivos a tar** e depois compactar o arquivo para o formato TarZ, o Aspose.Zip para .NET torna todo o processo simples. Neste tutorial, percorreremos cada etapa — desde a configuração do seu projeto até a criação de um arquivo tar, a adição de arquivos e, finalmente, a gravação de um arquivo .tar.z compactado. Ao final, você terá um trecho reutilizável que pode ser inserido em qualquer aplicação .NET.

## Respostas rápidas
- **Qual biblioteca lida com a criação de tar?** Aspose.Zip para .NET  
- **Quantas linhas de código?** Cerca de 15 linhas (excluindo comentários)  
- **Preciso de licença para testes?** Existe uma versão de avaliação gratuita; uma licença é necessária para produção.  
- **Versões .NET suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+  
- **Posso compactar pastas, não apenas arquivos?** Sim – você pode adicionar diretórios inteiros com um loop.

## O que é **adicionar arquivos a tar**?
Adicionar arquivos a um arquivo tar agrupa-os em um único contêiner não compactado que preserva a estrutura de diretórios e os metadados dos arquivos. Tar é um formato clássico do Unix e serve como base para muitos fluxos de trabalho de compressão, incluindo o formato TarZ usado neste guia.

## Por que adicionar arquivos a tar antes de compactar para TarZ?
- **Portabilidade** – Um arquivo tar funciona em diferentes plataformas sem se preocupar com o tratamento individual de arquivos.  
- **Velocidade** – Criar o contêiner tar é rápido; a compressão Z subsequente foca apenas na redução de tamanho.  
- **Compatibilidade** – Muitas ferramentas legadas esperam um `.tar` antes de aplicar compressão estilo gzip, que é exatamente o que `.tar.z` fornece.

## Pré‑requisitos

Antes de mergulharmos no código, certifique‑se de que você tem:

- **Aspose.Zip para .NET** instalado. Baixe-o no site oficial [here](https://releases.aspose.com/zip/net/).  
- Uma pasta na sua máquina que contenha os arquivos que você deseja arquivar. Substitua o caminho placeholder pelo seu diretório real.

## Importar namespaces

Adicione as declarações `using` necessárias no topo do seu arquivo C#:

```csharp
using System;
using Aspose.Zip.Tar;
```

## Guia passo a passo

### Etapa 1: Definir seu diretório de documentos

```csharp
string dataDir = "Your Document Directory";
```

> **Dica profissional:** Use `Path.Combine` se precisar montar caminhos dinamicamente; isso evita separadores de caminho ausentes em diferentes sistemas operacionais.

### Etapa 2: Criar um arquivo Tar e adicionar arquivos

#### 2.1: Criar a instância do arquivo Tar

```csharp
using (TarArchive archive = new TarArchive())
{
    // Your code for creating the Tar archive goes here
}
```

#### 2.2: Adicionar arquivos ao arquivo  

Dentro do bloco `using`, adicione cada arquivo que deseja incluir:

```csharp
archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
```

Você pode repetir `CreateEntry` quantas vezes precisar, ou percorrer um diretório em loop para adicioná‑los programaticamente.

#### 2.3: Salvar o arquivo TarZ compactado  

Depois de adicionar todas as entradas, compacte o arquivo tar para o formato `.tar.z`:

```csharp
archive.SaveZCompressed(dataDir + "archive.tar.z");
```

O arquivo resultante `archive.tar.z` ficará na mesma pasta especificada em `dataDir`.

## Problemas comuns e soluções

| Problema | Motivo | Solução |
|----------|--------|---------|
| **Arquivo não encontrado** | Caminho errado ou extensão de arquivo ausente | Verifique se `dataDir` termina com um separador de caminho e se os nomes dos arquivos estão corretos. |
| **Acesso negado** | Permissões insuficientes na pasta de destino | Execute a aplicação com direitos adequados ou escolha um diretório gravável. |
| **Arquivo compactado maior que o esperado** | Arquivos originais já estavam compactados (ex.: imagens, vídeos) | TarZ funciona melhor em arquivos de texto ou logs; considere deixar arquivos já compactados como‑estão. |

## Perguntas frequentes

**P: Posso compactar pastas inteiras com Aspose.Zip para .NET?**  
R: Absolutamente. Use um loop `Directory.GetFiles` e chame `CreateEntry` para cada arquivo, preservando os caminhos relativos.

**P: Existe uma versão de avaliação disponível para Aspose.Zip para .NET?**  
R: Sim, você pode explorar os recursos do Aspose.Zip para .NET baixando a avaliação gratuita [here](https://releases.aspose.com/).

**P: Onde encontro a documentação completa do Aspose.Zip para .NET?**  
R: A documentação está disponível [here](https://reference.aspose.com/zip/net/), oferecendo detalhes aprofundados sobre os recursos e o uso da biblioteca.

**P: Como obter suporte para Aspose.Zip para .NET?**  
R: Visite o [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) para solicitar ajuda, compartilhar experiências e conectar‑se com a comunidade.

**P: Posso obter uma licença temporária para Aspose.Zip para .NET?**  
R: Sim, se precisar de uma licença temporária, você pode obtê‑la [here](https://purchase.aspose.com/temporary-license/).

## Conclusão

Agora você aprendeu como **adicionar arquivos a tar** e compactar o resultado em um arquivo TarZ usando Aspose.Zip para .NET. Essa abordagem fornece um pacote limpo e portátil que pode ser facilmente transferido, armazenado ou processado posteriormente. Sinta‑se à vontade para adaptar o trecho para processar lotes de diretórios, integrá‑lo a pipelines de build ou combiná‑lo com outros componentes Aspose para fluxos de trabalho de documentos mais avançados.

---

**Última atualização:** 2025-11-29  
**Testado com:** Aspose.Zip para .NET 24.11  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}