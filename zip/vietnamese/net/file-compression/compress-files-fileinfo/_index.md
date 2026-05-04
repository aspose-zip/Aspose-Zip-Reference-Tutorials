---
date: 2026-02-28
description: Tìm hiểu cách thêm thư mục vào zip và thêm tệp vào zip bằng Aspose.Zip
  cho .NET. Hướng dẫn từng bước này cho thấy cách nén tệp bằng FileInfo trong các
  dự án ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cách Thêm Thư Mục Vào File Zip Sử Dụng Aspose.Zip cho .NET – Nén Tập Tin Bằng
  FileInfo
url: /vi/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Thư Mục Vào Zip Sử Dụng Aspose.Zip cho .NET

## Giới thiệu

Nếu bạn cần **tạo một tệp zip** một trình cài đặt, Aspose.Zip cho .NET cung cấp một API sạch, hiệu suất cao và hoạt động trong bất kỳ ứng dụng nào .NET (bao gồm cả ASP.NET). Trong hướng dẫn này, chúng tôi sẽ thực hiện việc nén các tệp bằng lớp `FileInfo`, chỉ cho bạn cách **tệp tệp vào zip**, và giải thích tại sao cách tiếp cận này là lý tưởng cho các dự án .NET hiện đại. Chúng tôi cũng sẽ đề xuất cách **thư mục vào zip** để bạn có thể gói toàn bộ chỉ mục thư mục trong một bước. Hãy bắt đầu nào!

## Trả lời nhanh
- **Cách dễ nhất để tạo một tệp zip là gì?** Sử dụng lớp `Archive` của Aspose.Zip kết hợp với các đối tượng `FileInfo`.
- **Tôi có thể thêm nhiều tệp cùng lúc không?** Có – chỉ cần tạo một `FileInfo` cho mỗi tệp và gọi `CreatEntry`.
- **Tôi có cần giấy phép đặc biệt cho ASP.NET không?** Cần một giấy phép thương mại Aspose.Zip cho môi trường production; bản thử miễn phí đủ để đánh giá giá trị.
- ** Phiên bản .NET nào được hỗ trợ?** .NET Framework4.5+, .NETCore3.1+, .NET5/6/7.
- **API có toàn bộ luồng không?** Có, miễn phí là mỗi luồng hoạt động với một `Archive` riêng có thể thực hiện.

## Kho lưu trữ Zip là gì và tại sao lại tạo một kho lưu trữ này?
Một gói tệp zip một hoặc nhiều tệp được gửi lại trong một thùng chứa nén duy nhất. Điều này giảm không lưu trữ, tăng tốc độ truyền tải qua mạng và đơn giản hóa công việc phân phối. Dù bạn đang gửi nhật ký, xuất báo cáo, đóng gói tài nguyên cho khách hàng, biết **cách tạo tệp zip** một cách lập trình là kỹ năng quý giá cho bất kỳ nhà phát triển .NET nào.

## Tại sao nên sử dụng Aspose.Zip để thêm tệp vào Zip?
- **Không phụ thuộc bên ngoài** – phát triển khai tĩnh .NET.
- **Kiểm soát đầy đủ khả năng nén và mã hóa** (ASCII, UTF‑8, v.v.).
- **Hỗ trợ tệp lớn** (>4GB) và bảo vệ bằng mật khẩu.
- **API nhất quán trên .NET Framework, .NET Core và .NET 5+**.

## Điều kiện tiên quyết

Trước khi họ bắt đầu viết mã, hãy chắc chắn rằng bạn đã có:

