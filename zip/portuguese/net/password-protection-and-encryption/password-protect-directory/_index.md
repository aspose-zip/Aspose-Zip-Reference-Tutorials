---
date: 2025-12-21
description: Aprenda a criar arquivos zip protegidos por senha no .NET, criptografar
  pastas e alterar a senha do zip usando o Aspose.Zip.
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Criar zip protegido por senha para diretórios .NET – Tutorial Aspose.Zip
url: /pt/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar zip protegido por senha para diretórios .NET – Tutorial Aspose.Zip

## Quick Answers
- **Qual biblioteca é recomendada?** Aspose.Zip for .NET  
- **Posso criptografar uma pasta inteira?** Sim – basta apontar a API para a pasta que você deseja compactar.  
- **É possível alterar a senha do zip?** Absolutamente, use `TraditionalEncryptionSettings`.  
- **Preciso de uma licença para produção?** É necessária uma licença válida do Aspose.Zip para uso comercial.  
- **Funciona com .NET Core/5/6?** Sim, a API é totalmente compatível com runtimes .NET modernos.  

## O que significa “criar zip protegido por senha”?
Criar um zip protegido por senha significa compactar arquivos ou diretórios em um arquivo ZIP aplicando criptografia, de modo que o arquivo só possa ser aberto com a senha correta. Isso protege o conteúdo contra acesso não autorizado.

## Por que usar Aspose.Zip para proteger diretórios com senha no .NET?
Aspose.Zip oferece uma API simples e de alto desempenho que suporta **c# zip password protection**, criptografia tradicional ZipCrypto e criptografia AES. Ela lida eficientemente com diretórios grandes e integra‑se perfeitamente a qualquer projeto .NET.

## Pré‑requisitos
- Conhecimento básico de programação em C#.  
- Visual Studio (qualquer edição recente).  
- Biblioteca Aspose.Zip para .NET – faça o download **[aqui](https://releases.aspose.com/zip/net/)**.  
- Uma pasta no disco que você deseja proteger com senha.

## Importar Namespaces
Adicione os namespaces necessários ao seu arquivo C# para que o compilador saiba onde encontrar as classes Aspose.Zip.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Passo 1: Definir o caminho para o diretório de recursos
Defina o caminho que aponta para o diretório que você pretende compactar e proteger.

```csharp
string dataDir = "Your Document Directory";
```

## Passo 2: Proteger o diretório com senha
Use `TraditionalEncryptionSettings` para especificar a senha e criar o arquivo compactado criptografado. Este é o núcleo da **c# zip password protection**.

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## Passo 3: Explicação do código
- **Criando o arquivo de saída:** `File.Open(..., FileMode.Create)` abre (ou cria) o arquivo ZIP que conterá os dados criptografados.  
- **Selecionando a pasta de origem:** `new DirectoryInfo(".\\CanterburyCorpus")` indica ao Aspose.Zip qual diretório compactar.  
- **Aplicando a senha:** `new TraditionalEncryptionSettings("p@s$")` define a senha que protegerá o arquivo.  
- **Adicionando entradas e salvando:** `archive.CreateEntries(corpus)` adiciona cada arquivo da pasta, e `archive.Save(zipFile)` grava o ZIP criptografado no disco.

## Como alterar a senha do zip posteriormente?
Se precisar **alterar a senha do zip**, basta recriar o arquivo compactado com uma nova instância de `TraditionalEncryptionSettings` que contenha a nova senha e salvá‑lo novamente.

## Problemas comuns e dicas
- **Pastas grandes:** Aspose.Zip transmite os dados, de modo que o uso de memória permanece baixo mesmo para diretórios enormes.  
- **Complexidade da senha:** Use uma senha forte (misture letras, números e símbolos) para melhorar a segurança.  
- **Erros de licença:** Certifique‑se de que aplicou um arquivo de licença válido; caso contrário, a biblioteca funciona em modo de avaliação com limitações.

## Frequently Asked Questions

### O Aspose.Zip para .NET é adequado para diretórios grandes?
Sim, o Aspose.Zip para .NET foi projetado para lidar eficientemente com diretórios grandes, oferecendo desempenho ideal.

### Posso alterar a senha de um diretório já protegido?
Sim, você pode modificar a senha ajustando o `TraditionalEncryptionSettings` no código conforme necessário.

### Existem requisitos de licenciamento para usar Aspose.Zip para .NET?
Sim, uma licença válida é necessária para usar o Aspose.Zip para .NET em um ambiente de produção. Você pode obter uma licença **[aqui](https://purchase.aspose.com/buy)**.

### Existe uma versão de avaliação gratuita disponível para Aspose.Zip para .NET?
Sim, você pode acessar uma avaliação gratuita **[aqui](https://releases.aspose.com/)**.

### Onde posso encontrar suporte adicional para Aspose.Zip para .NET?
Você pode visitar o **[fórum Aspose.Zip](https://forum.aspose.com/c/zip/37)** para obter suporte ou tirar dúvidas.

---

**Última atualização:** 2025-12-21  
**Testado com:** Aspose.Zip for .NET (latest release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}