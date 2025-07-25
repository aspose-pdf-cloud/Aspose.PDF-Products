---
title: Add Text to PDF via Cloud .NET SDK
url: net/text/add/
description: Insert text into PDF documents with Aspose.PDF Cloud SDK for .NET. Automate content editing easily.
lastmod: 2024-11-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Add Text to PDF in .NET SDK" h2="Add a Text to a PDF Document using server-side .NET API" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-words-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="How to add Text into PDF via Cloud .NET SDK " %}}

In order to add Text into PDF via Cloud .NET SDK , we'll use
[Aspose.PDF Cloud .NET SDK](https://.products.aspose.cloud/pdf/net/)
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

{{% blocks/products/pf/agp/feature-section-col title="Steps to add Text into PDF via .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud developers can easily load & add Text to PDF in just a few lines of code.

{{% /blocks/products/pf/agp/text %}}

1. Upload the File to Cloud Storage
1. Initializes the PdfApi with the provided credentials (Application ID and Application Key).
1. Reads the local PDF file and uploads it to the Aspose Cloud storage.
1. Calls the postSplitDocument method of the PdfApi to split the uploaded PDF document.
1. Downloads each split PDF page and saves it to the local file system.

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="This sample code shows adding Text to PDF documents" offSpacer="" %}}

```cs

    public static void Add()
    {
        const string localImageFileName = @"C:\Samples\Sample-Document-01.pdf";
        const string storageFileName = "Sample-Document-01.pdf";
        const string resultFileName = "Sample-Document-01.pdf";

        // Get your AppSid and AppSecret from https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);
        if (pdfApi.GetFilesList(".").Value.All(f => f.Name != storageFileName))
        {
            using var file = File.OpenRead(localImageFileName);
            var uploadResult = pdfApi.UploadFile(storageFileName, file);
            Console.WriteLine(uploadResult.Uploaded[0]);
        }

        Paragraph paragraph = new()
        {
            Lines =
            [
                new TextLine() {
                    Segments = [
                        new Segment("Lorem ipsum",
                        new TextState() {
                            FontSize = 20,
                            Font = "Arial",
                            ForegroundColor = new Color(255, 0, 0, 255),
                            BackgroundColor = new Color(255, 255, 255, 0),
                            FontStyle = FontStyles.Regular,
                            Underline = true
                        })
                    ]

                }
            ],
            HorizontalAlignment = TextHorizontalAlignment.Justify,
            VerticalAlignment = VerticalAlignment.Center,
        };

        pdfApi.PutAddText(storageFileName, 1, paragraph);
        pdfApi.DownloadFile(storageFileName)
            .CopyTo(File.Create(resultFileName));
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Work with Text in PDF" %}}

Text can be dynamically added to customize a PDF for a specific user, such as adding their name or personalized message. This is often used in marketing materials or for personalized reports. Adding text in specific fonts, colors, and alignments can make certain sections more readable and visually appealing, creating a better user experience. Text additions can help maintain consistent information across different PDF versions, avoiding manual edits and ensuring that key information remains in place.
Add the Text into PDF documents with [Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/).

**With our .NET library you can:**

+ Combine PDF documents.
+ Split PDF Files.
+ Convert PDF to other formats, and vice versa.
+ Manipulate Annotations.
+ Work with Images in PDF, etc.
+ You can try out our [free App](https://products.aspose.app/pdf/editor) to add the text into PDF files online and test the functionality.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

