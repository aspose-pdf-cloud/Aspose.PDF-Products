---
title: PDF File Conversion via Cloud .NET SDK
url: /net/conversion/
description: Convert PDF to Microsoft Word, Excel, PowerPoint Slides, HTML, Images and many other popular formats with just few lines of C# code.
lastmod: "2022-03-17"
---

{{< blocks/products/pf/feature-page-wrap >}}
{{< blocks/products/pf/feature-page-header h1="PDF Document Conversion Cloud .NET SDK" h2="Export PDF to Microsoft Office® Word, Excel, PowerPoint Presentations, Images, HTML and fixed-layout formats" >}}

{{% blocks/products/pf/feature-page-summary %}}
Aspose.PDF Cloud .NET SDK offers your cloud-based C# program to convert PDF to XLS, XLSX, PPTX, DOC, DOCX, MobiXML, JPEG, EMF, PNG, TIFF, GIF, SVG, XML, XPS, FDF, XFDF, EPUB and other formats. It also supports Tex, MHT, PCL, PS, XSL-FO, and Markdown (MD) file formats.
{{% /blocks/products/pf/feature-page-summary  %}}

{{% blocks/products/pf/feature-page-section  h2="Convert PDF to DOCX and More Formats" %}}

First you should create a new Configuration object with your personal Application Secret and Application Key. Next,
create an object to connect to the Cloud API. After, you can upload your document file. The next step is to convert the documents directly. Download and save the result.
{{% blocks/products/pf/feature-page-code h3="Cloud .NET SDK Code for PDF to DOCX Conversion" %}}

```cs
public static void ConvertPDFtoDOCX()
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

    var response = pdfApi.GetPdfInStorageToDoc(storageImageFileName, format: "DocX", mode: "Flow");
    response.CopyTo(System.IO.File.OpenWrite("sample.docx"));
    Console.WriteLine($"PDF to DOCX result: {response.Length} bytes");
}
```

{{% /blocks/products/pf/feature-page-code  %}}
{{% /blocks/products/pf/feature-page-section %}}

{{% blocks/products/pf/feature-page-section  h2="Convert PDF to JPEG via Cloud .NET SDK" %}}

Converting PDF to JPEG is very relevant today and has many advantages. Using JPEG files instead of PDF files can reduce the size of the desktop application, reduce the size of downloaded images, and provide a better and faster end user experience. Also, if you want to share documents on social networks, it would be much easier to do so with editable JPEG images.

{{% blocks/products/pf/feature-page-code h3="Save PDF as Jpeg File" %}}

```cs
public static void ConvertPDFtoJPEG()
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

    var response = pdfApi.GetPageConvertToJpeg(storageImageFileName, 1);
    response.CopyTo(System.IO.File.OpenWrite("sample.jpeg"));
    Console.WriteLine($"PDF to JPEG result: {response.Length} bytes");
}
```

{{% /blocks/products/pf/feature-page-code  %}}
{{% /blocks/products/pf/feature-page-section %}}


{{% blocks/products/pf/feature-page-section  h2="Convert PDF to PowerPoint Presentations" %}}
Aspose.PDF Cloud supports converting PDF pages to PowerPoint Presentation Slides with selectable text or images by rendering slides as images. First create a new Configuration object with your Application Secret and Application Key. Next create an object to connect to the Cloud API. Upload your document file and perform the conversion.
{{% blocks/products/pf/feature-page-code h3="PDF to PowerPoint Conversion C# Code" %}}

```cs
public static void ConvertPDFtoPPTX()
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

    var response = pdfApi.GetPdfInStorageToPptx(storageImageFileName);
    response.CopyTo(System.IO.File.OpenWrite("sample.pptx"));
    Console.WriteLine($"PDF to PPTX result: {response.Length} bytes");
}
```

{{% /blocks/products/pf/feature-page-code %}}
{{% /blocks/products/pf/feature-page-section %}}

{{< blocks/products/pf/feature-page-options pairs="pdf-to-pptx" >}}

{{% blocks/products/pf/feature-page-section  h2="Portable Document Format PDF to HTML Conversion" %}}
You can  convert pdf to html by using Aspose.PDF Cloud REST API. The SDKs are available in various languages such as, C#, Java, Python, Ruby, PHP, Node.js, Swift, Android and Go. This API enables you to convert PDF document to HTML format. The API returns output file in a zip format which you can later unzip to get the HTML file.
{{% blocks/products/pf/feature-page-code h3="C# Code for PDF to HTML Conversion" %}}

```cs
public static void ConvertPDFtoHTML()
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

    var response = pdfApi.GetPdfInStorageToHtml(storageImageFileName);
    response.CopyTo(System.IO.File.OpenWrite("sample-html.zip"));
    Console.WriteLine($"PDF to HTML result: {response.Length} bytes");
}
```

{{% /blocks/products/pf/feature-page-code %}}
{{% /blocks/products/pf/feature-page-section %}}

{{< blocks/products/pf/feature-page-options pairs="pdf-to-html" >}}

{{% blocks/products/pf/feature-page-section  h2="Convert PDF to XLSX" %}}
Aspose.PDF Cloud .NET SDK  have introduced a feature that renders PDF file to Excel workbook (XLSX files). During this conversion, the individual pages of the PDF file are converted to Excel worksheets.
{{% blocks/products/pf/feature-page-code h3="Convert PDF Pages to XLSX C# Code" %}}

```cs
public static void ConvertPDFtoXLSX()
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
    var response = pdfApi.GetPdfInStorageToXlsx(storageImageFileName);
    response.CopyTo(System.IO.File.OpenWrite("sample.xlsx"));
    Console.WriteLine($"PDF to Excel result: {response.Length} bytes");
}
```

{{% /blocks/products/pf/feature-page-code %}}
{{% /blocks/products/pf/feature-page-section %}}

{{< blocks/products/pf/feature-page-options pairs="pdf-to-bmp pdf-to-tiff pdf-to-png pdf-to-gif pdf-to-bmp" >}}

{{% blocks/products/pf/feature-page-section  h2="PDF API Other Supported Conversions" %}}
C# PDF API loads other multiple [formats](https://docs.aspose.cloud/pdf/supported-document-formats/) for manipulation and conversion. API loads the relevant supported format and save into the required format.
{{% /blocks/products/pf/feature-page-section %}}

{{< blocks/products/pf/feature-page-options pairs="pdf-to-pptx epub-to-pdf html-to-pdf pdf-to-docx md-to-pdf pcl-to-pdf svg-to-pdf tex-to-pdf ps-to-pdf" >}}


