---
title: 通过云端 Node.js SDK 将 PNG 转换为 PDF
url: nodejs/conversion/png-to-pdf/
description: 使用 Node.js 和 Aspose.PDF Cloud 将 PNG 图像转换为 PDF。快速、高质量的图像转换。
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="在 Node.js SDK 中将 PNG 转换为 PDF" h2="使用 Aspose.PDF Cloud Node.js SDK 导出 PNG 文档至包括 PDF 在内的多种格式" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="如何使用 Node.js SDK 转换 PNG 为 PDF" %}}

要将 PNG 转换为 PDF，我们将使用
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)
此 Cloud SDK SDK 帮助 Node.js 程序员使用 Node.js 编程语言通过 Aspose.PDF REST API 开发云端 PDF 创建、注释、编辑和转换应用程序。打开
[NPM](https://www.npmjs.com/package/asposepdfcloud)
包管理器，搜索
Aspose.PDF Cloud，
并安装。您还可以使用 Package Manager Console 中的以下命令。

{{% blocks/products/pf/agp/code-block title="Package Manager Console 命令" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="通过 Node.js 转换 PNG 为 PDF 的步骤" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud Node.js 开发人员可以轻松地在几行代码中加载并转换 PNG 文件为 PDF。

{{% /blocks/products/pf/agp/text %}}

1. 从 JSON 文件加载您的应用程序密钥和密钥，或以其他方式设置凭据
1. 创建一个对象以连接到云 API
1. 上传您的文档文件
1. 使用 putImageInStorageToPdf 进行转换
1. 如有需要，下载结果

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="此示例代码展示 PNG 转 PDF 云 Node.js SDK 转换" offSpacer="" %}}

```js

    const fs = require("fs");
    const credentials = require("./credentials.json");
    const { PdfApi } = require("asposepdfcloud");
    const { ImageTemplatesRequest } = require("asposepdfcloud/src/models/imageTemplatesRequest");
    const { ImageTemplate } = require("asposepdfcloud/src/models/imageTemplate");
    const { ImageSrcType } = require("asposepdfcloud/src/models/imageSrcType");

    // Load your Application Secret and Key from the JSON file or set credentials in another way
    async function convertPNGtoPDF() {
        const localImageFileName = "C:\\Samples\\sample.png";
        const storageImageFileName = "sample.png";
        const pdfApi = new PdfApi(credentials.id, credentials.key);
        let fileData = await fs.readFile(localImageFileName);
        try {
            let uploadResult = await pdfApi.uploadFile(storageImageFileName, fileData);
            console.log(uploadResult.response.text);
        }
        catch (error) {
            console.error(error.response.text);
        }
        let imageTemplateList = [];
        let imageTemplate = new ImageTemplate();
        imageTemplate.imagePath = storageImageFileName;
        imageTemplate.imageSrcType = ImageSrcType.Common;
        imageTemplateList.push(imageTemplate);

        let imageTemplatesRequest = new ImageTemplatesRequest()
        imageTemplatesRequest.IsOCR = false;
        imageTemplatesRequest.imagesList = imageTemplateList;

        try {
            let convertResult = await pdfApi.putImageInStorageToPdf("sample-png-to-pdf.pdf", imageTemplatesRequest);
            console.log(convertResult.response.text);
            const buffer = await pdfApi.downloadFile(STORAGE_FILENAME);
        } catch (error) {
            console.error(error.response.text);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="其他支持的转换" subTitle="您还可以将 MD 转换为其他许多文件格式，包括以下几种。" >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/bmp-to-pdf/" name="BMP TO PDF" description="位图图像" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/cgm-to-pdf/" name="CGM TO PDF" description="微软 Word 二进制格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/emf-to-pdf/" name="EMF TO PDF" description="Office 2007+ Words 文档" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/epub-to-pdf/" name="EPUB TO PDF" description="增强型图元文件格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/gif-to-pdf/" name="GIF TO PDF" description="图形交换格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/html-to-pdf/" name="HTML TO PDF" description="超文本标记语言" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/jpeg-to-pdf/" name="JPEG TO PDF" description="联合图像专家组" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/latex-to-pdf/" name="LATEX TO PDF" description="LaTeX 输出文本" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pcl-to-pdf/" name="PCL TO PDF" description="打印机命令语言" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/md-to-pdf/" name="MD TO PDF" description="Markdown" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-bmp/" name="PDF TO BMP" description="位图图像" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-epub/" name="PDF TO EPUB" description="电子书格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-gif/" name="PDF TO GIF" description="图形交换格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-html/" name="PDF TO HTML" description="超文本标记语言" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-jpeg/" name="PDF TO JPEG" description="联合图像专家组" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-pdfa/" name="PDF TO PDF/A" description="便携式文档格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-png/" name="PDF TO PNG" description="便携式网络图形" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-pptx/" name="PDF TO PPTX" description="微软幻灯片" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-svg/" name="PDF TO SVG" description="可缩放矢量图形" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-tex/" name="PDF TO TEX" description="计算机图形系统" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-tiff/" name="PDF TO TIFF" description="标记图像文件格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-word/" name="PDF TO WORD" description="微软Word二进制格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-xlsx/" name="PDF TO XLSX" description="微软Excel开放XML格式电子表格文件" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-xps/" name="PDF TO XPS" description="XML纸张规范" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/png-to-pdf/" name="PNG TO PDF" description="便携式网络图形" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/ps-to-pdf/" name="PS TO PDF" description="PostScript" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/svg-to-pdf/" name="SVG TO PDF" description="可缩放矢量图形" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/text-to-pdf/" name="TEXT TO PDF" description="文本文件" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/tiff-to-pdf/" name="TIFF TO PDF" description="标记图像文件格式" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/xps-to-pdf/" name="XPS TO PDF" description="XML纸张规范" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

