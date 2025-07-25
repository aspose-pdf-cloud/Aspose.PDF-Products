---
title: 通过云端 Node.js SDK 从 PDF 文档获取表单字段
url: nodejs/acroforms/get/
description: 使用 Aspose.PDF Cloud SDK for Node.js 获取并提取 PDF AcroForms 的表单字段值。
lastmod: 2024-11-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="在 Node.js SDK 中获取 PDF 表单" h2="使用 Node.js Cloud SDK 从 PDF 文档中获取所有表单字段" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="通过云端 Node.js SDK 从 PDF 文档获取 AcroForms" %}}

为了从 PDF 获取 AcroForms，我们将使用
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)。此云端 SDK 协助 Node.js 程序员使用 Aspose.PDF REST API 开发基于云的 PDF 创建、注释、编辑和转换应用程序。只需在 [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) 创建一个账户并获取您的应用信息。一旦您拥有 App SID 和密钥，您就可以开始使用 Aspose.PDF Cloud Node.js SDK。

{{% blocks/products/pf/agp/code-block title="包管理器控制台命令" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="通过 Node.js 获取 AcroForms 的步骤" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud 开发人员可以轻松地在几行代码中加载并获取 PDF 中的 acroforms。

{{% /blocks/products/pf/agp/text %}}

1. 将 PDF 文件上传到 Aspose.PDF Cloud 服务。
1. 记录在文件上传过程中发生的任何错误。
1. 从 Aspose.PDF Cloud 存储中检索 PDF 文件的表单字段。
1. 遍历表单字段并将字段名称和值记录到控制台。
1. 记录在字段检索过程中发生的任何错误
1. 如有需要，下载结果

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="此示例代码展示了如何使用 Node.js 从 PDF 文档中获取 AcroForms" offSpacer="" %}}

```js

    import credentials from "./credentials.json" with { type: "json" };
    import fs from 'node:fs/promises';
    import { PdfApi } from "asposepdfcloud";
    import { Border } from "asposepdfcloud/src/models/border";
    import { TextBoxField } from "asposepdfcloud/src/models/textBoxField";
    import { Dash } from "asposepdfcloud/src/models/dash";
    import { Rectangle } from "asposepdfcloud/src/models/rectangle";
    import { Field } from "asposepdfcloud/src/models/field";
    import { FieldType } from "asposepdfcloud/src/models/fieldType";
    import { Fields } from "asposepdfcloud/src/models/fields";

    async function getFormFields() {
        const localFileName = "C:\\Samples\\StudentInfoFormElectronic.pdf";
        const storageFileName = "StudentInfoFormElectronic.pdf";

        const pdfApi = new PdfApi(credentials.id, credentials.key);
        try {
            let fileData = await fs.readFile(localFileName);
            let uploadResult = await pdfApi.uploadFile(storageFileName, fileData);
            console.log(uploadResult.response.text);
        }
        catch (error) {
            console.error(error.message);
        }

        try {
            let response = await pdfApi.getFields(storageFileName);
            for (const item of response.body.fields.list) {
                if (item.type == "List") {
                    console.log(`Name: [${item.Name}] Value: [${item.Values.join()}]`);
                }
                else {
                    console.log(`Name: [${item.name}] Value: [${item.values[0]}]`);
                }
            }
        } catch (error) {
            console.error(error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="通过 Node.js SDK 处理 AcroForms" %}}

提取 AcroForm 数据可以高效地汇编和分析用户收集的信息，例如调查或申请响应。检索的 AcroForm 数据可以集成到数据库、电子表格或其他系统中以进行进一步处理或记录保存。提取 AcroForms 有助于审核已填写的表单，以验证所提供数据的准确性、真实性或完整性。在将表单转移到其他文档管理系统或创建备份时，检索 AcroForms 是必不可少的。
使用 [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/) 从 PDF 文档中获取 AcroForms。

**使用我们的 Node.js 库，您可以**

+ 以文本或图像格式添加 PDF 文档的页眉和页脚。
+ 将表格和印章（文本或图像）添加到 PDF 文档。
+ 将多个 PDF 文档附加到现有文件。
+ 处理 PDF 附件、注释和表单字段。
+ 对 PDF 文档进行加密或解密，并设置密码。
+ 从页面或整个 PDF 文档中删除所有印章和表格。
+ 根据 ID 从 PDF 文档中删除特定的印章或表格。
+ 替换 PDF 页面上或整个文档中的单个或多个文本实例。
+ 广泛支持将 PDF 文档转换为各种其他文件格式。
+ 提取 PDF 文件的各个元素并优化 PDF 文档。
+ 您可以尝试我们的[免费应用](https://products.aspose.app/pdf/xfa)，在线获取 PDF 文件中的 AcroForms 并测试功能。

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



