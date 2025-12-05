---
date: 2025-12-05
description: Узнайте, как создать zip‑архив и добавить файлы в zip с помощью Aspose.Zip
  для .NET. Этот пошаговый руководствe показывает, как сжимать файлы с помощью FileInfo
  в проектах ASP.NET.
language: ru
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Как создать ZIP‑архив с помощью Aspose.Zip для .NET – Сжатие файлов с использованием
  FileInfo
url: /net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать zip‑архив с помощью Aspose.Zip для .NET

## Введение

Если вам нужно **создать zip‑архив** программно, Aspose.Zip для .NET предоставляет чистый, высокопроизводительный API, который работает в любом приложении .NET (включая ASP.NET). В этом руководстве мы пройдемся по сжатию файлов с помощью класса `FileInfo`, покажем, как **добавлять файлы в zip**, и объясним, почему такой подход идеален для современных проектов .NET. Поехали!

## Быстрые ответы
- **Какой самый простой способ создать zip‑архив?** Использовать класс `Archive` из Aspose.Zip вместе с объектами `FileInfo`.  
- **Можно ли добавить несколько файлов сразу?** Да — просто создайте `FileInfo` для каждого файла и вызовите `CreateEntry`.  
- **Нужна ли специальная лицензия для ASP.NET?** Для продакшн‑использования требуется коммерческая лицензия Aspose.Zip; бесплатная пробная версия подходит для оценки.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Является ли API потокобезопасным?** Да, при условии, что каждый поток работает со своим экземпляром `Archive`.

## Что такое zip‑архив и зачем его создавать?
Zip‑архив объединяет один или несколько файлов в единый сжатый контейнер. Это уменьшает объём хранилища, ускоряет передачу по сети и упрощает распространение. Будь то доставка логов, экспорт отчётов или упаковка ресурсов для клиента, умение **создавать zip‑архивы** программно — ценное навыковое преимущество для любого разработчика .NET.

## Почему стоит использовать Aspose.Zip для добавления файлов в zip?
- **Никаких внешних зависимостей** — чистая реализация на .NET.  
- **Полный контроль над уровнем сжатия и кодировкой** (ASCII, UTF‑8 и др.).  
- **Поддержка больших файлов** (> 4 GB) и защиты паролем.  
- **Единый API для .NET Framework, .NET Core и .NET 5+**.

## Предварительные требования

Прежде чем перейти к коду, убедитесь, что у вас есть:

1. **Aspose.Zip для .NET** установлен. Скачайте последнюю версию с [страницы загрузки Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Папка на вашем компьютере, содержащая файлы, которые нужно сжать (например, `alice29.txt` и `fields.c`).  

## Подключение пространств имён

В любом C#‑файле, где вы будете работать с zip‑архивами, добавьте следующие `using`‑операторы:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Эти пространства имён предоставляют доступ к классу `Archive`, параметрам сохранения и стандартным утилитам ввода‑вывода.

## Пошаговое руководство

### Шаг 1: Настройте каталог с исходными файлами

Сначала укажите папку, в которой находятся исходные файлы. Замените заполнитель на абсолютный или относительный путь в вашей системе:

```csharp
string dataDir = "Your Document Directory";
```

> **Совет:** Используйте `Path.Combine` для построения путей кроссплатформенно.

### Шаг 2: Откройте zip‑файл для записи

Создайте `FileStream`, указывающий на выходной zip‑файл. Поток открывается в режиме **Create**, который перезаписывает любой существующий файл с тем же именем:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Шаг 3: Подготовьте объекты `FileInfo` для каждого исходного файла

`FileInfo` даёт Aspose.Zip прямой доступ к физическим файлам на диске. Создайте один экземпляр для каждого файла, который нужно сжать:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Зачем использовать `FileInfo`?** Он избегает загрузки всего файла в память, что особенно полезно для больших файлов.

### Шаг 4: Создайте архив и добавьте записи

Создайте объект `Archive`, затем вызовите `CreateEntry` для каждого `FileInfo`. Первый аргумент — имя файла внутри zip, второй аргумент —ный `FileInfo`:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Шаг 5: Сохраните zip‑архив с нужной кодировкой

Наконец, запишите архив в ранее открытый `FileStream`. Здесь мы используем кодировку ASCII для имён записей, но при необходимости можно переключиться на UTF‑8, если ваши имена файлов содержат не‑ASCII символы:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Когда блоки `using` завершаются, потоки автоматически закрываются, и zip‑файл готов к использованию.

## Распространённые проблемы и их решения

| Проблема | Причина | Решение |
|----------|---------|----------|
| **Пустой zip‑файл** | `FileInfo` указывает на несуществующий путь | Проверьте `dataDir` и имена файлов; используйте `File.Exists` для проверки перед созданием записей. |
| **Неправильная кодировка имён файлов** | Используется кодировка по умолчанию с не‑ASCII именами | Установите `Encoding = Encoding.UTF8` в `ArchiveSaveOptions`. |
| **OutOfMemoryException при работе с большими файлами** | Загрузка всего файла в память | `FileInfo` потоково читает файл; убедитесь, что вы не читаете его в массив байтов где‑то ещё. |
| **Отказ в доступе** | Приложение не имеет прав записи в целевую папку | Запустите приложение с нужными правами или выберите доступную директорию. |

## Часто задаваемые вопросы

**В: Можно ли добавить защиту паролем к zip‑архиву?**  
О: Да. После создания `Archive` задайте `archive.Password = "yourPassword"` перед вызовом `Save`.

**В: Можно ли обновлять существующий zip‑файл?**  
О: Aspose.Zip поддерживает открытие существующего архива через `Archive.Open` и последующее добавление новых записей.

**В: Как сжать файлы в контроллере ASP.NET MVC?**  
О: Тот же код работает; просто убедитесь, что выходной поток возвращается клиенту как `FileResult`.

**В: Поддерживает ли Aspose.Zip алгоритмы шифрования?**  
О: Да, поддерживаются стандартный ZipCrypto и AES‑256.

**В: Как рекурсивно сжать папку?**  
О: Пройдите `Directory.GetFiles` (и подпапки), создайте `FileInfo` для каждого файла и добавьте их в архив.

## Существующий раздел FAQ (оставлен без изменений)

### FAQ's

#### Q1: Is Aspose.Zip compatible with all file types?

A1: Aspose.Zip supports a wide range of file types, ensuring versatility in compression.

#### Q2: Can I use Aspose.Zip for commercial projects?

A2: Absolutely! Visit our [purchase page](https://purchase.aspose.com/buy) to explore licensing options.

#### Q3: How can I get support for Aspose.Zip?

A3: Join our community on the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) for assistance and discussions.

#### Q4: Is there a free trial available?

A4: Yes, you can grab your [free trial here](https://releases.aspose.com/).

#### Q5: How can I obtain a temporary license for Aspose.Zip?

A5: Visit [this link](https://purchase.aspose.com/temporary-license/) for information on obtaining a temporary license.

## Заключение

Теперь вы знаете, **как создавать zip‑архивы** с помощью Aspose.Zip для .NET, **как добавлять файлы в zip**, и почему этот метод идеален для ASP.NET и других приложений .NET. Экспериментируйте с различными уровнями сжатия, кодировками и параметрами шифрования, чтобы адаптировать архив под свои точные требования. Приятного сжатия!

---

**Последнее обновление:** 2025-12-05  
**Тестировано с:** Aspose.Zip для .NET 24.12 (latest)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}