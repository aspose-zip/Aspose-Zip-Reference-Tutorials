---
date: 2025-12-21
description: Tìm hiểu cách tạo các tệp zip được bảo vệ bằng mật khẩu trong .NET, mã
  hóa thư mục và thay đổi mật khẩu zip bằng Aspose.Zip.
linktitle: Password Protect Directory
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Tạo file zip có bảo vệ bằng mật khẩu cho các thư mục .NET – Hướng dẫn Aspose.Zip
url: /vi/net/password-protection-and-encryption/password-protect-directory/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo tệp zip được bảo vệ bằng mật khẩu cho các thư mục .NET – Hướng dẫn Aspose.Zip

Trong hướng dẫn này, bạn sẽ **tạo tệp zip được bảo vệ bằng mật khẩu** cho toàn bộ thư mục bằng thư viện Aspose.Zip cho .NET. Cho dù bạn cần **mã hoá một thư mục**, bảo vệ các tệp sao lưu, hoặc chỉ đơn giản là hạn chế quyền truy cập vào dữ liệu nhạy cảm, tutorial từng bước này sẽ chỉ cho bạn cách thực hiện bằng mã C# sạch sẽ.

## Câu trả lời nhanh
- **Thư viện nào được đề xuất?** Aspose.Zip for .NET  
- **Tôi có thể mã hoá toàn bộ thư mục không?** Có – chỉ cần chỉ API tới thư mục bạn muốn zip.  
- **Có hỗ trợ thay đổi mật khẩu zip không?** Hoàn toàn có, sử dụng `TraditionalEncryptionSettings`.  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Cần giấy phép Aspose.Zip hợp lệ cho việc sử dụng thương mại.  
- **Có hoạt động với .NET Core/5/6 không?** Có, API hoàn toàn tương thích với các runtime .NET hiện đại.  

## “Tạo zip được bảo vệ bằng mật khẩu” là gì?
Tạo một tệp zip được bảo vệ bằng mật khẩu có nghĩa là nén các tệp hoặc thư mục vào một tệp ZIP đồng thời áp dụng mã hoá để tệp chỉ có thể mở được bằng mật khẩu đúng. Điều này bảo vệ nội dung khỏi việc truy cập trái phép.

## Tại sao nên sử dụng Aspose.Zip để bảo vệ thư mục bằng mật khẩu trong .NET?
Aspose.Zip cung cấp một API đơn giản, hiệu suất cao hỗ trợ **c# zip password protection**, mã hoá truyền thống ZipCrypto và mã hoá AES. Nó xử lý các thư mục lớn một cách hiệu quả và tích hợp liền mạch với bất kỳ dự án .NET nào.

## Yêu cầu trước
- Kiến thức cơ bản về lập trình C#.  
- Visual Studio (bất kỳ phiên bản mới nào).  
- Thư viện Aspose.Zip cho .NET – tải xuống **[tại đây](https://releases.aspose.com/zip/net/)**.  
- Một thư mục trên đĩa mà bạn muốn bảo vệ bằng mật khẩu.

## Nhập các Namespace
Thêm các namespace cần thiết vào tệp C# của bạn để trình biên dịch biết nơi tìm các lớp Aspose.Zip.

```csharp
using Aspose.Zip;
using System.IO;
using Aspose.Zip.Saving;
```

## Bước 1: Đặt Đường dẫn tới Thư mục Nguồn
Xác định đường dẫn trỏ tới thư mục bạn muốn zip và bảo vệ.

```csharp
string dataDir = "Your Document Directory";
```

## Bước 2: Bảo vệ Thư mục bằng Mật khẩu
Sử dụng `TraditionalEncryptionSettings` để chỉ định mật khẩu và tạo tệp lưu trữ đã mã hoá. Đây là phần cốt lõi của **c# zip password protection**.

```csharp
//ExStart: PasswordProtectDirectory
using (FileStream zipFile = File.Open(dataDir + "all_corpus_encrypted_out.zip", FileMode.Create))
{
    DirectoryInfo corpus = new DirectoryInfo(".\\CanterburyCorpus");
    using (var archive = new Archive(new ArchiveEntrySettings(null, new TraditionalEncryptionSettings("p@s$"))))
    {
        archive.CreateEntries(corpus);
        archive.Save(zipFile);
        //ExEnd: PasswordProtectDirectory
    }
}
```

## Bước 3: Giải thích Mã
- **Tạo tệp đầu ra:** `File.Open(..., FileMode.Create)` mở (hoặc tạo) tệp ZIP sẽ chứa dữ liệu đã mã hoá.  
- **Chọn thư mục nguồn:** `new DirectoryInfo(".\\CanterburyCorpus")` cho Aspose.Zip biết thư mục nào sẽ được nén.  
- **Áp dụng mật khẩu:** `new TraditionalEncryptionSettings("p@s$")` đặt mật khẩu sẽ bảo vệ tệp lưu trữ.  
- **Thêm mục và lưu:** `archive.CreateEntries(corpus)` thêm mọi tệp trong thư mục, và `archive.Save(zipFile)` ghi tệp ZIP đã mã hoá ra đĩa.

## Làm thế nào để thay đổi mật khẩu zip sau này?
Nếu bạn cần **thay đổi mật khẩu zip**, chỉ cần tạo lại tệp lưu trữ với một đối tượng `TraditionalEncryptionSettings` mới chứa mật khẩu mới, sau đó lưu lại.

## Các vấn đề thường gặp & Mẹo
- **Thư mục lớn:** Aspose.Zip truyền dữ liệu theo luồng, vì vậy việc sử dụng bộ nhớ vẫn thấp ngay cả với các thư mục khổng lồ.  
- **Độ phức tạp của mật khẩu:** Sử dụng mật khẩu mạnh (kết hợp chữ cái, số, ký tự đặc biệt) để tăng cường bảo mật.  
- **Lỗi giấy phép:** Đảm bảo bạn đã áp dụng tệp giấy phép hợp lệ; nếu không, thư viện sẽ chạy ở chế độ đánh giá với các hạn chế.

## Câu hỏi thường gặp

### Aspose.Zip cho .NET có phù hợp với các thư mục lớn không?
Có, Aspose.Zip cho .NET được thiết kế để xử lý các thư mục lớn một cách hiệu quả, cung cấp hiệu năng tối ưu.

### Tôi có thể thay đổi mật khẩu cho một thư mục đã được bảo vệ không?
Có, bạn có thể thay đổi mật khẩu bằng cách điều chỉnh `TraditionalEncryptionSettings` trong mã cho phù hợp.

### Có yêu cầu giấy phép nào cho việc sử dụng Aspose.Zip cho .NET không?
Có, cần một giấy phép hợp lệ để sử dụng Aspose.Zip cho .NET trong môi trường sản xuất. Bạn có thể mua giấy phép **[tại đây](https://purchase.aspose.com/buy)**.

### Có bản dùng thử miễn phí cho Aspose.Zip cho .NET không?
Có, bạn có thể truy cập bản dùng thử miễn phí **[tại đây](https://releases.aspose.com/)**.

### Tôi có thể tìm hỗ trợ bổ sung cho Aspose.Zip cho .NET ở đâu?
Bạn có thể truy cập **[diễn đàn Aspose.Zip](https://forum.aspose.com/c/zip/37)** để nhận hỗ trợ hoặc đặt câu hỏi.

---

**Last Updated:** 2025-12-21  
**Được kiểm tra với:** Aspose.Zip for .NET (latest release)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}