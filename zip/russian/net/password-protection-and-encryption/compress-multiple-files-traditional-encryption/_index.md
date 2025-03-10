---
title: Сжатие нескольких файлов с шифрованием в Aspose.Zip .NET
linktitle: Сжатие нескольких файлов с помощью традиционного шифрования
second_title: Aspose.Zip .NET API для сжатия и архивирования файлов
description: Узнайте, как безопасно сжимать несколько файлов с помощью традиционного шифрования в Aspose.Zip для .NET. Улучшите защиту данных в ваших приложениях .NET.
weight: 17
url: /ru/net/password-protection-and-encryption/compress-multiple-files-traditional-encryption/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Сжатие нескольких файлов с шифрованием в Aspose.Zip .NET


## Введение

Добро пожаловать в это пошаговое руководство по сжатию нескольких файлов с помощью традиционного шифрования с использованием Aspose.Zip для .NET. Aspose.Zip — это мощная библиотека, которая позволяет разработчикам беспрепятственно работать с zip-архивами в своих .NET-приложениях. В этом руководстве мы покажем вам процесс сжатия нескольких файлов с помощью традиционного шифрования, обеспечивающего безопасность ваших данных.

## Предварительные условия

Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:

-  Aspose.Zip для .NET: убедитесь, что в вашей среде разработки установлена библиотека Aspose.Zip для .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/zip/net/).

-  Каталог ваших документов: заменить`"Your Document Directory"`в фрагменте кода с указанием фактического пути к каталогу вашего документа.

## Импортировать пространства имен

В вашем .NET-приложении начните с импорта необходимых пространств имен. Это позволит вам получить доступ к функциям, предоставляемым Aspose.Zip. Вот пример:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Шаг 1. Настройте ZIP-файл

 Создайте новый zip-файл, используя`Archive` сорт. На этом этапе вы также определите традиционные параметры шифрования, предоставив пароль для дополнительной безопасности.

```csharp
//ExStart: CompressMultipleFilesWithTraditionalEncryption
using (FileStream zipFile = File.Open(".\\CompressMultipleFilesWithTraditionalEncryption_out.zip", FileMode.Create))
{
    // Создать архив с традиционными настройками шифрования.
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        // Перейдите к следующему шагу...
    }
}
//ExEnd: CompressMultipleFilesWithTraditionalEncryption
```

## Шаг 2. Добавьте файлы в архив

Теперь добавьте в архив файлы, которые хотите сжать. В этом примере мы добавляем три файла: «alice29.txt», «asyoulik.txt» и «fields.c».

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.CreateEntry("asyoulik.txt", source2);
archive.CreateEntry("fields.c", source3);
```

## Шаг 3. Сохраните ZIP-файл.

Сохраните zip-файл с добавленными записями. Этот шаг завершает процесс сжатия.

```csharp
archive.Save(zipFile);
```

Поздравляем! Вы успешно сжали несколько файлов с помощью традиционного шифрования с помощью Aspose.Zip для .NET.

## Заключение

В этом руководстве мы рассмотрели, как использовать Aspose.Zip для .NET для сжатия нескольких файлов с помощью традиционного шифрования. Этот процесс обеспечивает безопасность ваших данных и одновременно эффективно управляет zip-архивами в ваших приложениях .NET.

---

## Часто задаваемые вопросы

### 1. Могу ли я использовать Aspose.Zip для .NET в средах Windows и Linux?

Да, Aspose.Zip для .NET совместим со средами Windows и Linux, что обеспечивает гибкость для разработчиков.

### 2. Существует ли бесплатная пробная версия Aspose.Zip для .NET?

 Да, вы можете изучить бесплатную пробную версию Aspose.Zip для .NET.[здесь](https://releases.aspose.com/).

### 3. Как мне получить поддержку Aspose.Zip для .NET?

 Для получения поддержки или вопросов вы можете посетить[Форум Aspose.Zip](https://forum.aspose.com/c/zip/37).

### 4. Доступны ли временные лицензии для Aspose.Zip для .NET?

 Да, временные лицензии можно получить[здесь](https://purchase.aspose.com/temporary-license/).

### 5. Где я могу найти подробную документацию по Aspose.Zip для .NET?

Обратитесь к документации[здесь](https://reference.aspose.com/zip/net/) для более подробной информации.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
