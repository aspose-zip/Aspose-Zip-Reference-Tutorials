---
date: 2026-05-30
description: Узнайте, как заархивировать папку с помощью Aspose.Zip для .NET, эффективно
  создавать zip‑архивы и экономить место хранения в ваших .NET‑приложениях.
keywords:
- how to zip folder
- create zip archive
- zip multiple folders
- add password zip
- set compression level
linktitle: Как заархивировать папку
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
title: Как заархивировать папку с помощью Aspose.Zip для .NET
url: /ru/net/directory-and-folder-compression/compress-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как заархивировать папку с помощью Aspose.Zip для .NET

В этом руководстве вы узнаете, **как быстро и надёжно заархивировать папку** с помощью Aspose.Zip для .NET. Независимо от того, создаёте ли вы настольную утилиту, облачный сервис или автоматический скрипт резервного копирования, сжатие папки в ZIP‑архив может существенно уменьшить объём хранилища и ускорить передачу по сети. Мы пройдём каждый шаг, объясним, почему важна каждая строка, и укажем типичные подводные камни, чтобы вы могли применять эту технику с уверенностью.

## Быстрые ответы
- **Что делает Aspose.Zip?** Предоставляет простой .NET API для создания и извлечения ZIP‑архивов без внешних зависимостей.  
- **Сколько времени занимает реализация?** Обычно менее 10 минут для базового сжатия папки.  
- **Какие версии .NET поддерживаются?** .NET Framework 2.0‑4.8.1, .NET Core 2.0‑3.1 и .NET 5‑10.  
- **Нужна ли лицензия для продакшна?** Да, для использования в продакшн‑среде требуется коммерческая лицензия.  
- **Можно ли сжать несколько папок одновременно?** Конечно — используйте метод `CreateEntries` для любой коллекции `DirectoryInfo`, чтобы **заархивировать несколько папок** за один запуск.  

`CreateEntries` добавляет все файлы из каталога в архив.

## Что такое «как заархивировать папку»?

Сжатие папки означает взятие каждого файла и подпапки внутри указанного каталога и упаковку их в один ZIP‑архив. Это уменьшает общий размер, сохраняет исходную иерархию и упрощает передачу или хранение данных. Полученный ZIP можно открыть на любой платформе без специального программного обеспечения, и он сохраняет структуру папок, так что при извлечении оригинальная раскладка восстанавливается точно так же, как была.

## Почему использовать Aspose.Zip для этой задачи?

Aspose.Zip позволяет **создавать zip‑архивы** напрямую из кода .NET с единым API для всех поддерживаемых сред выполнения. Загружайте класс `Archive`, добавляйте записи, задавайте `CompressionLevel`, при необходимости указывайте пароль и вызывайте `Save`. Библиотека обрабатывает папки с тысячами файлов менее чем за секунду на типичном оборудовании и поддерживает более 50 различных форматов сжатия и алгоритмов шифрования.

## Требования

