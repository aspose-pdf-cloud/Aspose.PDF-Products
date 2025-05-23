---
title: Creating an AcroForm via Cloud .NET SDK
url: /net/acroforms/add/
description: Add new form fields to PDFs with Aspose.PDF Cloud for .NET. Create interactive AcroForms in seconds.
lastmod: "2022-03-19"
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Create PDF Forms in .NET SDK" h2="Add Form Fields to a PDF Document on .NET apps to create Fillable document." logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-words-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="How to create an AcroForm via Cloud .NET SDK " %}}

 In order to create an AcroForm via Cloud .NET SDK , we'll use
 [Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
 This Cloud SDK allows you to easily build cloud-based PDF creator, editor & converter apps in C#, ASP.NET, or other .NET languages for various cloud platforms. Open
 [NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
 package manager, search for
 Aspose.PDF Cloud
 and install. You may also use the following command from the Package Manager Console.

{{% blocks/products/pf/agp/code-block title="Package Manager Console Command" offSpacer="true" %}}

```powershell

    PM> Install-Package Aspose.Pdf-Cloud
     
```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Steps to create AcroForms via .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

 Aspose.PDF Cloud developers can easily load & create acroforms in PDF in just a few lines of code.

{{% /blocks/products/pf/agp/text %}}

1. Create a new Configuration object with your Application Secret and Key
1. Create an object to connect to the Cloud API
1. Upload your document file
1. Perform the creating
1. Download the result

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="This sample code shows creating an AcroForms in PDF documents" offSpacer="" %}}

```cs

    public static void AddFormField()
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
        var textBoxField = new TextBoxField(PageIndex: 1)
        {
            PartialName = "Email",
            Rect = new Rectangle(100, 100, 180, 120),
            Value = "aspose-pdf-cloud@example.com",
            Border = new Border(Width: 5, Dash: new Dash(1, 1))
        };

        var response = pdfApi.PutTextBoxField(storageFileName, "Email", textBoxField);
        Console.WriteLine(response.Status);
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
