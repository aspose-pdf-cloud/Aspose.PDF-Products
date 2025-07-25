---
title: 通过云 Node.js SDK 从 PDF 提取图像
url: nodejs/images/extract/
description: 使用 Aspose.PDF Cloud SDK 在 Node.js 中从 PDF 提取所有图像。处理或分析嵌入的视觉内容。
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="在 Node.js SDK 中从 PDF 提取图像" h2="使用云 Node.js SDK 从 PDF 文档中提取图像。" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="如何通过 Node.js SDK 从 PDF 提取图像" %}}

要从 PDF 提取图像，我们将使用
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)。此云 SDK 帮助 Node.js 程序员开发基于云的 PDF 创建器、注释器、编辑器和转换器应用程序，通过 Aspose.PDF REST API 使用 Node.js 编程语言。只需在 [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) 创建一个帐户并获取您的应用程序信息。一旦您拥有 App SID 和密钥，您就可以开始使用 Aspose.PDF Cloud Node.js SDK。

{{% blocks/products/pf/agp/code-block title="包管理器控制台命令" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="使用 Node.js 从 PDF 获取图像的步骤" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud 开发人员可以轻松加载和提取 PDF 中的图像，仅需几行代码。

{{% /blocks/products/pf/agp/text %}}

1. 从 JSON 文件加载您的应用程序秘钥，或以其他方式设置凭据
1. 从上传的 PDF 文件中检索第一张图像。
1. 提取图像并将其保存为本地 PNG 文件。
1. 如有需要，请下载结果

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="使用 Node.js 从 PDF 提取图像" offSpacer="" %}}

```js

    import credentials from "./credentials.json"  with { type: "json" };
    import fs from 'node:fs/promises';
    import { PdfApi } from "asposepdfcloud";

    async function extract() {
        const localPdfFile = "C:\\Samples\\Sample.pdf";
        const storagePdfFile = "Sample.pdf";
        const localImageFile = "C:\\Samples\\Sample.png";

        const pdfApi = new PdfApi(credentials.id, credentials.key);
        try {
            let fileData = await fs.readFile(localPdfFile);
            let uploadResult = await pdfApi.uploadFile(storagePdfFile, fileData);
            console.log(uploadResult.response.text);
        }
        catch (error) {
            console.error(error.message);
        }

        try {
            const imagesResult = await pdfApi.getImages(storagePdfFile, 1, null, null);
            const imageId = imagesResult.body.images.list[0].id;
            const response = await pdfApi.getImageExtractAsPng(storagePdfFile, imageId);
            await fs.writeFile(localImageFile, response.body);
        } catch (error) {
            console.error(error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="在 PDF 中处理图像" %}}

提取的图像可在其他文档、演示文稿或营销材料中重复使用，避免重新创建，节省时间和资源。一旦提取，图像可以被编辑或增强，以提高其质量或适应特定用途，例如调整大小或重新上色。从 PDF 中提取的图像可以单独存储以用于档案目的，确保视觉内容的轻松访问和组织。通过从 PDF 中提取图像，用户可以更好地管理、编辑和利用视觉内容，适用于从专业演示到创意项目的广泛应用。
通过 [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/) 从 PDF 文档中提取图像。

**通过我们的 Node.js 库，您可以：**

+ 以文本或图像格式添加 PDF 文档的页眉和页脚。
+ 向 PDF 文档添加表格和印章（文本或图像）。
+ 将多个 PDF 文档附加到现有文件。
+ 处理 PDF 附件、注释和表单字段。
+ 对 PDF 文档应用加密或解密并设置密码。
+ 从页面或整个 PDF 文档中删除所有印章和表格。
+ 根据其 ID 从 PDF 文档中删除特定的印章或表格。
+ 替换 PDF 页面或整个文档上的单个或多个文本实例。
+ 广泛支持将 PDF 文档转换为各种其他文件格式。
+ 提取 PDF 文件的各种元素并优化 PDF 文档。
+ 您可以尝试我们的[免费应用](https://products.aspose.app/pdf/crop)在线更改 PDF 文件中的图像尺寸并测试功能。

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="学习资源" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="文档" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="源代码" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="API 参考" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="产品支持" tabId="support" >}}
{{< blocks/products/pf/slr-element name="免费支持" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="付费支持" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="博客" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="为什么选择 Aspose.PDF Cloud for Node.js?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="客户列表" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="安全性" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



