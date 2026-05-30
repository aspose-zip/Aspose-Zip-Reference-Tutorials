---
date: 2026-05-30
description: Aprenda a compactar pastas com Aspose.Zip para .NET, criar arquivos zip
  de forma eficiente e reduzir o espaço de armazenamento em suas aplicações .NET.
keywords:
- how to zip folder
- create zip archive
- zip multiple folders
- add password zip
- set compression level
linktitle: Como Compactar uma Pasta
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  headline: How to Zip Folder Using Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to zip folder with Aspose.Zip for .NET, create zip archive
    .net efficiently, and reduce storage space in your .NET applications.
  name: How to Zip Folder Using Aspose.Zip for .NET
  steps:
  - name: Initialize Your Document Directory
    text: Set the variable `dataDir` to the path of the directory you want to compress.
  - name: Create Output Zip Files
    text: Open two `FileStream` objects for the output ZIP files. This shows how you
      can generate more than one archive from the same source—useful for versioned
      backups.
  - name: Compress the Directory
    text: The `Archive` class represents a ZIP archive and provides methods to add
      entries and save the file. Use it to add every entry from the target folder.
      The example uses a sample folder named **CanterburyCorpus**, but you can point
      it to any directory. > **Pro tip:** If you need to **create zip archive
  type: HowTo
- questions:
  - answer: Yes. Set `archive.Password = "yourPassword";` before calling `Save`.
    question: Can I add a password to the ZIP archive?
  - answer: Filter the `DirectoryInfo` collection with `GetFiles("*.txt")` or similar
      before calling `CreateEntries`.
    question: How do I include only certain file types?
  - answer: Aspose.Zip supports incremental updates via `Archive.UpdateEntry`.
    question: Is there a way to update an existing ZIP without recreating it?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Como Compactar Pasta Usando Aspose.Zip para .NET
url: /pt/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Compactar Pasta Usando Aspose.Zip para .NET

Neste tutorial você descobrirá **como compactar pasta** de forma rápida e confiável com Aspose.Zip para .NET. Seja construindo um utilitário desktop, um serviço baseado em nuvem ou um script de backup automatizado, comprimir uma pasta em um arquivo ZIP pode reduzir drasticamente os requisitos de armazenamento e acelerar as transferências de rede. Percorreremos cada passo, explicaremos por que cada linha importa e destacaremos armadilhas comuns para que você possa aplicar a técnica com confiança.

## Respostas rápidas
- **O que o Aspose.Zip faz?** Ele fornece uma API .NET simples para criar e extrair arquivos ZIP sem dependências externas.  
- **Quanto tempo leva a implementação?** Normalmente menos de 10 minutos para uma compressão básica de pasta.  
- **Quais versões do .NET são suportadas?** .NET Framework 2.0‑4.8.1, .NET Core 2.0‑3.1 e .NET 5‑10.  
- **Preciso de licença para produção?** Sim, uma licença comercial é necessária para uso em produção.  
- **Posso comprimir várias pastas ao mesmo tempo?** Absolutamente—use o método `CreateEntries` em qualquer coleção `DirectoryInfo` para **compactar várias pastas** em uma única execução.  

`CreateEntries` adiciona todos os arquivos de um diretório ao arquivo.

## O que é “como compactar pasta”?

Compactar uma pasta significa pegar cada arquivo e sub‑pasta dentro de um diretório especificado e empacotá‑los em um único arquivo ZIP. Isso reduz o tamanho total, preserva a hierarquia original e facilita a transferência ou armazenamento dos dados. O ZIP resultante pode ser aberto em qualquer plataforma sem software especial, e mantém a estrutura de pastas para que, ao ser extraído, o layout original seja restaurado exatamente como era.

## Por que usar Aspose.Zip para esta tarefa?

Aspose.Zip permite **criar arquivos zip** diretamente a partir de código .NET com uma API consistente em todos os runtimes suportados. Carregue a classe `Archive`, adicione entradas, defina `CompressionLevel`, opcionalmente atribua uma senha e chame `Save`. A biblioteca processa pastas contendo milhares de arquivos em menos de um segundo em hardware típico, e suporta mais de 50 formatos de compressão diferentes e algoritmos de criptografia.

## Pré‑requisitos

