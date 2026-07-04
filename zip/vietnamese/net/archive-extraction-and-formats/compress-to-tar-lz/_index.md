---
date: 2026-07-04
description: Tìm hiểu cách nén nhiều tệp tar bằng Aspose.Zip for .NET và tạo các tệp
  tar.lz một cách hiệu quả.
keywords:
- compress multiple files tar
- create tar.lz archive
- compress files to tar.lz
linktitle: Nén sang TarLz
schemas:
- author: Aspose
  dateModified: '2026-07-04'
  description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  headline: How to compress multiple files tar with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress multiple files tar using Aspose.Zip for .NET
    and create tar.lz archives efficiently.
  name: How to compress multiple files tar with Aspose.Zip for .NET
  steps:
  - name: Compress a single file
    text: The first example shows the most basic scenario – adding one file to a TAR
      archive and then saving it as a **tar.lz** file. The `TarArchive` class represents
      a TAR container that can hold multiple files in a single archive. **Explanation**
      - `new TarArchive()` creates an empty TAR container. - `Crea
  - name: Compress multiple files in one archive
    text: Often you’ll need to bundle several files together. Just call `CreateEntry`
      for each file before saving. This demonstrates **add files to tar lz** and effectively
      **compress multiple files tar**. **Explanation** - The code follows the same
      pattern as Step 1, but adds a second entry (`lcet10.txt`). -
  - name: Specify your document directory
    text: Replace the placeholder with the actual path where your source files live.
      This path is used by the examples above. **Explanation** - Set `dataDir` to
      a fully‑qualified folder path, e.g., `@"C:\MyFiles\"`. - Keeping the directory
      in a variable makes the code reusable and easier to maintain.
  type: HowTo
- questions:
  - answer: Aspose.Zip for .NET.
    question: What library should I use?
  - answer: About 5‑10 minutes for a basic example.
    question: How long does the implementation take?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes – just add more entries before saving.
    question: Can I compress multiple files at once?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cách nén nhiều tệp tar bằng Aspose.Zip for .NET
url: /vi/net/archive-extraction-and-formats/compress-to-tar-lz/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách nén nhiều tệp tar bằng Aspose.Zip cho .NET

Trong phát triển .NET hiện đại, việc đóng gói tệp một cách hiệu quả có thể cải thiện đáng kể kích thước triển khai và thời gian truyền tải qua mạng. **Compress multiple files tar** là một yêu cầu thường gặp khi bạn cần một archive TAR nhẹ, nén bằng LZ cho sao lưu, phân phối hoặc tải lên đám mây. Trong hướng dẫn này, chúng tôi sẽ trình bày một **ví dụ nén tar.lz** rõ ràng, từng bước sử dụng thư viện Aspose.Zip, để bạn có thể nhanh chóng tạo một **tar.lz archive** trong các ứng dụng của mình.

## Câu trả lời nhanh
- **Thư viện nào nên sử dụng?** Aspose.Zip cho .NET.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 5‑10 phút cho một ví dụ cơ bản.  
- **Có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Có thể nén nhiều tệp cùng lúc không?** Có – chỉ cần thêm nhiều mục trước khi lưu.

## Làm thế nào để nén nhiều tệp tar bằng Aspose.Zip cho .NET?
Tải các tệp nguồn của bạn, tạo một thể hiện `TarArchive`, thêm mỗi tệp bằng `CreateEntry`, và hoàn thành bằng cách gọi `SaveLzipped`. Thư viện sẽ xử lý cấu trúc TAR và nén LZ nội bộ, vì vậy bạn sẽ có một tệp `*.tar.lz` duy nhất chỉ trong vài dòng mã. Cách tiếp cận này hoạt động trên Windows, Linux và macOS mà không cần bất kỳ phụ thuộc gốc nào.

## Nén tar.lz là gì?
`tar.lz` là một archive TAR đã được nén bằng thuật toán LZMA (thường được gọi đơn giản là **LZ**). Nó kết hợp sự đơn giản của việc nhóm tệp của TAR với tỷ lệ nén cao của LZ, làm cho nó lý tưởng cho các tệp sao lưu, phân phối gói, hoặc bất kỳ tình huống nào mà băng thông quan trọng.

