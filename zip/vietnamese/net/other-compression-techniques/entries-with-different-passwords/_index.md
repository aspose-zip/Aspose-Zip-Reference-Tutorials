---
date: 2025-12-18
description: Tìm hiểu cách mã hóa các tệp zip bằng các mật khẩu khác nhau bằng Aspose.Zip
  cho .NET. Hướng dẫn này chỉ cho bạn cách nén tệp với mật khẩu và tạo tệp lưu trữ
  7z trong C#.
linktitle: Entries with Different Passwords
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cách mã hóa tệp ZIP với các mật khẩu khác nhau trong Aspose.Zip cho .NET
url: /vi/net/other-compression-techniques/entries-with-different-passwords/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Mã Hoá Tệp ZIP với Mật Khẩu Khác Nhau trong Aspose.Zip cho .NET

## Giới thiệu

Nếu bạn cần **cách mã hoá zip** các tệp lưu trữ đồng thời cấp mỗi mục một mật khẩu riêng, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng ta sẽ đi qua các bước chi tiết để tạo một tệp 7‑zip trong đó mỗi tệp đều được bảo vệ bằng mật khẩu độc nhất, sử dụng thư viện Aspose.Zip cho .NET. Khi kết thúc, bạn sẽ hiểu tại sao việc mã hoá từng mục lại quan trọng, cách thiết lập, và cách xác minh kết quả trong dự án của mình.

## Trả lời nhanh
- **“encrypt zip” có nghĩa là gì?** Nó có nghĩa là áp dụng bảo vệ dựa trên mật khẩu (AES hoặc ZipCrypto) cho nội dung của một tệp ZIP/7z.  
- **Mỗi mục có thể có mật khẩu khác nhau không?** Có — Aspose.Zip cho phép bạn gán các mật khẩu riêng biệt cho từng tệp.  
- **Các phiên bản .NET nào được hỗ trợ?** Tất cả các phiên bản .NET Framework hiện đại, .NET Core và .NET 5/6.  
- **Có cần giấy phép cho môi trường sản xuất không?** Giấy phép thương mại là bắt buộc cho việc sử dụng trong sản xuất; bản dùng thử miễn phí có sẵn.  
- **Định dạng nén nào được sử dụng trong ví dụ?** Mẫu tạo một tệp 7z với mã hoá AES‑256.

## “how to encrypt zip” là gì với Aspose.Zip?

Mã hoá một tệp ZIP (hoặc 7z) có nghĩa là bảo vệ các mục của nó để không thể mở mà không có mật khẩu đúng. Aspose.Zip cho .NET hỗ trợ cả ZipCrypto cổ điển và mã hoá AES mạnh hơn, đồng thời cho phép bạn chỉ định cài đặt mã hoá cho từng mục, mang lại kiểm soát bảo mật chi tiết.

## Tại sao nên dùng mật khẩu khác nhau cho mỗi mục?

- **Phân đoạn bảo mật:** Nếu một mật khẩu bị rò rỉ, các tệp còn lại vẫn được bảo vệ.  
- **Tuân thủ quy định:** Một số ngành yêu cầu thông tin đăng nhập riêng cho các danh mục dữ liệu khác nhau.  
- **Quyền truy cập theo người dùng:** Bạn có thể phân phối một tệp lưu trữ duy nhất cho nhiều người dùng, mỗi người chỉ mở được các tệp mà họ được phép.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

