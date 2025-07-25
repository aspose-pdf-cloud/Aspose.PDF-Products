---
title: 通过云 .NET SDK 将 GIF 转换为 PDF
url: net/conversion/gif-to-pdf/
description: 使用 Aspose.PDF Cloud SDK for .NET 轻松将 GIF 动画或图像转换为 PDF。以 PDF 格式保留内容。
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="在 .NET SDK 中将 GIF 转换为 PDF" h2="使用 Aspose.PDF Cloud .NET SDK 将 GIF 文档导出为包括 PDF 在内的多种格式" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="如何使用 .NET SDK 将 GIF 转换为 PDF" %}}

为了将 GIF 转换为 PDF，我们将使用
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
此云 SDK 允许您轻松构建基于云的 PDF 创建、编辑和转换应用程序，支持 C#、ASP.NET 或其他 .NET 语言，并适用于各种云平台。打开
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
包管理器，搜索
Aspose.PDF Cloud
并安装。您也可以使用包管理器控制台中的以下命令。

{{% blocks/products/pf/agp/code-block title="包管理器控制台命令" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="通过 .NET SDK 将 GIF 转换为 PDF 的步骤" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud 开发人员可以通过几行代码轻松加载并将 GIF 文件转换为 PDF。

{{% /blocks/products/pf/agp/text %}}

1. 使用您的应用程序密钥和密钥创建一个新的配置对象
1. 创建一个对象以连接到云 API
1. 上传您的文档文件
1. 执行转换
1. 下载结果

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="此示例代码展示了 GIF 到 PDF 的云 .NET SDK 转换" offSpacer="" %}}

```cs

    public static void ConvertGifToPdf()
    {
        const string localImageFileName = @"C:\Samples\Conversion\sample.gif";
        const string storageImageFileName = "sample.gif";
        const string resultFileName = "sample-gif-to-pdf.pdf";
        
        // Get your AppSid and AppSecret https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);
        using var file = File.OpenRead(localImageFileName);
        pdfApi.UploadFile(storageImageFileName, file);

        var imageTemplatesRequest = new ImageTemplatesRequest(IsOCR: false,
            ImagesList: [new ImageTemplate(ImagePath: storageImageFileName, ImageSrcType: ImageSrcType.Common)]
        );
        
        var response = pdfApi.PutImageInStorageToPdf(resultFileName, imageTemplatesRequest);
        Console.WriteLine($"GIF to PDF result: {response.Status}");
        pdfApi.DownloadFile(resultFileName)
            .CopyTo(File.Create(resultFileName));
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="其他支持的转换" subTitle="您还可以转换许多其他文件格式" >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/bmp-to-pdf/" name="BMP TO PDF" description="位图图像" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/emf-to-pdf/" name="EMF TO PDF" description="增强型图元文件格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/epub-to-pdf/" name="EPUB TO PDF" description="电子书格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/gif-to-pdf/" name="GIF TO PDF" description="图形交换格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/html-to-pdf/" name="HTML-TO-PDF" description="超文本标记语言" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/jpeg-to-pdf/" name="JPEG TO PDF" description="JPEG 图像" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/md-to-pdf/" name="MD TO PDF" description="Markdown" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pcl-to-pdf/" name="PCL TO PDF" description="打印机命令语言" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-bmp/" name="PDF TO BMP" description="位图图像" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-docx/" name="PDF TO DOCX" description="Office 2007+ Word 文档" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-emf/" name="PDF TO EMF" description="增强型图元文件格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-epub/" name="PDF TO EPUB" description="电子书格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-gif/" name="PDF TO GIF" description="图形交换格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-html/" name="PDF TO HTML" description="超文本标记语言" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-jpeg/" name="PDF TO JPEG" description="JPEG 图像" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pdfa/" name="PDF TO PDF/A" description="便携式文档格式/A" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-png/" name="PDF TO PNG" description="便携式网络图形" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF TO PPTX" description="开放 XML 演示文稿格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-svg/" name="PDF TO SVG" description="可缩放矢量图形" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tex/" name="PDF TO TEX" description="LaTeX 输出文本" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tiff/" name="PDF TO TIFF" description="标记图像文件格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-txt/" name="PDF TO TXT" description="文本文档" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xlsx/" name="PDF TO XLSX" description="OOXML Excel 文件" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xps/" name="PDF TO XPS" description="XML 纸张规范" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF TO PPTX" description="开放 XML 演示文稿格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/png-to-pdf/" name="PNG TO PDF" description="便携式网络图形" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/svg-to-pdf/" name="SVG TO PDF" description="可缩放矢量图形" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tex-to-pdf/" name="TEX TO PDF" description="LaTeX 输出文本" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/text-to-pdf/" name="TEXT TO PDF" description="文本文档" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tiff-to-pdf/" name="TIFF TO PDF" description="标记图像文件格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/xps-to-pdf/" name="XPS TO PDF" description="XML 纸张规范" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



