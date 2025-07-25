---
title: Chuyển Đổi Văn Bản Thành PDF qua Cloud .NET SDK
url: net/conversion/text-to-pdf/
description: Chuyển đổi tệp văn bản đơn giản thành PDF định dạng với Aspose.PDF Cloud SDK cho .NET.
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Chuyển Đổi Văn Bản Thành PDF trong .NET SDK" h2="Xuất tài liệu Văn Bản sang nhiều định dạng bao gồm PDF với Aspose.PDF Cloud .NET SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK cho .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="Cách Chuyển Đổi Văn Bản Thành PDF Sử Dụng SDK cho .NET" %}}

Để chuyển đổi Văn Bản sang PDF, chúng ta sẽ sử dụng
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
Cloud SDK này cho phép bạn dễ dàng xây dựng ứng dụng tạo, chỉnh sửa & chuyển đổi PDF dựa trên đám mây bằng C#, ASP.NET, hoặc các ngôn ngữ .NET khác cho nhiều nền tảng đám mây. Mở
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
trình quản lý gói, tìm kiếm
Aspose.PDF Cloud
và cài đặt. Bạn cũng có thể sử dụng lệnh sau từ Package Manager Console.

{{% blocks/products/pf/agp/code-block title="Lệnh Package Manager Console" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Các Bước Chuyển Đổi Văn Bản Thành PDF qua .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

Các nhà phát triển Aspose.PDF Cloud có thể dễ dàng tải & chuyển đổi tệp Văn Bản sang PDF chỉ với vài dòng mã.

{{% /blocks/products/pf/agp/text %}}

1. Tạo đối tượng Cấu hình mới với Secret và Key của Ứng dụng của bạn
1. Tạo một đối tượng để kết nối với Cloud API
1. Tải lên tệp tài liệu của bạn
1. Thực hiện chuyển đổi
1. Tải về kết quả

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="Mã mẫu này cho thấy Chuyển Đổi Văn Bản Thành PDF qua Cloud .NET SDK" offSpacer="" %}}

```cs

    public static void ConvertTextToPdf()
    {
        const string localTextFileName = @"C:\Samples\Conversion\sample.txt";
        const string storageTextFileName = "sample.txt";
        const string resultFileName = "sample-txt-to-pdf.pdf";
        
        // Get your AppSid and AppSecret https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);

        using var file = File.OpenRead(localTextFileName);
        pdfApi.UploadFile(storageTextFileName, file);
        
        var response = pdfApi.PutMarkdownInStorageToPdf(resultFileName, storageTextFileName);
        Console.WriteLine($"TEXT to PDF result: {response.Status}");
        pdfApi.DownloadFile(resultFileName)
            .CopyTo(File.Create(resultFileName));
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="Các Chuyển Đổi Hỗ Trợ Khác" subTitle="Bạn cũng có thể chuyển đổi nhiều định dạng tệp khác" >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/bmp-to-pdf/" name="BMP TO PDF" description="Hình ảnh Bitmap" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/emf-to-pdf/" name="EMF TO PDF" description="Định dạng Siêu Tệp Metafile" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/epub-to-pdf/" name="EPUB TO PDF" description="Định dạng Sách Điện Tử" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/gif-to-pdf/" name="GIF TO PDF" description="Định dạng Trao Đổi Hình Ảnh" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/html-to-pdf/" name="HTML-TO-PDF" description="Ngôn Ngữ Đánh Dấu Siêu Văn Bản" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/jpeg-to-pdf/" name="JPEG TO PDF" description="Hình ảnh JPEG" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/md-to-pdf/" name="MD TO PDF" description="Markdown" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pcl-to-pdf/" name="PCL TO PDF" description="Ngôn Ngữ Lệnh Máy In" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-bmp/" name="PDF TO BMP" description="Hình ảnh Bitmap" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-docx/" name="PDF TO DOCX" description="Tài liệu Word Office 2007+" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-emf/" name="PDF TO EMF" description="Định dạng Siêu Tệp Metafile" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-epub/" name="PDF TO EPUB" description="Định dạng Sách Điện Tử" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-gif/" name="PDF TO GIF" description="Định dạng Trao Đổi Hình Ảnh" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-html/" name="PDF SANG HTML" description="Ngôn ngữ Đánh dấu Siêu văn bản" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-jpeg/" name="PDF SANG JPEG" description="Hình ảnh JPEG" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pdfa/" name="PDF SANG PDF/A" description="Định dạng Tài liệu Di động/A" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-png/" name="PDF SANG PNG" description="Đồ họa Mạng Di động" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF SANG PPTX" description="Định dạng trình bày XML Mở" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-svg/" name="PDF SANG SVG" description="Đồ họa Vector có thể Thay đổi" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tex/" name="PDF SANG TEX" description="Văn bản Đầu ra LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tiff/" name="PDF SANG TIFF" description="Định dạng Hình ảnh Được gắn Thẻ" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-txt/" name="PDF SANG TXT" description="Tài liệu Văn bản" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xlsx/" name="PDF SANG XLSX" description="Tệp Excel OOXML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xps/" name="PDF SANG XPS" description="Đặc tả Tài liệu XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF SANG PPTX" description="Định dạng trình bày XML Mở" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/png-to-pdf/" name="PNG SANG PDF" description="Đồ họa Mạng Di động" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/svg-to-pdf/" name="SVG SANG PDF" description="Đồ họa Vector có thể Thay đổi" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tex-to-pdf/" name="TEX SANG PDF" description="Văn bản Đầu ra LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/text-to-pdf/" name="VĂN BẢN SANG PDF" description="Tài liệu Văn bản" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tiff-to-pdf/" name="TIFF SANG PDF" description="Định dạng Hình ảnh Được gắn Thẻ" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/xps-to-pdf/" name="XPS SANG PDF" description="Đặc tả Tài liệu XML" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

