---
title: Convert PDF to TXT via Cloud .NET SDK
url: /net/conversion/pdf-to-txt/
description: Sample code for PDF to TXT C# conversion. Use API example code for batch PDF files to TXT images conversion within VB.NET, Asp.NET or any .NET based application.
lastmod: "2022-03-17"
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Convert PDF to TXT via Cloud .NET SDK" h2="Export PDF documents to multiple formats including TXT with Aspose.PDF Cloud .NET SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://www.aspose.cloud/templates/aspose/img/products/pdf/aspose_pdf-for-net.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://downloads.aspose.cloud/pdf/net" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="https://apireference.aspose.cloud/pdf/" mavenRepoLink="" >}}

{{% blocks/products/pf/agp/content h2="How to Convert PDF to TXT Using SDK for .NET" %}}

 In order to convert PDF to TXT, we’ll use
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

{{% blocks/products/pf/agp/feature-section-col title="Steps to Convert PDF to TXT  via Cloud .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

 Aspose.PDF Cloud developers can easily load & convert PDF to TXT files in just a few lines of code.

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

{{% blocks/products/pf/agp/code-block title="This sample code shows PDF to TXT Cloud .NET SDK Conversion" offSpacer="" %}}

```cs
public static void ConvertPDFtoText()
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
    var response = pdfApi.GetText(storageImageFileName,0,0,0,0);
    foreach (var item in response.TextOccurrences.List)
    {
        Console.WriteLine(item.Text);
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

    {{< blocks/products/pf/agp/faq-item question="" answer="" >}}


<!-- aboutfile Starts -->

{{< blocks/products/pf/agp/demobox sectionTitle="Free App to Convert PDF to TXT" sectionDescription="Check our live demos for [PDF to TXT conversion](https://products.aspose.app/pdf/conversion/pdf-to-txt) with following benefits." >}}
        {{< blocks/products/pf/agp/democard icon="fa-cogs" text=" No need to download or setup anything." >}}
        {{< blocks/products/pf/agp/democard icon="fa-edit" text=" No need to write any code." >}}
        {{< blocks/products/pf/agp/democard icon="fa-file-text" text=" Just upload your PDF file and hit the \"Convert\" button." >}}
        {{< blocks/products/pf/agp/democard icon="fa-download" text=" You will instantly get the download link for resultant TXT file." >}}

    {{% blocks/products/pf/agp/content h2="" %}}

 A PDF Processing Library to create cross-platform applications with the ability to generate, modify, convert, render, secure and print documents without using Adobe Acrobat. .NET PDF API offers compression, table creation, graph & image functions, hyperlinks, stamp and watermarking tasks, extended security controls & custom font handling.



    {{% /blocks/products/pf/agp/content %}}

    {{< blocks/products/pf/agp/about-file-section >}}

        {{< blocks/products/pf/agp/about-file-text fileFormat="PDF" readMoreLink="https://docs.fileformat.com/view/pdf/" >}}
Portable Document Format (PDF) is a type of document created by Adobe back in 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins. Most of the commercially available software suites also offer conversion of their documents to PDF file format without the requirement of any additional software component. Thus, PDF file format has full capability to contain information like text, images, hyperlinks, form-fields, rich media, digital signatures, attachments, metadata, Geospatial features and 3D objects in it that can become as part of source document.

        {{< /blocks/products/pf/agp/about-file-text >}}

        {{< blocks/products/pf/agp/about-file-text fileFormat="txt" readMoreLink="https://docs.fileformat.com/word-processing/txt/" >}}
A file with .TXT extension represents a text document that contains plain text in the form of lines. Paragraphs in a text document are recognized by carriage returns and are used for better arrangement of file contents. A standard text document can be opened in any text editor or word processing application on different operating systems. All the text contained in such a file is in human-readable format and represented by sequence of characters.

        {{< /blocks/products/pf/agp/about-file-text >}}

    {{< /blocks/products/pf/agp/about-file-section >}}

{{< /blocks/products/pf/agp/demobox >}}

<!-- aboutfile Ends -->

{{< blocks/products/pf/agp/other-supported-section title="Other Supported Conversions" subTitle="You can also convert PDF into many other file formats including few listed below." >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-word/" name="PDF TO WORD" description="{{word_name}}" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-excel/" name="PDF TO EXCEL" description="{{excel_name}}" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-bmp/" name="PDF TO BMP" description="Bitmap Image" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-doc/" name="PDF TO DOC" description="Microsoft Word Binary Format" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-docx/" name="PDF TO DOCX" description="Office 2007+ Words Document" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-emf/" name="PDF TO EMF" description="Enhanced Metafile Format" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-epub/" name="PDF TO EPUB" description="E-book Format" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-gif/" name="PDF TO GIF" description="Graphical Interchange Format" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-html/" name="PDF TO HTML" description="Hyper Text Markup Language" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-jpeg/" name="PDF TO JPEG" description="JPEG Image" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-png/" name="PDF TO PNG" description="Portable Network Graphics" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-pptx/" name="PDF TO PPTX" description="Open XML presentation Format" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-svg/" name="PDF TO SVG" description="Scalable Vector Graphics" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-tex/" name="PDF TO TEX" description="LaTeX Output Text" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-tiff/" name="PDF TO TIFF" description="Tagged Image Format" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-xls/" name="PDF TO XLS" description="Excel Binary Format" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-xlsx/" name="PDF TO XLSX" description="OOXML Excel File" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-xml/" name="PDF TO XML" description="Extensible Markup Language" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.com/pdf/net/conversion/pdf-to-xps/" name="PDF TO XPS" description="XML Paper Specifications" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
