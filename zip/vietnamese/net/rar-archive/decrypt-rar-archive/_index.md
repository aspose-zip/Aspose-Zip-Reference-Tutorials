---
description: Tìm hiểu cách giải nén RAR vào thư mục và giải mã các tệp RAR được mã
  hóa bằng Aspose.Zip cho .NET. Thực hiện hướng dẫn từng bước để đọc tệp RAR được
  mã hóa và chỉ định mật khẩu RAR.
linktitle: Decrypting a RAR Archive
second_title: Aspose.Zip .NET API for Files Compression & Archiving
title: Giải nén RAR vào thư mục với Aspose.Zip cho .NET
url: /vi/net/rar-archive/decrypt-rar-archive/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Giải nén RAR vào Thư mục với Aspose.Zip cho .NET

## Giới thiệu

Nếu bạn cần **extract RAR to folder** và làm việc với các kho lưu trữ được bảo vệ bằng mật khẩu, Aspose.Zip cho .NET giúp công việc trở nên dễ dàng. Trong hướng dẫn này, chúng tôi sẽ trình bày các bước cụ thể để đọc một tệp RAR được mã hoá, chỉ định mật khẩu RAR, và giải nén nội dung của kho lưu trữ vào thư mục đích. Dù bạn đang xây dựng một tiện ích desktop hay một dịch vụ phía máy chủ, bạn sẽ thấy cách tích hợp logic giải mã một cách nhanh chóng và đáng tin cậy.

## Câu trả lời nhanh
- **What does “extract RAR to folder” mean?** Nó có nghĩa là mở một kho lưu trữ RAR và ghi mỗi mục vào một thư mục được chỉ định trên đĩa.  
- **Which library handles decryption?** Aspose.Zip for .NET cung cấp hỗ trợ tích hợp cho các kho lưu trữ RAR được mã hoá.  
- **Do I need a license for testing?** Một giấy phép tạm thời có sẵn để đánh giá; giấy phép đầy đủ là bắt buộc cho môi trường sản xuất.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, và .NET 5/6+.  
- **How long does the implementation take?** Thường mất dưới 10 phút cho một kịch bản giải nén cơ bản.

## “extract RAR to folder” là gì?
Giải nén một kho lưu trữ RAR vào thư mục có nghĩa là giải nén mọi tệp được lưu trong kho và đặt chúng vào một thư mục bạn chọn. Khi kho lưu trữ được mã hoá, bạn cũng phải cung cấp mật khẩu đúng trước khi quá trình giải nén có thể thực hiện.

## Tại sao nên sử dụng Aspose.Zip để giải nén RAR được mã hoá?
Aspose.Zip trừu tượng hoá các phức tạp của định dạng RAR, xử lý cả các kho lưu trữ tiêu chuẩn và được mã hoá mà không cần phụ thuộc bên ngoài. Nó cung cấp một API hướng đối tượng sạch sẽ, hiệu năng mạnh mẽ và xử lý lỗi xuất sắc—lý tưởng cho các nhà phát triển .NET muốn có giải pháp đáng tin cậy cho **how to decrypt RAR** files.

## Yêu cầu trước

Trước khi bắt đầu hướng dẫn, hãy chắc chắn rằng bạn đã chuẩn bị các yêu cầu sau:

1. Thư viện Aspose.Zip cho .NET: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Zip trong dự án .NET của mình. Bạn có thể tải xuống từ [Aspose.Zip documentation](https://reference.aspose.com/zip/net/).
2. Thư mục tài liệu: Thiết lập một thư mục chứa kho lưu trữ RAR được mã hoá của bạn. Thay thế "Your Document Directory" trong mã mẫu bằng đường dẫn thực tế tới thư mục này.

## Nhập các Namespace

Chúng ta sẽ bắt đầu bằng việc nhập các namespace cần thiết để sử dụng thư viện Aspose.Zip một cách hiệu quả. Thêm các dòng sau vào đầu tệp .NET của bạn:

```csharp
//ExStart: ImportNamespaces
using Aspose.Zip;
using System.IO;
//ExEnd: ImportNamespaces
```

## Bước 1 – Mở kho lưu trữ RAR được mã hoá

Đầu tiên, mở một luồng chỉ đọc cho tệp RAR được mã hoá. Điều này chuẩn bị tệp cho quá trình giải mã và giải nén.

```csharp
//ExStart: DecryptRarArchive_Step1
using (FileStream fs = File.OpenRead(dataDir + "encrypted.rar"))
{
    //ExEnd: DecryptRarArchive_Step1
    // Continue to the next step here...
}
```

## Bước 2 – Chỉ định mật khẩu RAR (how to decrypt RAR)

Bây giờ tạo một thể hiện `RarArchive` và thông báo cho Aspose.Zip mật khẩu bảo vệ kho lưu trữ. Thay thế `"p@s$"` bằng mật khẩu thực tế bạn đã dùng khi tạo RAR được mã hoá.

```csharp
//ExStart: DecryptRarArchive_Step2
using (RarArchive archive = new RarArchive(fs, new RarArchiveLoadOptions() { DecryptionPassword = "p@s$" }))
{
    //ExEnd: DecryptRarArchive_Step2
    // Continue to the next step here...
}
```

## Bước 3 – Giải nén nội dung vào thư mục (extract encrypted RAR)

Cuối cùng, giải nén mọi mục vào thư mục bạn chọn. Điều này hoàn thành thao tác **extract RAR to folder**.

```csharp
//ExStart: DecryptRarArchive_Step3
archive.ExtractToDirectory(dataDir + "DecompressRar_out");
//ExEnd: DecryptRarArchive_Step3
```

Lặp lại các bước này cho mỗi kho lưu trữ RAR bạn cần giải mã, đảm bảo việc tích hợp Aspose.Zip cho .NET vào dự án của bạn diễn ra suôn sẻ.

## Những lỗi thường gặp & Mẹo

- **Incorrect password** – Nếu mật khẩu sai, Aspose.Zip sẽ ném ra `WrongPasswordException`. Hãy kiểm tra lại chuỗi bạn truyền cho `DecryptionPassword`.
- **Large archives** – Đối với các tệp RAR rất lớn, hãy cân nhắc giải nén vào một thư mục tạm trước, sau đó di chuyển các tệp tới vị trí cuối cùng để tránh hết dung lượng đĩa.
- **Path safety** – Luôn xác thực `dataDir` và các đường dẫn đầu ra để ngăn ngừa lỗ hổng traversal thư mục.

## Kết luận

Chúc mừng! Bạn đã thành công **extracted a RAR to folder** và học cách **read encrypted RAR file** bằng Aspose.Zip cho .NET. Thư viện mạnh mẽ này đơn giản hoá quá trình phức tạp của việc mở khóa các kho lưu trữ được bảo vệ bằng mật khẩu, trở thành công cụ vô giá cho các nhà phát triển làm việc với ứng dụng .NET.

## Câu hỏi thường gặp (FAQs)

### Aspose.Zip cho .NET có tương thích với mọi phiên bản kho lưu trữ RAR không?
Aspose.Zip cho .NET hỗ trợ nhiều phiên bản kho lưu trữ RAR, đảm bảo tương thích với đa dạng tệp tin.

### Tôi có thể sử dụng Aspose.Zip cho .NET trong các dự án thương mại không?
Có, Aspose.Zip cho .NET có sẵn để sử dụng thương mại. Truy cập [purchase page](https://purchase.aspose.com/buy) để biết chi tiết giấy phép.

### Có giấy phép tạm thời cho mục đích thử nghiệm không?
Có, bạn có thể nhận giấy phép tạm thời để thử nghiệm từ [here](https://purchase.aspose.com/temporary-license/).

### Tôi có thể tìm hỗ trợ bổ sung hoặc thảo luận cộng đồng ở đâu?
Truy cập [Aspose.Zip forum](https://forum.aspose.com/c/zip/37) để được hỗ trợ và thảo luận cộng đồng.

### Làm sao để truy cập tài liệu cho Aspose.Zip cho .NET?
[documentation](https://reference.aspose.com/zip/net/) cung cấp thông tin chi tiết về cách sử dụng Aspose.Zip cho .NET.

**Câu hỏi bổ sung**

**Q:** Làm sao tôi có thể giải nén chỉ các tệp cụ thể từ một RAR được mã hoá?  
**A:** Sử dụng `RarArchiveEntry` để tìm mục mong muốn và gọi `ExtractToFile` với mật khẩu giải mã đã được đặt trên kho lưu trữ.

**Q:** Nếu tôi cần thay đổi tên thư mục đầu ra một cách động thì sao?  
**A:** Tạo đường dẫn đầu ra bằng `Path.Combine` và bất kỳ biến runtime nào trước khi gọi `ExtractToDirectory`.

**Q:** Aspose.Zip có hỗ trợ các kho lưu trữ RAR đa phần không?  
**A:** Có, thư viện có thể mở và giải nén các bộ RAR đa phần miễn là tất cả các phần đều có thể truy cập.

---

**Last Updated:** 2026-03-13  
**Tested With:** Aspose.Zip for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}