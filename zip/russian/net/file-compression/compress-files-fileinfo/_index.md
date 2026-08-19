---
date: 2026-07-18
description: Узнайте, как добавить папку в zip и добавить файлы в zip с помощью Aspose.Zip
  для .NET. Это пошаговое руководство показывает, как сжать файлы с помощью FileInfo
  в проектах ASP.NET.
keywords:
- add folder to zip
- how to create zip archive
- add files to zip
- asp.net zip compression
- asp.net file compression
lastmod: 2026-07-18
linktitle: Сжать файлы с помощью FileInfo
og_description: Добавьте папку в zip с помощью Aspose.Zip для .NET. Узнайте, как создать
  zip‑архив, добавить файлы в zip и эффективно сжать папки в ASP.NET.
og_image_alt: 'Developer guide: Adding folder to zip archive with Aspose.Zip in .NET'
og_title: Добавить папку в Zip – Сжать файлы с Aspose.Zip для .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  headline: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  type: TechArticle
- description: Learn how to add folder to zip and add files to zip using Aspose.Zip
    for .NET. This step‑by‑step guide shows how to compress files with FileInfo in
    ASP.NET projects.
  name: Add Folder to Zip Using Aspose.Zip for .NET – Compress Files with FileInfo
  steps:
  - name: Set Up Your Document Directory
    text: 'First, define the folder that holds the source files. Replace the placeholder
      with the absolute or relative path on your system: > **Pro tip:** Use `Path.Combine`
      to build paths in a cross‑platform way.'
  - name: Open a Zip File for Writing
    text: 'Create a `FileStream` that points to the output zip file. The stream is
      opened in **Create** mode, which overwrites any existing file with the same
      name:'
  - name: Prepare `FileInfo` Objects for Each Source File
    text: '`FileInfo` gives Aspose.Zip direct access to the physical files on disk.
      Create one instance per file you want to compress: > **Why use `FileInfo`?**
      It avoids loading the entire file into memory, which is especially helpful for
      large files.'
  - name: Create the Archive and Add Entries
    text: 'The `Archive` class is Aspose.Zip''s core object that represents a zip
      container in memory. Instantiate an `Archive` object, then call `CreateEntry`
      for each `FileInfo`. The first argument is the name the file will have inside
      the zip, the second argument is the source `FileInfo`: The `CreateEntry` m'
  - name: Save the Zip Archive with Desired Encoding
    text: 'Finally, persist the archive to the `FileStream` you opened earlier. Here
      we use ASCII encoding for entry names, but you can switch to UTF‑8 if your filenames
      contain non‑ASCII characters: When the `using` blocks exit, the streams are
      automatically closed and the zip file is ready for use.'
  type: HowTo
- questions:
  - answer: No single‑call method exists, but enumerating files with `DirectoryInfo`
      and adding each via `CreateEntry` achieves the same result efficiently.
    question: Can I add an entire folder to a zip archive in a single call?
  - answer: Yes, you can set a password on the `Archive` object before saving to encrypt
      the entire archive.
    question: Does Aspose.Zip support password protection?
  - answer: The library processes files larger than 4 GB and can create archives exceeding
      10 GB without loading the whole archive into memory.
    question: How large a zip file can Aspose.Zip handle?
  - answer: Absolutely. Aspose.Zip supports .NET 5 through .NET 10, covering all current
      LTS releases.
    question: Is the API compatible with .NET 6 and .NET 8?
  - answer: You can choose `CompressionLevel.NoCompression`, `Fast`, `Normal`, or
      `Maximum` to balance speed and size.
    question: What compression levels are available?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress files
- Aspose.Zip
- .NET file compression
- zip archive
title: Добавить папку в Zip с помощью Aspose.Zip для .NET – Сжать файлы с помощью
  FileInfo
url: /ru/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить папку в архив Zip с помощью Aspose.Zip для .NET

## Введение

Если вам необходимо **add folder to zip** программно, Aspose.Zip для .NET предлагает чистый, высокопроизводительный API, который работает в любом .NET (включая ASP.NET) приложении. В этом руководстве мы пройдем процесс сжатия файлов с помощью класса `FileInfo`, покажем, как **add files to zip**, и объясним, почему этот подход идеален для современных .NET проектов. Мы также рассмотрим точные шаги для **add folder to zip**, чтобы вы могли упаковать целые каталоги за одну операцию. Приступим!

