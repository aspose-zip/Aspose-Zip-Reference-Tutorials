---
title: Compactação segura de arquivos em .NET com Aspose.Zip
linktitle: Compactar arquivos com senhas individuais
second_title: API Aspose.Zip .NET para compactação e arquivamento de arquivos
description: Aprenda como aprimorar a segurança de arquivos em aplicativos .NET! Siga nosso guia passo a passo sobre compactação de arquivos com senhas individuais usando Aspose.Zip para .NET.
weight: 16
url: /pt/net/password-protection-and-encryption/compress-files-individual-passwords/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Compactação segura de arquivos em .NET com Aspose.Zip


## Introdução

No mundo do desenvolvimento .NET, gerenciar e compactar arquivos com eficiência é uma tarefa crucial. Aspose.Zip for .NET fornece uma solução poderosa para compactação de arquivos, oferecendo vários recursos para aprimorar seus aplicativos. Um recurso notável é a capacidade de compactar arquivos com senhas individuais, proporcionando uma camada adicional de segurança. Neste tutorial, orientaremos você no processo de compactação de arquivos com senhas individuais usando Aspose.Zip para .NET.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:

-  Aspose.Zip para .NET: Certifique-se de ter a biblioteca Aspose.Zip instalada em seu projeto .NET. Você pode encontrar a documentação necessária[aqui](https://reference.aspose.com/zip/net/).

-  Download: Se ainda não o fez, baixe a biblioteca Aspose.Zip para .NET em[esse link](https://releases.aspose.com/zip/net/).

- Diretório de documentos: prepare um diretório contendo os arquivos que deseja compactar.

## Importar namespaces

No seu projeto .NET, importe os namespaces necessários:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Etapa 1: definir o caminho do diretório de recursos

Defina o caminho para o diretório de recursos onde seus arquivos estão localizados.

```csharp
string dataDir = "Your Document Directory";
```

## Etapa 2: compactar arquivos com senhas individuais

Agora, vamos compactar arquivos com senhas individuais. Usaremos três arquivos de amostra (`alice29.txt`, `asyoulik.txt` , e`fields.c`) com senhas distintas para cada um.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compacte cada arquivo com uma senha individual
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Salve os arquivos compactados
        archive.Save(zipFile);
    }
}
```

## Conclusão

Parabéns! Você aprendeu com sucesso como compactar arquivos com senhas individuais usando Aspose.Zip para .NET. Este recurso adiciona uma camada extra de segurança aos seus arquivos compactados, garantindo a confidencialidade.

## Perguntas frequentes (FAQ)

### Posso usar métodos de criptografia diferentes para cada arquivo?
Sim, Aspose.Zip for .NET permite usar diferentes métodos de criptografia para cada arquivo durante a compactação.

### Existe uma versão de teste disponível?
 Sim, você pode acessar a avaliação gratuita do Aspose.Zip for .NET[aqui](https://releases.aspose.com/).

### Como posso obter suporte se encontrar problemas?
 Visite a[Fórum Aspose.Zip](https://forum.aspose.com/c/zip/37) pela assistência da comunidade e pelo apoio da Aspose.

### Onde posso encontrar documentação detalhada para Aspose.Zip for .NET?
 A documentação está disponível[aqui](https://reference.aspose.com/zip/net/).

### Posso comprar uma licença temporária para fins de teste?
 Sim, você pode adquirir uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