1. **Aspose.Zip cho .NET** đã được cài đặt. Tải gói mới nhất từ ​​[trang tải Aspose.Zip](https://releases.aspose.com/zip/net/).
2. Một thư mục trên máy chứa các tệp bạn muốn nén (ví dụ: `alice29.txt` và `fields.c`).

## Nhập không gian tên

Trong bất kỳ tệp C# nào bạn sẽ làm việc với zip, hãy thêm các lệnh `using` sau:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Không gian tên này cho phép bạn truy cập lớp `Archive`, các tùy chọn lưu trữ và tiêu chuẩn I/O tiện ích.

## Hướng dẫn từng bước

### Bước 1: Thiết lập thư mục tài liệu của bạn

Đầu tiên, thư mục xác định chứa các nguồn tệp. Thay thế trình giữ chỗ bằng đường dẫn tuyệt đối hoặc tương đối trên hệ thống của bạn:

```csharp
string dataDir = "Your Document Directory";
```

> **Pro tip:** Sử dụng `Path.Combine` để xây dựng đường dẫn một cách đa nền tảng.

### Bước 2: Mở tệp Zip để ghi

Tạo một `FileStream` trỏ tới tệp zip đầu ra. Stream được mở ở chế độ **Create**, sẽ ghi đè bất kỳ tệp nào cùng tên đã tồn tại:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Bước 3: Chuẩn bị các đối tượng `FileInfo` cho mỗi tệp nguồn

`FileInfo` cho phép Aspose.Zip truy cập trực tiếp vào các tệp vật lý trên đĩa. Tạo một thể hiện cho mỗi tệp bạn muốn nén:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Why use `FileInfo`?** Nó tránh việc tải toàn bộ tệp vào bộ nhớ, rất hữu ích khi làm việc với các tệp lớn.

### Bước 4: Tạo tệp lưu trữ và thêm các mục

Khởi tạo một đối tượng `Archive`, sau đó gọi `CreateEntry` cho mỗi `FileInfo`. Tham số đầu tiên là tên tệp sẽ xuất hiện trong zip, tham số thứ hai là `FileInfo` nguồn:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Bước 5: Lưu tệp lưu trữ Zip với mã hóa mong muốn

Cuối cùng, lưu archive vào `FileStream` đã mở trước đó. Ở đây chúng ta dùng mã hoá ASCII cho tên entry, nhưng bạn có thể chuyển sang UTF‑8 nếu tên tệp chứa ký tự không phải ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Khi các khối `using` kết thúc, các stream sẽ tự động được đóng và tệp zip đã sẵn sàng để sử dụng.

## Cách thêm thư mục vào Zip bằng Aspose.Zip

Nếu bạn cần **thư mục vào zip** thay vì các lẻ tệp riêng biệt, quy trình rất đơn giản:

1. **Liệt kê thư mục** bằng `DirectoryInfo.GetFiles` (và tùy chọn `GetDirectories` để phản hồi).
2. **Tạo một `FileInfo`** cho mỗi tệp được phát hiện.
3. **Gọi `CreateEntry`** với đường dẫn tương thích bao gồm thư mục tên, ví dụ: `"MyFolder/Report.pdf"`.

Vì API hoạt động với `FileInfo` nên hiện tại bạn không phải tải toàn bộ tệp vào bộ nhớ nên an toàn cho các thư mục lớn. Kỹ thuật này cũng phù hợp với các bản viết kịch bản **zip nhiều tệp asp.net** khi bạn tạo một bộ báo cáo và cần gửi chúng dưới dạng một kho lưu trữ duy nhất.

## Các vấn đề thường gặp & Giải pháp

| Vấn đề | Nguyên nhân | Sửa chữa |
|-------|-------|------|
| **Tệp zip trống** | `FileInfo` trỏ tới đường dẫn không tồn tại | Kiểm tra tra `dataDir` và tệp tên; sử dụng `File.Exists` để xác định trước khi tạo mục nhập. |
| **Mã hóa tên tệp không chính xác** | Use default mã hóa với tên không phải ASCII | Đặt `Encoding = Encoding.UTF8` trong `ArchiveSaveOptions`. |
| **OutOfMemoryException trên các tệp lớn** | Tải toàn bộ tệp vào bộ nhớ | `FileInfo` sẽ truyền phát tệp; đảm bảo bạn không đọc được tệp văn bản ở một nơi khác. |
| **Quyền bị từ chối** | Ứng dụng không có quyền ghi vào đầu thư mục | Chạy ứng dụng với quyền thích hợp hoặc chọn thư mục có thể được ghi. |

### Câu hỏi thường gặp

#### Q1: Aspose.Zip có tương thích với tất cả các loại tệp không?

A1: Aspose.Zip hỗ trợ nhiều loại tệp, đảm bảo tính linh hoạt trong nén.

#### Q2: Tôi có thể sử dụng Aspose.Zip cho các dự án thương mại không?

A2: Chắc chắn rồi! Hãy truy cập trang [mua hàng](https://purchase.aspose.com/buy) của chúng tôi để tìm hiểu các tùy chọn cấp phép.

#### Q3: Làm thế nào để nhận được hỗ trợ cho Aspose.Zip?

A3: Tham gia cộng đồng của chúng tôi trên diễn đàn [Aspose.Zip](https://forum.aspose.com/c/zip/37) để được hỗ trợ và thảo luận.

#### Q4: Có bản dùng thử miễn phí không?

A4: Có, bạn có thể tải bản dùng thử miễn phí tại đây [https://releases.aspose.com/].

#### Q5: Làm thế nào để có được giấy phép tạm thời cho Aspose.Zip?

A5: Truy cập [liên kết này](https://purchase.aspose.com/temporary-license/) để biết thông tin về cách lấy giấy phép tạm thời.

## Kết luận

Bây giờ bạn đã biết **cách thêm thư mục vào zip** và **cách tạo zip archive** bằng Aspose.Zip cho .NET, cách **thêm tệp vào zip**, và tại sao phương pháp này lại lý tưởng cho ASP.NET và các ứng dụng .NET khác. Hãy thử nghiệm với các mức nén, mã hoá và tùy chọn bảo mật khác nhau để tùy chỉnh archive phù hợp nhất với nhu cầu của bạn. Chúc bạn nén thành công!

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Zip for .NET 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}