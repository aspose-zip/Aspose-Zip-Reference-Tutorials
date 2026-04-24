---
date: 2026-04-24
description: Học cách nén tar và tạo một kho lưu trữ TarBz2 trong .NET với Aspose.Zip.
  Hướng dẫn chi tiết này chỉ ra cách thêm tệp vào tar và tạo các tệp tarbz2 một cách
  hiệu quả.
keywords:
- how to compress tar
- add files to tar
- asp zip
- create tarbz2 archive
- tar archive .net
linktitle: Nén sang TarBz2
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cách nén tar và tạo TarBz2 bằng Aspose.Zip cho .NET
url: /vi/net/archive-extraction-and-formats/compress-to-tar-bz2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách nén tar và tạo TarBz2 với Aspose.Zip cho .NET

## Giới thiệu

Trong hướng dẫn này, bạn sẽ khám phá **cách nén tar** các tệp lưu trữ và chuyển chúng thành một tệp **TarBz2** gọn nhẹ bằng thư viện **Aspose.Zip** cho .NET. Dù bạn đang xây dựng công cụ sao lưu, xuất bản các gói triển khai, hay chỉ cần một gói nhẹ để phân phối, các bước dưới đây sẽ hướng dẫn bạn cách thêm tệp vào tar, áp dụng nén Bzip2 và tạo ra một lưu trữ sẵn sàng chia sẻ.

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có các điều kiện tiên quyết được liệt kê ở phần sau của hướng dẫn này để có thể theo dõi mà không gặp rắc rối.

## Câu trả lời nhanh
- **Thư viện nào tôi nên dùng?** Aspose.Zip for .NET  
- **Thời gian triển khai mất bao lâu?** Khoảng 5‑10 phút  
- **Tôi có cần giấy phép không?** Cần một giấy phép tạm thời cho môi trường sản xuất; bản dùng thử miễn phí có sẵn  
- **Tôi có thể nén nhiều tệp không?** Có – thêm bao nhiêu mục tùy thích vào lưu trữ tar  
- **Có tương thích với .NET 6+ không?** Chắc chắn, Aspose.Zip hỗ trợ .NET Framework và .NET Core/5/6  

## TarBz2 là gì?

Một tệp **TarBz2** kết hợp container **tar** truyền thống (giữ cấu trúc thư mục và siêu dữ liệu tệp) với nén **Bzip2**, tạo ra một gói `.tar.bz2` nén mạnh. Định dạng này phổ biến trên các hệ thống kiểu Unix vì nó cung cấp sự cân bằng tốt giữa tỷ lệ nén và tốc độ giải nén.

## Tại sao nén tệp thành TarBz2 với Aspose.Zip?

- **Tốc độ & Đơn giản** – Các cuộc gọi API một dòng xử lý cả việc tạo tar và nén Bzip2.  
- **Đa nền tảng** – Hoạt động trên các runtime .NET của Windows, Linux và macOS.  
- **Kiểm soát chi tiết** – Chọn các tệp cần bao gồm, đặt tên mục tùy chỉnh và truyền trực tiếp tới đĩa.  
- **Hỗ trợ .NET mạnh mẽ** – Hoàn hảo cho các kịch bản **tar archive .net**, từ ứng dụng console đến dịch vụ web.  

## Yêu cầu trước

