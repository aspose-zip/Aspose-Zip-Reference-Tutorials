---
date: 2026-02-17
description: Узнайте, как создавать ZIP‑архивы без сжатия и извлекать несколько ZIP‑файлов
  с помощью Aspose.Zip для .NET. Это руководство охватывает, как открыть ZIP, прочитать
  запись ZIP и шаги извлечения ZIP на C#.
linktitle: Decompressing a Stored File
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Создание ZIP без сжатия и распаковка файлов – Aspose.Zip
url: /ru/net/file-decompression/decompress-stored-file/
weight: 13
---

 Ensure no extra explanations.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Разархивирование сохранённого файла с помощью Aspose.Zip для .NET

## Introduction

В современных приложениях .NET **create zip without compression** — полезная техника, когда требуется быстрое архивирование без накладных расходов на сжатие данных. Aspose.Zip для .NET упрощает как создание таких архивов, так и последующее **extract multiple zip files**. В этом руководстве вы увидите, как открыть zip‑файл, прочитать данные zip‑записи и выполнить операцию **C# extract zip** шаг за шагом.

## Quick Answers
- **What is “create zip without compression”?** Это добавление файлов в ZIP‑архив методом «store», при котором данные остаются неизменными.  
- **Which library handles this in .NET?** Aspose.Zip for .NET.  
- **Do I need a license to run the sample?** Бесплатная пробная версия подходит для разработки; для продакшна требуется коммерческая лицензия.  
- **Can I extract several files at once?** Да — в руководстве показано, как **extract multiple zip files** в цикле.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is “create zip without compression”?

При создании ZIP‑архива методом **store** каждый файл добавляется в архив в исходном виде. Это приводит к большему размеру архива по сравнению с сжатыми ZIP‑файлами, но операция выполняется гораздо быстрее, а оригинальные байты файлов остаются нетронутыми — идеально для сценариев, где важнее скорость или целостность данных, чем размер.

## Understanding the zip compression method store

**zip compression method store** (также называемый «store») указывает формату ZIP пропустить любой шаг по уменьшению данных. Aspose.Zip предоставляет этот метод через перечисление `CompressionMethod.Store`, позволяя явно выбрать его для каждой записи. Использование метода store особенно удобно, когда вы работаете с уже сжатыми медиа‑файлами (например, JPEG, MP3), где дополнительное сжатие не дает выгоды.

## Why use Aspose.Zip for .NET?

- **Full control** над уровнем сжатия (store vs. deflate).  
- **Simple API** для чтения записей, открытия zip‑файлов и извлечения данных.  
- **Cross‑platform** поддержка .NET Framework, .NET Core и .NET 5+.  
- **Built‑in handling** больших архивов без загрузки всего в память.

## Prerequisites

Перед тем как приступить к руководству, убедитесь, что у вас есть следующее:

