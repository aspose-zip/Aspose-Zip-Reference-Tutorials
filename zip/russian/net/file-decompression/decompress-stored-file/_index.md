---
date: 2025-12-16
description: Узнайте, как создать zip‑архив без сжатия и извлекать несколько zip‑файлов
  с помощью Aspose.Zip для .NET. Это руководство охватывает открытие zip‑архива, чтение
  его записей и шаги извлечения zip‑файла на C#.
linktitle: Decompressing a Stored File
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Создание ZIP без сжатия и распаковка файлов – Aspose.Zip
url: /ru/net/file-decompression/decompress-stored-file/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Распаковка сохранённого файла с помощью Aspose.Zip для .NET

## Введение

В современных приложениях .NET **create zip without compression** — полезная техника, когда требуется быстрое архивирование без накладных расходов на сжатие данных. Aspose.Zip для .NET упрощает как создание таких архивов, так и последующее **extract multiple zip files**. В этом руководстве вы увидите, как открыть zip‑файл, прочитать данные zip‑записи и выполнить операцию **C# extract zip** шаг за шагом.

## Быстрые ответы
- **What is “create zip without compression”?** Это добавление файлов в ZIP‑архив методом «store», при котором данные остаются неизменными.
- **Which library handles this in .NET?** Aspose.Zip for .NET.
- **Do I need a license to run the sample?** Бесплатная пробная версия подходит для разработки; для продакшна требуется коммерческая лицензия.
- **Can I extract several files at once?** Да — в руководстве показано, как **extract multiple zip files** в цикле.
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Что такое “create zip without compression”?
При создании ZIP‑архива методом **store** каждый файл добавляется в архив в точности в том виде, в каком он есть. Это приводит к большему размеру архива по сравнению с сжатыми ZIP‑файлами, но операция выполняется гораздо быстрее, а оригинальные байты файлов остаются нетронутыми — идеально для сценариев, где важнее скорость или целостность данных, чем размер.

## Почему стоит использовать Aspose.Zip для .NET?
- **Full control** над уровнем сжатия (store vs. deflate).  
- **Simple API** для чтения записей, открытия zip‑файлов и извлечения данных.  
- **Cross‑platform** поддержка .NET Framework, .NET Core и .NET 5+.

## Требования

Перед тем как приступить к выполнению руководства, убедитесь, что у вас есть следующее:

- Aspose.Zip for .NET Library: Скачайте и установите библиотеку Aspose.Zip for .NET. Вы можете найти библиотеку [здесь](https://releases.aspose.com/zip/net/).

- Document Directory: Создайте каталог в системе, где будут храниться необходимые файлы для этого руководства.

## Импорт пространств имён

Для начала импортируем необходимые пространства имён в наш проект:

```csharp
using Aspose.Zip;
using System.IO;
```

## Как создать zip без сжатия

Сначала нам нужен ZIP‑архив, использующий метод **store** (т.е. без сжатия). Пример кода ниже создаёт такой архив и предоставляется Aspose.Zip в виде вспомогательного метода. При выполнении он генерирует `StoreMultipleFilesWithoutCompression_out.zip` в вашем каталоге документов.

```csharp
StoreMultipleFilesWithoutCompression.Run();
```

> **Pro tip:** Вспомогательный метод внутри устанавливает `CompressionMethod.Store` для каждой записи, гарантируя, что архив создаётся без какого‑либо сжатия данных.

## Как открыть zip и извлечь несколько файлов

Теперь, когда у нас есть сохранённый ZIP, посмотрим, **how to open zip** и извлечём файлы.

### Шаг 2.1: Открытие zip‑файла

```csharp
string dataDir = "Your Document Directory";

using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Open))
{
    using (Archive archive = new Archive(zipFile))
    {
```

Объект `Archive` представляет открытый ZIP и предоставляет доступ к каждой записи через коллекцию `Entries`.

### Шаг 2.2: Создание извлечённых файлов

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

Здесь мы **read zip entry** 0, копируем его байты в новый файл и автоматически закрываем потоки благодаря оператору `using`.

### Шаг 2.3: Повторение процесса для другого файла

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

## Распространённые проблемы и их решения

| Проблема | Причина | Решение |
|----------|----------|----------|
| `FileNotFoundException` при открытии ZIP | Неправильный путь `dataDir` | Убедитесь, что `dataDir` заканчивается слешем, либо используйте `Path.Combine`. |
| Извлечённый файл пустой | Буфер не сброшен | Блок `using` автоматически сбрасывает поток; убедитесь, что читаете поток до тех пор, пока `bytesRead` не станет 0 (как показано). |
| Исключение лицензии | Запуск без действующей лицензии | Примените пробную или постоянную лицензию перед развертыванием. |

## Часто задаваемые вопросы

### Q1: Совместим ли Aspose.Zip for .NET со всеми версиями .NET?

**A:** Да, Aspose.Zip for .NET разработан так, чтобы быть совместимым с различными версиями .NET, предоставляя разработчикам гибкость.

### Q2: Можно ли использовать Aspose.Zip for .NET в коммерческих и некоммерческих проектах?

**A:** Да, Aspose.Zip for .NET можно использовать как в коммерческих, так и в некоммерческих проектах. Смотрите [purchase page](https://purchase.aspose.com/buy) для деталей лицензирования.

### Q3: Как получить поддержку по Aspose.Zip for .NET?

**A:** Для поддержки посетите [Aspose.Zip forum](https://forum.aspose.com/c/zip/37), где сообщество разработчиков и экспертов поможет вам.

### Q4: Есть ли бесплатная пробная версия Aspose.Zip for .NET?

**A:** Да, вы можете изучить возможности Aspose.Zip for .NET, получив бесплатную пробную версию [здесь](https://releases.aspose.com/).

### Q5: Можно ли получить временную лицензию для тестирования?

**A:** Да, временную лицензию для тестирования можно получить, перейдя по [this link](https://purchase.aspose.com/temporary-license/).

### Q6: Как прочитать zip‑запись без извлечения всего архива?

**A:** Используйте `archive.Entries[index].Open()` для получения потока конкретной записи, затем считайте нужные байты, как показано в коде выше.

### Q7: Какой лучший способ **extract multiple zip files** в цикле?

**A:** Итерируйте `archive.Entries` с помощью `foreach`, открывая поток каждой записи и записывая его в целевой файл, аналогично шаблону, показанному в Шаге 2.2 и 2.3.

## Заключение

Освоение **create zip without compression** и последующего процесса извлечения важно для высокопроизводительных .NET‑приложений. Aspose.Zip for .NET предоставляет чистый, интуитивный API для **how to open zip**, чтения каждой **zip entry** и выполнения операции **C# extract zip** с минимальным объёмом кода. Следуя этому руководству, вы научились генерировать сохранённый архив, открывать его и эффективно извлекать содержимое.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-16  
**Tested With:** Aspose.Zip for .NET 24.12  
**Author:** Aspose