- **Aspose.Zip for .NET** – Tải gói mới nhất từ trang chính thức: [https://releases.aspose.com/zip/net/](https://releases.aspose.com/zip/net/)  
- **Document Directory** – Thư mục chứa các tệp bạn muốn lưu trữ. Trong các ví dụ chúng tôi tham chiếu nó bằng biến `dataDir`.

> **Mẹo chuyên nghiệp:** Giữ các tệp nguồn của bạn trong một thư mục riêng để tránh việc vô tình bao gồm các tệp không mong muốn.

## Nhập không gian tên

Đầu tiên, nhập các không gian tên cần thiết để bạn có thể truy cập các lớp Tar và Bzip2 của Aspose.Zip.

```csharp
using System;
using System.ComponentModel;
using Aspose.Zip.Bzip2;
using Aspose.Zip.Tar;
```

## Bước 1: Đặt thư mục tài liệu

Xác định đường dẫn trỏ tới thư mục chứa các tệp bạn muốn lưu trữ.

```csharp
string dataDir = "Your Document Directory";
```

> Thay thế `"Your Document Directory"` bằng đường dẫn tuyệt đối hoặc tương đối tới thư mục nguồn của bạn.

## Bước 2: Thêm tệp vào tar và tạo lưu trữ TarBz2

Cốt lõi của quá trình là tạo một `TarArchive`, thêm các mục, sau đó bao bọc nó bằng một `Bzip2Archive`. Đoạn mã dưới đây minh họa **cách tạo tar** và nén nó thành **TarBz2** theo kiểu mẫu disposable sạch sẽ.

```csharp
//ExStart: CompressFile
using (Bzip2Archive bz2 = new Bzip2Archive())
{
    using (TarArchive archive = new TarArchive())
    {
        archive.CreateEntry("alice29.txt", dataDir + "alice29.txt");
        archive.CreateEntry("lcet10.txt", dataDir + "lcet10.txt");

        bz2.SetSource(archive);
        bz2.Save(dataDir + "archive.tar.bz2");
    }
}
```

- `CreateEntry` **thêm tệp vào tar** – bạn có thể gọi phương thức này cho mỗi tệp cần trong lưu trữ.  
- `bz2.SetSource(archive)` chỉ cho lưu trữ Bzip2 nén toàn bộ luồng tar.  
- `bz2.Save(...)` ghi tệp **TarBz2** cuối cùng ra đĩa.

**Mẹo:** Để **thêm tệp vào tar** hàng loạt, chỉ cần lặp lại `archive.CreateEntry` cho mỗi tệp trước khi gọi `bz2.Save`.

## Vấn đề thường gặp & Giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|----------|
| **File not found** error | Đường dẫn `dataDir` sai hoặc thiếu phần mở rộng tệp | Xác minh đường dẫn đầy đủ và đảm bảo tệp tồn tại. |
| **Empty archive** | Không có mục nào được thêm trước `bz2.Save` | Thêm ít nhất một lời gọi `CreateEntry`. |
| **Permission denied** | Ứng dụng không có quyền ghi vào thư mục đầu ra | Chạy ứng dụng với quyền thích hợp hoặc chọn thư mục có thể ghi. |

## Câu hỏi thường gặp

**Q: Aspose.Zip có tương thích với mọi ứng dụng .NET không?**  
A: Có. Nó hoạt động với .NET Framework, .NET Core, .NET 5/6 và các runtime mới hơn.

**Q: Tôi có thể nén nhiều tệp cùng lúc không?**  
A: Chắc chắn. Gọi `CreateEntry` cho mỗi tệp trước khi lưu lưu trữ.

**Q: Tôi có thể tìm tài liệu bổ sung ở đâu?**  
A: Tài liệu chi tiết có sẵn [tại đây](https://reference.aspose.com/zip/net/).

**Q: Làm sao để lấy giấy phép tạm thời cho Aspose.Zip?**  
A: Bạn có thể yêu cầu một giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

**Q: Có phiên bản dùng thử miễn phí không?**  
A: Có, tải phiên bản dùng thử [tại đây](https://releases.aspose.com/).

## Kết luận

Bạn đã học được **cách nén tar**, thêm tệp vào đó, và bao gói kết quả trong một luồng Bzip2 để tạo ra một lưu trữ **TarBz2** bằng Aspose.Zip cho .NET. Cách tiếp cận này nhanh, đáng tin cậy và hoạt động trên mọi nền tảng .NET hiện đại. Hãy thoải mái thử nghiệm với các bộ tệp lớn hơn, tên mục tùy chỉnh, hoặc tích hợp mã vào quy trình sao lưu hoặc triển khai của bạn.

Nếu bạn gặp bất kỳ khó khăn nào, cộng đồng Aspose.Zip sẵn sàng hỗ trợ—chỉ cần truy cập [diễn đàn hỗ trợ Aspose.Zip](https://forum.aspose.com/c/zip/37).

---

**Cập nhật lần cuối:** 2026-04-24  
**Kiểm tra với:** Aspose.Zip for .NET (latest release)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}