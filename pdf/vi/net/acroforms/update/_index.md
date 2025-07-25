---
title: Cập nhật Tr Trường Form trong Tài Liệu PDF qua Cloud .NET SDK
url: net/acroforms/update/
description: Cập nhật các trường AcroForm hiện có trong PDF với Aspose.PDF Cloud SDK for .NET.ньоїІnh đáp ứng nhanh, chính xác và linh hoạt.
lastmod: 2022-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Cập nhật PDF Forms trong .NET SDK" h2="Cập nhật tất cả các trường form từ tài liệu PDF sử dụng Aspose.PDF Cloud .NET API" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-words-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="Làm cách nào để cập nhật Trường Form từ Tài Liệu PDF sử dụng Cloud .NET SDK" %}}

Để cập nhật một AcroForm qua Cloud .NET SDK, chúng ta sẽ sử dụng
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
Cloud SDK này cho phép bạn dễ dàng xây dựng các ứng dụng tạo, sửa đổi và chuyển đổi PDF dựa trên cloud trong C#, ASP.NET, hoặc ngôn ngữ .NET khác cho các nền tảng cloud khác nhau. Mở
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
quản lý gói, tìm kiếm
Aspose.PDF Cloud
và cài đặt. Bạn cũng có thể sử dụng lệnh sau từ trình điều khiển Package Manager Console.

{{% blocks/products/pf/agp/code-block title="Package Manager Console Command" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Các bước để cập nhật AcroForms qua .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

Phát triển viên Aspose.PDF Cloud có thể dễ dàng tải lên & cập nhật acroforms trong PDF chỉ với इतना vài dòng code.

{{% /blocks/products/pf/agp/text %}}

1. Tạo một đối tượng Configuration mới với Application Secret và Key của bạn
1. Tạo một đối tượng để kết nối với Cloud API
tải lên file tài liệu của bạn
Thực hiện thực hiện cập nhật
1. Tải xuống kết quả

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="Mã ví dụ này hiển thị cập nhật AcroForms trong tài liệu PDF" offSpacer="" %}}

```cs

    public static void UpdateFormFields()
    {
        const string localImageFileName = @"C:\Samples\StudentInfoFormElectronic.pdf";
        const string storageFileName = "StudentInfoFormElectronic.pdf";
        // Get your AppSid and AppSecret from https://dashboard.aspose.cloud (free registration required).            
        var pdfApi = new PdfApi(AppSecret, AppSid);
        var filesOnStorage = pdfApi.GetFilesList("");
        if (filesOnStorage.Value.All(f => f.Name != storageFileName))
        {
            using var file = File.OpenRead(localImageFileName);
            var uploadResult = pdfApi.UploadFile(storageFileName, file);
            Console.WriteLine(uploadResult.Uploaded[0]);
        }
        var fieldList = new List<Field>
        {
            new Field(
                    Name: "First Name",
                    Type: FieldType.Text,
                    Values: ["James"],
                    Rect: new Rectangle(125, 735, 200, 752))
        };

        var fields = new Fields(List: fieldList);

        var response = pdfApi.PutUpdateFields(storageFileName, fields);
        Console.WriteLine(response.Status);
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

