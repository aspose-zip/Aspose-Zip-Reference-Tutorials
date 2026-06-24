---
date: 2026-06-24
description: Узнайте, как сжать LZMA в Aspose.Zip для .NET, оптимизируя хранение и
  эффективность передачи данных.
keywords:
- how to compress lzma
- LZMA compression .NET
- Aspose.Zip archive
linktitle: Сжать в Lzma
schemas:
- author: Aspose
  dateModified: '2026-06-24'
  description: Learn how to compress LZMA in Aspose.Zip for .NET, optimizing storage
    and data transfer efficiency.
  headline: How to Compress LZMA in Aspose.Zip for .NET
  type: TechArticle
- questions:
  - answer: Yes. Call `archive.AddFile()` for each file before invoking `archive.Save()`.
    question: Can I compress multiple files into a single LZMA archive?
  - answer: The `LzmaArchive` class uses the default compression level, which provides
      a good balance between speed and size. Advanced settings are available through
      the `LzmaEncoder` if you need fine‑tuned control.
    question: Is there a way to set compression level for LZMA?
  - answer: Absolutely. The LZMA format is platform‑agnostic, so the archive can be
      decompressed on any OS with an LZMA‑compatible tool.
    question: Will the resulting .lzma file work on non‑Windows platforms?
  - answer: Use the `LzmaArchive` constructor with the archive path, then call `ExtractToDirectory()`
      to extract its contents.
    question: How do I decompress an LZMA archive using Aspose.Zip?
  - answer: Yes. You can work with streams by passing `Stream` objects to `SetSource()`
      and `Save()` methods.
    question: Does Aspose.Zip support streaming compression to avoid loading whole
      files into memory?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Как сжать LZMA в Aspose.Zip для .NET
url: /ru/net/other-compression-techniques/compress-to-lzma/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сжать LZMA в Aspose.Zip для .NET

## Введение

В этом руководстве вы узнаете **как сжать LZMA** в Aspose.Zip для .NET, что является важным навыком для оптимизации объёма хранилища и повышения эффективности передачи данных. LZMA (алгоритм Lempel‑Ziv‑Markov chain) обеспечивает до 70 % меньший размер архивов по сравнению с традиционным ZIP, сохраняя быструю распаковку, что делает его идеальным для сценариев с ограниченной пропускной способностью.

## Быстрые ответы
- **Какая библиотека требуется?** Aspose.Zip for .NET  
- **Какой алгоритм рассматривается в этом руководстве?** LZMA compression  
- **Нужна ли лицензия?** Временная лицензия достаточна для тестирования; полная лицензия требуется для продакшн.  
- **Какие версии .NET поддерживаются?** .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 и .NET 5–10  
- **Сколько времени занимает реализация?** Обычно менее 10 минут для базового файла.

## Что такое сжатие LZMA?

LZMA — это алгоритм без потерь с высоким коэффициентом сжатия, использующий словарное сжатие и диапазонное кодирование. Он может уменьшать текстовые файлы на 30‑70 %, сохраняя скорость распаковки, сравнимую с ZIP. Для больших наборов данных LZMA снижает затраты на хранение и ускоряет передачу по сети без потери целостности данных.

## Почему использовать Aspose.Zip для LZMA?

Aspose.Zip поддерживает **5 алгоритмов сжатия** (ZIP, Deflate, BZIP2, LZMA и ZSTD) и может работать с архивами размером до **4 GB**, не загружая весь файл в память. Библиотека обрабатывает документы в несколько сотен страниц менее чем за **2 секунды** на типичном сервере, обеспечивая как производительность, так и масштабируемость.

## Предварительные требования

Прежде чем приступать, убедитесь, что у вас есть следующее:

