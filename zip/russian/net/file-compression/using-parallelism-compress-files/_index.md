---
{}
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# архивировать несколько файлов c# с параллельным сжатием Aspose.Zip

## Введение

Если вам нужно **архивировать несколько файлов c#** быстро и эффективно, использование параллельной обработки — лучший путь. В современных приложениях .NET создание больших zip‑архивов может стать узким местом, особенно при работе с десятками или сотнями файлов. Aspose.Zip for .NET устраняет эту проблему, предлагая встроенное **параллельное zip‑сжатие**, которое распределяет работу по всем доступным ядрам процессора. В этом руководстве мы пройдем весь процесс: от настройки среды до сохранения zip‑архива с включённым параллелизмом, а также покажем, как **создать zip‑архив c#**, который работает плавно в .NET Core.

## Быстрые ответы
- **Что такое parallel zip compression?** Оно сжимает несколько файлов одновременно, используя несколько потоков для сокращения общего времени обработки.  
- **Какая библиотека .NET поддерживает это?** Aspose.Zip for .NET предоставляет простой API для параллельного сжатия.  
- **Нужна ли лицензия для продакшн?** Да — требуется полная лицензия; временная лицензия доступна для тестирования.  
- **Можно ли добавлять файлы в zip «на лету»?** Конечно — используйте `Archive.CreateEntry` для каждого файла, который хотите включить.  
- **Совместим ли он с .NET 6/7?** Да, API работает на всех современных средах .NET.

## Что такое архивирование нескольких файлов c#?
`zip multiple files c#` относится к практике создания единого ZIP‑архива, содержащего множество отдельных файлов, с использованием кода C#. Когда вы комбинируете это с **parallel zip compression**, библиотека обрабатывает каждый файл в отдельном потоке, значительно сокращая время, необходимое для создания конечного архива.

## Почему стоит использовать Aspose.Zip для параллельного сжатия?
Параллельное сжатие позволяет использовать все ядра многопроцессорного компьютера, часто обеспечивая **2‑3× более быструю** пропускную способность по сравнению с однопоточным подходом. Оно также масштабируется без проблем: добавление большего количества файлов не увеличивает время выполнения линейно, а API управляет потоками за вас, позволяя сосредоточиться на бизнес‑логике.  

- **Скорость:** Использует все логические процессоры, сокращая время создания zip‑архива до 70 % в типовых нагрузках.  
- **Масштабируемость:** Обрабатывает партии из более чем 500 файлов без пропорционального увеличения времени CPU.  
- **Простота:** Методы высокого уровня скрывают сложность `System.Threading.Tasks`.  
- **Гибкость:** Поддерживает .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 и .NET 5–10, включая .NET 6/7 для облачных сервисов.

## Предварительные требования

- Базовые знания C# и разработки на .NET.  
- Aspose.Zip for .NET установлен. Вы можете скачать его **[здесь](https://releases.aspose.com/zip/net/)**.  
- Временная или полная лицензия (временная лицензия достаточна для этого руководства).  

## Импорт пространств имён

Пространство имён `Aspose.Zip` содержит все типы, необходимые для работы с ZIP‑архивами.  

```csharp
using Aspose.Zip;
using System.IO;
using System.Threading.Tasks;
```

Сначала импортируйте необходимые пространства имён в ваш файл C#, чтобы компилятор знал, где находятся используемые классы.  

```csharp
using Aspose.Zip;
using System.IO;
using System.Text;
using Aspose.Zip.Saving;
```

## Шаг 1: Настройте каталог документов

Определите папку, содержащую файлы, которые вы хотите сжать. Этот путь сохраняется в переменной `dataDir`, которую можно указать на любой каталог на диске.  

```csharp
string dataDir = @"C:\MyFiles\ToCompress";
```

```csharp
string dataDir = "Your Document Directory";
```

## Шаг 2: Инициализируйте процесс сжатия

Откройте новый ZIP‑файл для записи. Оператор `using` гарантирует корректное освобождение файлового потока после операции, предотвращая утечки дескрипторов файлов.  

```csharp
using (FileStream zipStream = new FileStream("output.zip", FileMode.Create))
{
    // Archive instance will be created inside the using block
}
```

```csharp
using (FileStream zipFile = File.Open(dataDir + "UsingParallelismToCompressFiles_out.zip", FileMode.Create))
{
    // Your code for compression will go here.
}
```

## Шаг 3: Чтение и сжатие файлов параллельно

`Parallel.ForEach` выполняет цикл foreach, в котором итерации могут работать одновременно на нескольких потоках.  

Откройте каждый исходный файл, который вы планируете добавить в архив. В этом примере мы работаем с двумя классическими текстами, но вы можете **добавлять файлы в zip** для любого количества документов. Цикл `Parallel.ForEach` автоматически распределяет работу по потокам.  

```csharp
var files = Directory.GetFiles(dataDir);
Parallel.ForEach(files, filePath =>
{
    // Read and add each file inside the parallel loop
});
```

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

Класс `Archive` — это объект верхнего уровня Aspose.Zip, представляющий ZIP‑контейнер, который вы создаёте.  

`CreateEntry` создаёт новую запись в ZIP‑архиве для указанного файла. Каждый вызов `CreateEntry` добавляет новую файловую запись в архив.  

```csharp
Archive archive = new Archive(zipStream);
archive.CreateEntry(fileName, fileStream);
```

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", source1);
    archive.CreateEntry("asyoulik.txt", source2);
    // Your code for additional entries will go here.
}
```

## Шаг 5: Определение критерия параллелизма

`ParallelOptions` — тип .NET, который управляет тем, как выполняются параллельные циклы.  

Настройте сжатие для параллельного выполнения, задав `ParallelOptions`. Флаг `ParallelCompressInMemory` указывает Aspose.Zip всегда использовать параллельную обработку, а `MaxDegreeOfParallelism` позволяет ограничить количество одновременно работающих потоков.  

```csharp
ParallelOptions options = new ParallelOptions
{
    MaxDegreeOfParallelism = Environment.ProcessorCount // use all cores
};
archive.ParallelCompressInMemory = true;
archive.ParallelOptions = options;
```

```csharp
var parallelOptions = new ParallelOptions
{
    ParallelCompressInMemory = ParallelCompressionMode.Always
};
```

## Шаг 6: Сохранение сжатого архива

Наконец, запишите архив на диск с нужными параметрами, включая кодировку, комментарий и ранее определённые параметры параллелизма. Метод `Save` завершает создание ZIP‑файла.  

```csharp
archive.Save();
```

```csharp
archive.Save(zipFile,
    new ArchiveSaveOptions()
    {
        ParallelOptions = parallelOptions,
        Encoding = Encoding.ASCII,
        ArchiveComment = "There are two poems from Canterbury corpus"
    });
