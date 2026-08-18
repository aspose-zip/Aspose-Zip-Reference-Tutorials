---
date: 2026-06-19
description: Tìm hiểu cách nén các tệp tar, tạo các tệp nén targz và giải nén các
  tệp zip được bảo vệ bằng mật khẩu bằng Aspose.Zip cho .NET – nâng cao hiệu quả lưu
  trữ và bảo mật.
keywords:
- how to compress tar
- extract password zip
- aspose zip compress
- aspose zip extract
- create targz archive
linktitle: Trích xuất Lưu trữ và Định dạng
schemas:
- author: Aspose
  dateModified: '2026-06-19'
  description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  headline: How to Compress Tar Files with Aspose.Zip for .NET
  type: TechArticle
- description: Learn how to compress tar files, create targz archives, and extract
    password‑protected zip files using Aspose.Zip for .NET – boosting storage efficiency
    and security.
  name: How to Compress Tar Files with Aspose.Zip for .NET
  steps:
  - name: Choose the archive format you need
    text: 'Decide which tar‑based format best matches your compression‑speed trade‑off:
      - **TarBz2** – Highest compression ratio (≈30 % smaller than TarGz) but slower.
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
  - answer: Practically none, but extremely large archives (>10 GB) may benefit from
      splitting into multiple parts for easier handling.
    question: Is there a limit to the number of files I can add to a TAR archive?
  type: FAQPage
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Cách Nén Tập Tin Tar bằng Aspose.Zip cho .NET
url: /vi/net/archive-extraction-and-formats/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Nén Tập Tin Tar bằng Aspose.Zip cho .NET

## Giới thiệu

Trong hướng dẫn này, bạn sẽ khám phá **cách nén tar** bằng Aspose.Zip cho .NET, học cách tạo các archive TarGz, và xem cách giải nén các archive zip được bảo vệ bằng mật khẩu. Xử lý archive hiệu quả là một kỹ năng cốt lõi cho các nhà phát triển .NET hiện đại—cho dù bạn đang xây dựng dịch vụ sao lưu, khách hàng lưu trữ đám mây, hoặc quy trình xử lý dữ liệu, việc thành thạo các định dạng này giúp giảm chi phí lưu trữ, tăng tốc truyền tải, và bảo vệ dữ liệu nhạy cảm.

## Câu trả lời nhanh
- **TarBz2 là gì?** Một archive nén kết hợp gói TAR với nén BZIP2 để đạt tỷ lệ nén cao.  
- **Tại sao chọn Aspose.Zip cho .NET?** Nó cung cấp một API duy nhất, mượt mà để tạo và giải nén nhiều định dạng archive mà không cần phụ thuộc bên ngoài.  
- **Tôi có thể tạo archive TarGz không?** Có – Aspose.Zip hỗ trợ TarGz, TarLz, TarXz, TarZ, và hơn nữa.  
- **Làm thế nào để giải nén archive zip được bảo vệ bằng mật khẩu?** Sử dụng thuộc tính `Password` trên đối tượng `ArchiveEntry` khi giải nén.  
- **Tôi có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Cần giấy phép thương mại cho môi trường sản xuất; bản dùng thử miễn phí có sẵn để đánh giá.

## Nén Tar là gì?
Tar (Tape Archive) là một định dạng container gói nhiều tệp và thư mục thành một luồng duy nhất mà không nén. Khi bạn áp dụng một thuật toán nén như BZIP2, GZip, LZMA, hoặc XZ, kết quả là một **archive dựa trên tar** như `.tar.bz2`, `.tar.gz`, `.tar.lz`, v.v. Các định dạng này được hỗ trợ rộng rãi trên Linux, macOS và Windows, làm cho chúng trở nên lý tưởng cho việc trao đổi dữ liệu đa nền tảng.

## Tại sao nên sử dụng Aspose.Zip cho .NET để xử lý các định dạng này?
Aspose.Zip cung cấp một **API thống nhất, không phụ thuộc** hỗ trợ hơn 50 định dạng archive và nén, bao gồm TarBz2, TarGz, TarLz, TarXz và TarZ. Nó chạy trên Windows, Linux và macOS, và kiến trúc dựa trên stream giữ mức sử dụng bộ nhớ dưới 10 MB ngay cả với các archive hàng trăm megabyte. Bảo vệ bằng mật khẩu được tích hợp sẵn, cho phép mã hóa từng entry mà không cần thư viện bổ sung.