- Aspose.Zip for .NET Library: Скачайте и установите библиотеку Aspose.Zip for .NET. Вы можете найти библиотеку [здесь](https://releases.aspose.com/zip/net/).

- Document Directory: Создайте каталог в системе, где будут храниться необходимые файлы для этого руководства.

## Import Namespaces

Для начала импортируем необходимые пространства имён в наш проект:

```csharp
using Aspose.Zip;
using System.IO;
```

## How to Create Zip Without Compression

Сначала нам нужен ZIP‑архив, использующий метод **store** (т.е. без сжатия). Приведённый ниже пример кода создаёт такой архив и предоставляется Aspose.Zip как вспомогательный метод. При выполнении будет сгенерирован файл `StoreMultipleFilesWithoutCompression_out.zip` в вашем каталоге документов.

```csharp
StoreMultipleFilesWithoutCompression.Run();
```

> **Pro tip:** Вспомогательный метод внутри устанавливает `CompressionMethod.Store` для каждой записи, гарантируя, что архив создаётся без какого‑либо сжатия данных.

## How to Open Zip and Extract Multiple Files

Теперь, когда у нас есть сохранённый ZIP, посмотрим, **how to open zip** и извлечём файлы.

### Step 2.1: Opening the Zip File

```csharp
string dataDir = "Your Document Directory";

using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Open))
{
    using (Archive archive = new Archive(zipFile))
    {
```

Объект `Archive` представляет открытый ZIP и даёт доступ к каждой записи через коллекцию `Entries`.

### Step 2.2: Creating Extracted Files

```csharp
        using (var extracted = File.Create(dataDir + "alice_extracted_store_out.txt"))
        {
            using (var decompressed = archive.Entries[0].Open())
            {
                byte[] buffer = new byte[8192];
                int bytesRead;

                // Reading from decompressed stream to extracting file.
                while (0 < (bytesRead = decompressed.Read(buffer, 0, buffer.Length)))
                {
                    extracted.Write(buffer, 0, bytesRead);
                }
            }
        }
```

Здесь мы **read zip entry** 0, копируем её байты в новый файл и автоматически закрываем потоки благодаря оператору `using`.

### Step 2.3: Repeating the Process for Another File

```csharp
        using (var extracted = File.Create(dataDir + "asyoulik_extracted_store_out.txt"))
        {
            using (var decompressed = archive.Entries[1].Open())
            {
                byte[] buffer = new byte[8192];
                int bytesRead;

                // Reading from decompressed stream to extracting file.
                while (0 < (bytesRead = decompressed.Read(buffer, 0, buffer.Length)))
                {
                    extracted.Write(buffer, 0, bytesRead);
                }
            }
        }
    }
}
```

Итерируя `archive.Entries`, вы можете **extract multiple zip files** (или несколько записей) всего несколькими строками кода.

## Common Issues and Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| `FileNotFoundException` when opening the ZIP | Неправильный путь `dataDir` | Убедитесь, что `dataDir` заканчивается слешем, или используйте `Path.Combine`. |
| Extracted file is empty | Буфер не был сброшен | Блок `using` автоматически сбрасывает; убедитесь, что читаете поток до тех пор, пока `bytesRead` не станет 0 (как показано). |
| License exception | Запуск без действующей лицензии | Примените пробную или постоянную лицензию перед развертыванием. |

## Frequently Asked Questions

### Q1: Is Aspose.Zip for .NET compatible with all .NET frameworks?

**A:** Да, Aspose.Zip for .NET разработан так, чтобы быть совместимым с различными версиями .NET, предоставляя гибкость разработчикам.

### Q2: Can I use Aspose.Zip for .NET in both commercial and non‑commercial projects?

**A:** Да, Aspose.Zip for .NET можно использовать как в коммерческих, так и в некоммерческих проектах. Смотрите детали лицензирования на [purchase page](https://purchase.aspose.com/buy).

### Q3: How can I get support for Aspose.Zip for .NET?

**A:** Для поддержки посетите [Aspose.Zip forum](https://forum.aspose.com/c/zip/37), где сообщество разработчиков и экспертов поможет вам.

### Q4: Is there a free trial available for Aspose.Zip for .NET?

**A:** Да, вы можете изучить возможности Aspose.Zip for .NET, получив бесплатную пробную версию [здесь](https://releases.aspose.com/).

### Q5: Can I obtain a temporary license for testing purposes?

**A:** Да, временную лицензию для тестирования можно получить, перейдя по [this link](https://purchase.aspose.com/temporary-license/).

### Q6: How do I read a zip entry without extracting the whole archive?

**A:** Используйте `archive.Entries[index].Open()` для получения потока конкретной записи, затем прочитайте нужные байты, как показано в коде выше.

### Q7: What is the best way to **extract multiple zip files** in a loop?

**A:** Итерируйте `archive.Entries` с помощью `foreach`, открывая поток каждой записи и записывая его в целевой файл, аналогично шаблону, показанному в Шаге 2.2 и 2.3.

## Conclusion

Освоение **create zip without compression** и последующего процесса извлечения критически важно для высокопроизводительных .NET‑приложений. Aspose.Zip for .NET предоставляет чистый, интуитивный API для **how to open zip**, чтения каждой **zip entry** и выполнения операции **C# extract zip** с минимальным объёмом кода. Следуя этому руководству, вы научились генерировать архив без сжатия, открывать его и эффективно извлекать содержимое.

---

**Last Updated:** 2026-02-17  
**Tested With:** Aspose.Zip for .NET 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}