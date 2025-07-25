---
title: 通过云端 Node.js SDK 删除书签
url: nodejs/bookmarks/remove/
description: 使用 Node.js 和 Aspose.PDF Cloud SDK 删除 PDF 书签。简化文档结构。
lastmod: 2025-02-20
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="在 Node.js SDK 中从 PDF 删除书签" h2="使用云端 Node.js SDK 从 PDF 文档中删除书签。" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="如何通过 Node.js SDK 删除书签" %}}

为了从 PDF 中删除书签，我们将使用
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)。此云端 SDK 帮助 Node.js 程序员使用 Node.js 编程语言通过 Aspose.PDF REST API 开发基于云的 PDF 创建、注释、编辑和转换应用程序。只需在 [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) 创建一个帐户并获取您的应用程序信息。一旦您有了 App SID 和密钥，就可以开始使用 Aspose.PDF Cloud Node.js SDK。

{{% blocks/products/pf/agp/code-block title="包管理器控制台命令" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="通过云端 Node.js 删除书签的步骤" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud 开发者只需几行代码即可轻松从 PDF 中删除书签。

{{% /blocks/products/pf/agp/text %}}

1. 创建一个对象以连接到 Pdf.Cloud API
1. 上传您的文档文件
1. 使用 deleteBookmark() 函数从文档中删除所需的书签
1. 在成功从文档中删除书签后执行某些操作
1. 如果需要，下载结果

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="此示例代码展示了使用 Node.js 从 PDF 文档中删除书签" offSpacer="" %}}

```js

    import credentials from "credentials.json"  with { type: "json" };    // json-file in this format: { "id": "*****", "key": "*******" }
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "asposepdfcloud";

    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample.pdf",
        LOCAL_RESULT_DOCUMENT_NAME: "output_sample.pdf",    
        DROP_BOOKMARK_PATH: "/1"
    };

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfBookmarks = {
        async uploadDocument() {
            const pdfFilePath = path.join(configParams.LOCAL_FOLDER, configParams.PDF_DOCUMENT_NAME);
            const pdfFileData = await fs.readFile(pdfFilePath);
            await pdfApi.uploadFile(configParams.PDF_DOCUMENT_NAME, pdfFileData);
        },

        async downloadResult() {
            const changedPdfData = await pdfApi.downloadFile(configParams.PDF_DOCUMENT_NAME);
            const filePath = path.join(configParams.LOCAL_FOLDER, configParams.LOCAL_RESULT_DOCUMENT_NAME);
            await fs.writeFile(filePath, changedPdfData.body);
            console.log("Downloaded: " + filePath);
        },

        async deleteBookmark(){
            const dropResult = await pdfApi.deleteBookmark(configParams.PDF_DOCUMENT_NAME, configParams.DROP_BOOKMARK_PATH);
            
            if (dropResult.body.code == 200) {
                console.log("Bookmark '" + configParams.DROP_BOOKMARK_PATH + "' successfully deleted!");
                return true;
            }
            else
                throw new Error("Unexpected error : can't get bookmarks list!!!");
        },
    };

    async function main() {
        try
        {
            await pdfBookmarks.uploadDocument();
            await pdfBookmarks.deleteBookmark();
            await pdfBookmarks.downloadResult();
        }
        catch(error) {
            console.log(error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="通过 Node.js SDK 处理书签" %}}

从 PDF 中删除书签有助于保持文档的准确性、优化性能、增强安全性，并确保正确的格式。这在分享、打印或存档文档之前尤为重要。
使用 [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/) 从 PDF 文档中删除书签。

**使用我们的 Node.js 库，您可以**

+ 以文本或图像格式添加 PDF 文档的页眉和页脚。
+ 向 PDF 文档添加表格和印章（文本或图像）。
+ 将多个 PDF 文档附加到现有文件。
+ 处理 PDF 附件、注释和表单字段。
+ 对 PDF 文档应用加密或解密并设置密码。
+ 从页面或整个 PDF 文档中删除所有印章和表格。
+ 根据 ID 从 PDF 文档中删除特定的印章或表格。
+ 替换 PDF 页面或整个文档中的单个或多个文本实例。
+ 提供广泛的支持，将 PDF 文档转换为多种其他文件格式。
+ 提取 PDF 文件的各种元素并优化 PDF 文档。
+ 您可以尝试我们的[免费应用程序](https://products.aspose.app/pdf/family/) 在线测试功能。

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

{{< blocks/products/pf/slr-tab tabTitle="为什么选择 Aspose.PDF Cloud for Node.js？" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="客户列表" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="安全性" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



