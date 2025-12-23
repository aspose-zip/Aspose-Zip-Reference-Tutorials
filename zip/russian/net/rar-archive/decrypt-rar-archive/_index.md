---
date: 2025-12-23
description: Узнайте, как извлекать rar‑архивы, защищённые паролем, и распаковывать
  зашифрованные rar‑файлы с помощью Aspose.Zip для .NET. Следуйте пошаговому руководству,
  чтобы эффективно читать зашифрованный rar‑файл.
linktitle: Decrypting a RAR Archive
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Извлечение защищённого паролем RAR с помощью Aspose.Zip для .NET
url: /ru/net/rar-archive/decrypt-rar-archive/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Извлечение защищённого паролем RAR с помощью Aspose.Zip для .NET

## Introduction

Если вам когда‑нибудь нужно было **извлекать защищённый паролем rar** архивы в приложении .NET, вы знаете, насколько это сложно. К счастью, Aspose.Zip для .NET убирает догадки и позволяет читать зашифрованные rar‑файлы всего в несколько строк кода. В этом руководстве мы пройдем весь процесс — от настройки проекта до извлечения содержимого — чтобы вы могли без проблем интегрировать дешифрование в свои решения.

## Quick Answers
- **Какая библиотека обрабатывает дешифрование RAR?** Aspose.Zip for .NET  
- **Нужна ли лицензия для продакшн?** Да, требуется коммерческая лицензия.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Можно ли извлекать несколько архивов в цикле?** Конечно — просто повторяйте шаги для каждого файла.  
- **Пароль чувствителен к регистру?** Да, рассматривайте его как обычную строку.

## What is “extract password protected rar”?

Извлечение защищённого паролем RAR‑архива означает открытие архива, предоставление правильного пароля для дешифрования и запись содержащихся файлов в целевую папку. Aspose.Zip абстрагирует детали низкого уровня, позволяя сосредоточиться на бизнес‑логике.

## Why use Aspose.Zip for .NET?

- **Полная поддержка RAR** — Обрабатывает форматы RAR4 и RAR5, включая зашифрованные архивы.  
- **Простой API** — Достаточно нескольких вызовов методов, чтобы открыть, расшифровать и извлечь.  
- **Кроссплатформенный** — Работает на Windows, Linux и macOS в средах .NET.  
- **Без внешних зависимостей** — Не требуется поставлять сторонние утилиты RAR.

## Prerequisites

1. **Aspose.Zip for .NET Library** — Установите библиотеку через NuGet или скачайте её с [Aspose.Zip documentation](https://reference.aspose.com/zip/net/).  
2. **Document Directory** — Иметь папку, содержащую зашифрованный RAR‑архив, с которым вы хотите работать. Замените путь‑заполнитель в коде на ваш реальный каталог.

## Import Namespaces

Add the required `using` statements at the top of your C# file:

```csharp
//ExStart: ImportNamespaces
using Aspose.Zip;
using System.IO;
//ExEnd: ImportNamespaces
```

## Step 1: Open the Encrypted RAR Archive

Open a read‑only stream for the RAR file you wish to decrypt. Change `"encrypted.rar"` to match your file name.

```csharp
//ExStart: DecryptRarArchive_Step1
using (FileStream fs = File.OpenRead(dataDir + "encrypted.rar"))
{
    //ExEnd: DecryptRarArchive_Step1
    // Continue to the next step here...
}
```

## Step 2: Specify Decryption Password

Provide the password that protects the archive. In this example the password is `"p@s$"`. Replace it with the actual password you set.

```csharp
//ExStart: DecryptRarArchive_Step2
using (RarArchive archive = new RarArchive(fs, new RarArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
{
    //ExEnd: DecryptRarArchive_Step2
    // Continue to the next step here...
}
```

## Step 3: Extract Contents to Directory

Extract the decrypted files to a folder of your choice. Change `"DecompressRar_out"` to your desired output path.

```csharp
//ExStart: DecryptRarArchive_Step3
archive.ExtractToDirectory(dataDir + "DecompressRar_out");
//ExEnd: DecryptRarArchive_Step3
```

## How to extract password protected rar files using Aspose.Zip

Следуя трем шагам выше, вы можете **извлекать защищённый паролем rar** архивы программно. Этот подход работает с любым количеством файлов — просто перебирайте список файлов и повторяйте шаги.

## Common Use Cases

- **Автоматизированный ввод данных** — Получайте данные из зашифрованных RAR‑поставок и обрабатывайте их автоматически.  
- **Восстановление корпоративных резервных копий** — Расшифровывайте и восстанавливайте архивные бэкапы, хранящиеся в защищённых паролем RAR‑файлах.  
- **Безопасный обмен файлами** — Позвольте пользователям загружать зашифрованные RAR‑архивы, затем извлекать их на сервере после проверки.

## Conclusion

Теперь вы знаете, как **извлекать зашифрованные rar‑файлы** и **читать зашифрованный rar‑файл** с помощью Aspose.Zip для .NET. Библиотека берёт на себя тяжёлую работу, позволяя вам сосредоточиться на интеграции извлечённых данных в рабочий процесс вашего приложения.

## Frequently Asked Questions (FAQs)

### Поддерживает ли Aspose.Zip for .NET все версии RAR‑архивов?
Aspose.Zip for .NET поддерживает различные версии RAR‑архивов, обеспечивая совместимость с широким спектром файлов.

### Могу ли я использовать Aspose.Zip for .NET в коммерческих проектах?
Да, Aspose.Zip for .NET доступен для коммерческого использования. Посетите [purchase page](https://purchase.aspose.com/buy) для деталей лицензирования.

### Доступны ли временные лицензии для тестирования?
Да, вы можете получить временную лицензию для тестирования по ссылке [here](https://purchase.aspose.com/temporary-license/).

### Где я могу найти дополнительную поддержку или обсуждения сообщества?
Посетите [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) для поддержки и обсуждений.

### Как получить доступ к документации Aspose.Zip for .NET?
Документация по ссылке [documentation](https://reference.aspose.com/zip/net/) предоставляет полную информацию об использовании Aspose.Zip for .NET.

**Additional Q&A**

**Q: Что происходит, если пароль неверный?**  
A: Aspose.Zip бросает `InvalidPasswordException`. Перехватите исключение, чтобы корректно обработать ошибку.

**Q: Могу ли я извлекать только определённые файлы из архива?**  
A: Да, пройдитесь по `archive.Entries` и вызовите `entry.ExtractToFile()` для нужных записей.

**Q: Можно ли извлекать архивы размером более 2 ГБ?**  
A: Конечно — Aspose.Zip работает со потоками, поэтому размер файла ограничен только доступными системными ресурсами.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}