```

> **Совет:** Если вы сжимаете очень большие файлы, рассмотрите возможность установки `ParallelOptions.MaxDegreeOfParallelism` в значение, меньшее количества логических процессоров. Это помогает сохранять отзывчивость сервера под нагрузкой.

### Распространённые сценарии использования

- **Пакетная отчётность:** Создайте zip‑пакет ежедневных CSV‑отчётов для downstream‑систем.  
- **Архивирование документов:** Храните большие коллекции PDF, изображений или логов в одном архиве для резервного копирования.  
- **API экспорта данных:** Возвращайте zip‑файл, содержащий несколько файлов данных клиенту в одном HTTP‑ответе.  

## Распространённые проблемы и советы

- **Нагрузка на память при больших файлах:** Вместо загрузки всего файла в память, передавайте файл потоками кусками или используйте режим `ParallelCompressInMemory` выборочно.  
- **Безопасность потоков:** API Aspose.Zip потокобезопасен в параллельном режиме, но избегайте изменения того же `FileStream` извне библиотеки во время сжатия.  
- **Тонкая настройка производительности:** Экспериментируйте с `ParallelOptions.MaxDegreeOfParallelism`, если необходимо ограничить использование CPU на совместных серверах.  

## Часто задаваемые вопросы

**Q: Можно ли использовать Aspose.Zip for .NET вместе с другими библиотеками сжатия?**  
A: Да, Aspose.Zip может сосуществовать с другими .NET‑библиотеками; просто держите их пространства имён отдельными.  

**Q: Доступна ли временная лицензия для тестирования?**  
A: Да, вы можете получить временную лицензию для тестирования **[здесь](https://purchase.aspose.com/temporary-license/)**.  

**Q: Где я могу попросить помощи, если возникнут проблемы?**  
A: Посетите **[форум Aspose.Zip](https://forum.aspose.com/c/zip/37)** для поддержки сообщества и обсуждений.  

**Q: Где я могу найти больше примеров кода и подробную документацию API?**  
A: Изучите **[документацию Aspose.Zip](https://reference.aspose.com/zip/net/)** для обширных примеров.  

**Q: Как приобрести полную лицензию на Aspose.Zip?**  
A: Вы можете приобрести Aspose.Zip for .NET **[здесь](https://purchase.aspose.com/buy)**.  

---

**Последнее обновление:** 2026-06-09  
**Тестировано с:** Aspose.Zip 24.11 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [zip multiple files c# – Лёгкое сжатие с Aspose.Zip для .NET](/zip/net/file-compression/compress-multiple-files/)
- [Как создать zip‑архив и добавить файл в zip с помощью Aspose.Zip for .NET](/zip/net/file-compression/compress-single-file/)
- [Сжатие нескольких файлов с шифрованием в Aspose.Zip .NET](/zip/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}