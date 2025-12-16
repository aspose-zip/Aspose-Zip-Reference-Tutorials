---
date: 2025-12-14
description: Узнайте, как распаковать zip в C# и извлечь отдельный zip‑файл с помощью
  Aspose.Zip для .NET в ваших проектах на C#.
linktitle: Decompressing a Single File
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Распаковка zip в C# – извлечение отдельного файла с помощью Aspose.Zip
url: /ru/net/file-decompression/decompress-single-file/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Распаковка zip c# – Извлечение одного файла с помощью Aspose.Zip

## Introduction

Если вам нужно **decompress zip c#** файлы и извлечь только одну запись, Aspose.Zip for .NET делает задачу простой. В этом руководстве мы пройдем полный, реальный пример, показывающий, как извлечь один файл из ZIP‑архива, отслеживать прогресс и обработать результат чистым, поддерживаемым способом. К концу вы будете уверенно добавлять zip extraction в любое приложение C#.

## Quick Answers
- **Что покрывает это руководство?** Распаковка ZIP‑архива и извлечение одного файла с помощью Aspose.Zip for .NET.  
- **Какой основной ключевой запрос?** decompress zip c#  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; коммерческая лицензия требуется для продакшна.  
- **Поддерживается ли .NET Core?** Да — тот же код работает на .NET Framework и .NET Core.  
- **Сколько времени занимает реализация?** Около 10‑15 минут для базовой настройки.

## Требования

Прежде чем приступить к руководству, убедитесь, что у вас есть следующие требования:

- Aspose.Zip for .NET Library: Скачайте и установите библиотеку из [Aspose.Zip for .NET Documentation](https://reference.aspose.com/zip/net/).
- Development Environment: Иметь готовую рабочую среду разработки .NET, включая Visual Studio или любую другую совместимую IDE.
- Basic Understanding of C#: Ознакомьтесь с основами программирования на C#.

А теперь давайте приступим к коду!

## Импорт пространств имён

Начните с импорта необходимых пространств имён, чтобы начать работу с Aspose.Zip:

```csharp
using Aspose.Zip;
using System;
using System.IO;
```

## Пошаговое руководство по decompress zip c#

### Шаг 1: Установите ваш Document Directory

Начните с указания каталога, где хранятся ваши документы. Замените `"Your Document Directory"` на фактический путь.

```csharp
string dataDir = "Your Document Directory";
```

### Шаг 2: Создайте сжатый файл (демо‑настройка)

Следующий вызов создаёт пример ZIP‑файла, который мы позже распакуем. Это отражает типичный сценарий, когда у вас уже есть ZIP‑архив.

```csharp
CompressSingleFile.Run();
```

### Шаг 3: Распаковать файл – извлечь один файл из ZIP

Теперь давайте перейдём к сути – извлечению единственной записи. Приведённый ниже код открывает ZIP‑архив, привязывает обработчик прогресса и извлекает первую запись в текстовый файл.

```csharp
// ExStart: DecompressSingleFile
using (FileStream fs = File.OpenRead(dataDir + "CompressSingleFile_out.zip"))
{
    using (Archive archive = new Archive(fs))
    {
        int percentReady = 0;
        archive.Entries[0].ExtractionProgressed += (s, e) =>
        {
            int percent = (int)((100 * e.ProceededBytes) / ((ArchiveEntry)s).UncompressedSize);
            if (percent > percentReady)
            {
                Console.WriteLine(string.Format("{0}% decompressed", percent));
                percentReady = percent;
            }
        };
        archive.Entries[0].Extract(dataDir + "alice_extracted_out.txt");
    }
}
```

Этот фрагмент **извлекает одну zip‑запись**, одновременно выводя прогресс в реальном времени (например, “30% decompressed”). Вы можете изменить индекс (`Entries[0]`), чтобы выбрать любой другой файл внутри архива.

## Почему использовать Aspose.Zip для распаковки файлов C#?

- **Нет внешних зависимостей** – чистая .NET‑библиотека.  
- **Поддерживает большие архивы** с потоковой обработкой, поэтому использование памяти остаётся низким.  
- **Встроенные события прогресса** упрощают предоставление обратной связи в UI.  
- **Работает на .NET Framework, .NET Core и .NET 5/6**.

## Распространённые проблемы и советы

- **Разделители путей файлов** – используйте `Path.Combine` для кросс‑платформенной безопасности.  
- **ZIP‑архивы с паролем** – задайте `archive.Password` перед извлечением.  
- **Несколько записей** – перебирайте `archive.Entries` и сравнивайте по `FileName`.  

## Часто задаваемые вопросы

### Q1: Могу ли я сжать несколько файлов с помощью Aspose.Zip for .NET?

A1: Да, Aspose.Zip for .NET поддерживает сжатие нескольких файлов. Обратитесь к документации для подробных инструкций.

### Q2: Совместим ли Aspose.Zip с .NET Core?

A2: Абсолютно! Aspose.Zip без проблем интегрируется как с .NET Framework, так и с .NET Core.

### Q3: Как работать с архивами, защищёнными паролем?

A3: Aspose.Zip предоставляет методы для работы с архивами, защищёнными паролем. Обратитесь к документации за рекомендациями.

### Q4: Есть ли особенности лицензирования при использовании Aspose.Zip?

A4: Ознакомьтесь с информацией о лицензировании на [Aspose website](https://purchase.aspose.com/buy).

### Q5: Где можно получить помощь, если возникнут проблемы?

A5: Посетите [Aspose.Zip Forum](https://forum.aspose.com/c/zip/37) для поддержки сообщества.

## Заключение

Поздравляем! Вы успешно разобрались с нюансами **decompress zip c#** и извлекли один файл с помощью Aspose.Zip for .NET. Внедрите этот шаблон в свои приложения, чтобы упростить работу с файлами, улучшить пользовательский опыт и поддерживать чистоту кода.

---

**Last Updated:** 2025-12-14  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}