---
date: 2025-12-05
description: Tìm hiểu cách tạo tệp zip và thêm các tệp vào zip bằng Aspose.Zip cho
  .NET. Hướng dẫn từng bước này chỉ cách nén tệp bằng FileInfo trong các dự án ASP.NET.
linktitle: Compress Files using FileInfo
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cách tạo tệp Zip bằng Aspose.Zip cho .NET – Nén tệp với FileInfo
url: /vi/net/file-compression/compress-files-fileinfo/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Tạo Tập Tin Zip Sử Dụng Aspose.Zip cho .NET

## Giới thiệu

Nếu bạn cần **tạo một tập tin zip** một cách lập trình, Aspose.Zip cho .NET cung cấp cho bạn một API sạch sẽ, hiệu năng cao và hoạt động trong bất kỳ ứng dụng .NET nào (bao gồm cả ASP.NET). Trong hướng dẫn này, chúng ta sẽ đi qua việc nén các tệp bằng lớp `FileInfo`, chỉ cho bạn cách **thêm tệp vào zip**, và giải thích tại sao cách tiếp cận này là lý tưởng cho các dự án .NET hiện đại. Hãy bắt đầu nào!

## Câu trả lời nhanh
- **Cách dễ nhất để tạo một tập tin zip là gì?** Sử dụng lớp `Archive` của Aspose.Zip kết hợp với các đối tượng `FileInfo`.  
- **Tôi có thể thêm nhiều tệp cùng lúc không?** Có – chỉ cần tạo một `FileInfo` cho mỗi tệp và gọi `CreateEntry`.  
- **Tôi có cần giấy phép đặc biệt cho ASP.NET không?** Cần một giấy phép thương mại Aspose.Zip cho môi trường sản xuất; bản dùng thử miễn phí đủ cho việc đánh giá.  
- **Những phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **API có an toàn với đa luồng không?** Có, miễn là mỗi luồng làm việc với một thể hiện `Archive` riêng.

## Tập tin Zip là gì và tại sao lại tạo?
Một tập tin zip gói một hoặc nhiều tệp lại trong một container nén duy nhất. Điều này giảm không gian lưu trữ, tăng tốc truyền tải qua mạng và đơn giản hoá việc phân phối. Dù bạn đang gửi log, xuất báo cáo, hay đóng gói tài nguyên cho khách hàng, việc biết **cách tạo tập tin zip** một cách lập trình là kỹ năng quý giá cho bất kỳ nhà phát triển .NET nào.

## Tại sao nên dùng Aspose.Zip để Thêm Tệp vào Zip?
- **Không phụ thuộc bên ngoài** – triển khai thuần .NET.  
- **Kiểm soát đầy đủ mức nén và mã hoá** (ASCII, UTF‑8, v.v.).  
- **Hỗ trợ tệp lớn** (> 4 GB) và bảo vệ bằng mật khẩu.  
- **API nhất quán trên .NET Framework, .NET Core và .NET 5+**.

## Yêu cầu trước

Trước khi chúng ta bắt đầu viết mã, hãy chắc chắn rằng bạn đã có:

1. **Aspose.Zip cho .NET** đã được cài đặt. Tải gói mới nhất từ [trang tải Aspose.Zip](https://releases.aspose.com/zip/net/).  
2. Một thư mục trên máy chứa các tệp bạn muốn nén (ví dụ: `alice29.txt` và `fields.c`).  

## Nhập không gian tên

Trong bất kỳ tệp C# nào mà bạn sẽ làm việc với zip, thêm các câu lệnh `using` sau:

```csharp
using Aspose.Zip;
using Aspose.Zip.Saving;
using Aspose.ZIP;
using System.IO;
using System.Text;
```

Các không gian tên này cung cấp cho bạn quyền truy cập vào lớp `Archive`, các tùy chọn lưu, và các tiện ích I/O chuẩn.

## Hướng dẫn từng bước

### Bước 1: Thiết lập Thư mục Tài liệu

Đầu tiên, xác định thư mục chứa các tệp nguồn. Thay thế placeholder bằng đường dẫn tuyệt đối hoặc tương đối trên hệ thống của bạn:

```csharp
string dataDir = "Your Document Directory";
```

> **Mẹo chuyên nghiệp:** Sử dụng `Path.Combine` để xây dựng đường dẫn một cách đa nền tảng.

### Bước 2: Mở Tập tin Zip để Ghi

Tạo một `FileStream` trỏ tới tập tin zip đầu ra. Luồng được mở ở chế độ **Create**, sẽ ghi đè bất kỳ tệp nào cùng tên đã tồn tại:

```csharp
using (FileStream zipFile = File.Open(dataDir + "CompressFilesByFileInfo_out.zip", FileMode.Create))
{
```

### Bước 3: Chuẩn bị Đối tượng `FileInfo` cho Mỗi Tệp Nguồn

`FileInfo` cho phép Aspose.Zip truy cập trực tiếp tới các tệp vật lý trên đĩa. Tạo một thể hiện cho mỗi tệp bạn muốn nén:

```csharp
FileInfo fi1 = new FileInfo(dataDir + "alice29.txt");
FileInfo fi2 = new FileInfo(dataDir + "fields.c");
```

> **Tại sao lại dùng `FileInfo`?** Nó tránh việc tải toàn bộ tệp vào bộ nhớ, rất hữu ích khi làm việc với tệp lớn.

### Bước 4: Tạo Archive và Thêm Các Entry

Khởi tạo một đối tượng `Archive`, sau đó gọi `CreateEntry` cho mỗi `FileInfo`. Tham số đầu tiên là tên tệp sẽ xuất hiện bên trong zip, tham số thứ hai là `FileInfo` nguồn:

```csharp
using (var archive = new Archive())
{
    archive.CreateEntry("alice29.txt", fi1);
    archive.CreateEntry("fields.c", fi2);
```

### Bước 5: Lưu Archive Zip với Mã hoá Mong Muốn

Cuối cùng, ghi archive vào `FileStream` mà bạn đã mở ở bước trước. Ở đây chúng ta dùng mã hoá ASCII cho tên entry, nhưng bạn có thể chuyển sang UTF‑8 nếu tên tệp chứa ký tự không phải ASCII:

```csharp
    archive.Save(zipFile, new ArchiveSaveOptions() { Encoding = Encoding.ASCII });
}
```

Khi các khối `using` kết thúc, các luồng sẽ tự động đóng và tập tin zip đã sẵn sàng để sử dụng.

## Các vấn đề thường gặp & Giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **Tập tin zip rỗng** | `FileInfo` trỏ tới đường dẫn không tồn tại | Kiểm tra `dataDir` và tên tệp; dùng `File.Exists` để xác nhận trước khi tạo entry. |
| **Mã hoá tên tệp không đúng** | Dùng mã hoá mặc định với tên không phải ASCII | Đặt `Encoding = Encoding.UTF8` trong `ArchiveSaveOptions`. |
| **OutOfMemoryException khi nén tệp lớn** | Đọc toàn bộ tệp vào bộ nhớ | `FileInfo` sẽ stream tệp; đảm bảo bạn không đọc tệp vào mảng byte ở nơi khác. |
| **Permission denied** | Ứng dụng không có quyền ghi vào thư mục đầu ra | Chạy ứng dụng với quyền thích hợp hoặc chọn thư mục có thể ghi được. |

## Câu hỏi thường gặp

**Hỏi: Tôi có thể thêm bảo vệ bằng mật khẩu cho tập tin zip không?**  
Đáp: Có. Sau khi tạo `Archive`, đặt `archive.Password = "yourPassword"` trước khi gọi `Save`.

**Hỏi: Có thể cập nhật một tập tin zip đã tồn tại không?**  
Đáp: Aspose.Zip hỗ trợ mở một archive hiện có bằng `Archive.Open` và sau đó thêm các entry mới.

**Hỏi: Làm sao để nén tệp trong một controller ASP.NET MVC?**  
Đáp: Cùng một đoạn mã hoạt động; chỉ cần đảm bảo luồng đầu ra được trả về dưới dạng `FileResult` cho client.

**Hỏi: Aspose.Zip có hỗ trợ các thuật toán mã hoá không?**  
Đáp: Nó hỗ trợ chuẩn ZipCrypto và AES‑256.

**Hỏi: Nếu tôi cần nén một thư mục một cách đệ quy thì sao?**  
Đáp: Duyệt qua `Directory.GetFiles` (và các thư mục con) và tạo `FileInfo` cho mỗi tệp, sau đó thêm chúng vào archive.

## Phần FAQ hiện có (giữ nguyên)

### FAQ's

#### Q1: Aspose.Zip có tương thích với mọi loại tệp không?

A1: Aspose.Zip hỗ trợ một loạt các loại tệp, đảm bảo tính đa dụng trong việc nén.

#### Q2: Tôi có thể sử dụng Aspose.Zip cho các dự án thương mại không?

A2: Chắc chắn! Ghé thăm [trang mua hàng](https://purchase.aspose.com/buy) để khám phá các tùy chọn giấy phép.

#### Q3: Làm sao tôi có thể nhận hỗ trợ cho Aspose.Zip?

A3: Tham gia cộng đồng của chúng tôi trên [diễn đàn Aspose.Zip](https://forum.aspose.com/c/zip/37) để được trợ giúp và thảo luận.

#### Q4: Có bản dùng thử miễn phí không?

A4: Có, bạn có thể lấy [bản dùng thử miễn phí tại đây](https://releases.aspose.com/).

#### Q5: Làm sao tôi có thể nhận giấy phép tạm thời cho Aspose.Zip?

A5: Truy cập [liên kết này](https://purchase.aspose.com/temporary-license/) để biết thông tin về việc nhận giấy phép tạm thời.

## Kết luận

Bây giờ bạn đã biết **cách tạo tập tin zip** bằng Aspose.Zip cho .NET, **cách thêm tệp vào zip**, và tại sao phương pháp này lại lý tưởng cho ASP.NET và các ứng dụng .NET khác. Hãy thử nghiệm với các mức nén, mã hoá và tùy chọn bảo mật khác nhau để tùy chỉnh archive theo nhu cầu chính xác của bạn. Chúc bạn nén thành công!

---

**Cập nhật lần cuối:** 2025-12-05  
**Đã kiểm tra với:** Aspose.Zip cho .NET 24.12 (phiên bản mới nhất)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}