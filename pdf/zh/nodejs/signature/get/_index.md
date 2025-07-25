---
title: 通过云端 Node.js SDK 从 PDF 获取签名
url: nodejs/signature/get/
description: Aspose.PDF Cloud 允许您从 PDF 文档中获取签名。查看 Node.js 源代码以从 PDF 文件中获取签名。
lastmod: 2024-11-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="在 Node.js SDK 中从 PDF 获取签名" h2="使用云端 Node.js SDK 在 PDF 文档中处理签名的 API" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="如何通过 Node.js SDK 从 PDF 获取签名" %}}

为了从 PDF 提取签名，我们将使用
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)。此云端 SDK 协助 Node.js 程序员使用 Aspose.PDF REST API 开发基于云的 PDF 创建、批注、编辑和转换应用程序。只需在 [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) 创建一个帐户并获取您的应用程序信息。一旦您拥有 App SID 和密钥，您就可以准备使用 Aspose.PDF Cloud Node.js SDK。

{{% blocks/products/pf/agp/code-block title="包管理器控制台命令" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="通过云端 Node.js 获取 PDF 签名的步骤" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud 开发人员可以通过几行代码轻松加载并获取 PDF 中的签名。

{{% /blocks/products/pf/agp/text %}}

1. 读取本地 PDF 文件。
1. 提取签名字段
1. 从 Aspose PDF Cloud 存储中下载更新后的 PDF 文件。

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="使用 Node.js 从 PDF 提取签名" offSpacer="" %}}

```js

    import credentials from "../../../Credentials/credentials.json"  with { type: "json" };
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "../../src/api/api.js";


    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample-signed.pdf",
    }

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfSignatures = {
        async uploadDocument () {
            const fileNamePath = path.join(configParams.LOCAL_FOLDER, configParams.PDF_DOCUMENT_NAME);
            const pdfFileData = await fs.readFile(fileNamePath);
            await pdfApi.uploadFile(configParams.PDF_DOCUMENT_NAME, pdfFileData);
            console.log("File '" + configParams.PDF_DOCUMENT_NAME + "' successfully uploaded!");
        },

        showSignatureFieldsArray(fields)
        {
            if (fields.list.length > 0)
                fields.list.forEach(function(item) {
                    console.log("Signature => value: '" + item.signature.contact + "'");
                });
            else
                console.log("Signature fileds is empty!");
        },

        async getSignatureFields () {
            if (pdfApi)
            {
                const response = await pdfApi.getDocumentSignatureFields(configParams.PDF_DOCUMENT_NAME);

                if (response.body.code == 200 && response.body.fields) {
                    console.log("getSignatureFields(): Signature fields successfully extracted in to the '" + configParams.PDF_DOCUMENT_NAME + "' documen:")
                    this.showSignatureFieldsArray(response.body.fields);
                }
                else
                    console.error("getSignatures(): Failed to extract signatures in the document. Response code: " + response.body.code);
            }
        },
    }

    async function main() {
        try {
            await pdfSignatures.uploadDocument();
            await pdfSignatures.getSignatureFields();
        } catch (error) {
            console.error("Error:", error.message);
        }
    }

```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="处理 PDF 中的签名" %}}

从 PDF 提取签名对于验证文档真实性、审核数字交易以及确保符合法律或监管标准至关重要。通过检索签名字段，组织可以确认谁签署了文档、何时签署以及文档自签署以来是否被更改。此过程有助于在数字工作流中保持信任，并提供可追溯的批准或协议证据。
使用 [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/) 从 PDF 文档中提取签名。

**使用我们的 Node.js 库，您可以：**

+ 以文本或图像格式添加 PDF 文档的页眉和页脚。
+ 向 PDF 文档添加表格和印章（文本或图像）。
+ 将多个 PDF 文档追加到现有文件。
+ 处理 PDF 附件、注释和表单字段。
+ 对 PDF 文档应用加密或解密并设置密码。
+ 从页面或整个 PDF 文档中删除所有印章和表格。
+ 根据 ID 删除 PDF 文档中的特定印章或表格。
+ 替换 PDF 页面或整个文档中的单个或多个文本实例。
+ 广泛支持将 PDF 文档转换为各种其他文件格式。
+ 提取 PDF 文件的各个元素并优化 PDF 文档。
+ 您可以尝试我们的[免费应用程序](https://products.aspose.app/pdf/family/)在线测试功能。

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

{{< blocks/products/pf/slr-tab tabTitle="为什么选择Node.js的Aspose.PDF Cloud？" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="客户列表" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="安全性" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