- **Aspose.Zip cho .NET** đã được cài đặt – xem [tài liệu chính thức](https://reference.aspose.com/zip/net/) để tải và hướng dẫn cài đặt.  
- Một thư mục trên máy tính nơi bạn sẽ lưu các tệp nguồn (gọi là “Document Directory”).  
- Kiến thức cơ bản về C# và Visual Studio (hoặc IDE .NET ưa thích của bạn).

## Nhập không gian tên

Chúng ta bắt đầu bằng cách import các không gian tên chứa các lớp cần thiết.

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

## Bước 1: Đặt Thư Mục Tài Liệu

Xác định đường dẫn chứa các tệp bạn muốn nén.

```csharp
string dataDir = "Your Document Directory";
```

## Bước 2: Tạo Các Mục với Mật Khẩu Khác Nhau

Đây là phần cốt lõi của hướng dẫn. Chúng ta mở một tệp 7z mới, tạo ba đối tượng `FileInfo`, và thêm mỗi đối tượng vào như một mục với mật khẩu AES riêng.

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

### Cách Hoạt Động

- `SevenZipArchive` là container cho một tệp 7‑z.  
- `CreateEntry` nhận tên mục, tệp nguồn, cờ ghi đè, và một đối tượng `SevenZipEntrySettings`.  
- Trong `SevenZipEntrySettings` chúng ta cung cấp hai đối tượng cài đặt: một cho nén (`SevenZipStoreCompressionSettings`) và một cho mã hoá (`SevenZipAESEncryptionSettings`).  
- Mỗi lần gọi cung cấp **mật khẩu khác nhau** (`"test1"`, `"test2"`, `"test3"`), thực hiện bảo vệ từng mục riêng biệt.

## Bước 3: Kiểm Tra

Sau khi lưu tệp lưu trữ, bạn có thể in ra một thông báo xác nhận đơn giản.

```csharp
Console.WriteLine("Successfully Created a Seven Zip File with AES Encryption Settings");
```

Chạy chương trình, sau đó thử mở `archive.7z` bằng công cụ như 7‑Zip. Nó sẽ yêu cầu mật khẩu cho mỗi mục, xác nhận rằng các mật khẩu thực sự khác nhau.

## Các Vấn Đề Thường Gặp và Giải Pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|-----------|
| **Lỗi mật khẩu không đúng** | Chuỗi mật khẩu chứa khoảng trắng thừa hoặc ký tự ẩn. | Cắt bỏ khoảng trắng (`new SevenZipAESEncryptionSettings(password.Trim())`). |
| **Tệp không mở được trong các công cụ cũ** | Một số công cụ ZIP legacy không hỗ trợ mã hoá AES‑256 dùng trong 7z. | Dùng trình giải nén hiện đại (7‑Zip 19.00+). |
| **Tệp không được thêm vào lưu trữ** | Đường dẫn tệp nguồn sai hoặc tệp không tồn tại. | Kiểm tra `dataDir` và tên tệp, hoặc dùng `Path.Combine(dataDir, "data1.bin")`. |

## Câu Hỏi Thường Gặp

### Q1: Aspose.Zip cho .NET có tương thích với mọi phiên bản .NET không?

A1: Có, Aspose.Zip cho .NET được thiết kế để tích hợp liền mạch với mọi phiên bản của .NET framework.

### Q2: Tôi có thể sử dụng Aspose.Zip cho .NET trong các dự án thương mại không?

A2: Hoàn toàn có thể! Aspose.Zip cho .NET cung cấp giấy phép thương mại, và bạn có thể tìm thông tin mua tại [đây](https://purchase.aspose.com/buy).

### Q3: Có bản dùng thử miễn phí không?

A3: Có, bạn có thể khám phá các tính năng của Aspose.Zip cho .NET với bản dùng thử miễn phí. Bắt đầu [tại đây](https://releases.aspose.com/).

### Q4: Làm sao tôi có thể nhận hỗ trợ cho Aspose.Zip cho .NET?

A4: Đối với bất kỳ câu hỏi hay hỗ trợ nào, hãy truy cập [Diễn đàn Aspose.Zip](https://forum.aspose.com/c/zip/37).

### Q5: Tôi có thể sử dụng Aspose.Zip cho .NET mà không có giấy phép vĩnh viễn không?

A5: Có, bạn có thể lấy giấy phép tạm thời cho nhu cầu ngắn hạn. Xem chi tiết [tại đây](https://purchase.aspose.com/temporary-license/).

## Kết luận

Bạn vừa học **cách mã hoá zip** các tệp lưu trữ với mật khẩu riêng cho từng mục bằng Aspose.Zip cho .NET. Kỹ thuật này cho phép bạn bảo vệ từng tệp một cách độc lập, đáp ứng các yêu cầu bảo mật nghiêm ngặt và đơn giản hoá việc phân phối theo người dùng. Hãy thử nghiệm với các cài đặt nén khác, tập hợp tệp lớn hơn, hoặc tích hợp logic này vào dịch vụ web tạo lưu trữ an toàn ngay lập tức.

---

**Cập nhật lần cuối:** 2025-12-18  
**Đã kiểm tra với:** Aspose.Zip cho .NET 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}