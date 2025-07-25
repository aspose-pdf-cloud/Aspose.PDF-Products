---
title: 通过 Cloud .NET SDK 将 XPS 转换为 PDF
url: net/conversion/xps-to-pdf/
description: 使用 Aspose.PDF Cloud SDK for .NET 将 XPS 文档转换为 PDF。简化跨平台兼容性。
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="在 .NET SDK 中将 XPS 转换为 PDF" h2="使用 Aspose.PDF Cloud .NET SDK 将 XPS 文档导出为包括 PDF 在内的多种格式" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for .NET" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-dotnet" >}}

{{% blocks/products/pf/agp/content h2="如何使用 SDK for .NET 将 XPS 转换为 PDF" %}}

为了将 XPS 转换为 PDF，我们将使用
[Aspose.PDF Cloud .NET SDK](https://products.aspose.cloud/pdf/net/)
此云 SDK 允许您轻松地在 C#、ASP.NET 或其他 .NET 语言中为各种云平台构建云 PDF 创建、编辑和转换应用程序。打开
[NuGet](https://www.nuget.org/packages/Aspose.Pdf-Cloud)
包管理器，搜索
Aspose.PDF Cloud
并安装。您还可以使用包管理器控制台中的以下命令。

{{% blocks/products/pf/agp/code-block title="包管理器控制台命令" offSpacer="true" %}}

```powershell

     
    PM> Install-Package Aspose.Pdf-Cloud
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="XPS 转换为 PDF 的步骤 - Cloud .NET SDK" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud 开发人员可以轻松地在几行代码中加载并将 XPS 文件转换为 PDF。

{{% /blocks/products/pf/agp/text %}}

1. 使用您的应用程序密钥和密码创建一个新的 Configuration 对象
1. 创建一个对象以连接到云 API
1. 上传您的文档文件
1. 执行转换
1. 下载结果

{{% /blocks/products/pf/agp/feature-section-col %}}



{{% blocks/products/pf/agp/code-block title="此示例代码显示 XPS 到 PDF 的 Cloud .NET SDK 转换" offSpacer="" %}}

```cs

    public static void ConvertXpsToPdf()
    {
        const string localXpsFileName = @"C:\Samples\Conversion\sample.oxps";
        const string storageXpsFileName = "sample.oxps";
        const string resultFileName = "sample-xps-to-pdf.pdf";

        // Get your AppSid and AppSecret https://dashboard.aspose.cloud (free registration required).
        var pdfApi = new PdfApi(AppSecret, AppSid);
        using var file = File.OpenRead(localXpsFileName);
        pdfApi.UploadFile(storageXpsFileName, file);
        
        var response = pdfApi.PutXpsInStorageToPdf(resultFileName, storageXpsFileName);
        Console.WriteLine($"XPS to PDF result: {response.Status}");
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
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pcl-to-pdf/" name="PCL TO PDF" description="打印机控制语言" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-bmp/" name="PDF TO BMP" description="位图图像" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-docx/" name="PDF TO DOCX" description="Office 2007+ Word 文档" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-emf/" name="PDF TO EMF" description="增强型图元文件格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-epub/" name="PDF TO EPUB" description="电子书格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-gif/" name="PDF TO GIF" description="图形交换格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-html/" name="PDF 转 HTML" description="超文本标记语言" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-jpeg/" name="PDF 转 JPEG" description="JPEG 图像" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pdfa/" name="PDF 转 PDF/A" description="便携式文档格式/A" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-png/" name="PDF 转 PNG" description="便携式网络图形" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF 转 PPTX" description="开放 XML 演示格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-svg/" name="PDF 转 SVG" description="可缩放矢量图形" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tex/" name="PDF 转 TEX" description="LaTeX 输出文本" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-tiff/" name="PDF 转 TIFF" description="标记图像文件格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-txt/" name="PDF 转 TXT" description="文本文档" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xlsx/" name="PDF 转 XLSX" description="OOXML Excel 文件" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-xps/" name="PDF 转 XPS" description="XML 纸张规范" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/pdf-to-pptx/" name="PDF 转 PPTX" description="开放 XML 演示格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/png-to-pdf/" name="PNG 转 PDF" description="便携式网络图形" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/svg-to-pdf/" name="SVG 转 PDF" description="可缩放矢量图形" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tex-to-pdf/" name="TEX 转 PDF" description="LaTeX 输出文本" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/text-to-pdf/" name="TEXT 转 PDF" description="文本文档" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/tiff-to-pdf/" name="TIFF 转 PDF" description="标记图像文件格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/net/conversion/xps-to-pdf/" name="XPS 转 PDF" description="XML 纸张规范" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}


