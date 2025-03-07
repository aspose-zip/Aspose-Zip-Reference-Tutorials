---
title: Aspose.Zip для .NET — Учебное пособие по безопасному хранению файлов
linktitle: Храните несколько файлов без сжатия с паролем
second_title: Aspose.Zip .NET API для сжатия и архивирования файлов
description: Узнайте, как использовать Aspose.Zip для .NET для безопасного хранения нескольких файлов без сжатия. Простые шаги для защиты паролем. Раскройте возможности управления файлами!
weight: 13
url: /ru/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Zip для .NET — Учебное пособие по безопасному хранению файлов


В мире .NET-разработки управление файлами и манипулирование ими является обычной задачей. Aspose.Zip для .NET — это мощная библиотека, которая предоставляет разработчикам возможность легко сжимать, распаковывать и манипулировать zip-архивами. В этом уроке мы углубимся в конкретный сценарий: хранение нескольких файлов без сжатия и защиту их паролем. К концу этого руководства вы будете обладать знаниями по реализации этой функциональности с помощью Aspose.Zip для .NET.

## Предварительные условия

Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:

-  Библиотека Aspose.Zip для .NET: убедитесь, что у вас установлена библиотека Aspose.Zip для .NET. Вы можете скачать его[здесь](https://releases.aspose.com/zip/net/).

-  Каталог документов: подготовьте каталог, в котором расположены исходные файлы. В приведенном примере переменная`dataDir` представляет каталог вашего документа.

## Импортировать пространства имен

Для начала давайте импортируем необходимые пространства имен для нашего кода:

```csharp
// Путь к каталогу ресурсов.
string dataDir = "Your Document Directory"

// Импорт пространств имен Aspose.Zip
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## Шаг 1: Откройте ZIP-файл

```csharp
//ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

 Этот шаг включает в себя создание нового zip-файла с помощью`FileStream`. Файл будет называться «StoreMutlipleFilesWithoutCompressionWithPassword_out.zip».

## Шаг 2. Откройте исходный файл

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

Здесь мы открываем первый исходный файл «alice29.txt», который будет храниться в zip-архиве.

## Шаг 3. Создайте архив

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

 На этом этапе мы создаем экземпляр`Archive` class, определяющий настройки сжатия и шифрования. Мы используем`StoreCompressionSettings` хранить файлы без сжатия и`AesEcryptionSettings` применить шифрование AES с паролем («p@s$»).

## Шаг 4. Создайте запись в архиве и сохраните ее.

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

Этот последний шаг включает в себя создание записи в архиве «alice29.txt» и сохранение архива, завершая процесс сохранения файла без сжатия и с защитой паролем.

Завершите руководство, суммировав ключевые моменты и предложив читателям изучить дополнительные возможности Aspose.Zip для .NET.

## Заключение

В этом уроке мы рассмотрели, как использовать Aspose.Zip для .NET для хранения нескольких файлов без сжатия и защиты их паролем. Продолжая свой путь разработки .NET, используйте возможности Aspose.Zip для оптимизации задач управления файлами и повышения безопасности ваших приложений.

---

### Часто задаваемые вопросы

### Могу ли я использовать Aspose.Zip для .NET с другими методами шифрования?
 Да, Aspose.Zip поддерживает различные методы шифрования. Проверьте документацию[здесь](https://reference.aspose.com/zip/net/) для получения подробной информации.

### Где я могу получить поддержку Aspose.Zip для .NET?
 Посетить[Форум Aspose.Zip](https://forum.aspose.com/c/zip/37) за поддержку сообщества и обсуждения.

### Доступна ли бесплатная пробная версия Aspose.Zip для .NET?
 Да, вы можете получить доступ к бесплатной пробной версии[здесь](https://releases.aspose.com/).

### Как я могу получить временную лицензию на Aspose.Zip для .NET?
 Запросить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).

### Где я могу приобрести Aspose.Zip для .NET?
 Вы можете купить Aspose.Zip для .NET.[здесь](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