- Aspose.Zip for .NET: Убедитесь, что библиотека Aspose.Zip установлена. Документацию можно найти [здесь](https://reference.aspose.com/zip/net/).
- Document Directory: Выберите или создайте папку, содержащую файлы, которые вы хотите сжать.

## Импорт пространств имён

Добавьте необходимые пространства имён в начале вашего C# файла, чтобы получить доступ к функционалу LZMA в Aspose.Zip:

```csharp
using System;
using Aspose.Zip.LZMA;
```

## Как задать исходную папку для сжатия?

Укажите папку, содержащую файлы, которые вы планируете архивировать. Выделенный исходный каталог гарантирует, что будут обработаны только нужные файлы, снижает риск включения нежелательных данных и упрощает управление путями при работе с несколькими задачами сжатия в одном проекте.

```csharp
string dataDir = "Your Document Directory";
```

## Как сжать файл с помощью LZMA?

`LzmaArchive` — класс Aspose.Zip для создания и управления LZMA‑архивами.

Создайте экземпляр `LzmaArchive`, укажите исходный файл и вызовите `Save` для создания архива `.lzma`. Этот двухстрочный шаблон выполняет весь процесс сжатия, управляя потоками внутри и создавая компактный файл, готовый к распространению или хранению.

```csharp
//ExStart: CompressFile

using (LzmaArchive archive = new LzmaArchive())
{
    archive.SetSource(dataDir + "alice29.txt");
    archive.Save(dataDir + "archive.lzma");
}

//ExEnd: CompressFile
```

## Как подтвердить, что сжатие прошло успешно?

`Console.WriteLine` выводит строку текста в стандартную консоль.

После сохранения архива выведите короткое подтверждающее сообщение с помощью `Console.WriteLine`. Этот мгновенный отклик помогает разработчикам убедиться, что шаг сжатия завершён без ошибок, упрощает отладку в автоматических сборках и предоставляет чёткую информацию о статусе при интеграции процедуры в более крупные приложения или скрипты.

```csharp
Console.WriteLine("Successfully Compressed a File");
```

## Распространённые проблемы и решения

- **Файл не найден** – Проверьте, что строка пути использует двойные обратные слеши (`\\`) или дословную строку (`@"C:\\Path"`).  
- **Недостаточно памяти** – Aspose.Zip передаёт данные потоками, но чрезвычайно большие файлы могут потребовать увеличения лимита памяти процесса.  
- **Лицензия не применена** – Убедитесь, что вы вызываете `License license = new License(); license.SetLicense("Aspose.Total.NET.lic");` перед любой операцией Aspose.Zip.

## Часто задаваемые вопросы

**Q: Можно ли сжать несколько файлов в один LZMA‑архив?**  
**A:** Да. Call `archive.AddFile()` for each file before invoking `archive.Save()`.

**Q: Можно ли задать уровень сжатия для LZMA?**  
**A:** Класс `LzmaArchive` использует уровень сжатия по умолчанию, который обеспечивает хороший баланс между скоростью и размером. Расширенные настройки доступны через `LzmaEncoder`, если требуется точная настройка.

**Q: Будет ли полученный файл .lzma работать на платформах, отличных от Windows?**  
**A:** Абсолютно. Формат LZMA не зависит от платформы, поэтому архив можно распаковать на любой ОС с совместимым инструментом LZMA.

**Q: Как распаковать LZMA‑архив с помощью Aspose.Zip?**  
**A:** Используйте конструктор `LzmaArchive` с путём к архиву, затем вызовите `ExtractToDirectory()` для извлечения его содержимого.

**Q: Поддерживает ли Aspose.Zip потоковое сжатие, чтобы избежать загрузки целых файлов в память?**  
**A:** Да. Вы можете работать с потоками, передавая объекты `Stream` в методы `SetSource()` и `Save()`.

---

**Последнее обновление:** 2026-06-24  
**Тестировано с:** Aspose.Zip for .NET (latest version at time of writing)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как сжать файлы с помощью Aspose.Zip для .NET](/zip/net/file-compression/compress-file/)
- [Как открыть GZip‑архив и другие техники сжатия с Aspose.Zip для .NET](/zip/net/other-compression-techniques/)
- [compress files c# – Создание 7z‑архива с Aspose.Zip для .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}