## Быстрые ответы
- **Как самый простой способ создать zip‑архив?** Используйте класс `Archive` из Aspose.Zip вместе с объектами `FileInfo`.  
- **Могу ли я добавить несколько файлов одновременно?** Да — просто создайте `FileInfo` для каждого файла и вызовите `CreateEntry`.  
- **Нужна ли специальная лицензия для ASP.NET?** Для продакшна требуется коммерческая лицензия Aspose.Zip; бесплатная пробная версия подходит для оценки.  
- **Какие версии .NET поддерживаются?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 и .NET 5–10.  
- **API потокобезопасен?** Да, при условии, что каждый поток работает со своим экземпляром `Archive`.

## Что такое Zip‑архив и зачем его создавать?

Zip‑архив объединяет один или несколько файлов в один сжатый контейнер. Это уменьшает объём хранилища, ускоряет передачу по сети и упрощает распространение. Независимо от того, отправляете ли вы журналы, экспортируете отчёты или упаковываете ресурсы для клиента, знание **how to create zip archive** файлов программно является ценным навыком для любого .NET‑разработчика.

## Почему использовать Aspose.Zip для добавления файлов в Zip?

Aspose.Zip предоставляет чистое решение на .NET, устраняющее внешние зависимости, одновременно предоставляя разработчикам тонкий контроль над сжатием, кодировкой и безопасностью. Он поддерживает большие файлы, защиту паролем и стабильно работает во всех поддерживаемых версиях .NET, что делает его надёжным выбором как для устаревших, так и для современных приложений.  

- **Zero external dependencies** – чистая реализация на .NET.  
- **Full control over compression level and encoding** (ASCII, UTF‑8 и т.д.).  
- **Supports files larger than 4 GB** и защита паролем.  
- **Consistent API across 50+ .NET versions** – от .NET Framework 2.0 до .NET 10.  

## Требования

Прежде чем перейти к коду, убедитесь, что у вас есть:

1. **Aspose.Zip for .NET** установлен. Скачайте последнюю версию с [Aspose.Zip download page](https://releases.aspose.com/zip/net/).  
2. Папка на вашем компьютере, содержащая файлы, которые вы хотите сжать (например, `alice29.txt` и `fields.c`).  

## Импорт пространств имён

В любом файле C#, где вы будете работать с zip‑архивами, добавьте следующие `using`‑операторы:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

## Пошаговое руководство

### Шаг 1: Настройте каталог документов

Сначала определите папку, в которой находятся исходные файлы. Замените заполнитель на абсолютный или относительный путь в вашей системе:

```csharp
string dataDir = "Your Document Directory";
```

> **Подсказка:** Используйте `Path.Combine` для построения путей кроссплатформенно.

### Шаг 2: Откройте Zip‑файл для записи

Создайте `FileStream`, указывающий на выходной zip‑файл. Поток открывается в режиме **Create**, который перезаписывает любой существующий файл с тем же именем:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Шаг 3: Подготовьте объекты `FileInfo` для каждого исходного файла

`FileInfo` дает Aspose.Zip прямой доступ к физическим файлам на диске. Создайте один экземпляр для каждого файла, который хотите сжать:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Почему использовать `FileInfo`?** Это избегает загрузки всего файла в память, что особенно полезно для больших файлов.

### Шаг 4: Создайте архив и добавьте записи

Класс `Archive` — основной объект Aspose.Zip, представляющий zip‑контейнер в памяти. Создайте объект `Archive`, затем вызовите `CreateEntry` для каждого `FileInfo`. Первый аргумент — имя файла внутри zip, второй аргумент — исходный `FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

Метод `CreateEntry` добавляет новую файловую запись в архив, связывая имя записи с исходным `FileInfo`, так что данные передаются напрямую с диска при сохранении архива.

### Шаг 5: Сохраните Zip‑архив с нужной кодировкой

Наконец, сохраните архив в `FileStream`, который вы открыли ранее. Здесь мы используем ASCII‑кодировку для имён записей, но можете переключиться на UTF‑8, если имена файлов содержат не‑ASCII символы:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Когда блоки `using` завершаются, потоки автоматически закрываются, и zip‑файл готов к использованию.

## Как добавить папку в Zip с помощью Aspose.Zip?

Загрузите целевой каталог, перечислите все файлы и добавьте каждый с относительным путём, включающим имя папки. Этот подход позволяет **add folder to zip** без ручного перечисления файлов. Сохраняя иерархию папок в именах записей, полученный архив можно извлечь с сохранением исходной структуры каталогов, что важно для многих сценариев развертывания.

1. Используйте `DirectoryInfo`, чтобы указать папку, которую хотите сжать.  
2. Вызовите `GetFiles("*", SearchOption.AllDirectories)`, чтобы рекурсивно получить все файлы.  
3. Для каждого файла создайте `FileInfo` и вызовите `CreateEntry` с путём вроде `"MyFolder/Report.pdf"`.

Поскольку API работает с `FileInfo`, каждый файл передаётся напрямую с диска, что сохраняет низкое использование памяти даже для папок, содержащих сотни мегабайт.

## Распространённые проблемы и решения

| Issue | Cause | Fix |
|-------|-------|-----|
| **Пустой zip‑файл** | `FileInfo` указывает на несуществующий путь | Проверьте `dataDir` и имена файлов; используйте `File.Exists` для проверки перед созданием записей. |
| **Неправильная кодировка имени файла** | Используется кодировка по умолчанию для не‑ASCII имён | Установите `Encoding = Encoding.UTF8` в `ArchiveSaveOptions`. |
| **OutOfMemoryException при больших файлах** | Загрузка всего файла в память | `FileInfo` передаёт файл потоково; убедитесь, что вы не читаете файл в массив байтов где‑то ещё. |
| **Отказ в доступе** | Приложение не имеет прав записи в целевую папку | Запустите приложение с необходимыми правами или выберите записываемый каталог. |

## Часто задаваемые вопросы

**Q: Можно ли добавить всю папку в zip‑архив одним вызовом?**  
A: Одного метода нет, но перечисление файлов через `DirectoryInfo` и добавление каждого через `CreateEntry` достигает того же результата эффективно.

**Q: Поддерживает ли Aspose.Zip защиту паролем?**  
A: Да, вы можете задать пароль у объекта `Archive` перед сохранением, чтобы зашифровать весь архив.

**Q: Какой максимальный размер zip‑файла может обработать Aspose.Zip?**  
A: Библиотека работает с файлами более 4 GB и может создавать архивы более 10 GB, не загружая весь архив в память.

**Q: Совместим ли API с .NET 6 и .NET 8?**  
A: Абсолютно. Aspose.Zip поддерживает .NET 5‑10, охватывая все текущие LTS‑версии.

**Q: Какие уровни сжатия доступны?**  
A: Вы можете выбрать `CompressionLevel.NoCompression`, `Fast`, `Normal` или `Maximum` для баланса скорости и размера.

## Дополнительные ресурсы

- Скачать последнюю версию пакета Aspose.Zip: [Aspose.Zip download page](https://releases.aspose.com/zip/net/)  
- Купить лицензию для продакшна: [purchase page](https://purchase.aspose.com/buy)  
- Получить помощь от сообщества: [Aspose.Zip forum](https://forum.aspose.com/c/zip/37)  
- Попробовать Aspose.Zip бесплатно: [free trial here](https://releases.aspose.com/)  
- Получить временную лицензию для оценки: [this link](https://purchase.aspose.com/temporary-license/)

## Заключение

Теперь вы знаете **how to add folder to zip** и **how to create zip archive** файлы с помощью Aspose.Zip для .NET, как **add files to zip**, и почему этот метод идеален для ASP.NET и других .NET приложений. Поэкспериментируйте с различными уровнями сжатия, кодировками и параметрами шифрования, чтобы адаптировать архив под ваши точные требования. Приятного сжатия!

---

**Последнее обновление:** 2026-07-18  
**Тестировано с:** Aspose.Zip for .NET 24.12 (latest)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как заархивировать папку с помощью Aspose.Zip для .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [zip multiple files c# – Лёгкое сжатие с Aspose.Zip для .NET](/zip/net/file-compression/compress-multiple-files/)
- [Создать Zip‑архив .NET – Сжатие файлов с Aspose.Zip](/zip/net/file-compression/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}