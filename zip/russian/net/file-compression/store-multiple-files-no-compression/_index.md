---
date: 2026-05-30
description: Узнайте, как создать zip без сжатия в .NET с помощью Aspose.Zip для .NET.
  Это руководство покажет, как архивировать файлы без сжатия, хранить файлы в несжатом
  виде и эффективно управлять архивами.
keywords:
- zip without compression
- generate zip archive .net
- Aspose.Zip uncompressed
linktitle: Сохранение нескольких файлов без сжатия
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  headline: Create zip without compression in .NET using Aspose.Zip
  type: TechArticle
- description: Learn how to create zip without compression in .NET with Aspose.Zip
    for .NET. This guide shows you how to zip files without compression, store files
    uncompressed, and manage archives efficiently.
  name: Create zip without compression in .NET using Aspose.Zip
  steps:
  - name: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
    text: '**Create the archive** – instantiate `Archive` with a target stream or
      file path.'
  - name: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
    text: '**Configure entry settings** – for each file, create an `ArchiveEntrySettings`
      object and assign `new StoreCompressionSettings()` to its `Compression` property.'
  - name: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
    text: '**Add entries** – call `archive.Add(entrySettings)` for every file, then
      finalize with `archive.Save()`.'
  type: HowTo
- questions:
  - answer: Yes, you can create different `ArchiveEntrySettings` for each file and
      mix compressed and uncompressed entries in the same archive.
    question: Can I compress specific file types while storing others without compression?
  - answer: Absolutely. The library supports .NET Framework, .NET Core, .NET Standard,
      and the latest .NET versions.
    question: Is Aspose.Zip for .NET compatible with .NET Core and .NET 5/6?
  - answer: Wrap the archiving code in a `try‑catch` block and log the exception details.
      This ensures graceful failure and easier debugging.
    question: How should I handle exceptions during the archiving process?
  - answer: Yes, you can process multiple files in parallel and add them to the archive,
      but remember that the `Archive` object itself is not thread‑safe; synchronize
      access when adding entries.
    question: Does Aspose.Zip support multi‑threaded archiving?
  - answer: Definitely. The API is designed for simple drop‑in usage. Refer to the
      official [documentation](https://reference.aspose.com/zip/net/) for migration
      guidance.
    question: Can I integrate Aspose.Zip into an existing project without major code
      changes?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Создание zip без сжатия в .NET с использованием Aspose.Zip
url: /ru/net/file-compression/store-multiple-files-no-compression/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать zip без сжатия в .NET с помощью Aspose.Zip

В современной разработке на .NET **создание zip без сжатия** может значительно ускорить процесс архивирования и сделать размер файлов предсказуемым. Когда вам нужно **архивировать файлы без сжатия** — например, чтобы соответствовать нормативным требованиям, ускорить последующую обработку или гарантировать неизменность исходной последовательности байтов — Aspose.Zip для .NET предоставляет чистый, простой API. В этом руководстве мы пройдем все шаги по созданию несжатого ZIP‑архива, добавлению файлов и интеграции решения в ваше приложение.

## Быстрые ответы
- **Что означает “uncompressed zip”?** Это ZIP‑архив, в котором каждая запись хранится методом “store”, оставляя оригинальные байты файлов нетронутыми.  
- **Почему избегать сжатия?** Чтобы ускорить архивирование, сохранить исходные размеры файлов для последующей обработки или соответствовать нормативным требованиям, запрещающим изменение данных.  
- **Какой класс Aspose.Zip обрабатывает это?** `ArchiveEntrySettings` в сочетании с `StoreCompressionSettings`.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для тестирования; для продакшн требуется коммерческая лицензия.  
- **Поддерживаемые версии .NET?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 и .NET 5–10.  

## Что такое zip без сжатия?
**Zip без сжатия** — это ZIP‑архив, в котором каждая запись файла использует метод *store*, то есть данные копируются в архив дословно без применения какого‑либо алгоритма сжатия. В результате размер архива практически равен сумме оригинальных файлов плюс несколько байтов служебных данных ZIP.

## Почему использовать Aspose.Zip для zip‑файлов без сжатия?
Aspose.Zip оптимизирован для высокопроизводительного архивирования, позволяя мгновенно сохранять файлы без накладных расходов на алгоритмы сжатия. Он гарантирует полную совместимость с ZIP, позволяет смешивать сохранённые и сжатые записи и предоставляет простой API, абстрагирующий низкоуровневые структуры ZIP, делая реализацию быстрой и надёжной.

## Предварительные требования
- **Aspose.Zip for .NET** – интегрирован в ваш проект. См. официальную [документацию](https://reference.aspose.com/zip/net/) для шагов установки.  
- **Среда разработки .NET** – Visual Studio, VS Code или любая предпочитаемая IDE.  
- **Каталог документов** – папка на вашем компьютере, содержащая файлы, которые вы хотите заархивировать (например, “Your Document Directory”).

## Импорт пространств имён
Перед написанием кода импортируйте необходимые пространства имён, чтобы компилятор знал, где находятся классы Aspose.

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
using System.Text;
```

## Шаг 1: Установить каталог документов
Определите путь, где находятся ваши исходные файлы. Замените заполнитель реальной папкой в вашей системе.

```csharp
string dataDir = "Your Document Directory";
```

## Шаг 2: Создать ZIP‑архив без сжатия
Суть руководства – мы создаём экземпляр `Archive`, настроенный с `StoreCompressionSettings`. `Archive` представляет контейнер ZIP, способный содержать несколько записей. `StoreCompressionSettings` указывает, что запись должна храниться без сжатия. Это сообщает Aspose.Zip *хранить* (т.е. не сжимать) каждую запись.

```csharp
using (FileStream zipFile = File.Open(dataDir + "StoreMultipleFilesWithoutCompression_out.zip", FileMode.Create))
{
    FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo fi2 = new FileInfo(dataDir + "lcet10.txt");

    using (Archive archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings())))
    {
        archive.CreateEntry("alice29.txt", fi1);
        archive.CreateEntry("lcet10.txt", fi2);
        archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
    }
}
```

> **Совет:** Если вам нужно **сохранять файлы в zip**, при этом сжимать некоторые и оставлять другие без сжатия, создайте отдельные экземпляры `ArchiveEntrySettings` для каждого файла и добавьте их в один и тот же `Archive`.

## Как создать zip без сжатия в .NET?
Загрузите исходные файлы, создайте объект `Archive` и добавьте каждый файл, используя `ArchiveEntrySettings` с `new StoreCompressionSettings()`. Вся операция требует всего три строки кода и выполняется за линейное время от общего размера файлов, обеспечивая максимально быструю архивацию.

### Пошаговое руководство
1. **Создать архив** – создать экземпляр `Archive` с целевым потоком или путем к файлу.  
2. **Настроить параметры записи** – для каждого файла создать объект `ArchiveEntrySettings` и присвоить его свойству `Compression` значение `new StoreCompressionSettings()`.  
3. **Добавить записи** – вызвать `archive.Add(entrySettings)` для каждого файла, затем завершить вызовом `archive.Save()`.

## Распространённые проблемы и решения
| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| **Файл не найден** | Неправильный путь `dataDir` или отсутствует расширение файла. | Проверьте путь и убедитесь, что файлы существуют. Используйте `Path.Combine` для более безопасного объединения. |
| **Отказ в доступе** | Процесс не имеет прав на чтение исходных файлов или запись ZIP. | Запустите приложение с необходимыми правами или выберите папку с правом записи. |
| **Неожиданный размер файла в ZIP** | Архив был создан с использованием сжатия по умолчанию. | Убедитесь, что в `ArchiveEntrySettings` передано `new StoreCompressionSettings()`. |

## Часто задаваемые вопросы

**Q:** Могу ли я сжимать определённые типы файлов, а остальные хранить без сжатия?  
**A:** Да, вы можете создать разные `ArchiveEntrySettings` для каждого файла и смешивать сжатые и несжатые записи в одном архиве.

**Q:** Совместим ли Aspose.Zip для .NET с .NET Core и .NET 5/6?  
**A:** Абсолютно. Библиотека поддерживает .NET Framework, .NET Core, .NET Standard и последние версии .NET.

**Q:** Как следует обрабатывать исключения во время процесса архивирования?  
**A:** Оберните код архивирования в блок `try‑catch` и запишите детали исключения в журнал. Это обеспечивает корректное завершение и упрощает отладку.

**Q:** Поддерживает ли Aspose.Zip многопоточное архивирование?  
**A:** Да, вы можете обрабатывать несколько файлов параллельно и добавлять их в архив, но помните, что объект `Archive` не является потокобезопасным; синхронизируйте доступ при добавлении записей.

**Q:** Могу ли я интегрировать Aspose.Zip в существующий проект без значительных изменений кода?  
**A:** Определённо. API разработан для простого «подключения». Обратитесь к официальной [документации](https://reference.aspose.com/zip/net/) для рекомендаций по миграции.

---

**Последнее обновление:** 2026-05-30  
**Тестировано с:** Aspose.Zip for .NET (latest version at time of writing)  
**Автор:** Aspose

## Связанные руководства

- [Создать ZIP‑архив .NET – Сжатие файлов с Aspose.Zip](/zip/net/file-compression/)
- [zip несколько файлов c# – Легкое сжатие с Aspose.Zip для .NET](/zip/net/file-compression/compress-multiple-files/)
- [Создать Zip без сжатия и распаковать файлы – Aspose.Zip](/zip/net/file-decompression/decompress-stored-file/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}