## Yêu cầu trước
- .NET Framework 2.0–4.8.1, .NET Core 2.0–3.1, hoặc .NET 5–10.  
- Gói NuGet Aspose.Zip cho .NET đã được cài đặt (`Install-Package Aspose.Zip`).  
- Kiến thức cơ bản về I/O tệp C# và hệ thống dự án .NET.

## Hướng dẫn từng bước

### Cách Nén Tập Tin Tar – Trả lời trực tiếp
`Archive` đại diện cho một tệp archive và cung cấp các phương thức để thêm entry và lưu nó.  
Tạo một thể hiện `Archive`, thêm các tệp bạn muốn gói, đặt `CompressionType.BZip2`, và gọi `Save` với `ArchiveFormat.TarBz2`. Thư viện sẽ ghi container TAR và nén nó trong một lần truyền stream duy nhất, vì vậy bạn không bao giờ phải tải toàn bộ archive vào bộ nhớ.

### Bước 1: Chọn định dạng archive bạn cần
Xác định định dạng dựa trên tar nào phù hợp nhất với sự cân bằng giữa tốc độ và mức nén của bạn:

- **TarBz2** – Tỷ lệ nén cao nhất (≈30 % nhỏ hơn TarGz) nhưng chậm hơn.  
- **TarGz** – Cân bằng tốt giữa tốc độ và kích thước; lý tưởng cho hầu hết các kịch bản lưu trữ đám mây.  
- **TarLz / TarXz** – Nén rất cao với tốc độ trung bình, hữu ích cho lưu trữ lâu dài.  
- **TarZ** – Định dạng legacy để tương thích với các công cụ Unix cũ.

### Bước 2: Tạo một thể hiện `Archive` mới
`Archive` là đối tượng cấp cao nhất đại diện cho một tệp archive duy nhất trong bộ nhớ.  

Lớp `Archive` quản lý quy trình đóng gói và nén, cung cấp các phương thức để thêm entry và ghi tệp cuối cùng.

### Bước 3: Thêm tệp và thư mục
Bạn có thể thêm toàn bộ cây thư mục bằng `AddAll` hoặc thêm các tệp riêng lẻ bằng `AddFile`. Việc bảo tồn cấu trúc thư mục gốc đơn giản chỉ cần truyền đường dẫn thư mục gốc.

### Bước 4: Đặt loại nén mong muốn
`CompressionType` liệt kê các thuật toán được hỗ trợ.  

`CompressionType` xác định thuật toán (BZip2, GZip, LZMA, XZ, v.v.) sẽ được áp dụng cho luồng TAR khi lưu.

### Bước 5: Lưu archive
`ArchiveFormat` là một tập enum (ví dụ: `TarBz2`, `TarGz`) cho biết trình ghi nên sử dụng container và thuật toán nén nào.  

Gọi `Save` sẽ ghi archive ra đĩa bằng định dạng đã chọn.

### Bước 6: Giải nén archive có mật khẩu
`ArchiveEntry` đại diện cho một tệp hoặc thư mục entry duy nhất trong archive.  

Để giải nén zip được bảo vệ bằng mật khẩu, mở archive, tìm mỗi `ArchiveEntry`, gán thuộc tính `Password` của nó, và gọi `Extract`. Mô hình mật khẩu theo entry này cho phép bạn bảo vệ các tệp riêng lẻ trong một zip duy nhất.

### Bước 7: Xác minh kết quả
Sau khi giải nén, so sánh kích thước tệp và checksum SHA‑256 để xác nhận rằng quá trình round‑trip của archive đã giữ nguyên tính toàn vẹn dữ liệu.

## Các trường hợp sử dụng phổ biến
- **Công cụ sao lưu** – Lưu các bản sao lưu hàng ngày dưới dạng `.tar.bz2` để giảm chi phí lưu trữ lên tới 30 %.  
- **Trao đổi dữ liệu đa nền tảng** – Các định dạng dựa trên Tar được các công cụ Linux, macOS và Windows hiểu một cách tự nhiên.  
- **Phân phối an toàn** – Gán mật khẩu cho các entry nhạy cảm, đáp ứng yêu cầu tuân thủ mà không cần công cụ mã hoá bổ sung.

