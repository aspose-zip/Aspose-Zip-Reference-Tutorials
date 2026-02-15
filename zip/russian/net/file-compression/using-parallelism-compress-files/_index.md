---
date: 2026-02-15
description: Узнайте, как архивировать несколько файлов на C# с помощью Aspose.Zip
  для .NET, используя параллельное сжатие. Пошаговое руководство, примеры кода и советы
  для быстрых, масштабируемых архивов.
linktitle: Using Parallelism to Zip Multiple Files in C#
second_title: Aspose.Zip .NET API – zip multiple files c# with Parallel Processing
title: Как заархивировать несколько файлов в C# с использованием Aspose.Zip Parallel
  Compression
url: /ru/net/file-compression/using-parallelism-compress-files/
weight: 17
---

.

Let's write final.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# zip multiple files c# с Aspose.Zip Parallel Compression

## Введение

Если вам нужно **zip multiple files c#** быстро и эффективно, использование параллельной обработки — лучший путь. В современных приложениях .NET создание больших zip‑архивов может стать узким местом, особенно при работе с десятками или сотнями файлов. Aspose.Zip for .NET устраняет эту проблему, предлагая встроенное **parallel zip compression**, которое распределяет работу по всем доступным ядрам процессора. В этом руководстве мы пройдем весь процесс: от настройки окружения до сохранения zip‑архива с включённым параллелизмом.

## Краткие ответы
- **Что такое параллельное zip‑сжатие?** Оно сжимает несколько файлов одновременно, используя несколько потоков, чтобы сократить общее время обработки.  
- **Какая .NET‑библиотека поддерживает это?** Aspose.Zip for .NET предоставляет простой API для параллельного сжатия.  
- **Нужна ли лицензия для продакшна?** Да — требуется полная лицензия; временная лицензия доступна для тестирования.  
- **Можно ли добавлять файлы в zip «на лету»?** Конечно — используйте `Archive.CreateEntry` для каждого файла, который хотите включить.  
- **Совместим ли он с .NET 6/7?** Да, API работает на всех современных .NET‑runtime.

## Что такое zip multiple files c#?
`zip multiple files c#` обозначает практику создания единого ZIP‑архива, содержащего множество отдельных файлов, с помощью кода на C#. Когда вы комбинируете это с **parallel zip compression**, библиотека обрабатывает каждый файл в отдельном потоке, резко сокращая время, необходимое для создания финального архива.

## Почему стоит использовать Aspose.Zip для параллельного сжатия?
- **Скорость:** Полностью использует многоядерные процессоры, часто обеспечивая в 2‑3 раза более быстрое сжатие по сравнению с последовательными подходами.  
- **Масштабируемость:** Обрабатывает большие партии файлов без линейного увеличения времени обработки.  
- **Простота:** API высокого уровня абстрагирует работу с потоками, позволяя сосредоточиться на бизнес‑логике.  
- **Гибкость:** Работает с любой версией .NET (Framework, Core, .NET 5/6/7) и легко интегрируется в существующие проекты.

## Требования

- Базовые знания C# и разработки на .NET.  
- Aspose.Zip for .NET установлен. Вы можете скачать его **[здесь](https://releases.aspose.com/zip/net/)**.  
- Временная или полная лицензия (временная лицензия достаточна для этого руководства).  

## Импорт пространств имён

Сначала импортируйте необходимые пространства имён в ваш C#‑файл, чтобы компилятор знал, где находятся используемые классы.

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Шаг 1: Настройте каталог документов

Определите папку, содержащую файлы, которые нужно сжать. Этот путь сохраняется в переменной `dataDir`.

```csharp
string dataDir = "Your Document Directory";
```

## Шаг 2: Инициализируйте процесс сжатия

Откройте новый ZIP‑файл для записи. Оператор `using` гарантирует корректное освобождение файлового потока после завершения операции.

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## Шаг 3: Чтение и сжатие файлов параллельно

Откройте каждый исходный файл, который планируете добавить в архив. В этом примере мы работаем с двумя классическими текстами, но вы можете **add files to zip** для любого количества документов.

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
    using (FileStream source2 = File.Open(dataDir + "asyoulik.txt", FileMode.Open, FileAccess.Read))
    {
        // Your code for compressing files in parallel will go here.
    }
}
```

## Шаг 4: Создание записей архива

Создайте экземпляр `Archive` и добавьте каждый файл как отдельную запись. Здесь происходит шаг **create zip archive c#**.

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## Шаг 5: Определите критерий параллелизма

Настройте сжатие для параллельного выполнения, задав `ParallelOptions`. Флаг `ParallelCompressInMemory` сообщает Aspose.Zip всегда использовать параллельную обработку.

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## Шаг 6: Сохраните сжатый архив

Наконец, запишите архив на диск с нужными параметрами, включая кодировку, комментарий и ранее определённые параллельные настройки.

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

> **Pro tip:** Если вы сжимаете очень большие файлы, рассмотрите возможность установки `ParallelOptions.MaxDegreeOfParallelism` в значение, меньшее количества логических процессоров. Это помогает сохранять отзывчивость сервера под нагрузкой.

### Типичные сценарии использования

- **Пакетная отчётность:** Создайте zip‑пакет ежедневных CSV‑отчётов для downstream‑систем.  
- **Архивирование документов:** Храните большие коллекции PDF, изображений или логов в одном архиве для резервного копирования.  
- **API экспорта данных:** Верните zip‑файл, содержащий несколько файлов данных, клиенту в одном HTTP‑ответе.

## Распространённые проблемы и советы

- **Нагрузка на память при работе с большими файлами:** Вместо загрузки всего файла в память, передавайте файл потоками кусками или используйте режим `ParallelCompressInMemory` выборочно.  
- **Безопасность потоков:** API Aspose.Zip потокобезопасен в параллельном режиме, но избегайте изменения того же `FileStream` извне библиотеки во время сжатия.  
- **Тонкая настройка производительности:** Экспериментируйте с `ParallelOptions.MaxDegreeOfParallelism`, если нужно ограничить использование CPU на совместных серверах.  

## Часто задаваемые вопросы

**Q: Можно ли использовать Aspose.Zip for .NET вместе с другими библиотеками сжатия?**  
A: Да, Aspose.Zip может сосуществовать с другими .NET‑библиотеками; просто держите их пространства имён раздельными.

**Q: Доступна ли временная лицензия для тестовых целей?**  
A: Да, временную лицензию для тестирования можно получить **[здесь](https://purchase.aspose.com/temporary-license/)**.

**Q: Где можно получить помощь, если возникнут проблемы?**  
A: Посетите **[форум Aspose.Zip](https://forum.aspose.com/c/zip/37)** для поддержки сообщества и обсуждений.

**Q: Где найти больше примеров кода и подробную документацию API?**  
A: Изучите **[документацию Aspose.Zip](https://reference.aspose.com/zip/net/)** для обширных примеров.

**Q: Как приобрести полную лицензию на Aspose.Zip?**  
A: Вы можете приобрести Aspose.Zip for .NET **[здесь](https://purchase.aspose.com/buy)**.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Zip 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}