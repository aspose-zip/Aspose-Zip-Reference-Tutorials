---
title: Tạo bảy tệp Zip - Hướng dẫn Aspose.Zip cho .NET
linktitle: SevenZip với nhiều phương pháp nén khác nhau
second_title: API Aspose.Zip .NET để nén và lưu trữ tệp
description: Tìm hiểu cách tạo bảy tệp Zip bằng Aspose.Zip cho .NET bằng các phương pháp nén khác nhau. Các bước dễ dàng cho LZMA2, BZip2 và Store (không nén).
type: docs
weight: 12
url: /vi/net/sevenzip-compression/sevenzip-various-compression-methods/
---

## Giới thiệu

Trong lĩnh vực phát triển .NET, quản lý và nén tệp là một nhiệm vụ phổ biến. Aspose.Zip for .NET cung cấp một giải pháp mạnh mẽ để làm việc với các kho lưu trữ nén, cung cấp nhiều phương pháp nén khác nhau. Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng Aspose.Zip cho .NET để tạo các tệp Seven Zip với các phương pháp nén khác nhau.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo rằng bạn có những điều sau:

- Hiểu biết cơ bản về lập trình C#.
- Visual Studio được cài đặt trên máy của bạn.
-  Aspose.Zip cho thư viện .NET. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/zip/net/).

## Nhập không gian tên

Bắt đầu bằng cách nhập các Không gian tên cần thiết vào dự án C# của bạn. Sử dụng đoạn mã sau để bắt đầu:

```csharp
using Aspose.Zip.Saving;
using Aspose.Zip.SevenZip;
```

## Nén LZMA2

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

## Nén BZip2

```csharp
//BZip2
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipBZip2CompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_bzip2.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with BZip2 Compression");
```

## Lưu trữ, không nén

```csharp
//Lưu trữ, không nén
using (SevenZipArchive archive = new SevenZipArchive(new SevenZipEntrySettings(new SevenZipStoreCompressionSettings())))
{
    archive.CreateEntries(dataDir);
    archive.Save("SevenZip_store.7z");
}
Console.WriteLine("Successfully Created a Seven Zip File with No Compression (Store)");
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá tính linh hoạt của Aspose.Zip dành cho .NET trong việc tạo tệp Seven Zip bằng nhiều phương pháp nén khác nhau. Cho dù bạn cần tỷ lệ nén cao hay không muốn nén gì cả, Aspose.Zip cung cấp tính linh hoạt để đáp ứng yêu cầu của bạn.

## Câu hỏi thường gặp

### Tôi có thể sử dụng Aspose.Zip cho .NET với bất kỳ loại tệp nào không?
Có, Aspose.Zip for .NET hỗ trợ nhiều loại tệp, cho phép bạn nén và giải nén nhiều định dạng khác nhau.

### Aspose.Zip cho .NET có dùng thử miễn phí không?
 Có, bạn có thể dùng thử miễn phí[đây](https://releases.aspose.com/).

### Tôi có thể tìm tài liệu về Aspose.Zip cho .NET ở đâu?
 Tài liệu có sẵn[đây](https://reference.aspose.com/zip/net/).

### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Zip cho .NET?
 Giấy phép tạm thời có thể được lấy[đây](https://purchase.aspose.com/temporary-license/).

### Tôi có thể nhận hỗ trợ cho Aspose.Zip cho .NET ở đâu?
 Bạn có thể tìm kiếm sự hỗ trợ trên[Diễn đàn Aspose.Zip](https://forum.aspose.com/c/zip/37).
