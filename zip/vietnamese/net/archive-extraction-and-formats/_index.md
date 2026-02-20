---
date: 2026-02-20
description: Học cách nén các tệp tarbz2, tạo các kho lưu trữ targz và trích xuất
  .NET cùng việc giải nén zip có bảo vệ mật khẩu bằng Aspose.Zip cho .NET. Nâng cao
  hiệu quả lưu trữ và bảo mật.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cách nén tệp TarBz2 bằng Aspose.Zip cho .NET
url: /vi/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Nén Tập Tin TarBz2 bằng Aspose.Zip cho .NET

## Giới thiệu

Trong hướng dẫn này, bạn sẽ học **cách nén các tệp tarbz2** bằng Aspose.Zip cho .NET đồng thời khám phá cách tạo các kho lưu trữ TarGz và thực hiện việc giải nén các tệp zip được bảo vệ bằng mật khẩu trong .net. Xử lý tệp hiệu quả là nền tảng của phát triển .NET hiện đại, và việc thành thạo các định dạng này giúp bạn giảm chi phí lưu trữ, tăng tốc truyền dữ liệu và bảo vệ thông tin nhạy cảm. Dù bạn đang xây dựng dịch vụ sao lưu, ứng dụng khách lưu trữ đám mây, hay quy trình xử lý dữ liệu, các kỹ thuật ở đây sẽ làm cho công việc quản lý tệp của bạn trở nên mượt mà và đáng tin cậy hơn.

## Câu trả lời nhanh
- **TarBz2 là gì?** Một kho lưu trữ nén kết hợp việc đóng gói TAR với nén BZIP2 để đạt tỷ lệ nén cao.  
- **Tại sao chọn Aspose.Zip cho .NET?** Nó cung cấp một API duy nhất, mượt mà để tạo và giải nén nhiều định dạng kho lưu trữ mà không cần phụ thuộc bên ngoài.  
- **Tôi có thể tạo một kho lưu trữ TarGz không?** Có – Aspose.Zip hỗ trợ TarGz, TarLz, TarXz, TarZ và nhiều định dạng khác.  
- **Làm sao để giải nén một tệp zip được bảo vệ bằng mật khẩu?** Sử dụng thuộc tính `Password` trên đối tượng `ArchiveEntry` khi giải nén.  
- **Tôi có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Cần giấy phép thương mại cho môi trường sản xuất; bản dùng thử miễn phí có sẵn để đánh giá.

## Cách Nén Tập Tin TarBz2
Nén tệp thành TarBz2 có nghĩa là đầu tiên gộp nhiều tệp và thư mục vào một container **TAR** duy nhất, sau đó áp dụng nén **BZIP2**. Kết quả là một tệp `.tar.bz2` duy nhất, vừa dễ vận chuyển vừa nén mạnh.

