---
date: 2026-10-25
description: Tìm hiểu cách trích xuất mật khẩu zip và thiết lập thuật toán nén khi
  nén tệp tar bằng Aspose.Zip cho .NET, nâng cao hiệu quả lưu trữ và bảo mật.
keywords:
- extract zip password
- set compression algorithm
- add folder archive
- tarbz2 vs targz
- aspose zip compress
lastmod: 2026-10-25
linktitle: Trích xuất Lưu trữ và Định dạng
og_description: Tìm hiểu cách trích xuất mật khẩu zip và thiết lập thuật toán nén
  khi nén tệp tar bằng Aspose.Zip cho .NET, nâng cao hiệu quả lưu trữ và bảo mật.
og_image_alt: 'Developer guide: extract zip password and compress tar archives using
  Aspose.Zip for .NET'
og_title: Trích xuất mật khẩu zip và nén tệp tar bằng Aspose.Zip
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  headline: Extract zip password and compress tar files with Aspose.Zip
  type: TechArticle
- description: Learn how to extract zip password and set compression algorithm when
    compressing tar files with Aspose.Zip for .NET, boosting storage efficiency and
    security.
  name: Extract zip password and compress tar files with Aspose.Zip
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
      - **TarGz** – Good balance of speed and size; ideal for most cloud‑storage scenarios.
      - **TarLz / TarXz** – Very high compression with moderate'
  - name: Create a new `Archive` instance
    text: '`Archive` is the top‑level object that represents a single archive file
      in memory. The `Archive` class manages the packing and compression workflow,
      exposing methods to add entries and write the final file.'
  - name: Add files and folders
    text: You can add an entire directory tree with `AddAll` or add individual files
      with `AddFile`. Preserving the original folder hierarchy is as simple as passing
      the base directory path.
  - name: Set the desired compression type
    text: '`CompressionType` enumerates the supported algorithms. `CompressionType`
      defines the algorithm (BZip2, GZip, LZMA, XZ, etc.) that will be applied to
      the TAR stream during saving.'
  - name: Save the archive
    text: '`ArchiveFormat` is an enum set (e.g., `TarBz2`, `TarGz`) that tells the
      writer which container and compression to use. Calling `Save` writes the archive
      to disk using the selected format.'
  - name: Extracting archives with passwords
    text: '`ArchiveEntry` represents a single file or directory entry inside an archive.
      To extract a password‑protected zip, open the archive, locate each `ArchiveEntry`,
      assign its `Password` property, and call `Extract`. This per‑entry password
      model lets you protect individual files inside a single zip.'
  - name: Verify the result
    text: After extraction, compare file sizes and SHA‑256 checksums to confirm that
      the archive round‑trip preserved data integrity.
  type: HowTo
- questions:
  - answer: Set `CompressionType.GZip` and use `ArchiveFormat.TarGz` when calling
      `Save`. This produces a `.tar.gz` file in a single step.
    question: How do I create a TarGz archive?
  - answer: No. Each entry must be supplied with the correct password; extraction
      fails with an `InvalidPasswordException` otherwise.
    question: Can I extract a password‑protected archive without knowing the password?
  - answer: Yes. Assign a password to each `ArchiveEntry` individually before calling
      `Extract`.
    question: Does Aspose.Zip support extracting archives with different passwords
      per entry?
  - answer: TarBz2 typically yields the smallest size, followed by TarLz and TarXz.
      TarGz offers a faster, still‑effective alternative.
    question: Which format gives the best compression?
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
tags:
- compress tar
- Aspose.Zip
- .NET archive handling
title: Trích xuất mật khẩu zip và nén tệp tar bằng Aspose.Zip
url: /vi/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Trích xuất mật khẩu zip và nén tệp tar với Aspose.Zip

## Giới thiệu

