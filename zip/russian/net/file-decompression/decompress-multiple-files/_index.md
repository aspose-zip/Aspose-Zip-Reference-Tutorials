---
title: Распаковка нескольких файлов с помощью Aspose.Zip для .NET
linktitle: Распаковка нескольких файлов
second_title: Aspose.Zip .NET API для сжатия и архивирования файлов
description: Узнайте, как распаковать несколько файлов с помощью Aspose.Zip для .NET. Следуйте нашему пошаговому руководству для эффективного управления файлами.
weight: 11
url: /ru/net/file-decompression/decompress-multiple-files/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Распаковка нескольких файлов с помощью Aspose.Zip для .NET

## Введение

Добро пожаловать в наше подробное руководство по распаковке нескольких файлов с помощью Aspose.Zip для .NET! Если вы хотите эффективно обрабатывать сжатые файлы, содержащие несколько записей, вы попали по адресу. В этом руководстве мы шаг за шагом проведем вас через весь процесс, используя Aspose.Zip для .NET.

## Предварительные условия

Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:

-  Aspose.Zip для .NET: убедитесь, что у вас установлена библиотека Aspose.Zip для .NET. Вы можете скачать его[здесь](https://releases.aspose.com/zip/net/).

- Каталог документов: установите каталог, в котором будут храниться ваши документы. Вы будете использовать его в качестве базового каталога в коде.

Теперь давайте начнем с пошагового руководства.

## Импортировать пространства имен

В вашем проекте .NET начните с импорта необходимых пространств имен для Aspose.Zip:

```csharp
using Aspose.Zip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Шаг 1. Сжатие нескольких файлов

Чтобы распаковать несколько файлов, сначала вам понадобится сжатый файл с несколькими записями. Давайте создадим один:

```csharp
string dataDir = "Your Document Directory";

// Запустите метод сжатия
CompressMultipleFiles.Run();
```

## Шаг 2. Распаковка файлов

Теперь давайте шаг за шагом распакуем файлы:

### Шаг 2.1: Открытие сжатого файла

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressMultipleFiles_out.zip", FileMode.Open))
{
    // ...
}
```

### Шаг 2.2. Листинг записей и отслеживание прогресса

```csharp
StringBuilder sb = new StringBuilder("Entries are: ");
int percentReady = 0;

using (Archive archive = new Archive(zipFile, new ArchiveLoadOptions()
{
    EntryListed = (s, e) => { sb.AppendFormat("{0}, ", e.Entry.Name); },
    EntryExtractionProgressed = (s, e) =>
    {
        int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
        if (percent > percentReady)
        {
            Console.WriteLine(string.Format("{0}% compressed", percent));
            percentReady = percent;
        }
    }
}))
{
    Console.WriteLine(sb.ToString(0, sb.Length - 2));
```

### Шаг 2.3: Извлечение первой записи

```csharp
using (var extracted = File.Create(dataDir + "alice_extracted_out.txt"))
{
    using (var decompressed = archive.Entries[0].Open())
    {
        // Чтение и запись данных из распакованного потока в извлекаемый файл.
    }
}
```

### Шаг 2.4: Извлечение второй записи

```csharp
archive.Entries[1].Extract(dataDir + "asyoulik_extracted_out.txt");
```

И вот оно! Вы успешно распаковали несколько файлов с помощью Aspose.Zip для .NET.

## Заключение

В этом руководстве мы рассмотрели основные шаги по распаковке нескольких файлов с помощью Aspose.Zip для .NET. Следуя этому руководству, вы сможете легко и эффективно управлять сжатыми файлами.

## Часто задаваемые вопросы

### Вопрос 1: Могу ли я использовать Aspose.Zip для .NET как в коммерческих, так и в личных проектах?

 О1: Да, Aspose.Zip для .NET можно использовать как в коммерческих, так и в личных проектах. Подробную информацию о лицензировании см.[Информация о лицензировании Aspose](https://purchase.aspose.com/buy).

### Вопрос 2. Существует ли бесплатная пробная версия Aspose.Zip для .NET?

 О2: Да, вы можете попробовать бесплатную пробную версию Aspose.Zip для .NET.[здесь](https://releases.aspose.com/zip/net).

### Вопрос 3. Где я могу найти дополнительную поддержку Aspose.Zip для .NET?

 A3: Посетите[Форум Aspose.Zip](https://forum.aspose.com/c/zip/37) за поддержку сообщества и обсуждения.

### Вопрос 4: Как приобрести временную лицензию на Aspose.Zip для .NET?

 A4: Получите временную лицензию на Aspose.Zip для .NET.[здесь](https://purchase.aspose.com/temporary-license/).

### Вопрос 5: Существуют ли какие-либо особые системные требования для использования Aspose.Zip для .NET?

 A5: См.[документация](https://reference.aspose.com/zip/net/) подробные системные требования.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