- **Aspose.Zip для .NET** – скачайте его [здесь](https://releases.aspose.com/zip/net/) или [здесь](https://releases.aspose.com/zip/net).  
- **Среда разработки** – Visual Studio, Rider или любой IDE, поддерживающий C#.  
- **Каталог документов** – замените `"Your Document Directory"` в коде на путь к папке, которую хотите сжать.  
- **Справочная документация** – обратитесь к официальным документам [здесь](https://reference.aspose.com/zip/net/).

## Импорт пространств имён

Начните с импорта необходимых пространств имён. Они дают доступ к основным классам сжатия.

```csharp
using Aspose.Zip;
using System.IO;
```

## Как заархивировать папку с помощью Aspose.Zip

Ниже приведён простой пример, демонстрирующий **как заархивировать папку**. Тот же шаблон можно расширить для **сжатия нескольких файлов .net** или создания пользовательских структур архива.

### Шаг 1: Инициализировать ваш каталог документов

Установите переменную `dataDir` в путь к каталогу, который нужно сжать.

```csharp
string dataDir = "Your Document Directory";
```

### Шаг 2: Создать выходные ZIP‑файлы

Откройте два объекта `FileStream` для выходных ZIP‑файлов. Это показывает, как можно генерировать более одного архива из одного источника — полезно для версионных резервных копий.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressDirectory_out.zip", FileMode.Create))
{
    using (FileStream zipFile2 = File.Open(dataDir + "CompressDirectory2_out.zip", FileMode.Create))
    {
```

### Шаг 3: Сжать каталог

Класс `Archive` представляет ZIP‑архив и предоставляет методы для добавления записей и сохранения файла. Используйте его, чтобы добавить каждую запись из целевой папки. В примере используется образцовая папка **CanterburyCorpus**, но вы можете указать любой каталог.

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

> **Полезный совет:** Если нужно **создать zip‑архив .net** с определённым уровнем сжатия, задайте `archive.CompressionLevel` перед вызовом `Save`.

## Распространённые проблемы и решения

| Симптом | Вероятная причина | Решение |
|---------|-------------------|---------|
| Пустой ZIP‑файл | `dataDir` указывает на неверную папку или отсутствует завершающий слеш | Проверьте путь и убедитесь, что в папке есть файлы |
| `UnauthorizedAccessException` | Приложение не имеет прав доступа к файловой системе | Запустите Visual Studio от имени администратора или предоставьте права чтения/записи |
| Большое потребление памяти для огромных каталогов | Загрузка всех записей в память сразу | Используйте `Archive.CreateEntryFromFile` в цикле, чтобы потоково обрабатывать файлы по отдельности |

## Часто задаваемые вопросы (Дополнительно)

**В: Можно ли добавить пароль к ZIP‑архиву?**  
О: Да. Установите `archive.Password = "yourPassword";` перед вызовом `Save`.

**В: Как включить только определённые типы файлов?**  
О: Отфильтруйте коллекцию `DirectoryInfo` с помощью `GetFiles("*.txt")` или аналогичного метода перед вызовом `CreateEntries`.

**В: Есть ли способ обновить существующий ZIP без его полного пересоздания?**  
О: Aspose.Zip поддерживает инкрементные обновления через `Archive.UpdateEntry`.

## FAQ

### В1: Можно ли использовать Aspose.Zip для .NET в коммерческих и личных проектах?

О1: Да, Aspose.Zip для .NET лицензируется как для коммерческого, так и для личного использования.

### В2: Доступна ли бесплатная пробная версия?

О2: Да, вы можете попробовать бесплатную версию [здесь](https://releases.aspose.com/zip/net).

### В3: Как получить поддержку по Aspose.Zip для .NET?

О3: Посетите [форум Aspose.Zip](https://forum.aspose.com/c/zip/37) для поддержки сообщества или рассмотрите покупку [временной лицензии](https://purchase.aspose.com/temporary-license/) для персональной помощи.

### В4: Есть ли другие примеры и руководства?

О4: Да, в [документации](https://reference.aspose.com/zip/net/) содержится обширный набор примеров и учебных материалов.

### В5: Можно ли приобрести Aspose.Zip для .NET?

О5: Конечно, покупку можно оформить [здесь](https://purchase.aspose.com/buy).

## Заключение

Теперь у вас есть полностью готовый к продакшн‑использованию шаблон **как заархивировать папку** с помощью Aspose.Zip для .NET. Используя класс `Archive`, вы можете **создавать zip‑архивы**, задавать пользовательский `CompressionLevel`, добавлять защиту паролем и даже **заархивировать несколько папок** за один проход — что делает его идеальным для автоматизации резервного копирования папок. Поэкспериментируйте с API, добавьте шифрование, разбейте архивы на части или потоково передавайте их в облако, и у вас будет надёжное решение для любой задачи сжатия в .NET.

---

**Последнее обновление:** 2026-05-30  
**Тестировано с:** Aspose.Zip 24.11 для .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Похожие руководства

- [zip multiple files c# – Лёгкое сжатие с Aspose.Zip для .NET](/zip/net/file-compression/compress-multiple-files/)
- [Aspose.Zip для .NET – Защита паролем ZIP‑архива и хранение нескольких файлов без сжатия](/zip/net/password-protection-and-encryption/store-multiple-files-no-compression-password/)
- [Как заархивировать папку – Сжатие каталога с Aspose.Zip](/zip/net/directory-and-folder-compression/decompress-folder/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}