Trong hướng dẫn này, bạn sẽ khám phá các kỹ thuật **extract zip password**, học cách đặt thuật toán nén khi tạo các kho lưu trữ dựa trên tar, và xem cách xây dựng TarGz, TarBz2 và các định dạng khác với Aspose.Zip cho .NET. Dù bạn đang xây dựng dịch vụ sao lưu, khách hàng lưu trữ đám mây, hoặc quy trình xử lý dữ liệu, việc thành thạo các thao tác này sẽ giảm chi phí lưu trữ, tăng tốc truyền tải và bảo mật các tệp nhạy cảm.

## Câu trả lời nhanh
- **TarBz2 là gì?** Một kho lưu trữ nén kết hợp gói TAR với nén BZIP2 để đạt tỷ lệ nén cao.  
- **Tại sao chọn Aspose.Zip cho .NET?** Nó hỗ trợ hơn 50 định dạng lưu trữ và nén, chạy trên Windows, Linux và macOS, và giữ mức sử dụng bộ nhớ dưới 10 MB cho các kho lưu trữ hàng trăm megabyte.  
- **Tôi có thể tạo kho lưu trữ TarGz không?** Có – Aspose.Zip cung cấp TarGz, TarLz, TarXz, TarZ và nhiều hơn nữa.  
- **Làm thế nào để trích xuất kho lưu trữ zip có bảo vệ bằng mật khẩu?** Đặt thuộc tính `Password` trên mỗi `ArchiveEntry` trước khi gọi `Extract`.  
- **Tôi có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Cần giấy phép thương mại cho môi trường sản xuất; bản dùng thử miễn phí có sẵn để đánh giá.

## Tar compression là gì?

Tar compression kết hợp container TAR với một thuật toán nén như BZIP2, GZIP, LZMA hoặc XZ. Kết quả là một tệp duy nhất (ví dụ, `.tar.gz`, `.tar.bz2`) có thể được giải nén trên Linux, macOS và Windows. Nó giữ nguyên cấu trúc thư mục gốc, cho phép trích xuất ngẫu nhiên, và được hỗ trợ rộng rãi bởi các công cụ dòng lệnh và thư viện lập trình, làm cho nó trở nên lý tưởng cho việc phân phối đa nền tảng và lưu trữ lưu trữ.

## Tại sao sử dụng Aspose.Zip cho .NET để xử lý các định dạng này?

Aspose.Zip cung cấp một API thống nhất, không phụ thuộc, hỗ trợ **50+** định dạng lưu trữ và nén, bao gồm tất cả các loại tar‑based chính. Kiến trúc streaming của nó xử lý các kho lưu trữ lớn hơn 10 GB trong khi giữ mức sử dụng RAM dưới 10 MB, làm cho nó lý tưởng cho các tải công việc máy chủ có thông lượng cao.  

**Câu trả lời trực tiếp:** Bạn sử dụng Aspose.Zip vì nó cho phép bạn tạo, nén và trích xuất các kho lưu trữ dựa trên tar và các tệp zip có bảo vệ bằng mật khẩu bằng một API fluent duy nhất, không cần công cụ bên ngoài, đồng thời xử lý các kho lưu trữ đa gigabyte trong chế độ streaming tiết kiệm bộ nhớ.

## Yêu cầu trước
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, hoặc .NET 5–10.  
- Gói NuGet Aspose.Zip cho .NET (`Install-Package Aspose.Zip`).  
- Kiến thức cơ bản về I/O tệp C# và hệ thống dự án .NET.

## Hướng dẫn từng bước

### Cách nén tệp tar – câu trả lời trực tiếp
Tạo một thể hiện `Archive`, thêm các tệp bạn muốn đóng gói, đặt `CompressionType.BZip2` (hoặc thuật toán khác), và gọi `Save` với `ArchiveFormat.TarBz2`. Thư viện ghi container TAR và nén nó trong một lần streaming, vì vậy bạn không bao giờ tải toàn bộ kho lưu trữ vào bộ nhớ.

