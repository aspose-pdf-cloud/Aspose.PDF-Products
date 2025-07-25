---
title: Cập nhật Metadata trong Tài liệu PDF qua Cloud .NET SDK
url: net/metadata/update/
description: Cập nhật metadata PDF với Aspose.PDF Cloud SDK cho .NET. Thay đổi całkowowo thuộc tính tài liệu.
lastmod: 2022-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Cập nhật Metadata trong PDF trong .NET SDK" h2="Cập nhật tất cả metadata từ tài liệu PDF sử dụng Aspose.PDF Cloud .NET API" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK cho .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-words-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="Cách cập nhật Metadata từ tài liệu PDF sử dụng Cloud .NET SDK" %}}

Để cập nhật Metadata qua Cloud .NET SDK, chúng ta sẽ sử dụng
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
Cloud SDK này cho phép bạn dễ dàng xây dựng các ứng dụng tạo, chỉnh sửa & chuyển đổi PDF dựa trên cloud bằng C#, ASP.NET hoặc các ngôn ngữ .NET khác cho các nền tảng cloud khác nhau. Mở
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
quản lý gói, tìm kiếm
Aspose.PDF Cloud
và cài đặt. Bạn cũng có thể sử dụng lệnh sau từ Package Manager Console.

{{% blocks/products/pf/agp/code-block title="Lệnh Package Manager Console" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Bước để cập nhật Metadata qua .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

Những lập trình viên Aspose.PDF Cloud có thể dễ dàng tải & cập nhật metadata trong PDF chỉ bằng vài dòng mã.

{{% /blocks/products/pf/agp/text %}}

1. Tạo một đối tượng Configuration mới với Application Secret và Key của bạn
1. Tạo một đối tượng kết nối đến Cloud API
1. Tải tượng lên tệp tài liệu của bạn
1. Cập nhật thuộc tính dungl PutSetProperty
1. Xử lý thuộc tính, ví dụ, in ra console

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="Mã mẫu này hiển thị cập nhật Metadata trong tài liệu PDF" offSpacer="" %}}

```cs

    public static void UpdateMetadata()
    {
        const string localImageFileName = @"C:\Samples\sample.pdf";
        const string storageFileName = "sample.pdf";


        // Get your AppSid and AppSecret https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);

        using var file = File.OpenRead(localImageFileName);
        var uploadResult = pdfApi.UploadFile(storageFileName, file);
        Console.WriteLine(uploadResult.Uploaded[0]);
        var response = pdfApi.GetDocumentProperty(storageFileName, "xmp:ArchiveType");
        if (response.DocumentProperty.Value != null && !response.DocumentProperty.Value.StartsWith("Aspose"))
        {
            var responseSet = pdfApi.PutSetProperty(storageFileName, "xmp:ArchiveType", "Aspose Sample Document");
            Console.WriteLine(responseSet.Status);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

