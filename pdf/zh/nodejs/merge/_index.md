---
title: 合并多个 PDF 文档 | Node.js
description: 使用 Node.js 和 Aspose.PDF Cloud SDK 将多个 PDF 合并为一个。
weight: 40
url: nodejs/merge
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="在 Node.js SDK 中合并 PDF" h2="在 Node.js 云 API 中合并多个 PDF 文件，无需使用 Adobe PDF 等软件。" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="如何使用 Node.js SDK 合并多个 PDF 文件" %}}

如今，管理和组织文档对于企业和个人来说至关重要。将多个 PDF 文件合并为一个文档可以简化共享、存档和打印。无论您需要合并多个报告、发票还是合同，合并 PDF 都提供了一种干净、组织良好的解决方案。使用 Aspose Cloud Node.js 库，您可以轻松利用云计算的强大功能以编程方式合并多个 PDF 文档。本指南将引导您通过 Node.js 中的 Aspose 云 API 合并 PDF 文件。

**为什么我需要合并多个 PDF 文档？**

将多个相关文档合并为一个文件以便于管理。将发票、收据或报告合并为一个文件以简化共享。通过将其合并为一个紧凑的文档来减少存储中的文件数量。通过自动化合并多个文件的过程来节省时间。

**使用 Node.js 合并 PDF**

PDF Cloud Node.js SDK 提供了一个易于使用且安全的 API，可以快速准确地合并 PDF 文件，即使在处理复杂格式时也是如此。您无需手动合并文件，只需通过 Node.js SDK 的一个方法调用即可在几秒钟内合并它们。无需安装其他软件——文档合并在云中进行，将过程从本地系统卸载并节省资源。

{{% blocks/products/pf/agp/code-block title="包管理器控制台命令" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="通过 Cloud Node.js 合并 PDF 的步骤" %}}

{{% blocks/products/pf/agp/text %}}

一个基本的以编程方式合并 PDF
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)
API 可以用几行代码完成。

{{% /blocks/products/pf/agp/text %}}

1. 导入必要的类。
1. 从本地文件系统读取 PDF 文件。
1. 将 PDF 文件上传到 Aspose.PDF Cloud 存储。
1. 使用 Aspose.PDF Cloud API 合并 PDF 文档。
1. 将结果记录到控制台。
1. 如有需要下载结果

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="使用 Node.js 合并多个 PDF 文件" offSpacer="" %}}

```js

    const fs = require("fs");
    const { PdfApi } = require("asposepdfcloud");
    const { MergeDocuments } = require("asposepdfcloud/src/models/mergeDocuments");

    async function mergeDocument()
    {
        const api = new PdfApi("YOUR_API_SID", "YOUR_API_KEY");

        const fileName = "merged.pdf";
        const fileNames = ["Sample.pdf", "Sample2.pdf"];
        const storage = null;
        const folder = "Documents";

        const mergeRequest = new MergeDocuments();
        mergeRequest.list = [];
        await Promise.all(
            fileNames.map(async fileName =>
            {
                const buffer = fs.readFileSync(fileName);
                await api.uploadFile(folder + "/" + fileName, buffer, storage);
                mergeRequest.list.push(folder + "/" + fileName);
            })
        );
        const result = await api.putMergeDocuments(
            fileName,
            mergeRequest,
            storage,
            folder);

        console.log(result.body.status);
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="结合功能和能力" %}}

我们通过不断发展的 Cloud SDK 提供顶级的文档处理能力，支持多种编程语言和主要平台。这些工具使开发人员能够完全控制和定制文档合并选项，以满足其独特需求。

**使用我们的 Node.js 工具，您可以：**

+ 以文本或图像格式添加 PDF 文档的页眉和页脚。
+ 向 PDF 文档添加表格和图章（文本或图像）。
+ 将多个 PDF 文档附加到现有文件中。
+ 处理 PDF 附件、注释和表单字段。
+ 对 PDF 文档应用加密或解密并设置密码。
+ 从页面或整个 PDF 文档中删除所有图章和表格。
+ 根据其 ID 从 PDF 文档中删除特定图章或表格。
+ 替换 PDF 页面或整个文档中的一个或多个文本实例。
+ 广泛支持将 PDF 文档转换为多种其他文件格式。
+ 提取 PDF 文件的各种元素并优化 PDF 文档。
+ 您可以尝试我们的[免费应用](https://products.aspose.app/pdf/merger)在线合并 PDF 文件并测试功能。

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



