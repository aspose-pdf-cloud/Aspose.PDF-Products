---
title: Convert PDF to PDF/A via Cloud .NET SDK
url: /net/conversion/pdf-to-pdfa/ 
description: Sample code for PDF to PDF/A C# conversion. Use API example code for batch PDF files to PDF/A conversion within VB.NET, Asp.NET or any .NET based application.
lastmod: "2022-03-17"
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Convert PDF to PDF/A via Cloud .NET SDK" h2="Export PDF documents to multiple formats including PDF/A with Aspose.PDF Cloud .NET SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-net.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://downloads.aspose.cloud/pdf/net" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://apireference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="How to Convert PDF to PDF/A Using SDK for .NET" %}}

 In order to convert PDF to PDF/A, we’ll use
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

{{% blocks/products/pf/agp/feature-section-col title="Steps to Convert PDF to PDF/A  via Cloud .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

 Aspose.PDF Cloud developers can easily load & convert PDF to PDF/A files in just a few lines of code.

{{% /blocks/products/pf/agp/text %}}

1. Create a new Configuration object with your Application Secret and Application Key
1. Create an object to connect to the Cloud API
1. Upload your document file
1. Perform the conversion
1. Download the result

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="System Requirements" %}}

{{% blocks/products/pf/agp/text %}}

It is easy to get started with Aspose.PDF Cloud .NET SDK and there is nothing to install. Simply create an account at Aspose for Cloud and get your application information. Once you have the App SID & key, you are ready to give the Aspose.PDF Cloud .NET SDK.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="This sample code shows PDF to PDF/A Cloud .NET SDK Conversion" offSpacer="" %}}

```cs
public static void ConvertPDFtoPDFa()
{
    var localImageFileName = @"C:\Samples\sample.pdf";
    var storageImageFileName = "sample.pdf";

    // Get your ClientId and ClientSecret from https://dashboard.aspose.cloud (free registration required).
    var config = new Configuration(AppSecret, AppKey);
    var pdfApi = new PdfApi(config);

    using (var file = File.OpenRead(localImageFileName))
    {
        var uploadResult = pdfApi.UploadFile(storageImageFileName, file);
    }

    var response = pdfApi.GetPdfInStorageToPdfA(storageImageFileName,
        type: Aspose.Pdf.Cloud.Sdk.Model.PdfAType.PDFA1A.ToString());
    response.CopyTo(System.IO.File.OpenWrite("sample-pdfa1.pdf"));
    Console.WriteLine($"PDF to PDFA result: {response.Length} bytes");
}
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

<!-- aboutfile Starts -->

{{< blocks/products/pf/agp/demobox sectionTitle="Free App to Convert PDF/A to PDF" sectionDescription="Check our live demos for [PDF/A to PDF conversion](https://products.aspose.app/pdf/conversion/pdf-to-pdfa1a) with following benefits." >}}
{{< blocks/products/pf/agp/democard icon="fa-cogs" text=" No need to download or setup anything." >}}
{{< blocks/products/pf/agp/democard icon="fa-edit" text=" No need to write any code." >}}
{{< blocks/products/pf/agp/democard icon="fa-file-text" text=" Just upload your PDF/A file and hit the \"Convert\" button." >}}
{{< blocks/products/pf/agp/democard icon="fa-download" text=" You will instantly get the download link for resultant PDF file." >}}

{{% blocks/products/pf/agp/content h2="" %}}

A PDF Processing Library to create cross-platform applications with the ability to generate, modify, convert, render, secure and print documents without using Adobe Acrobat. .NET PDF API offers compression, table creation, graph & image functions, hyperlinks, stamp and watermarking tasks, extended security controls & custom font handling.

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/about-file-section >}}

{{< blocks/products/pf/agp/about-file-text fileFormat="PDF/A" readMoreLink="https://docs.fileformat.com/pdf/" >}}
Portable Document Format (PDF) is a type of document created by Adobe back in 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins. Most of the commercially available software suites also offer conversion of their documents to PDF file format without the requirement of any additional software component. Thus, PDF file format has full capability to contain information like text, images, hyperlinks, form-fields, rich media, digital signatures, attachments, metadata, Geospatial features and 3D objects in it that can become as part of source document.


{{< /blocks/products/pf/agp/about-file-text >}}

{{< blocks/products/pf/agp/about-file-text fileFormat="pdfa" readMoreLink="https://docs.fileformat.com/pdf/a/" >}}
PDF/A is an ISO standard format for archiving of electronic documents in PDF format. Its primary reason for coming into being was to meet the requirements of long term archiving. The standard ensures the opening of archived files even after long time by imposing certain limitations on document integral parts to achieve conformance. The format is now widely adopted across all industries . PDFA/A viewers like Adobe Acrobat Reader, ensure that files saved with this format can be opened even in future in accordance with the information shared by this Standard.

{{< /blocks/products/pf/agp/about-file-text >}}

{{< /blocks/products/pf/agp/about-file-section >}}

{{< /blocks/products/pf/agp/demobox >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}