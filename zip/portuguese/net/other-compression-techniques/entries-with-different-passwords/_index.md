---
date: 2025-12-18
description: Aprenda a criptografar arquivos zip com diferentes senhas usando Aspose.Zip
  para .NET. Este guia mostra como compactar arquivos com senhas e criar um arquivo
  7z em C#.
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Como criptografar arquivos ZIP com senhas diferentes no Aspose.Zip para .NET
url: /pt/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Criptografar Arquivos ZIP com Senhas Diferentes no Aspose.Zip para .NET

## Introdução

Se você precisa **how to encrypt zip** arquivos enquanto atribui a cada entrada sua própria senha, você está no lugar certo. Neste tutorial vamos percorrer os passos exatos para criar um arquivo 7‑zip onde cada arquivo está protegido com uma senha única, usando a biblioteca Aspose.Zip para .NET. Ao final, você entenderá por que a criptografia por entrada é importante, como configurá‑la e como verificar o resultado em seus próprios projetos.

## Respostas Rápidas
- **O que significa “encrypt zip”?** Significa aplicar proteção baseada em senha (AES ou ZipCrypto) ao conteúdo de um arquivo ZIP/7z.  
- **Cada entrada pode ter uma senha diferente?** Sim—Aspose.Zip permite atribuir senhas distintas por arquivo.  
- **Quais versões do .NET são suportadas?** Todas as versões modernas do .NET Framework, .NET Core e .NET 5/6.  
- **Preciso de licença para produção?** Uma licença comercial é necessária para uso em produção; uma avaliação gratuita está disponível.  
- **Qual formato de compressão é usado no exemplo?** O exemplo cria um arquivo 7z com criptografia AES‑256.

## O que é “how to encrypt zip” com Aspose.Zip?

Criptografar um arquivo ZIP (ou 7z) significa proteger suas entradas para que não possam ser abertas sem a senha correta. Aspose.Zip para .NET suporta tanto o clássico ZipCrypto quanto a criptografia AES mais forte, e permite especificar configurações de criptografia por entrada, oferecendo controle granular sobre a segurança.

## Por que usar senhas diferentes para cada entrada?

- **Segmentação de segurança:** Se uma senha for comprometida, os demais arquivos permanecem protegidos.  
- **Conformidade regulatória:** Algumas indústrias exigem credenciais separadas para diferentes categorias de dados.  
- **Acesso específico por usuário:** Você pode distribuir um único arquivo para vários usuários, cada um desbloqueando apenas os arquivos que tem permissão para ver.

## Pré-requisitos

Antes de começarmos, certifique-se de que você tem:

- **Aspose.Zip for .NET** instalado – veja a [documentação](https://reference.aspose.com/zip/net/) oficial para instruções de download e instalação.  
- Uma pasta na sua máquina onde você armazenará os arquivos de origem (o “Document Directory”).  
- Familiaridade básica com C# e Visual Studio (ou sua IDE .NET preferida).

## Importar Namespaces

Começamos importando os namespaces que contêm as classes que precisaremos.

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Etapa 1: Defina Seu Document Directory

Defina o caminho que contém os arquivos que você deseja arquivar.

```csharp
string dataDir = "Your Document Directory";
```

## Etapa 2: Crie Entradas com Senhas Diferentes

Aqui está o núcleo do tutorial. Abrimos um novo arquivo 7z, criamos três objetos `FileInfo` e adicionamos cada um como uma entrada com sua própria senha AES.

```csharp
//ExStart: EntriesWithDifferentPasswords
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    FileInfo fi1 = new FileInfo("data1.bin");
    FileInfo fi2 = new FileInfo("data2.bin");
    FileInfo fi3 = new FileInfo("data3.bin");

    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", fi1, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.CreateEntry("entry2.bin", fi2, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test2")));
        archive.CreateEntry("entry3.bin", fi3, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test3")));
        
        archive.Save(sevenZipFile);
    }
}
//ExEnd: EntriesWithDifferentPasswords
```

### Como Isso Funciona

- `SevenZipArchive` é o contêiner para um arquivo 7‑z.  
- `CreateEntry` recebe o nome da entrada, o arquivo de origem, um sinalizador de sobrescrita e um objeto `SevenZipEntrySettings`.  
- Dentro de `SevenZipEntrySettings` fornecemos dois objetos de configuração: um para compressão (`SevenZipStoreCompressionSettings`) e outro para criptografia (`SevenZipAESEncryptionSettings`).  
- Cada chamada fornece uma **senha diferente** (`"test1"`, `"test2"`, `"test3"`), alcançando proteção por entrada.

## Etapa 3: Verificação

Depois que o arquivo for salvo, você pode exibir uma mensagem simples de confirmação.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Execute o programa e, em seguida, tente abrir `archive.7z` com uma ferramenta como 7‑Zip. Ela solicitará uma senha para cada entrada, confirmando que as senhas são realmente distintas.

## Problemas Comuns e Soluções

| Problema | Motivo | Correção |
|----------|--------|----------|
| **Erro de senha incorreta** | A string da senha contém espaços extras ou caracteres invisíveis. | Remova espaços extras das strings de senha (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Arquivo não abre em ferramentas antigas** | Algumas ferramentas ZIP legadas não suportam a criptografia AES‑256 usada pelo 7z. | Use um extrator moderno (7‑Zip 19.00+). |
| **Arquivo não adicionado ao archive** | O caminho do arquivo de origem está errado ou o arquivo não existe. | Verifique `dataDir` e os nomes dos arquivos, ou use `Path.Combine(dataDir, "data1.bin")`. |

## Perguntas Frequentes

### Q1: O Aspose.Zip para .NET é compatível com todas as versões do .NET?

A1: Sim, o Aspose.Zip para .NET foi projetado para integrar-se perfeitamente com todas as versões do framework .NET.

### Q2: Posso usar o Aspose.Zip para .NET em meus projetos comerciais?

A2: Absolutamente! O Aspose.Zip para .NET oferece licenças comerciais, e você pode encontrar mais informações sobre como comprar [aqui](https://purchase.aspose.com/buy).

### Q3: Existe uma avaliação gratuita disponível?

A3: Sim, você pode explorar os recursos do Aspose.Zip para .NET com uma avaliação gratuita. Comece [aqui](https://releases.aspose.com/).

### Q4: Como posso obter suporte para o Aspose.Zip para .NET?

A4: Para quaisquer dúvidas ou assistência, visite o [Fórum Aspose.Zip](https://forum.aspose.com/c/zip/37).

### Q5: Posso usar o Aspose.Zip para .NET sem uma licença permanente?

A5: Sim, você pode obter uma licença temporária para suas necessidades de curto prazo. Encontre mais detalhes [aqui](https://purchase.aspose.com/temporary-license/).

## Conclusão

Você acabou de aprender **how to encrypt zip** arquivos com senhas por entrada usando Aspose.Zip para .NET. Essa técnica oferece a flexibilidade de proteger cada arquivo individualmente, atendendo a requisitos de segurança mais rigorosos e simplificando a distribuição específica por usuário. Sinta-se à vontade para experimentar outras configurações de compressão, conjuntos de arquivos maiores ou integrar essa lógica em um serviço web que gera arquivos seguros sob demanda.

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Zip for .NET 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}