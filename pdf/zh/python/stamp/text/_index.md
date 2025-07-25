---
title: 通过云 Python SDK 向 PDF 添加文本印章
url: python/stamp/text/
description: 使用 Aspose.PDF Cloud SDK 在 Python 中向 PDF 文件添加基于文本的印章。自动化文档标记。
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="在 Python SDK 中向 PDF 添加印章" h2="使用云 Python SDK 在 PDF 文档中处理印章的 API。" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="如何通过云 Python SDK 向 PDF 添加文本印章 " %}}

为了向 PDF 添加印章，我们将使用
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/)。此云 SDK 协助 Python 程序员使用 Python 编程语言通过 Aspose.PDF REST API 开发基于云的 PDF 创建、注释、编辑和转换应用程序。只需在 [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) 创建一个帐户并获取您的应用程序信息。一旦您拥有 App SID 和密钥，您就可以开始使用 Aspose.PDF Cloud Python SDK。如果 python 包托管在 Github 上，您可以直接从 Github 安装：

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

{{% blocks/products/pf/agp/feature-section-col title="通过 Python SDK 向 PDF 添加印章的步骤" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud 开发人员可以轻松地用几行代码加载并向 PDF 添加印章。

{{% /blocks/products/pf/agp/text %}}

1. 安装 [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. 将 PDF 文档上传到 Aspose Cloud 服务器
1. 从 Aspose Cloud 服务器下载处理后的 PDF 文档
1. 向 PDF 文档的特定页面添加文本印章

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="使用 Python 向 PDF 添加印章" offSpacer="" %}}

```python

    import shutil
    import json
    import logging
    from pathlib import Path
    from asposepdfcloud import ApiClient, PdfApi, Stamp, AsposeResponse, HorizontalAlignment, StampType

    # Configure logging
    logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")

    class Config:
        """Configuration parameters."""
        CREDENTIALS_FILE = Path(r"C:\\Projects\\ASPOSE\\Pdf.Cloud\\Credentials\\credentials.json")
        LOCAL_FOLDER = Path(r"C:\Samples")
        PDF_DOCUMENT_NAME = "sample.pdf"
        LOCAL_RESULT_DOCUMENT_NAME = "output_sample.pdf"
        PAGE_NUMBER = 2
        STAMP_TEXT = "NEW TEXT STAMP"

    class PdfPages:
        """ Class for managing PDF pages using Aspose PDF Cloud API. """
        def __init__(self, credentials_file: Path = Config.CREDENTIALS_FILE):
            self.pdf_api = None
            self._init_api(credentials_file)

        def _init_api(self, credentials_file: Path):
            """ Initialize the API client. """
            try:
                with credentials_file.open("r", encoding="utf-8") as file:
                    credentials = json.load(file)
                    api_key, app_id = credentials.get("key"), credentials.get("id")
                    if not api_key or not app_id:
                        raise ValueError("init_api(): Error: Missing API keys in the credentials file.")
                    self.pdf_api = PdfApi(ApiClient(api_key, app_id))
            except (FileNotFoundError, json.JSONDecodeError, ValueError) as e:
                logging.error(f"init_api(): Failed to load credentials: {e}")

        def upload_document(self):
            """ Upload a PDF document to the Aspose Cloud server. """
            if self.pdf_api:
                file_path = Config.LOCAL_FOLDER / Config.PDF_DOCUMENT_NAME
                try:
                    self.pdf_api.upload_file(Config.PDF_DOCUMENT_NAME, str(file_path))
                    logging.info(f"upload_document(): File {Config.PDF_DOCUMENT_NAME} uploaded successfully.")
                except Exception as e:
                    logging.error(f"upload_document(): Failed to upload file: {e}")

        def download_result(self):
            """ Download the processed PDF document from the Aspose Cloud server. """
            if self.pdf_api:
                try:
                    temp_file = self.pdf_api.download_file(Config.PDF_DOCUMENT_NAME)
                    local_path = Config.LOCAL_FOLDER / Config.LOCAL_RESULT_DOCUMENT_NAME
                    shutil.move(temp_file, str(local_path))
                    logging.info(f"download_result(): File successfully downloaded: {local_path}")
                except Exception as e:
                    logging.error(f"download_result(): Failed to download file: {e}")

        def add_page_text_stamp(self):
            """ Adds a text stamp to a specific page in a PDF document. """
            if self.pdf_api:
                page_stamp: Stamp = Stamp(
                    type = StampType.TEXT,
                    background = True,
                    horizontal_alignment = HorizontalAlignment.CENTER,
                    text_alignment = HorizontalAlignment.CENTER,
                    value = Config.STAMP_TEXT,
                    page_index = Config.PAGE_NUMBER,
                )

                response: AsposeResponse = self.pdf_api.put_page_add_stamp(Config.PDF_DOCUMENT_NAME, Config.PAGE_NUMBER, page_stamp)

                if response.code == 200:
                    logging.info(f"Text stamp '{Config.STAMP_TEXT}' added to page #{Config.PAGE_NUMBER}.")
                else:
                    logging.error(f"Failed to add text stamp '{Config.STAMP_TEXT}' to page #{Config.PAGE_NUMBER}.")

    if __name__ == "__main__":
        pdf_pages = PdfPages()
        pdf_pages.upload_document()
        pdf_pages.add_page_text_stamp()
        pdf_pages.download_result()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="在 PDF 中使用印章" %}}

向 PDF 文档添加印章可实现多种目的，提高数字文件的功能和安全性。作为开发人员，了解这些优势可以指导功能实现，从而简化文档工作流程并增强数据完整性。在协作环境中，文档通常需要多次审核和批准。印章可以阻止未经授权的分发和修改。将印章功能集成到 PDF 管理系统中可以显著增强文档工作流程、安全性和合规性。通过有效利用印章，组织可以确保其文档的专业性和安全性。
使用 [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/) 向 PDF 文档添加印章。

**使用我们的 Python 库，您可以：**

+ 合并 PDF 文档。
+ 拆分 PDF 文件。
+ 将 PDF 转换为其他格式，反之亦然。
+ 操作注释。
+ 处理 PDF 中的图像等。
+ 您可以尝试我们的[免费应用](https://products.aspose.app/pdf/family)在线测试功能。

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