## Tại sao nên sử dụng Aspose.Zip cho .NET?
Aspose.Zip cung cấp một giải pháp thuần .NET, đa nền tảng, tạo các archive TAR, ZIP và dựa trên LZ mà không cần công cụ bên ngoài, hỗ trợ hơn 30 định dạng archive, và mang lại mức nén tốt hơn tới 30 % trên các tệp lớn, đồng thời cung cấp các ngoại lệ chi tiết để xử lý lỗi mạnh mẽ. Nó cũng tích hợp liền mạch với các framework ghi log của .NET và cung cấp các sự kiện tiến độ chi tiết.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- **Thư viện Aspose.Zip cho .NET** – tải xuống từ [here](https://releases.aspose.com/zip/net/).  
- Một thư mục chứa các tệp bạn muốn lưu trữ. Đường dẫn tới thư mục này sẽ được lưu trong biến `dataDir` (bạn sẽ thiết lập nó ở Bước 3).

## Nhập các Namespace
Thêm các namespace cần thiết để trình biên dịch biết nơi tìm các lớp chúng ta sẽ sử dụng.

```csharp
using System;
using Aspose.Zip.Tar;
```

## Cách tạo tar.lz archive – Hướng dẫn từng bước

### Bước 1: Nén một tệp duy nhất
Ví dụ đầu tiên cho thấy kịch bản cơ bản nhất – thêm một tệp vào archive TAR và sau đó lưu nó dưới dạng tệp **tar.lz**.

Lớp `TarArchive` đại diện cho một container TAR có thể chứa nhiều tệp trong một archive duy nhất.  

**Giải thích**

- `new TarArchive()` tạo một container TAR trống.  
- `CreateEntry` thêm tệp `alice29.txt` từ `dataDir` của bạn.  
- `SaveLzipped` ghi archive ra đĩa và áp dụng nén LZ, tạo ra `archive.tar.lz`.

```csharp
//ExStart: CompressSingleFile
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Bước 2: Nén nhiều tệp trong một archive
Thường bạn sẽ cần gộp một vài tệp lại với nhau. Chỉ cần gọi `CreateEntry` cho mỗi tệp trước khi lưu. Điều này minh họa **add files to tar lz** và thực tế **compress multiple files tar**.

**Giải thích**

- Mã nguồn tuân theo cùng mẫu như Bước 1, nhưng thêm mục thứ hai (`lcet10.txt`).  
- Bạn có thể lặp lại `CreateEntry` bao nhiêu lần cần thiết; thư viện sẽ tự động quản lý cấu trúc TAR nội bộ.

```csharp
//ExStart: CompressMultipleFiles
using (TarArchive archive = new TarArchive())
{
    archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
    archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");
    archive.SaveLzipped(dataDir + "archive.tar.lz");
}
```

### Bước 3: Xác định thư mục tài liệu của bạn
Thay thế placeholder bằng đường dẫn thực tế nơi các tệp nguồn của bạn nằm. Đường dẫn này được các ví dụ ở trên sử dụng.

**Giải thích**

- Đặt `dataDir` thành đường dẫn thư mục đầy đủ, ví dụ `@"C:\MyFiles\"`.  
- Giữ thư mục trong một biến giúp mã có thể tái sử dụng và dễ bảo trì hơn.

```csharp
string dataDir = "Your Document Directory";
```

## Những lỗi thường gặp & khắc phục
| Triệu chứng | Nguyên nhân có thể | Cách khắc phục |
|------------|--------------------|----------------|
| `FileNotFoundException` khi chạy mẫu | `dataDir` trỏ tới thư mục không tồn tại hoặc tên tệp bị sai | Kiểm tra lại đường dẫn và tên tệp; sử dụng `Path.Combine` để an toàn. |
| Tệp đầu ra có kích thước **0 KB** | `archive.SaveLzipped` được gọi trước khi có bất kỳ mục nào được thêm | Đảm bảo có ít nhất một lời gọi `CreateEntry` trước `SaveLzipped`. |
| Quá trình nén có vẻ chậm | Các tệp lớn với kích thước bộ đệm mặc định | Xem xét xử lý tệp theo khối hoặc sử dụng I/O bất đồng bộ nếu hiệu năng quan trọng. |

## Kết luận
Bạn giờ đã biết **cách nén tar.lz** bằng Aspose.Zip cho .NET, dù đang xử lý một tài liệu đơn lẻ hay một bộ sưu tập tệp. **Ví dụ nén tar.lz** này minh họa một cách sạch sẽ, sẵn sàng cho sản xuất để **tạo tar lz archive** mà có thể dễ dàng chuyển giao hoặc lưu trữ. Bạn có thể nén tệp thành tar.lz bằng cùng một API bằng cách gọi `SaveLzipped` sau khi đã thêm tất cả các mục mong muốn.

## Câu hỏi thường gặp

**Q:** Tôi có thể nén tệp có kích thước bất kỳ bằng Aspose.Zip cho .NET không?  
**A:** Có, thư viện xử lý cả tệp nhỏ và rất lớn; chỉ cần đảm bảo bạn có đủ bộ nhớ và không gian đĩa cho cấu trúc TAR tạm thời.

**Q:** Mã có tương thích với phiên bản Aspose.Zip mới nhất không?  
**A:** Mẫu này nhắm vào phiên bản hiện tại; luôn cập nhật gói NuGet để có các bản sửa lỗi và tính năng mới.

**Q:** Có các lưu ý về giấy phép không?  
**A:** Một giấy phép thương mại là bắt buộc cho việc sử dụng trong môi trường sản xuất. Xem chi tiết giấy phép trên [Aspose website](https://purchase.aspose.com/buy).

**Q:** Tôi có thể sử dụng điều này trong dự án thương mại không?  
**A:** Chắc chắn – một khi bạn có giấy phép hợp lệ, bạn có thể nhúng thư viện vào bất kỳ ứng dụng thương mại nào.

**Q:** Tôi có thể nhận hỗ trợ ở đâu nếu gặp vấn đề?  
**A:** Truy cập [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) để được cộng đồng và hỗ trợ chính thức giúp đỡ.

**Cập nhật lần cuối:** 2026-07-04  
**Đã kiểm tra với:** Aspose.Zip cho .NET (phiên bản mới nhất)  
**Tác giả:** Aspose  

---

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Tạo tar archive và thêm tệp vào tar bằng Aspose.Zip cho .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Cách nén tar và tạo TarBz2 bằng Aspose.Zip cho .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Thêm tệp vào tar và tạo tarxz archive bằng Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}