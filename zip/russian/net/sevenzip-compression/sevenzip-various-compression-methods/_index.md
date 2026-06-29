---
date: 2026-06-29
description: Узнайте, как сжать папку в 7z с помощью Aspose.Zip for .NET, рассматривая
  методы сжатия SevenZip, такие как LZMA2, BZip2 и Store. Идеально подходит для программного
  создания архивов 7z.
keywords:
- compress folder to 7z
- add files to 7z
- create 7z without compression
- seven zip compression methods
linktitle: SevenZip с различными методами сжатия
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to compress folder to 7z with Aspose.Zip for .NET, covering
    seven zip compression methods such as LZMA2, BZip2, and Store. Perfect for creating
    7z archives programmatically.
  headline: How to Compress Folder to 7z – Aspose.Zip for .NET Tutorial
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Zip supports a wide range of file formats, allowing you to
      compress and decompress virtually any file type.
    question: Can I use Aspose.Zip for .NET with any type of file?
  - answer: Yes, you can obtain a free trial **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Zip for .NET?
  - answer: The full API reference is available **[here](https://reference.aspose.com/zip/net/)**.
    question: Where can I find documentation for Aspose.Zip for .NET?
  - answer: Temporary licenses can be obtained **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licenses for Aspose.Zip for .NET?
  - answer: You can seek support on the **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.
    question: Where can I get support for Aspose.Zip for .NET?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Как сжать папку в 7z – руководство по Aspose.Zip for .NET
url: /ru/net/sevenzip-compression/sevenzip-various-compression-methods/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сжать папку в 7z – руководство Aspose.Zip для .NET

## Введение

Если вам нужно **compress folder to 7z** архивы программно в приложении .NET, вы попали по адресу. Aspose.Zip for .NET упрощает создание Seven Zip архивов с любым из поддерживаемых алгоритмов сжатия, будь то упаковка целой директории для распространения или просто надёжное решение **seven zip archive .net**. В этом руководстве мы рассмотрим три популярных метода сжатия — LZMA2, BZip2 и Store (без сжатия) — и покажем, как создать 7z‑файл всего в несколько строк кода C#.

## Быстрые ответы
- **Какую библиотеку использовать?** Aspose.Zip for .NET предоставляет самый полный набор функций Seven Zip.  
- **Какой метод сжатия даёт лучший коэффициент?** LZMA2 обычно обеспечивает наивысшее сжатие для смешанных данных.  
- **Можно ли создать 7z без какого‑либо сжатия?** Да — используйте метод Store (без сжатия).  
- **Нужна ли лицензия для разработки?** Доступна бесплатная пробная версия; лицензия требуется для продакшн‑использования.  
- **Совместимо ли это с .NET 6/7?** Абсолютно — Aspose.Zip поддерживает .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1 и .NET 5–10.

## Какие существуют методы сжатия Seven Zip?

Seven Zip поддерживает несколько алгоритмов, каждый из которых оптимизирован под разные сценарии. **LZMA2** обеспечивает наивысший коэффициент сжатия (обычно на 30‑40 % лучше, чем BZip2), **BZip2** предлагает надёжное сжатие с более широкой поддержкой устаревших инструментов, а **Store** просто архивирует файлы без их уменьшения, полностью сохраняя оригинальные метки времени.

## Требования

Перед тем как начать, убедитесь, что у вас есть:

- Базовые знания C# и Visual Studio.  
- Установленная библиотека Aspose.Zip for .NET. Скачайте её со страницы официального скачивания **[here](https://releases.aspose.com/zip/net/)**.  
- Папка (`dataDir`) с файлами, которые нужно заархивировать.

## Импорт пространств имён

Сначала добавьте необходимые пространства имён в ваш C#‑файл:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

Эти классы дают доступ к настройкам сжатия и работе с архивами.

## Сжатие LZMA2 – Как создать 7z с максимальным коэффициентом сжатия

Класс `Archive` представляет 7z‑архив, который может содержать несколько файлов.  
Алгоритм LZMA2 обеспечивает наивысший коэффициент сжатия среди поддерживаемых методов. Он работает, разбивая входные данные на блоки и применяя сложное словарное сжатие. В Aspose.Zip вы задаёте `CompressionMethod` равным `CompressionMethod.Lzma2` у объекта `Archive` перед добавлением файлов.

```csharp
//ExStart: SevenZipWithVariousCompressionMethods

//LZMA2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipLZMA2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_lzma2.7z");
}

//ExEnd: SevenZipWithVariousCompressionMethods
Console.WriteLine("Successfully Created a Seven Zip File with LZMA2 Compression");
```

> **Pro tip:** LZMA2 работает лучше всего, когда исходные файлы больше 1 МБ. Для множества небольших файлов BZip2 может быть быстрее.

## Сжатие BZip2 – Сбалансированный выбор

Класс `Archive` представляет 7z‑архив, который может содержать несколько файлов.  
BZip2 предлагает надёжное сжатие с хорошей совместимостью со старыми инструментами. Он использует преобразование Бурроуза‑Уилера и кодирование Хаффмана для уменьшения размера. В Aspose.Zip вы выбираете `CompressionMethod.BZip2` при настройке экземпляра `Archive`, что обеспечивает баланс между скоростью и коэффициентом сжатия для большинства текстовых и бинарных файлов.

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

BZip2 обеспечивает хорошее сжатие при приемлемой скорости, что делает его надёжным вариантом, когда LZMA2 не поддерживается целевой средой.

## Store (без сжатия) – Когда размер не важен

Класс `Archive` представляет 7z‑архив, который может содержать несколько файлов.  
Метод Store создаёт архив без сжатия данных. Он просто копирует оригинальные файлы в контейнер 7z, сохраняя метки времени и структуру каталогов. Чтобы использовать его в Aspose.Zip, установите `CompressionMethod.Store` у `Archive` перед добавлением файлов, которые нужно собрать.

```csharp
//Store, no compression
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

Используйте метод Store, если вам нужно просто собрать файлы вместе без изменения их размера — идеально для сохранения оригинальных меток времени или когда архив будет распакован «на лету».

## Как добавить файлы в 7z?

Добавляйте файлы в 7z‑архив, создавая экземпляр `Archive`, задавая желаемый `CompressionMethod` и вызывая `AddAllFiles(dataDir)`. Метод рекурсивно сканирует указанную папку, сохраняя иерархию каталогов внутри архива. Такой подход позволяет **compress folder to 7z** одной строкой кода после первоначальной настройки.

## Распространённые сценарии использования

| Сценарий | Рекомендуемый метод |
|----------|--------------------|
| Распространение крупных установщиков | LZMA2 |
| Обмен журналами со старыми инструментами | BZip2 |
| Упаковка файлов для быстрой распаковки | Store (no compression) |
| Необходимо **compress folder to 7z** на лету в веб‑сервисе | LZMA2 (для лучшего коэффициента) |

## Устранение неполадок и советы

- **Отсутствуют файлы в архиве?** Проверьте, что `dataDir` указывает на правильный каталог и процесс имеет права чтения.  
- **Архив не открывается в старых версиях 7‑Zip?** Оставайтесь на BZip2 или Store, так как LZMA2 может требовать более новых библиотек декомпрессии.  
- **Узкое место в производительности?** Для огромных наборов данных рассмотрите потоковую запись архива вместо загрузки всех записей в память.

## Часто задаваемые вопросы

**В: Можно ли использовать Aspose.Zip for .NET с любым типом файлов?**  
О: Да, Aspose.Zip поддерживает широкий спектр форматов файлов, позволяя сжимать и распаковывать практически любой тип файлов.

**В: Доступна ли бесплатная пробная версия Aspose.Zip for .NET?**  
О: Да, бесплатную пробную версию можно получить **[here](https://releases.aspose.com/)**.

**В: Где найти документацию по Aspose.Zip for .NET?**  
О: Полная ссылка на API доступна **[here](https://reference.aspose.com/zip/net/)**.

**В: Как получить временные лицензии для Aspose.Zip for .NET?**  
О: Временные лицензии можно получить **[here](https://purchase.aspose.com/temporary-license/)**.

**В: Где можно получить поддержку по Aspose.Zip for .NET?**  
О: Поддержку можно искать на **[Aspose.Zip forum](https://forum.aspose.com/c/zip/37)**.

---

**Последнее обновление:** 2026-06-29  
**Тестировано с:** Aspose.Zip for .NET 24.12  
**Автор:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Похожие руководства

- [compress files c# – Create 7z archive with Aspose.Zip for .NET](/zip/net/sevenzip-compression/create-sevenzip-entries/)
- [How to Zip Folder Using Aspose.Zip for .NET](/zip/net/directory-and-folder-compression/compress-directory/)
- [How to Compress LZMA in Aspose.Zip for .NET](/zip/net/other-compression-techniques/compress-to-lzma/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}