## Tại sao nên sử dụng Aspose.Zip cho .NET để xử lý các định dạng này?
- **API thống nhất** – Một thư viện, nhiều định dạng (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **Không phụ thuộc vào thư viện gốc** – Hoạt động trên Windows, Linux và macOS ngay lập tức.  
- **Hỗ trợ mật khẩu** – Bảo vệ và giải nén các kho lưu trữ một cách an toàn với mật khẩu riêng cho mỗi mục.  
- **Tập trung vào hiệu năng** – Xử lý dựa trên luồng giảm thiểu lượng bộ nhớ sử dụng.

## Yêu cầu trước
- .NET 6.0 hoặc mới hơn (hoặc .NET Core 3.1+ / .NET Framework 4.5+).  
- Gói NuGet Aspose.Zip cho .NET đã được cài đặt (`Install-Package Aspose.Zip`).  
- Kiến thức cơ bản về C# và I/O tệp.

## Hướng Dẫn Từng Bước

### Bước 1: Chọn định dạng lưu trữ bạn cần
Quyết định xem **TarBz2**, **TarGz**, **TarLz**, **TarXz**, hay **TarZ** nào phù hợp nhất với tỷ lệ nén và yêu cầu tương thích của bạn.  
- **TarBz2** – Nén tốt nhất, tốc độ xử lý chậm hơn.  
- **TarGz** – Cân bằng tốt giữa tốc độ và kích thước (bao gồm từ khóa phụ *how to create targz*).  
- **TarZ** – Định dạng cũ, hữu ích cho khả năng tương thích với các công cụ Unix cũ.

### Bước 2: Tạo một thể hiện `Archive` mới
Khởi tạo lớp `Archive` và chỉ định đường dẫn tệp đầu ra. Đối tượng này sẽ quản lý quá trình đóng gói và nén.

### Bước 3: Thêm tệp và thư mục
Sử dụng các phương thức `AddAll` hoặc `AddFile` để bao gồm các tệp bạn muốn nén. Bạn có thể giữ cấu trúc thư mục bằng cách thêm một thư mục gốc.

### Bước 4: Đặt loại nén mong muốn
Chỉ định thuật toán nén (`CompressionType.BZip2`, `CompressionType.GZip`, v.v.) khi lưu kho lưu trữ. Đây là nơi bạn thực sự **nén các tệp thành TarBz2** hoặc bất kỳ định dạng nào khác.

### Bước 5: Lưu tập tin nén
Gọi `Save` với enum định dạng phù hợp (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz`, v.v.). Thư viện sẽ ghi container TAR và áp dụng nén đã chọn trong một lần xử lý.

### Bước 6: Giải nén các tập tin nén có mật khẩu
Nếu bạn cần **giải nén các mục trong kho lưu trữ với mật khẩu khác nhau** (từ khóa phụ *password protected zip extraction*), mở kho lưu trữ, xác định từng mục, gán mật khẩu và sau đó giải nén.

### Bước 7: Xác minh kết quả
Sau khi giải nén, so sánh kích thước tệp và checksum để đảm bảo kho lưu trữ đã được tạo và giải nén đúng cách.

## Các trường hợp sử dụng phổ biến
- **Tiện ích sao lưu** – Lưu các bản sao lưu hàng ngày dưới dạng `.tar.bz2` để giảm chi phí lưu trữ.  
- **Trao đổi dữ liệu đa nền tảng** – Các định dạng dựa trên Tar được hiểu rộng rãi trên Linux, macOS và Windows.  
- **Phân phối an toàn** – Bảo vệ các mục riêng lẻ bằng mật khẩu cho các môi trường yêu cầu tuân thủ.

## Khắc phục sự cố & Mẹo
- **Các tập tin nén lớn** – Sử dụng API streaming (`Archive.CreateEntryFromFile`) để tránh tải toàn bộ tệp vào bộ nhớ.  
- **Mật khẩu không khớp** – Đảm bảo mật khẩu được đặt cho mỗi `ArchiveEntry` khớp với mật khẩu dùng khi giải nén; nếu không sẽ gặp `InvalidPasswordException`.  
- **Mức nén không được hỗ trợ** – BZIP2 không hỗ trợ mức nén tùy chỉnh; nếu cần kiểm soát chi tiết hơn, hãy xem xét TarLz hoặc TarXz.

## Câu hỏi thường gặp

**Q: Làm sao để tạo một kho lưu trữ TarGz?**  
A: Đặt loại nén thành `CompressionType.GZip` và định dạng thành `ArchiveFormat.TarGz` khi gọi `Save`.

**Q: Tôi có thể giải nén một kho lưu trữ được bảo vệ bằng mật khẩu mà không biết mật khẩu không?**  
A: Không. Mỗi mục phải được cung cấp mật khẩu đúng; nếu không việc giải nén sẽ thất bại.

**Q: Aspose.Zip có hỗ trợ giải nén các kho lưu trữ với mật khẩu khác nhau cho mỗi mục không?**  
A: Có. Bạn có thể gán mật khẩu cho từng `ArchiveEntry` riêng lẻ trước khi giải nén.

**Q: Định dạng nào cho tỷ lệ nén tốt nhất?**  
A: TarBz2 thường cung cấp tỷ lệ nén cao nhất, tiếp theo là TarLz và TarXz. TarGz mang lại cân bằng tốt giữa tốc độ và kích thước.

**Q: Có giới hạn số lượng tệp tôi có thể thêm vào một kho lưu trữ TAR không?**  
A: Thực tế không, nhưng các kho lưu trữ cực lớn có thể hưởng lợi từ việc chia thành nhiều phần để dễ quản lý hơn.

## Hướng Dẫn Giải Nén và Định Dạng

### [Nén Tập Tin thành TarBz2 với Aspose.Zip cho .NET](./compress-to-tar-bz2/)
Tìm hiểu cách nén tệp thành định dạng TarBz2 trong .NET bằng Aspose.Zip. Thực hiện theo hướng dẫn từng bước để nén tệp hiệu quả.

### [Nén thành TarGz với Aspose.Zip cho .NET](./compress-to-tar-gz/)
Khám phá nén tệp hiệu quả trong .NET với Aspose.Zip. Nén thành TarGz một cách dễ dàng.

### [Nén thành TarLz với Aspose.Zip cho .NET](./compress-to-tar-lz/)
Nén tệp trong .NET với Aspose.Zip một cách nhanh chóng. Học cách tạo các kho lưu trữ TarLz từng bước.

### [Nén thành TarXz với Aspose.Zip cho .NET](./compress-to-tar-xz/)
Học cách nén tệp thành định dạng TarXz trong .NET bằng Aspose.Zip. Thực hiện theo hướng dẫn từng bước để lưu trữ và truyền tải dữ liệu hiệu quả.

### [Nén thành TarZ với Aspose.Zip cho .NET](./compress-to-tar-z/)
Khám phá quy trình nén thành TarZ bằng Aspose.Zip cho .NET. Xử lý tệp hiệu quả cho các dự án .NET của bạn.

### [Giải nén các mục trong kho lưu trữ với mật khẩu khác nhau trong Aspose.Zip cho .NET](./extract-archive-different-passwords/)
Tìm hiểu cách giải nén các mục trong kho lưu trữ với mật khẩu khác nhau trong Aspose.Zip cho .NET. Tăng cường bảo mật và tính linh hoạt cho ứng dụng của bạn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose