---
title: Chuyển đổi PDF sang Hình ảnh PNG qua Cloud .NET SDK
weight: 530
url: net/conversion/pdf-to-png/
description: Chuyển đổi PDFs thành hình ảnh PNG với Aspose.PDF Cloud SDK cho .NET. Đầu ra chất lượng cao cho sử dụng kỹ thuật số.
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Chuyển đổi PDF sang PNG trong .NET SDK" h2="Chuyển đổi tài liệu PDF sang định dạng PNG với Aspose.PDF Cloud .NET SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK cho .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="Cách Chuyển đổi PDF sang PNG Sử dụng SDK cho .NET" %}}

Để chuyển đổi PDF sang PNG, chúng tôi sẽ sử dụng
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
SDK Cloud này cho phép bạn dễ dàng xây dựng các ứng dụng tạo, chỉnh sửa & chuyển đổi PDF dựa trên đám mây bằng C#, ASP.NET hoặc các ngôn ngữ .NET khác cho các nền tảng đám mây khác nhau. Mở
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
trình quản lý gói, tìm kiếm
Aspose.PDF Cloud
và cài đặt. Bạn cũng có thể sử dụng lệnh sau từ Bảng điều khiển Trình quản lý Gói.

{{% blocks/products/pf/agp/code-block title="Lệnh Bảng điều khiển Trình quản lý Gói" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Các bước Chuyển đổi PDF sang PNG qua .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

Các nhà phát triển Aspose.PDF Cloud có thể dễ dàng tải & chuyển đổi tệp PDF sang PNG chỉ trong vài dòng mã.

{{% /blocks/products/pf/agp/text %}}

1. Tạo một đối tượng Cấu hình mới với Mật khẩu và Khóa Ứng dụng của bạn
1. Tạo một đối tượng để kết nối với API Đám mây
1. Tải lên tệp tài liệu của bạn
1. Thực hiện chuyển đổi
1. Tải xuống kết quả

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="Mã mẫu này hiển thị Chuyển đổi PDF sang PNG Cloud .NET SDK" offSpacer="" %}}

```cs

    public static void ConvertPdfToPng()
    {
        const string localImageFileName = @"C:\Samples\sample.pdf";
        const string storageImageFileName = "sample.pdf";
        const string resultFileName = "sample.png";

        // Get your AppSid and AppSecret https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);
        using var file = File.OpenRead(localImageFileName);
        pdfApi.UploadFile(storageImageFileName, file);

        var response = pdfApi.GetPageConvertToPng(storageImageFileName, 1);
        response.CopyTo(File.OpenWrite(resultFileName));
        Console.WriteLine($"PDF to PNG result: {response.Length} bytes");
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="Các Chuyển đổi Khác Được Hỗ trợ" subTitle="Bạn cũng có thể chuyển đổi nhiều định dạng tệp khác" >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/bmp-to-pdf/" name="BMP SANG PDF" description="Hình ảnh Bitmap" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/emf-to-pdf/" name="EMF SANG PDF" description="Định dạng Tệp Siêu Dữ liệu Nâng cao" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/epub-to-pdf/" name="EPUB SANG PDF" description="Định dạng Sách điện tử" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/gif-to-pdf/" name="GIF SANG PDF" description="Định dạng Trao đổi Hình ảnh Đồ họa" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/html-to-pdf/" name="HTML SANG PDF" description="Ngôn ngữ Đánh dấu Siêu văn bản" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/jpeg-to-pdf/" name="JPEG SANG PDF" description="Hình ảnh JPEG" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/md-to-pdf/" name="MD SANG PDF" description="Markdown" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pcl-to-pdf/" name="PCL SANG PDF" description="Ngôn ngữ Lệnh Máy in" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-bmp/" name="PDF SANG BMP" description="Hình ảnh Bitmap" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-docx/" name="PDF SANG DOCX" description="Tài liệu Words Office 2007+" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-emf/" name="PDF SANG EMF" description="Định dạng Tệp Siêu Dữ liệu Nâng cao" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-epub/" name="PDF SANG EPUB" description="Định dạng Sách điện tử" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-gif/" name="PDF TO GIF" description="Định dạng Trao đổi Đồ họa" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-html/" name="PDF TO HTML" description="Ngôn ngữ Đánh dấu Siêu văn bản" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-jpeg/" name="PDF TO JPEG" description="Hình ảnh JPEG" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pdfa/" name="PDF TO PDF/A" description="Định dạng Tài liệu Di động/A" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-png/" name="PDF TO PNG" description="Đồ họa Mạng Di động" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF TO PPTX" description="Định dạng trình bày Open XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-svg/" name="PDF TO SVG" description="Đồ họa Vector Có thể Mở rộng" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tex/" name="PDF TO TEX" description="Văn bản Xuất LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tiff/" name="PDF TO TIFF" description="Định dạng Hình ảnh Gắn thẻ" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-txt/" name="PDF TO TXT" description="Tài liệu Văn bản" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xlsx/" name="PDF TO XLSX" description="Tệp Excel OOXML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xps/" name="PDF TO XPS" description="Đặc tả Giấy XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF TO PPTX" description="Định dạng trình bày Open XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/png-to-pdf/" name="PNG TO PDF" description="Đồ họa Mạng Di động" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/svg-to-pdf/" name="SVG TO PDF" description="Đồ họa Vector Có thể Mở rộng" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tex-to-pdf/" name="TEX TO PDF" description="Văn bản Xuất LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/text-to-pdf/" name="TEXT TO PDF" description="Tài liệu Văn bản" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tiff-to-pdf/" name="TIFF TO PDF" description="Định dạng Hình ảnh Gắn thẻ" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/xps-to-pdf/" name="XPS TO PDF" description="Đặc tả Giấy XML" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}