## Khắc phục sự cố & Mẹo
- **Archive lớn** – Ưu tiên API streaming (`Archive.CreateEntryFromFile`) để giữ mức sử dụng bộ nhớ thấp.  
- **Mật khẩu không khớp** – Mật khẩu được đặt trên mỗi `ArchiveEntry` phải khớp chính xác; nếu không sẽ ném ra `InvalidPasswordException`.  
- **Mức nén** – BZIP2 không cho phép tùy chỉnh mức; nếu bạn cần kiểm soát chi tiết hơn, chuyển sang LZMA (`CompressionType.LZMA`) hoặc XZ (`CompressionType.XZ`).  

## Câu hỏi thường gặp

**Q: Làm thế nào để tạo một archive TarGz?**  
A: Đặt `CompressionType.GZip` và sử dụng `ArchiveFormat.TarGz` khi gọi `Save`. Điều này tạo ra một tệp `.tar.gz` trong một bước duy nhất.

**Q: Tôi có thể giải nén một archive được bảo vệ bằng mật khẩu mà không biết mật khẩu không?**  
A: Không. Mỗi entry phải được cung cấp mật khẩu đúng; nếu không, quá trình giải nén sẽ thất bại với `InvalidPasswordException`.

**Q: Aspose.Zip có hỗ trợ giải nén archive với mật khẩu khác nhau cho mỗi entry không?**  
A: Có. Gán mật khẩu cho từng `ArchiveEntry` riêng biệt trước khi gọi `Extract`.

**Q: Định dạng nào cho mức nén tốt nhất?**  
A: Thông thường TarBz2 cho kích thước nhỏ nhất, tiếp theo là TarLz và TarXz. TarGz cung cấp một lựa chọn nhanh hơn, vẫn hiệu quả.

**Q: Có giới hạn số lượng tệp tôi có thể thêm vào một archive TAR không?**  
A: Thực tế không có giới hạn, nhưng các archive cực lớn (>10 GB) có thể hưởng lợi từ việc chia thành nhiều phần để dễ xử lý hơn.

## Hướng dẫn Giải nén Archive và Định dạng

### [Nén Tập Tin thành TarBz2 với Aspose.Zip cho .NET](./compress-to-tar-bz2/)
Tìm hiểu cách nén tệp thành định dạng TarBz2 trong .NET bằng Aspose.Zip. Thực hiện theo hướng dẫn từng bước của chúng tôi để nén tệp hiệu quả.  

### [Nén thành TarGz với Aspose.Zip cho .NET](./compress-to-tar-gz/)
Khám phá nén tệp hiệu quả trong .NET với Aspose.Zip. Nén thành TarGz một cách dễ dàng.  

### [Nén thành TarLz với Aspose.Zip cho .NET](./compress-to-tar-lz/)
Dễ dàng nén tệp trong .NET với Aspose.Zip. Học cách tạo archive TarLz từng bước.  

### [Nén thành TarXz với Aspose.Zip cho .NET](./compress-to-tar-xz/)
Tìm hiểu cách nén tệp thành định dạng TarXz trong .NET bằng Aspose.Zip. Thực hiện theo hướng dẫn của chúng tôi để lưu trữ và truyền tải hiệu quả.  

### [Nén thành TarZ với Aspose.Zip cho .NET](./compress-to-tar-z/)
Khám phá quy trình nén từng bước thành TarZ bằng Aspose.Zip cho .NET. Xử lý tệp hiệu quả cho các dự án .NET của bạn.  

### [Giải nén các Entry trong Archive với Mật khẩu Khác nhau trong Aspose.Zip cho .NET](./extract-archive-different-passwords/)
Tìm hiểu cách giải nén các entry trong archive với mật khẩu khác nhau trong Aspose.Zip cho .NET. Tăng cường bảo mật và tính linh hoạt trong ứng dụng của bạn.

---

**Last Updated:** 2026-06-19  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose

## Hướng dẫn liên quan

- [Tạo archive tar và thêm tệp vào tar với Aspose.Zip cho .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-gz/)
- [Cách nén tar và tạo TarBz2 với Aspose.Zip cho .NET](/zip/net/archive-extraction-and-formats/compress-to-tar-bz2/)
- [Thêm tệp vào tar và tạo archive tarxz với Aspose.Zip](/zip/net/archive-extraction-and-formats/compress-to-tar-xz/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}