- **Aspose.Zip para .NET** – faça o download [aqui](https://releases.aspose.com/zip/net/) ou [aqui](https://releases.aspose.com/zip/net).  
- **Ambiente de Desenvolvimento** – Visual Studio, Rider ou qualquer IDE que suporte C#.  
- **Diretório de Documentos** – substitua `"Your Document Directory"` no código pelo caminho da pasta que deseja comprimir.  
- **Documentação de Referência** – consulte os documentos oficiais [aqui](https://reference.aspose.com/zip/net/).

## Importar Namespaces

Comece importando os namespaces necessários. Eles dão acesso às classes principais de compressão.

```csharp
using Aspose.Zip;
using System.IO;
```

## Como Compactar Pasta com Aspose.Zip

A seguir, um exemplo simples que demonstra **como compactar pasta**. O mesmo padrão pode ser estendido para **compactar vários arquivos .net** ou para criar estruturas de arquivo personalizadas.

### Etapa 1: Inicializar Seu Diretório de Documentos

Defina a variável `dataDir` para o caminho do diretório que você deseja comprimir.

```csharp
string dataDir = "Your Document Directory";
```

### Etapa 2: Criar Arquivos ZIP de Saída

Abra dois objetos `FileStream` para os arquivos ZIP de saída. Isso mostra como gerar mais de um arquivo a partir da mesma fonte—útil para backups versionados.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### Etapa 3: Compactar o Diretório

A classe `Archive` representa um arquivo ZIP e fornece métodos para adicionar entradas e salvar o arquivo. Use‑a para adicionar cada entrada da pasta de destino. O exemplo usa uma pasta de amostra chamada **CanterburyCorpus**, mas você pode apontar para qualquer diretório.

```csharp
        using (Archive archive = new Archive())
        {
            DirectoryInfo corpus = new DirectoryInfo(dataDir + "CanterburyCorpus");
            archive.CreateEntries(corpus);
            archive.Save(zipFile);
            archive.Save(zipFile2);
        }
    }
}
```

> **Dica profissional:** Se precisar **criar zip archive .net** com um nível de compressão específico, defina `archive.CompressionLevel` antes de chamar `Save`.

## Problemas comuns e soluções

| Sintoma | Causa Provável | Correção |
|---------|----------------|----------|
| Arquivo ZIP vazio | `dataDir` aponta para a pasta errada ou falta a barra final | Verifique o caminho e assegure que a pasta contém arquivos |
| `UnauthorizedAccessException` | Aplicação não tem permissões de sistema de arquivos | Execute o Visual Studio como administrador ou conceda direitos de leitura/gravação |
| Uso elevado de memória para diretórios enormes | Carregando todas as entradas na memória de uma vez | Use `Archive.CreateEntryFromFile` em um loop para transmitir os arquivos individualmente |

## Perguntas Frequentes (Adicionais)

**Q: Posso adicionar uma senha ao arquivo ZIP?**  
A: Sim. Defina `archive.Password = "yourPassword";` antes de chamar `Save`.

**Q: Como incluir apenas certos tipos de arquivo?**  
A: Filtre a coleção `DirectoryInfo` com `GetFiles("*.txt")` ou similar antes de chamar `CreateEntries`.

**Q: Existe uma forma de atualizar um ZIP existente sem recriá‑lo?**  
A: Aspose.Zip suporta atualizações incrementais via `Archive.UpdateEntry`.

## Perguntas Frequentes

### Q1: Posso usar Aspose.Zip para .NET em projetos comerciais e pessoais?

A1: Sim, Aspose.Zip para .NET está licenciado para uso comercial e pessoal.

### Q2: Há uma versão de teste gratuita disponível?

A2: Sim, você pode explorar uma avaliação gratuita [aqui](https://releases.aspose.com/zip/net).

### Q3: Como obtenho suporte para Aspose.Zip para .NET?

A3: Visite o [forum Aspose.Zip](https://forum.aspose.com/c/zip/37) para suporte da comunidade ou considere adquirir uma [licença temporária](https://purchase.aspose.com/temporary-license/) para assistência dedicada.

### Q4: Existem outros exemplos e tutoriais disponíveis?

A4: Sim, a [documentação](https://reference.aspose.com/zip/net/) contém exemplos e tutoriais abrangentes.

### Q5: Posso comprar Aspose.Zip para .NET?

A5: Certamente, você pode fazer a compra [aqui](https://purchase.aspose.com/buy).

## Conclusão

Agora você tem um padrão completo e pronto para produção de **como compactar pasta** usando Aspose.Zip para .NET. Ao aproveitar a classe `Archive` da biblioteca, você pode **criar arquivos zip**, definir um `CompressionLevel` personalizado, adicionar proteção por senha e até **compactar várias pastas** em uma única passagem—tornando‑a ideal para automatizar tarefas de backup de pastas. Experimente a API para adicionar criptografia, dividir arquivos ou transmitir diretamente para armazenamento em nuvem, e terá uma solução robusta para qualquer necessidade de compressão baseada em .NET.

---

**Última atualização:** 2026-05-30  
**Testado com:** Aspose.Zip 24.11 para .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [compactar vários arquivos c# – Compressão sem esforço com Aspose.Zip para .NET](/zip/net/file-compression/compress-multiple-files/)
- [Aspose.Zip para .NET - Proteger Arquivo Zip com Senha & Armazenar Vários Arquivos Sem Compressão](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [Como Compactar Pasta – Compactar Diretório com Aspose.Zip](/zip/net/directory-and-folder-compression/decompress-folder/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}