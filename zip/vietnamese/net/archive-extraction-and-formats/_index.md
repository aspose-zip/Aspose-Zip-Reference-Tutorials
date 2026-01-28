---
date: 2026-01-28
description: Tìm hiểu cách giải nén tệp có mật khẩu, nén file thành TarBz2, tạo các
  tệp TarGz bằng Aspose.Zip cho .NET. Tăng cường hiệu quả lưu trữ và bảo mật.
linktitle: Archive Extraction and Formats
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Giải nén tệp có mật khẩu và nén thành TarBz2 (.NET)
url: /vi/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Trích xuất Archive có Mật khẩu và Nén thành TarBz2 (.NET)

Trong hướng dẫn này, bạn sẽ khám phá **cách trích xuất archive có mật khẩu** và cũng nắm vững **cách nén file thành TarBz2** bằng Aspose.Zip cho .NET. Dù bạn đang xây dựng dịch vụ sao lưu, client lưu trữ đám mây, hay pipeline xử lý dữ liệu, những kỹ thuật này giúp giảm dung lượng lưu trữ, tăng tốc truyền tải và bảo vệ dữ liệu nhạy cảm.

## Câu trả lời nhanh
- **TarBz2 là gì?** Một archive nén kết hợp gói TAR với nén BZIP2 để đạt tỷ lệ nén cao.  
- **Tại sao chọn Aspose.Zip cho .NET?** Nó cung cấp một API duy nhất, mượt mà cho nhiều định dạng archive mà không cần phụ thuộc gốc.  
- **Tôi có thể tạo archive TarGz không?** Có – Aspose.Zip hỗ trợ TarGz, TarLz, TarXz, TarZ và nhiều hơn nữa.  
- **Làm thế nào để trích xuất archive được bảo vệ bằng mật khẩu?** Đặt thuộc tính `Password` trên mỗi `ArchiveEntry` trước khi trích xuất.  
- **Tôi có cần giấy phép cho việc sử dụng trong môi trường production không?** Cần giấy phép thương mại cho production; bản dùng thử miễn phí có sẵn để đánh giá.

## Cách trích xuất archive có mật khẩu bằng Aspose.Zip cho .NET
Việc trích xuất một archive **được bảo vệ bằng mật khẩu** là rất đơn giản. Bạn mở archive, tìm entry cần thiết, gán mật khẩu cho nó, và sau đó gọi `Extract`. Cách tiếp cận này hoạt động cho TarBz2, TarGz và các định dạng được hỗ trợ khác.

## “Nén file thành TarBz2” thực sự có nghĩa là gì?
Nén file thành TarBz2 có nghĩa là đầu tiên gộp nhiều file và thư mục vào một container **TAR** duy nhất, sau đó áp dụng nén **BZIP2**. Kết quả là một file `.tar.bz2` vừa dễ truyền tải vừa được nén mạnh.

## Tại sao sử dụng Aspose.Zip cho .NET để xử lý các định dạng này?
- **Unified API** – Một thư viện, nhiều định dạng (TarBz2, TarGz, TarLz, TarXz, TarZ).  
- **No native dependencies** – Hoạt động trên Windows, Linux và macOS ngay lập tức.  
- **Password support** – Bảo vệ và trích xuất archive một cách an toàn với mật khẩu riêng cho mỗi entry.  
- **Performance‑focused** – Xử lý dựa trên stream giảm thiểu việc sử dụng bộ nhớ.

## Yêu cầu trước
- .NET 6.0 hoặc mới hơn (hoặc .NET Core 3.1+ / .NET Framework 4.5+).  
- Gói NuGet Aspose.Zip cho .NET đã được cài đặt (`Install-Package Aspose.Zip`).  
- Kiến thức cơ bản về C# và I/O file.

## Hướng dẫn từng bước

### Bước 1: Chọn định dạng archive bạn cần
Quyết định **TarBz2**, **TarGz**, **TarLz**, **TarXz**, hay **TarZ** nào phù hợp nhất với tỷ lệ nén và yêu cầu tương thích của bạn.  
- **TarBz2** – Nén tốt nhất, xử lý chậm hơn.  
- **TarGz** – Cân bằng tốt giữa tốc độ và kích thước (bao gồm từ khóa phụ *compress files to targz*).  
- **TarZ** – Định dạng legacy cho các công cụ Unix cũ.

### Bước 2: Tạo một đối tượng `Archive` mới
Tạo một thể hiện của lớp `Archive` và chỉ đến đường dẫn file đầu ra. Đối tượng này sẽ quản lý quá trình đóng gói và nén.

### Bước 3: Thêm file và thư mục
Sử dụng các phương thức `AddAll` hoặc `AddFile` để bao gồm các file bạn muốn nén. Giữ nguyên cấu trúc thư mục bằng cách thêm một thư mục gốc.

### Bước 4: Đặt loại nén mong muốn
Chỉ định thuật toán nén (`CompressionType.BZip2`, `CompressionType.GZip`, v.v.) khi lưu archive. Đây là nơi bạn thực sự **nén file thành tarbz2** hoặc bất kỳ định dạng nào khác.