### Bước 1: Chọn định dạng kho lưu trữ bạn cần
Xác định định dạng dựa trên tar nào phù hợp nhất với sự cân bằng nén‑tốc độ của bạn:
- **TarBz2** – Tỷ lệ nén cao nhất (≈30 % nhỏ hơn TarGz) nhưng chậm hơn.  
- **TarGz** – Cân bằng tốt giữa tốc độ và kích thước; lý tưởng cho hầu hết các kịch bản lưu trữ đám mây.  
- **TarLz / TarXz** – Nén rất cao với tốc độ trung bình, hữu ích cho lưu trữ lưu trữ lâu dài.  
- **TarZ** – Định dạng kế thừa để tương thích với các công cụ Unix cũ.

### Bước 2: Tạo một `Archive` mới
`Archive` đại diện cho một tệp kho lưu trữ duy nhất và cung cấp các phương thức để thêm mục và lưu kho lưu trữ.  
Lớp `Archive` quản lý quy trình đóng gói và nén, cung cấp các phương thức để thêm mục và ghi tệp cuối cùng.

### Bước 3: Thêm tệp và thư mục
Bạn có thể thêm toàn bộ cây thư mục bằng `AddAll` hoặc thêm các tệp riêng lẻ bằng `AddFile`.  
`AddAll` thêm toàn bộ cây thư mục vào kho lưu trữ, giữ nguyên cấu trúc của nó.  
`AddFile` thêm một tệp duy nhất vào kho lưu trữ. Việc giữ nguyên cấu trúc thư mục gốc đơn giản chỉ cần truyền đường dẫn thư mục gốc.

### Bước 4: Đặt loại nén mong muốn
`CompressionType` enum chỉ định thuật toán nén được áp dụng cho luồng TAR.  
`CompressionType` liệt kê các thuật toán được hỗ trợ (BZip2, GZip, LZMA, XZ, v.v.) sẽ được áp dụng trong quá trình lưu.

### Bước 5: Lưu kho lưu trữ
`ArchiveFormat` enum chọn container và kết hợp nén cho tệp đầu ra.  
Gọi `Save` sẽ ghi kho lưu trữ ra đĩa bằng định dạng đã chọn.

### Bước 6: Trích xuất kho lưu trữ có mật khẩu
`ArchiveEntry` đại diện cho một tệp hoặc mục thư mục đơn lẻ trong một kho lưu trữ.  
Để trích xuất zip có bảo vệ bằng mật khẩu, mở kho lưu trữ, xác định mỗi `ArchiveEntry`, gán thuộc tính `Password` của nó, và gọi `Extract`. Thuộc tính `Password` đặt mật khẩu giải mã cho một mục zip. Mô hình mật khẩu theo từng mục này cho phép bạn bảo vệ các tệp riêng lẻ trong một zip duy nhất.

### Bước 7: Xác minh kết quả
Sau khi trích xuất, so sánh kích thước tệp và checksum SHA‑256 để xác nhận rằng quá trình vòng tròn của kho lưu trữ đã giữ nguyên tính toàn vẹn dữ liệu.

## Các trường hợp sử dụng phổ biến
- **Backup utilities** – Lưu các bản sao lưu hàng ngày dưới dạng `.tar.bz2` để giảm chi phí lưu trữ lên tới 30 %.  
- **Cross‑platform data exchange** – Các định dạng dựa trên Tar được hiểu một cách tự nhiên bởi các công cụ Linux, macOS và Windows.  
- **Secure distribution** – Gán mật khẩu cho các mục nhạy cảm, đáp ứng yêu cầu tuân thủ mà không cần công cụ mã hóa bổ sung.

## Khắc phục sự cố & mẹo
- **Large archives** – Sử dụng API streaming (`Archive.CreateEntryFromFile`) để giữ mức sử dụng bộ nhớ thấp.  
- **Password mismatches** – Mật khẩu được đặt trên mỗi `ArchiveEntry` phải khớp chính xác; nếu không sẽ ném `InvalidPasswordException`.  
- **Compression level** – BZIP2 không cung cấp các mức tùy chỉnh; nếu bạn cần kiểm soát chi tiết hơn, chuyển sang LZMA (`CompressionType.LZMA`) hoặc XZ (`CompressionType.XZ`).  

