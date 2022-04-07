---
title: Split PDF Files via Cloud .NET SDK 
url: /net/split/single/
description: This topic explain you how to split single pages of a PDF file and save each page as a new PDF or any supported format using Aspose.Pdf for Cloud API in your applications. 
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Split single PDF Documents using Cloud API" h2="Split Single PDF Pages in C# Cloud API without the use of any software like Adobe PDF." logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for .NET" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-net.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://downloads.aspose.cloud/pdf/net" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="How to Split Single PDF Files Using C# Cloud API" %}}

 In order to split PDF files we'll use
 [Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
 This Cloud SDK allows you to easily build cloud-based PDF creator, editor & converter apps in C#, ASP.NET, or other .NET languages for various cloud platforms. Open
 [NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
 package manager, search for
 Aspose.PDF Cloud
 and install. You may also use the following command from the Package Manager Console.

{{% blocks/products/pf/agp/code-block title="Command" offSpacer="true" %}}

```powershell

    PM> Install-Package Aspose.Pdf-Cloud 



```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Steps for Splitting PDF Files via Cloud .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

 A basic merging pdfs programmatically with
 [Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
 APIs can be done with just few lines of code.

{{% /blocks/products/pf/agp/text %}}

1. Create a new Configuration object with your Application Secret and Key
1. Create an object to connect to the Cloud API
1. Upload your document file
1. Perform the splitting
1. Download the result

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="System Requirements" %}}

{{% blocks/products/pf/agp/text %}}

It is easy to get started with Aspose.PDF Cloud .NET SDK and there is nothing to install. Simply create an account at Aspose for Cloud and get your application information. Once you have the App SID & key, you are ready to give the Aspose.PDF Cloud .NET SDK.

+ .NET Framework 2.0 or later
+ JSON.NET

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Split Single PDF File - C#" offSpacer="" %}}

```cs
{
    var localImageFileName = @"C:\Samples\Sample-Document-01.pdf";
    var storageFileName = "Sample-Document-01.pdf";

    // Get your ClientId and ClientSecret from https://dashboard.aspose.cloud (free registration required).
    var config = new Configuration(AppSecret, AppKey);
    var pdfApi = new PdfApi(config);

    if (!pdfApi.GetFilesList("").Value.Any(f => f.Name == storageFileName))
    {
    using (var file = File.OpenRead(localImageFileName))
    {
    var uploadResult = pdfApi.UploadFile(storageFileName, file);
        Console.WriteLine(uploadResult.Uploaded[0]);
    }
    }
    var response = pdfApi.PostSplitDocument(storageFileName);
}
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}


<!-- aboutfile Starts -->

{{% blocks/products/pf/agp/content h2="About Aspose.PDF Cloud .NET SDK" %}}

A PDF Processing Library to create cross-platform applications with the ability to generate, modify, convert, render, secure and print documents without using Adobe Acrobat. .NET PDF API offers compression, table creation, graph & image functions, hyperlinks, stamp and watermarking tasks, extended security controls & custom font handling.


{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/about-file-section >}}

{{< blocks/products/pf/agp/demobox sectionTitle="Online PDF Splitter Live Demos" sectionDescription="Split PDF documents right now by visiting our [Live Demos website](https://products.aspose.app/pdf/splitter). The live demo has the following benefits" >}}
{{< blocks/products/pf/agp/democard icon="fa-cogs" text=" No need to download Aspose API." >}}
{{< blocks/products/pf/agp/democard icon="fa-edit" text=" No need to write any code." >}}
{{< blocks/products/pf/agp/democard icon="fa-file-text" text="Just upload your PDF files." >}}
{{< blocks/products/pf/agp/democard icon="fa-download" text=" It will be splitted and concatenated instantly." >}}

{{< blocks/products/pf/agp/about-file-text fileFormat="PDF" readMoreLink="https://docs.fileformat.com/view/pdf/" >}}
Portable Document Format (PDF) is a type of document created by Adobe back in 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins. Most of the commercially available software suites also offer conversion of their documents to PDF file format without the requirement of any additional software component. Thus, PDF file format has full capability to contain information like text, images, hyperlinks, form-fields, rich media, digital signatures, attachments, metadata, Geospatial features and 3D objects in it that can become as part of source document.

{{< /blocks/products/pf/agp/about-file-text >}}

{{< /blocks/products/pf/agp/about-file-section >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}