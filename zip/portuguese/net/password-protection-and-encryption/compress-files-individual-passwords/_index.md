---
date: 2026-03-02
description: Aprenda a criar um arquivo zip protegido por senha e compactar arquivos
  com senhas no .NET usando Aspose.Zip. Siga nosso guia passo a passo.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Criar um Arquivo ZIP Protegido por Senha no .NET com Aspose.Zip
url: /pt/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar um Arquivo ZIP Protegido por Senha em .NET com Aspose.Zip

## Introdução

Quando você precisa compartilhar dados sensíveis, um **arquivo zip protegido por senha** é uma das maneiras mais simples e eficazes de manter as informações seguras. Em aplicações .NET, o Aspose.Zip facilita **compactar arquivos com senhas**, atribuindo a cada arquivo sua própria chave de criptografia. Neste tutorial você aprenderá exatamente como criar esse tipo de arquivo, por que isso é importante e onde pode aplicá‑lo em projetos do mundo real.

## Respostas Rápidas
- **Qual biblioteca devo usar?** Aspose.Zip para .NET fornece suporte nativo a senhas por arquivo e múltiplos métodos de criptografia.  
- **Quantas linhas de código?** Cerca de 30 linhas, incluindo configuração e gravação do arquivo.  
- **Cada arquivo pode ter uma senha diferente?** Sim – você pode atribuir uma senha única a cada entrada.  
- **Quais métodos de criptografia estão disponíveis?** ZipCrypto tradicional, AES‑128 e AES‑256.  
- **Preciso de licença para produção?** Uma licença comercial é necessária para uso em produção; há uma versão de avaliação gratuita.

## O que é um arquivo zip protegido por senha?
Um arquivo zip protegido por senha é um arquivo compactado (ZIP) que requer uma senha para extrair seu conteúdo. A senha pode proteger todo o arquivo ou entradas individuais, e algoritmos modernos como AES‑128/256 fornecem criptografia forte.

## Por que compactar arquivos com senhas usando Aspose.Zip?
- **Segurança granular** – atribua uma senha distinta por arquivo, ideal para cenários multi‑tenant.  
- **Múltiplos padrões de criptografia** – escolha entre o legado ZipCrypto e o robusto AES.  
- **Sem ferramentas externas** – tudo é tratado programaticamente dentro do seu código .NET.  
- **Desempenho** – compressão rápida com Deflate mantendo o tamanho do arquivo pequeno.

## Pré‑requisitos

Antes de começar, verifique se você tem:

- **Aspose.Zip para .NET** – instale a biblioteca no seu projeto. Documentação detalhada está disponível [aqui](https://reference.aspose.com/zip/net/).  
- **Baixe o pacote mais recente** se ainda não o fez, a partir deste [link](https://releases.aspose.com/zip/net/).  
- Uma pasta contendo os arquivos que você deseja compactar.

## Importar Namespaces

Adicione os namespaces necessários no topo do seu arquivo C#:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Etapa 1: Definir o Caminho do Diretório de Recursos

Aponte o código para a pasta que contém os arquivos de origem:

```csharp
string dataDir = "Your Document Directory";
```

## Etapa 2: Compactar Arquivos com Senhas Individuais

Agora criaremos um **arquivo zip protegido por senha** onde cada arquivo usa sua própria senha e método de criptografia. O exemplo usa três arquivos de amostra (`alice29.txt`, `asyoulik.txt` e `fields.c`) com senhas diferentes.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### Como funciona
- **CreateEntry** adiciona um arquivo ao arquivo zip.  
- O quarto argumento (`ArchiveEntrySettings`) permite especificar tanto a compressão (`DeflateCompressionSettings`) quanto a criptografia (`TraditionalEncryptionSettings` ou `AesEcryptionSettings`).  
- Ao passar uma string de senha diferente para cada entrada, você obtém um **arquivo zip protegido por senha** onde cada arquivo só pode ser desbloqueado com sua própria chave.

## Problemas Comuns & Solução de Problemas

| Sintoma | Causa Provável | Solução |
|---------|----------------|--------|
| Falha na extração com “Wrong password” | Incompatibilidade de senha ou método de criptografia incorreto | Verifique a senha exata e assegure‑se de usar o mesmo `EncryptionMethod` ao extrair. |
| O tamanho do arquivo é maior que o esperado | Uso de AES‑256 em arquivos de texto pequenos pode acrescentar sobrecarga | Para arquivos pequenos, AES‑128 pode ser suficiente e gera um arquivo menor. |
| Exceção em tempo de execução ao chamar `archive.Save` | Falta de permissão de gravação na pasta de destino | Garanta que a aplicação tenha acesso de escrita a `dataDir` ou use outro caminho de saída. |

## Perguntas Frequentes (FAQs)

### Posso usar diferentes métodos de criptografia para cada arquivo?
Sim, o Aspose.Zip para .NET permite combinar métodos de criptografia — ZipCrypto tradicional, AES‑128 e AES‑256 — em nível de arquivo.

### Existe uma versão de avaliação disponível?
Sim, você pode acessar a avaliação gratuita do Aspose.Zip para .NET [aqui](https://releases.aspose.com/).

### Como obter suporte caso eu encontre problemas?
Visite o [fórum Aspose.Zip](https://forum.aspose.com/c/zip/37) para obter ajuda da comunidade e do suporte da Aspose.

### Onde encontrar documentação detalhada do Aspose.Zip para .NET?
A documentação está disponível [aqui](https://reference.aspose.com/zip/net/).

### Posso adquirir uma licença temporária para fins de teste?
Sim, você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2026-03-02  
**Testado com:** Aspose.Zip para .NET (última versão)  
**Autor:** Aspose  

---