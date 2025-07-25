---
title: 通过 Python Cloud SDK 将 PDF 转换为 DOC
url: python/conversion/pdf-to-word/
description: 使用 Aspose.PDF Cloud SDK 在 Python 中将 PDF 转换为可编辑的 DOCX 格式。实现轻松编辑和重用。
lastmod: 2024-10-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="在 Python SDK 中将 PDF 转换为 DOC" h2="使用 Aspose.PDF Cloud Python SDK 将 PDF 文档导出为包括 DOC 在内的多种格式" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOC" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Python SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python" >}}

{{% blocks/products/pf/agp/content h2="如何使用 Python SDK 将 PDF 转换为 DOC" %}}

为了将 PDF 转换为 DOC，我们将使用
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/)
此 Cloud SDK 协助 Python 程序员使用 Python 编程语言通过 Aspose.PDF REST API 开发基于云的 PDF 创建、注释、编辑和转换应用程序。只需在 [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) 创建一个帐户并获取您的应用程序信息。一旦您有了 App SID 和密钥，您就可以开始使用 Aspose.PDF Cloud Python SDK。如果 python 包托管在 Github 上，您可以直接从 Github 安装：

{{% blocks/products/pf/agp/code-block title="从 Github 安装" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="包管理器控制台命令" offSpacer="true" %}}

```bash

     
    pip install asposepdfcloud
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="通过 Python 转换 PDF 为 DOC 的步骤" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud Python 开发者可以轻松地在几行代码中加载和转换 PDF 文件为 DOC。

{{% /blocks/products/pf/agp/text %}}

1. 设置输入文件名
1. 设置输出文件名
1. 创建选项字典
1. 调用 API 方法

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="系统要求" %}}

{{% blocks/products/pf/agp/text %}}

开始使用 Aspose.PDF Cloud Python SDK 很简单：

* Python 2.7 和 3.4+

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="此示例代码显示 PDF 到 DOC 的 Cloud Python SDK 转换" offSpacer="" %}}

```python

    file_name = 'pages.pdf'
    result_file_name = "result.doc"

    opts = {
        "file": test_data_path + file_name
    }

    response = pdf_api.put_pdf_in_request_to_doc(
        temp_folder + '/' + result_file_name, **opts)
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="其他支持的转换" subTitle="您还可以将 PDF 转换为许多其他文件格式，包括以下几种。" >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/python/conversion/pdf-to-word/" name="PDF 转 WORD" description="Microsoft Word DOC 和 DOC" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/python/conversion/pdf-to-excel/" name="PDF 转 EXCEL" description="Microsoft Excel" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/python/conversion/pdf-to-jpeg/" name="PDF 转 JPEG" description="JPEG 图像" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/python/conversion/pdf-to-png/" name="PDF 转 PNG" description="便携式网络图形" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/python/conversion/pdf-to-pptx/" name="PDF 转 PPTX" description="开放 XML 演示文稿格式" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



