---
date: 2026-06-29
description: Узнайте, как извлечь архив xar и распаковать файл xar в папку с помощью
  Aspose.Zip для .NET. Следуйте этому пошаговому руководству.
keywords:
- extract xar archive
- how to extract xar
- decompress xar file
- aspose zip decompress
linktitle: Распаковать Xar в папку
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to extract xar archive and decompress xar file to a folder
    using Aspose.Zip for .NET. Follow this step‑by‑step guide.
  headline: How to Extract Xar Archive to Folder Using Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip is regularly updated to ensure compatibility with the
      latest .NET framework versions. Refer to the [documentation](https://reference.aspose.com/zip/net/)
      for specific details.
    question: Is Aspose.Zip compatible with the latest .NET framework versions?
  - answer: Absolutely! You can download a free trial version from [here](https://releases.aspose.com/).
    question: Can I try Aspose.Zip before making a purchase?
  - answer: For any queries or assistance, visit the [Aspose.Zip forum](https://forum.aspose.com/c/zip/37).
    question: How can I get support for Aspose.Zip?
  - answer: Yes, temporary licenses can be obtained from [here](https://purchase.aspose.com/temporary-license/).
    question: Are temporary licenses available for Aspose.Zip?
  - answer: You can purchase Aspose.Zip for .NET [here](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Как извлечь архив Xar в папку с помощью Aspose.Zip для .NET
url: /ru/net/file-decompression/decompress-xar-folder/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как извлечь архив Xar в папку с помощью Aspose.Zip для .NET

Если вы разработчик .NET и вам нужно **быстро и надёжно извлекать файлы xar‑архивов**, Aspose.Zip для .NET предлагает чистый, высокопроизводительный API, который обрабатывает весь процесс без внешних инструментов. В этом руководстве мы пройдём каждый шаг, необходимый для распаковки Xar‑архива в папку, объясним, почему этот метод экономит ваше время, и предоставим готовый к запуску код. К концу вы поймёте, когда использовать этот подход, как интегрировать его в проект и как избежать распространённых подводных камней.

## Краткие ответы
- **Что делает библиотека?** Она читает и извлекает архивы Xar без внешних инструментов.  
- **Какие версии .NET поддерживаются?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 и .NET 5–10.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; коммерческая лицензия требуется для продакшна.  
- **Сколько времени занимает реализация?** Обычно менее 10 минут.  
- **Можно ли извлекать в пользовательскую папку?** Да — просто укажите целевой путь в `ExtractToDirectory`.

## Что такое «как извлечь xar»?
Извлечение Xar‑архива означает чтение сжатого пакета и запись его внутренних файлов в каталог на диске. Это полезно, когда вы получаете XAR‑пакеты из macOS‑инсталляторов, утилит резервного копирования или сторонних инструментов и нужно обработать их содержимое в приложении .NET.

## Почему использовать Aspose.Zip для этой задачи?
Aspose.Zip предоставляет нативное решение для .NET, устраняющее необходимость во внешних утилитах, обеспечивая быструю и надёжную распаковку с полной кроссплатформенной поддержкой.  
- **Никаких внешних зависимостей** — чистый .NET, без нативных бинарных файлов.  
- **API на основе потоков** — работает с файлами, потоками памяти или сетевыми потоками.  
- **Надёжная обработка ошибок** — подробные исключения помогают отлаживать повреждённые архивы.  
- **Полная совместимость с .NET** — работает в средах Windows, Linux и macOS.  
- **Широкая поддержка форматов** — Aspose.Zip может извлекать более 30 типов архивов (ZIP, TAR, XAR, 7z и др.) и обрабатывает файлы до 2 ГБ без загрузки всего архива в память, обеспечивая предсказуемую производительность даже на скромных серверах.

## Требования
Прежде чем приступить, убедитесь, что у вас есть следующее:

- **Aspose.Zip для .NET** — интегрирован в ваш проект. Скачать можно [здесь](https://releases.aspose.com/zip/net/).  
- **Каталог документов** — папка в вашем решении, где будет находиться примерный файл `.xar` и куда будет сохраняться результат распаковки.

## Импорт пространств имён
В вашем .NET‑проекте подключите необходимые пространства имён для доступа к функционалу Aspose.Zip:

```csharp
using System.IO;
using Aspose.Zip.Xar;
```

## Шаг 1: Определите каталог документов
```csharp
string dataDir = "Your Document Directory";
```

Замените `"Your Document Directory"` на абсолютный или относительный путь, содержащий `sample.xar` и в котором вы хотите создать папку вывода. Позднее использование `Path.Combine` помогает избежать проблем с разделителями путей в разных ОС.

## Шаг 2: Распаковать архив Xar
Класс `XarArchive` является точкой входа Aspose.Zip для чтения XAR‑контейнеров и получения их записей. Он предоставляет методы для перечисления файлов и их извлечения на диск.

```csharp
//ExStart: DecompressXarArchive
using (FileStream fs = File.OpenRead(dataDir + "sample.xar"))
{
    using (XarArchive archive = new XarArchive(fs))
    {
        archive.ExtractToDirectory(dataDir + "DecompressXar_out");
    }
}
```

Этот фрагмент открывает файл Xar, создаёт экземпляр `XarArchive` и извлекает **весь архив** в `DecompressXar_out`. Операция полностью основана на потоках, поэтому эффективно работает даже с большими пакетами.

## Как извлечь архив xar в папку?
`XarArchive.Open` открывает XAR‑архив и возвращает экземпляр `XarArchive`. `ExtractToDirectory` извлекает содержимое архива в указанный каталог.  
Загрузите файл XAR с помощью `XarArchive.Open("sample.xar")` и вызовите `archive.ExtractToDirectory("DecompressXar_out")`. API автоматически создаёт целевую папку, сохраняет исходную иерархию каталогов и записывает каждую запись через буферизованные потоки, так что вы получаете точную копию оригинального пакета всего в два вызова метода.

### Шаг 3: Запуск кода
Соберите и запустите приложение. После выполнения вы найдёте новую папку `DecompressXar_out` внутри вашего каталога документов, содержащую все файлы, упакованные в исходный `.xar`‑архив.

## Распространённые проблемы и советы
- **Файл не найден** — Убедитесь, что путь в `File.OpenRead` правильно указывает на `sample.xar`. Используйте `Path.Combine` для более безопасного построения пути.  
- **Отказ в доступе** — Запустите приложение с достаточными правами доступа к файловой системе, особенно при записи в защищённые каталоги.  
- **Повреждённый архив** — Aspose.Zip бросает `InvalidDataException`; проверьте целостность исходного файла `.xar`.  
- **Большие архивы** — При работе с архивами более 1 ГБ рассмотрите увеличение размера буфера через `ArchiveOptions` для повышения пропускной способности.

## Часто задаваемые вопросы

**В: Совместима ли Aspose.Zip с последними версиями .NET?**  
О: Да, Aspose.Zip регулярно обновляется для обеспечения совместимости с новейшими версиями .NET. Смотрите [документацию](https://reference.aspose.com/zip/net/) для деталей.

**В: Можно ли попробовать Aspose.Zip перед покупкой?**  
О: Конечно! Бесплатную пробную версию можно скачать [здесь](https://releases.aspose.com/).

**В: Как получить поддержку по Aspose.Zip?**  
О: По любым вопросам обращайтесь на [форум Aspose.Zip](https://forum.aspose.com/c/zip/37).

**В: Есть ли временные лицензии для Aspose.Zip?**  
О: Да, временные лицензии доступны [здесь](https://purchase.aspose.com/temporary-license/).

**В: Где купить Aspose.Zip для .NET?**  
О: Приобрести Aspose.Zip для .NET можно [здесь](https://purchase.aspose.com/buy).

**В: Можно ли извлекать только отдельные файлы из Xar‑архива?**  
О: Да — используйте `archive.Entries` для перечисления элементов и вызовите `ExtractToFile` у выбранных записей.

**В: Поддерживает ли библиотека зашифрованные Xar‑файлы?**  
О: В текущей версии Xar‑архивы не поддерживают шифрование; если вы столкнётесь с защищённым файлом, его необходимо расшифровать перед использованием Aspose.Zip.

---

**Последнее обновление:** 2026-06-29  
**Тестировано с:** Aspose.Zip 24.11 для .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как распаковать файлы с помощью Aspose.Zip для .NET](/zip/net/file-decompression/)
- [Как извлечь zip в папку с помощью Aspose.Zip для .NET](/zip/net/file-decompression/decompress-compressed-folder-directory/)
- [Создать tar-архив и добавить файлы в tar с помощью Aspose.Zip для .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}