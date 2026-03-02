---
date: 2026-03-02
description: Tìm hiểu cách tạo tệp zip được bảo vệ bằng mật khẩu và nén các tệp với
  mật khẩu trong .NET bằng Aspose.Zip. Hãy theo dõi hướng dẫn từng bước của chúng
  tôi.
linktitle: Compress Files with Individual Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Tạo một tệp ZIP được bảo vệ bằng mật khẩu trong .NET với Aspose.Zip
url: /vi/net/password-protection-and-encryption/compress-files-individual-passwords/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo một ZIP Archive được bảo vệ bằng mật khẩu trong .NET với Aspose.Zip

## Introduction

Khi bạn cần chia sẻ dữ liệu nhạy cảm, một **zip archive được bảo vệ bằng mật khẩu** là một trong những cách đơn giản nhất nhưng hiệu quả nhất để giữ thông tin an toàn. Trong các ứng dụng .NET, Aspose.Zip giúp dễ dàng **nén file có mật khẩu**, cung cấp cho mỗi file một khóa mã hoá riêng. Trong hướng dẫn này, bạn sẽ học cách tạo archive như vậy, tại sao nó quan trọng, và nơi bạn có thể áp dụng trong các dự án thực tế.

## Quick Answers
- **Thư viện nào tôi nên dùng?** Aspose.Zip cho .NET cung cấp hỗ trợ tích hợp cho mật khẩu theo từng file và nhiều phương pháp mã hoá.  
- **Bao nhiêu dòng code?** Khoảng 30 dòng, bao gồm thiết lập và lưu archive.  
- **Mỗi file có thể có mật khẩu khác nhau không?** Có – bạn có thể gán mật khẩu duy nhất cho mỗi mục.  
- **Các phương pháp mã hoá nào có sẵn?** ZipCrypto truyền thống, AES‑128 và AES‑256.  
- **Tôi có cần giấy phép cho môi trường production không?** Cần giấy phép thương mại cho việc sử dụng trong production; bản dùng thử miễn phí có sẵn.

## What is a password protected zip archive?
Một zip archive được bảo vệ bằng mật khẩu là một tệp nén (ZIP) yêu cầu mật khẩu để giải nén nội dung. Mật khẩu có thể bảo vệ toàn bộ archive hoặc các mục riêng lẻ, và các thuật toán hiện đại như AES‑128/256 cung cấp mã hoá mạnh.

## Why compress files with passwords using Aspose.Zip?
- **Bảo mật chi tiết** – gán mật khẩu riêng cho mỗi file, lý tưởng cho các kịch bản đa người dùng.  
- **Nhiều tiêu chuẩn mã hoá** – chọn giữa ZipCrypto cũ và AES mạnh.  
- **Không cần công cụ bên ngoài** – mọi thứ được xử lý bằng lập trình trong codebase .NET của bạn.  
- **Hiệu suất** – nén nhanh với Deflate đồng thời giữ kích thước archive nhỏ.

## Prerequisites

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- **Aspose.Zip for .NET** – cài đặt thư viện vào dự án của bạn. Tài liệu chi tiết có sẵn [here](https://reference.aspose.com/zip/net/).  
- **Download the latest package** nếu bạn chưa có, từ [this link](https://releases.aspose.com/zip/net/).  
- Một thư mục chứa các file bạn muốn nén.

## Import Namespaces

Thêm các namespace cần thiết ở đầu file C# của bạn:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using System.IO;
```

## Step 1: Set the Resource Directory Path

Chỉ định đường dẫn tới thư mục chứa các file nguồn:

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Compress Files with Individual Passwords

Bây giờ chúng ta sẽ tạo một **zip archive được bảo vệ bằng mật khẩu** trong đó mỗi file sử dụng mật khẩu và phương pháp mã hoá riêng. Ví dụ sử dụng ba file mẫu (`alice29.txt`, `asyoulik.txt`, và `fields.c`) với các mật khẩu khác nhau.

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesWithIndividualPasswords_out.zip", FileMode.Create))
{
    FileInfo source1 = new FileInfo(dataDir + "alice29.txt");
    FileInfo source2 = new FileInfo(dataDir + "asyoulik.txt");
    FileInfo source3 = new FileInfo(dataDir + "fields.c");

    using (var archive = new Archive())
    {
        // Compress each file with an individual password
        archive.CreateEntry("alice29.txt", source1, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new TraditionalEncryptionSettings("pass1")));
        archive.CreateEntry("asyoulik.txt", source2, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass2", EncryptionMethod.AES128)));
        archive.CreateEntry("fields.c", source3, true, new ArchiveEntrySettings(new DeflateCompressionSettings(), new AesEcryptionSettings("pass3", EncryptionMethod.AES256)));
        
        // Save the compressed files
        archive.Save(zipFile);
    }
}
```

### How it works
- **CreateEntry** thêm một file vào archive.  
- Tham số thứ tư (`ArchiveEntrySettings`) cho phép bạn chỉ định cả nén (`DeflateCompressionSettings`) và mã hoá (`TraditionalEncryptionSettings` hoặc `AesEcryptionSettings`).  
- Bằng cách truyền một chuỗi mật khẩu khác nhau cho mỗi mục, bạn sẽ có một **zip archive được bảo vệ bằng mật khẩu** nơi mỗi file chỉ có thể mở bằng khóa riêng của nó.

## Common Issues & Troubleshooting

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| Trích xuất thất bại với “Wrong password” | Mật khẩu không khớp hoặc phương pháp mã hoá sai | Xác minh chuỗi mật khẩu chính xác và đảm bảo bạn đã sử dụng cùng `EncryptionMethod` khi giải nén. |
| Kích thước archive lớn hơn mong đợi | Sử dụng AES‑256 trên các file văn bản nhỏ có thể tạo thêm overhead | Đối với file nhỏ, AES‑128 có thể đủ và tạo archive nhỏ hơn. |
| Ngoại lệ runtime khi `archive.Save` | Thiếu quyền ghi trên thư mục đích | Đảm bảo ứng dụng có quyền ghi vào `dataDir` hoặc sử dụng đường dẫn đầu ra khác. |

## Frequently Asked Questions (FAQs)

### Tôi có thể sử dụng các phương pháp mã hoá khác nhau cho mỗi file không?
Có, Aspose.Zip cho .NET cho phép bạn kết hợp các phương pháp mã hoá—ZipCrypto truyền thống, AES‑128 và AES‑256—trên từng file.

### Có phiên bản dùng thử không?
Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.Zip cho .NET [here](https://releases.aspose.com/).

### Làm sao tôi có thể nhận hỗ trợ nếu gặp vấn đề?
Truy cập [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) để được cộng đồng và bộ phận hỗ trợ của Aspose trợ giúp.

### Tôi có thể tìm tài liệu chi tiết cho Aspose.Zip cho .NET ở đâu?
Tài liệu có sẵn [here](https://reference.aspose.com/zip/net/).

### Tôi có thể mua giấy phép tạm thời để thử nghiệm không?
Có, bạn có thể mua giấy phép tạm thời [here](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2026-03-02  
**Đã kiểm tra với:** Aspose.Zip cho .NET (phiên bản mới nhất)  
**Tác giả:** Aspose