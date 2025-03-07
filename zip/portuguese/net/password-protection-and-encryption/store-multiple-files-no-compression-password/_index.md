---
title: Aspose.Zip para .NET - Tutorial de armazenamento seguro de arquivos
linktitle: Armazene vários arquivos sem compactação com senha
second_title: API Aspose.Zip .NET para compactação e arquivamento de arquivos
description: Explore como usar Aspose.Zip for .NET para armazenar vários arquivos com segurança sem compactação. Etapas fáceis para proteção por senha. Desbloqueie o poder do gerenciamento de arquivos!
weight: 13
url: /pt/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip para .NET - Tutorial de armazenamento seguro de arquivos


No mundo do desenvolvimento .NET, gerenciar e manipular arquivos é uma tarefa comum. Aspose.Zip for .NET é uma biblioteca poderosa que fornece aos desenvolvedores a capacidade de compactar, descompactar e manipular arquivos zip perfeitamente. Neste tutorial, nos aprofundaremos em um cenário específico: armazenar vários arquivos sem compactação e protegê-los com senha. Ao final deste guia, você estará equipado com o conhecimento para implementar essa funcionalidade usando Aspose.Zip for .NET.

## Pré-requisitos

Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Biblioteca Aspose.Zip for .NET: Certifique-se de ter a biblioteca Aspose.Zip for .NET instalada. Você pode baixá-lo[aqui](https://releases.aspose.com/zip/net/).

-  Diretório de documentos: prepare um diretório onde seus arquivos de origem estão localizados. No exemplo fornecido, a variável`dataDir` representa o diretório do seu documento.

## Importar namespaces

Para começar, vamos importar os namespaces necessários para nosso código:

```csharp
// O caminho para o diretório de recursos.
string dataDir = "Your Document Directory"

// Importar namespaces Aspose.Zip
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## Etapa 1: abra o arquivo Zip

```csharp
//ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

 Esta etapa envolve a criação de um novo arquivo zip usando`FileStream`. O arquivo será denominado "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip."

## Etapa 2: abra o arquivo de origem

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

Aqui, abrimos o primeiro arquivo fonte, “alice29.txt”, que será armazenado no arquivo zip.

## Etapa 3: criar um arquivo

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

 Nesta etapa, criamos uma instância do`Archive` classe, especificando as configurações de compactação e criptografia. Nós usamos o`StoreCompressionSettings` para armazenar arquivos sem compactação e`AesEcryptionSettings` para aplicar criptografia AES com uma senha ("p@s$").

## Etapa 4: criar entrada de arquivo e salvar

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

Esta etapa final envolve a criação de uma entrada no arquivo para “alice29.txt” e o salvamento do arquivo, completando o processo de armazenamento de um arquivo sem compactação e com proteção por senha.

Conclua seu tutorial resumindo os pontos principais e incentivando os leitores a explorar outras possibilidades com Aspose.Zip for .NET.

## Conclusão

Neste tutorial, exploramos como usar Aspose.Zip for .NET para armazenar vários arquivos sem compactação e protegê-los com uma senha. À medida que você continua sua jornada com o desenvolvimento .NET, aproveite os recursos do Aspose.Zip para agilizar as tarefas de gerenciamento de arquivos e aumentar a segurança de seus aplicativos.

---

### Perguntas frequentes

### Posso usar o Aspose.Zip for .NET com outros métodos de criptografia?
 Sim, Aspose.Zip oferece suporte a vários métodos de criptografia. Verifique a documentação[aqui](https://reference.aspose.com/zip/net/) para detalhes.

### Onde posso obter suporte para Aspose.Zip for .NET?
 Visite a[Fórum Aspose.Zip](https://forum.aspose.com/c/zip/37) para apoio e discussões da comunidade.

### Existe uma avaliação gratuita disponível para Aspose.Zip for .NET?
 Sim, você pode acessar o teste gratuito[aqui](https://releases.aspose.com/).

### Como posso obter uma licença temporária do Aspose.Zip for .NET?
 Solicite uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).

### Onde posso comprar o Aspose.Zip para .NET?
 Você pode comprar Aspose.Zip para .NET[aqui](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
