---
title: Update Metadata in PDF Document via Cloud .NET SDK 
url: /net/metadata/update/
description: This topic shows you how to update all of the metadata from the PDF document using Aspose.PDF Cloud API in your applications.
lastmod: "2022-03-19"
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Update Metadata in PDF document via Cloud .NET SDK" h2="Build your own Cloud apps to update Fillable document files using server-side APIs." logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-words-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="How to Update Metadata from PDF Document using Cloud .NET SDK" %}}

 In order to update a Metadata via Cloud .NET SDK , we'll use
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

{{% blocks/products/pf/agp/feature-section-col title="Steps to update Metadata via .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

 Aspose.PDF Cloud developers can easily load & update metadata in PDF in just a few lines of code.

{{% /blocks/products/pf/agp/text %}}

1. Create a new Configuration object with your Application Secret and Key
1. Create an object to connect to the Cloud API
1. Upload your document file
1. Update properties using PutSetProperty
1. Handle properties, for example, print to console

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="System Requirements" %}}

{{% blocks/products/pf/agp/text %}}

It is easy to get started with Aspose.PDF Cloud .NET SDK and there is nothing to install. Simply create an account at Aspose for Cloud and get your application information. Once you have the App SID & key, you are ready to give the Aspose.PDF Cloud .NET SDK.

* .NET Framework 2.0 or later
* JSON.NET

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="This sample code shows updating the Metadata in PDF documents" offSpacer="" %}}

```cs
 public static void UpdateMetadata()
{
    var localImageFileName = @"C:\Samples\sample.pdf";
    var storageFileName = "sample.pdf";


    // Get your ClientId and ClientSecret from https://dashboard.aspose.cloud (free registration required).
    var config = new Configuration(AppSecret, AppKey);
    var pdfApi = new PdfApi(config);

    using (var file = File.OpenRead(localImageFileName))
    {
        var uploadResult = pdfApi.UploadFile(storageFileName, file);
        Console.WriteLine(uploadResult.Uploaded[0]);
    }
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

<!-- aboutfile Starts -->

{{% blocks/products/pf/agp/content h2="About Aspose.PDF Cloud .NET SDK" %}}

A PDF Processing Library to create cross-platform applications with the ability to generate, modify, convert, render, secure and print documents without using Adobe Acrobat. .NET PDF API offers compression, table creation, graph & image functions, hyperlinks, stamp and watermarking tasks, extended security controls & custom font handling.

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/about-file-section >}}

{{< blocks/products/pf/agp/demobox sectionTitle="Edit PDF Metadata online App" sectionDescription="View and Edit PDF metadata information now by visiting our [Live Demos website](https://products.aspose.app/pdf/metadata). The live demo has the following benefits" >}}

{{< blocks/products/pf/agp/democard icon="fa-cogs" text=" No need to download or setup anything" >}}
{{< blocks/products/pf/agp/democard icon="fa-edit" text=" No need to write any code" >}}
{{< blocks/products/pf/agp/democard icon="fa-file-text" text="Click Convert button. Your PDF files will be uploaded and will be converted to format." >}}
{{< blocks/products/pf/agp/democard icon="fa-download" text=" Instantly get the download link for the resultant file" >}}

{{< blocks/products/pf/agp/about-file-text fileFormat="PDF" readMoreLink="https://docs.fileformat.com/view/pdf/" >}}
Portable Document Format (PDF) is a type of document created by Adobe back in 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins. Most of the commercially available software suites also offer conversion of their documents to PDF file format without the requirement of any additional software component. Thus, PDF file format has full capability to contain information like text, images, hyperlinks, form-fields, rich media, digital signatures, attachments, metadata, Geospatial features and 3D objects in it that can become as part of source document.

{{< /blocks/products/pf/agp/about-file-text >}}

{{< /blocks/products/pf/agp/about-file-section >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}