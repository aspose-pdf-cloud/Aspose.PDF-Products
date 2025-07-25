---
title: Обновление метаданных в PDF-документе с использованием облачного .NET SDK
url: net/metadata/update/
description: Обновите метаданные PDF с помощью облачного SDK для .NET Aspose.PDF Cloud. Программно измените свойства документа.
lastmod: 2022-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Обновление метаданных в PDF в .NET SDK" h2="Обновите все метаданные из PDF-документа с помощью облачного API Aspose.PDF Cloud .NET" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK для .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-words-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="Как обновить метаданные PDF-документа с использованием облачного .NET SDK" %}}

Чтобы обновить Метаданные с помощью облачного .NET SDK, мы будем использовать
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
Это облачное SDK позволяет легко создавать облачные приложения для создания, редактирования и конвертирования PDF в C#, ASP.NET или других языкама .NET для различных облачных платформ. Откройте
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
менеджер пакетов, найдите
Aspose.PDF Cloud
и установите. Вы также можете использовать следующую команду из Package Manager Console.

{{% blocks/products/pf/agp/code-block title="Package Manager Console Command" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Шаги для обновления Метаданных с помощью .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

Разработчики Aspose.PDF Cloud могут легко загрузить и обновить метаданные в PDF всего за несколько строк кода.

{{% /blocks/products/pf/agp/text %}}

1. Создайте новый объект Configuration с вашим Application Secret и Key
1. Создайте объект для подключения к облачному API
1. Загрузите свой файл документа
1. Обновите свойства с помощью PutSetProperty
1. Обработайте свойства, например, выведите на консоль

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="Этот пример кода показывает обновление Метаданных в PDF-документах" offSpacer="" %}}

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

