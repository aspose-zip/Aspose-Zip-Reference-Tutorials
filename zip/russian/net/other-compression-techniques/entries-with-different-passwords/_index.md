---
date: 2025-12-18
description: Узнайте, как шифровать zip‑файлы разными паролями с помощью Aspose.Zip
  для .NET. Это руководство показывает, как сжимать файлы с паролями и создавать архивы
  7z на C#.
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Как зашифровать ZIP‑файлы разными паролями в Aspose.Zip для .NET
url: /ru/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как зашифровать ZIP‑файлы с разными паролями в Aspose.Zip для .NET

## Введение

Если вам нужно **зашифровать zip**‑архивы, задавая каждому элементу свой пароль, вы попали по адресу. В этом руководстве мы пошагово покажем, как создать 7‑zip‑архив, где каждый файл защищён уникальным паролем, используя библиотеку Aspose.Zip для .NET. К концу вы поймёте, почему важна шифровка на уровне отдельных записей, как её настроить и как проверить результат в своих проектах.

## Быстрые ответы
- **Что означает «encrypt zip»?** Это применение защиты на основе пароля (AES или ZipCrypto) к содержимому ZIP/7z‑архива.  
- **Можно ли задать разный пароль для каждой записи?** Да — Aspose.Zip позволяет назначать отдельные пароли для файлов.  
- **Какие версии .NET поддерживаются?** Все современные .NET Framework, .NET Core и .NET 5/6.  
- **Нужна ли лицензия для продакшн?** Для использования в продакшн требуется коммерческая лицензия; доступна бесплатная пробная версия.  
- **Какой формат сжатия используется в примере?** Пример создаёт 7z‑архив с шифрованием AES‑256.

## Что такое «how to encrypt zip» с Aspose.Zip?

Шифрование ZIP (или 7z)‑файла означает защиту его записей так, чтобы их нельзя было открыть без правильного пароля. Aspose.Zip для .NET поддерживает как классический ZipCrypto, так и более надёжное AES‑шифрование, и позволяет задавать параметры шифрования для каждой записи отдельно, предоставляя тонкую настройку безопасности.

## Почему стоит использовать разные пароли для каждой записи?

- **Сегментация безопасности:** Если один пароль будет скомпрометирован, остальные файлы останутся защищёнными.  
- **Соответствие нормативам:** В некоторых отраслях требуется отдельные учётные данные для разных категорий данных.  
- **Доступ для конкретных пользователей:** Один архив можно распределять нескольким пользователям, каждый из которых сможет открыть только те файлы, к которым у него есть право доступа.

## Предварительные требования

Прежде чем приступить, убедитесь, что у вас есть:

- **Aspose.Zip для .NET** установлен — см. официальную [документацию](https://reference.aspose.com/zip/net/) для загрузки и инструкций по установке.  
- Папка на вашем компьютере, где будут храниться исходные файлы («Document Directory»).  
- Базовые знания C# и Visual Studio (или любой другой предпочитаемой IDE для .NET).

## Подключение пространств имён

Начинаем с подключения пространств имён, содержащих необходимые классы.

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Шаг 1: Укажите каталог документов

Определите путь, в котором находятся файлы, которые нужно заархивировать.

```csharp
string dataDir = "Your Document Directory";
```

## Шаг 2: Создайте записи с разными паролями

Это ядро руководства. Мы открываем новый 7z‑файл, создаём три объекта `FileInfo` и добавляем каждый как запись со своим паролем AES.

```csharp
//ExStart: EntriesWithDifferentPasswords
using (FileStream sevenZipFile = File.Open("archive.7z", FileMode.Create))
{
    FileInfo fi1 = new FileInfo("data1.bin");
    FileInfo fi2 = new FileInfo("data2.bin");
    FileInfo fi3 = new FileInfo("data3.bin");

    using (var archive = new SevenZipArchive())
    {
        archive.CreateEntry("entry1.bin", fi1, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test1")));
        archive.CreateEntry("entry2.bin", fi2, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test2")));
        archive.CreateEntry("entry3.bin", fi3, false, new SevenZipEntrySettings(new SevenZipStoreCompressionSettings(), new SevenZipAESEncryptionSettings("test3")));
        
        archive.Save(sevenZipFile);
    }
}
//ExEnd: EntriesWithDifferentPasswords
```

### Как это работает

- `SevenZipArchive` — контейнер для 7‑z‑архива.  
- `CreateEntry` принимает имя записи, исходный файл, флаг перезаписи и объект `SevenZipEntrySettings`.  
- В `SevenZipEntrySettings` мы указываем два объекта настроек: один для сжатия (`SevenZipStoreCompressionSettings`), другой для шифрования (`SevenZipAESEncryptionSettings`).  
- Каждый вызов передаёт **разный пароль** (`"test1"`, `"test2"`, `"test3"`), обеспечивая защиту на уровне отдельных записей.

## Шаг 3: Проверка

После сохранения архива выведите простое подтверждающее сообщение.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Запустите программу, затем попытайтесь открыть `archive.7z` с помощью инструмента, например 7‑Zip. Он запросит пароль для каждой записи, подтверждая, что пароли действительно различаются.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|---------|
| **Ошибка «Incorrect password»** | В строке пароля присутствуют лишние пробелы или невидимые символы. | Обрежьте строки паролей (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Архив не открывается в старых инструментах** | Некоторые устаревшие ZIP‑утилиты не поддерживают AES‑256, используемый в 7z. | Используйте современный извлекатель (7‑Zip 19.00+). |
| **Файл не добавлен в архив** | Неправильный путь к исходному файлу или файл не существует. | Проверьте `dataDir` и имена файлов, либо используйте `Path.Combine(dataDir, "data1.bin")`. |

## Часто задаваемые вопросы

### В1: Совместима ли Aspose.Zip для .NET со всеми версиями .NET?

ОТВ: Да, Aspose.Zip для .NET разработан для бесшовной интеграции со всеми версиями .NET Framework.

### В2: Можно ли использовать Aspose.Zip для .NET в коммерческих проектах?

ОТВ: Абсолютно! Aspose.Zip для .NET предлагает коммерческие лицензии, подробнее о покупке можно узнать [здесь](https://purchase.aspose.com/buy).

### В3: Доступна ли бесплатная пробная версия?

ОТВ: Да, вы можете опробовать функции Aspose.Zip для .NET с помощью бесплатного триала. Начать можно [здесь](https://releases.aspose.com/).

### В4: Как получить поддержку по Aspose.Zip для .NET?

ОТВ: По любым вопросам или запросам обращайтесь к [форуму Aspose.Zip](https://forum.aspose.com/c/zip/37).

### В5: Можно ли пользоваться Aspose.Zip для .NET без постоянной лицензии?

ОТВ: Да, можно оформить временную лицензию для краткосрочных задач. Подробнее см. [здесь](https://purchase.aspose.com/temporary-license/).

## Заключение

Вы только что узнали, **как зашифровать zip**‑архивы с паролями на уровне отдельных записей, используя Aspose.Zip для .NET. Эта техника даёт гибкость защищать каждый файл индивидуально, отвечая более строгим требованиям безопасности и упрощая распределение архивов для конкретных пользователей. Экспериментируйте с другими настройками сжатия, большими наборами файлов или интегрируйте эту логику в веб‑службу, генерирующую защищённые архивы «на лету».

---

**Последнее обновление:** 2025-12-18  
**Тестировано с:** Aspose.Zip для .NET 24.12 (последняя на момент написания)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}