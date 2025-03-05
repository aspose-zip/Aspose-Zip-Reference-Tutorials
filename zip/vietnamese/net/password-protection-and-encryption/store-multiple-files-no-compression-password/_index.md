---
title: Aspose.Zip for .NET - Hướng dẫn lưu trữ tệp an toàn
linktitle: Lưu trữ nhiều tệp mà không cần nén bằng mật khẩu
second_title: API Aspose.Zip .NET để nén và lưu trữ tệp
description: Khám phá cách sử dụng Aspose.Zip cho .NET để lưu trữ an toàn nhiều tệp mà không cần nén. Các bước dễ dàng để bảo vệ mật khẩu. Mở khóa sức mạnh của quản lý tập tin!
type: docs
weight: 13
url: /vi/net/password-protection-and-encryption/store-multiple-files-no-compression-password/
---

Trong thế giới phát triển .NET, việc quản lý và thao tác với các tệp là một nhiệm vụ phổ biến. Aspose.Zip for .NET là một thư viện mạnh mẽ cung cấp cho các nhà phát triển khả năng nén, giải nén và thao tác các kho lưu trữ zip một cách liền mạch. Trong hướng dẫn này, chúng ta sẽ đi sâu vào một tình huống cụ thể: lưu trữ nhiều tệp mà không cần nén và bảo vệ chúng bằng mật khẩu. Đến cuối hướng dẫn này, bạn sẽ được trang bị kiến thức để triển khai chức năng này bằng Aspose.Zip cho .NET.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

-  Aspose.Zip cho Thư viện .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Zip cho .NET. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/zip/net/).

-  Thư mục tài liệu: Chuẩn bị một thư mục chứa các tập tin nguồn của bạn. Trong ví dụ được cung cấp, biến`dataDir` đại diện cho thư mục tài liệu của bạn.

## Nhập không gian tên

Để bắt đầu, hãy nhập các không gian tên cần thiết cho mã của chúng ta:

```csharp
// Đường dẫn đến thư mục tài nguyên.
string dataDir = "Your Document Directory"

// Nhập không gian tên Aspose.Zip
using Aspose.Zip;
using Aspose.Zip.Settings.Compression;
using Aspose.Zip.Settings.Encryption;
```

## Bước 1: Mở tệp Zip

```csharp
//ExStart: StoreMutlipleFilesWithoutCompressionWithPassword
using (FileStream zipFile = File.Open(dataDir + "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip", FileMode.Create))
{
```

 Bước này liên quan đến việc tạo một tệp zip mới bằng cách sử dụng`FileStream`. Tệp sẽ có tên là "StoreMutlipleFilesWithoutCompressionWithPassword_out.zip."

## Bước 2: Mở tệp nguồn

```csharp
using (FileStream source1 = File.Open(dataDir + "alice29.txt", FileMode.Open, FileAccess.Read))
{
```

Ở đây, chúng tôi mở tệp nguồn đầu tiên, "alice29.txt", tệp này sẽ được lưu trữ trong kho lưu trữ zip.

## Bước 3: Tạo kho lưu trữ

```csharp
using (var archive = new Archive(new ArchiveEntrySettings(new StoreCompressionSettings(), new AesEcryptionSettings("p@s$", EncryptionMethod.AES256))))
{
```

 Trong bước này, chúng ta tạo một thể hiện của`Archive` lớp, chỉ định cài đặt nén và mã hóa. Chúng tôi sử dụng`StoreCompressionSettings` để lưu trữ tập tin mà không cần nén và`AesEcryptionSettings` để áp dụng mã hóa AES bằng mật khẩu ("p@s$").

## Bước 4: Tạo mục lưu trữ và lưu

```csharp
archive.CreateEntry("alice29.txt", source1);
archive.Save(zipFile);
```

Bước cuối cùng này bao gồm việc tạo một mục trong kho lưu trữ cho "alice29.txt" và lưu kho lưu trữ, hoàn tất quá trình lưu trữ tệp mà không cần nén và có bảo vệ bằng mật khẩu.

Kết thúc hướng dẫn của bạn bằng cách tóm tắt các điểm chính và khuyến khích người đọc khám phá các khả năng khác với Aspose.Zip dành cho .NET.

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách sử dụng Aspose.Zip cho .NET để lưu trữ nhiều tệp mà không cần nén và bảo mật chúng bằng mật khẩu. Khi bạn tiếp tục hành trình phát triển .NET, hãy tận dụng các khả năng của Aspose.Zip để hợp lý hóa các tác vụ quản lý tệp và nâng cao tính bảo mật cho ứng dụng của bạn.

---

### Câu hỏi thường gặp

### Tôi có thể sử dụng Aspose.Zip cho .NET bằng các phương thức mã hóa khác không?
 Có, Aspose.Zip hỗ trợ nhiều phương thức mã hóa khác nhau. Kiểm tra tài liệu[đây](https://reference.aspose.com/zip/net/) để biết chi tiết.

### Tôi có thể nhận hỗ trợ cho Aspose.Zip cho .NET ở đâu?
 Tham quan[Diễn đàn Aspose.Zip](https://forum.aspose.com/c/zip/37) để được cộng đồng hỗ trợ và thảo luận.

### Có bản dùng thử miễn phí dành cho Aspose.Zip cho .NET không?
 Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.aspose.com/).

### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Zip cho .NET?
 Yêu cầu giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).

### Tôi có thể mua Aspose.Zip cho .NET ở đâu?
 Bạn có thể mua Aspose.Zip cho .NET[đây](https://purchase.aspose.com/buy).