## Câu hỏi thường gặp

**Q: Làm thế nào để tạo kho lưu trữ TarGz?**  
A: Đặt `CompressionType.GZip` và sử dụng `ArchiveFormat.TarGz` khi gọi `Save`. Điều này tạo ra một tệp `.tar.gz` trong một bước duy nhất.

**Q: Tôi có thể trích xuất một kho lưu trữ có bảo vệ bằng mật khẩu mà không biết mật khẩu không?**  
A: Không. Mỗi mục phải được cung cấp mật khẩu đúng; nếu không, quá trình trích xuất sẽ thất bại với `InvalidPasswordException`.

**Q: Aspose.Zip có hỗ trợ trích xuất các kho lưu trữ với mật khẩu khác nhau cho mỗi mục không?**  
A: Có. Gán mật khẩu cho từng `ArchiveEntry` riêng lẻ trước khi gọi `Extract`.

**Q: Định dạng nào cho mức nén tốt nhất?**  
A: Thông thường TarBz2 cho kích thước nhỏ nhất, tiếp theo là TarLz và TarXz. TarGz cung cấp một lựa chọn nhanh hơn, vẫn hiệu quả.

**Q: Có giới hạn về số lượng tệp tôi có thể thêm vào một kho lưu trữ TAR không?**  
A: Thực tế không có, nhưng các kho lưu trữ cực lớn (>10 GB) có thể hưởng lợi từ việc chia thành nhiều phần để dễ xử lý hơn.

## Hướng dẫn trích xuất kho lưu trữ và các định dạng

### [Nén tệp thành TarBz2 với Aspose.Zip cho .NET](./compress-to-tar-bz2/)
Tìm hiểu cách nén tệp thành định dạng TarBz2 trong .NET bằng Aspose.Zip. Theo dõi hướng dẫn từng bước của chúng tôi để nén tệp hiệu quả.  

### [Nén thành TarGz với Aspose.Zip cho .NET](./compress-to-tar-gz/)
Khám phá việc nén tệp hiệu quả trong .NET với Aspose.Zip. Nén thành TarGz một cách dễ dàng.  

### [Nén thành TarLz với Aspose.Zip cho .NET](./compress-to-tar-lz/)
Dễ dàng nén tệp trong .NET với Aspose.Zip. Học cách tạo các kho lưu trữ TarLz từng bước.  

### [Nén thành TarXz với Aspose.Zip cho .NET](./compress-to-tar-xz/)
Tìm hiểu cách nén tệp thành định dạng TarXz trong .NET bằng Aspose.Zip. Theo dõi hướng dẫn của chúng tôi để lưu trữ và truyền tải hiệu quả.  

### [Nén thành TarZ với Aspose.Zip cho .NET](./compress-to-tar-z/)
Khám phá việc nén từng bước thành TarZ bằng Aspose.Zip cho .NET. Xử lý tệp hiệu quả cho các dự án .NET của bạn.  

### [Trích xuất các mục kho lưu trữ với mật khẩu khác nhau trong Aspose.Zip cho .NET](./extract-archive-different-passwords/)
Tìm hiểu cách trích xuất các mục kho lưu trữ với mật khẩu khác nhau trong Aspose.Zip cho .NET. Tăng cường bảo mật và linh hoạt trong ứng dụng của bạn.

## Các hướng dẫn liên quan

- [Tạo kho lưu trữ tar và thêm tệp vào tar với Aspose.Zip cho .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Cách nén tar và tạo TarBz2 với Aspose.Zip cho .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Thêm tệp vào tar và tạo kho lưu trữ tarxz với Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)

---

**Cập nhật lần cuối:** 2026-10-25  
**Kiểm tra với:** Aspose.Zip for .NET 24.11  
**Tác giả:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}