### Bước 5: Lưu archive
Gọi `Save` với enum định dạng phù hợp (`ArchiveFormat.TarBz2`, `ArchiveFormat.TarGz`, v.v.). Thư viện sẽ ghi container TAR và áp dụng nén đã chọn trong một lần.

### Bước 6: Trích xuất archive có mật khẩu
Nếu bạn cần **trích xuất các entry trong archive với mật khẩu khác nhau** (từ khóa phụ *how to extract password protected archive*), mở archive, tìm từng entry, gán mật khẩu cho nó, và sau đó trích xuất.

### Bước 7: Xác minh kết quả
Sau khi trích xuất, so sánh kích thước file và checksum để đảm bảo archive đã được tạo và giải nén đúng.

## Các trường hợp sử dụng phổ biến
- **Backup utilities** – Lưu các bản sao lưu hàng ngày dưới dạng `.tar.bz2` để giảm chi phí lưu trữ.  
- **Cross‑platform data exchange** – Các định dạng dựa trên Tar được hiểu rộng rãi trên Linux, macOS và Windows.  
- **Secure distribution** – Bảo vệ từng entry bằng mật khẩu cho môi trường yêu cầu tuân thủ.

## Khắc phục sự cố & Mẹo
- **Large archives** – Sử dụng API streaming (`Archive.CreateEntryFromFile`) để tránh tải toàn bộ file vào bộ nhớ.  
- **Password mismatches** – Đảm bảo mật khẩu được đặt trên mỗi `ArchiveEntry` khớp với mật khẩu dùng khi trích xuất; nếu không sẽ gặp `InvalidPasswordException`.  
- **Unsupported compression level** – BZIP2 không hỗ trợ mức nén tùy chỉnh; nếu cần kiểm soát chi tiết hơn, hãy cân nhắc TarLz hoặc TarXz.  
- **Performance tip** – Khi tạo **create tarbz2 archive**, bật buffering trên stream nền để cải thiện tốc độ ghi.

## Câu hỏi thường gặp

**H: Làm thế nào để tạo archive TarGz?**  
Đặt loại nén thành `CompressionType.GZip` và định dạng thành `ArchiveFormat.TarGz` khi gọi `Save`.

**H: Tôi có thể trích xuất archive được bảo vệ bằng mật khẩu mà không biết mật khẩu không?**  
Không. Mỗi entry phải được cung cấp mật khẩu đúng; nếu không việc trích xuất sẽ thất bại.

**H: Aspose.Zip có hỗ trợ trích xuất archive với mật khẩu khác nhau cho mỗi entry không?**  
Có. Bạn có thể gán mật khẩu cho từng `ArchiveEntry` riêng biệt trước khi trích xuất.

**H: Định dạng nào cho mức nén tốt nhất?**  
TarBz2 thường cung cấp tỷ lệ nén cao nhất, tiếp theo là TarLz và TarXz. TarGz mang lại cân bằng tốt giữa tốc độ và kích thước.

**H: Có giới hạn số lượng file tôi có thể thêm vào archive TAR không?**  
Thực tế không, nhưng các archive cực lớn có thể hưởng lợi từ việc chia thành nhiều phần để dễ quản lý hơn.

## Hướng dẫn Trích xuất Archive và Định dạng Tutorials
### [Nén File thành TarBz2 với Aspose.Zip cho .NET](./compress-to-tar-bz2/)
Học cách nén file thành định dạng TarBz2 trong .NET bằng Aspose.Zip. Thực hiện theo hướng dẫn từng bước của chúng tôi để nén file hiệu quả.

### [Nén thành TarGz với Aspose.Zip cho .NET](./compress-to-tar-gz/)
Tìm hiểu nén file hiệu quả trong .NET với Aspose.Zip. Nén thành TarGz một cách dễ dàng.

### [Nén thành TarLz với Aspose.Zip cho .NET](./compress-to-tar-lz/)
Nén file trong .NET một cách dễ dàng với Aspose.Zip. Học cách tạo archive TarLz từng bước.

### [Nén thành TarXz với Aspose.Zip cho .NET](./compress-to-tar-xz/)
Học cách nén file thành định dạng TarXz trong .NET bằng Aspose.Zip. Thực hiện theo hướng dẫn từng bước để lưu trữ và truyền tải file hiệu quả.

### [Nén thành TarZ với Aspose.Zip cho .NET](./compress-to-tar-z/)
Tìm hiểu quy trình nén từng bước thành TarZ bằng Aspose.Zip cho .NET. Xử lý file hiệu quả cho dự án .NET của bạn.

### [Trích xuất các Entry trong Archive với Mật khẩu Khác nhau trong Aspose.Zip cho .NET](./extract-archive-different-passwords/)
Học cách trích xuất các entry trong archive với mật khẩu khác nhau trong Aspose.Zip cho .NET. Tăng cường bảo mật và tính linh hoạt cho ứng dụng của bạn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2026-01-28  
**Kiểm tra với:** Aspose.Zip for .NET 24.11  
**Tác giả:** Aspose  

---