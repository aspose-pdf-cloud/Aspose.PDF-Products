---
title: 通过 Aspose.Pdf Cloud Python SDK 提取和附加 PDF 文档中的附件
url: python/attachments/
description: 使用 Aspose.PDF Cloud SDK 在 Python 中管理 PDF 文件附件。只需几行代码即可嵌入或访问文件。
lastmod: 2024-10-31
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Python SDK 中的 PDF 附件" h2="使用 Aspose.PDF Cloud Python SDK 处理 PDF 文档附件的 API" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Python SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python" >}}

{{% blocks/products/pf/agp/content h2="如何使用 Cloud Python SDK 提取或附加 PDF 文档中的附件" %}}

为了处理 PDF 文档中的附件，我们将使用
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/Python/)
这个 Cloud SDK 帮助 Python 程序员使用 Python 编程语言通过 Aspose.PDF REST API 开发基于云的 PDF 创建、注释、编辑和转换应用程序。只需在 [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) 创建一个帐户并获取您的应用程序信息。一旦您拥有 App SID 和密钥，您就可以开始使用 Aspose.PDF Cloud Python SDK。如果 Python 软件包托管在 Github 上，您可以直接从 Github 安装：

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

{{% blocks/products/pf/agp/feature-section-col title="通过 Python SDK 获取附件的步骤" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud Python 开发人员可以轻松提取和附加 PDF 文档中的附件。开发人员只需几行代码。

{{% /blocks/products/pf/agp/text %}}

1. 从 JSON 文件中加载您的应用程序密钥和密钥，或以其他方式设置凭据
1. 创建一个对象以连接到 Cloud API
1. 设置文档文件的名称和路径
1. 执行提取附件操作
1. Cloud API 函数的响应将包含附件列表

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="此示例代码演示如何使用 PDF Cloud Python SDK 提取 PDF 文档的附件" offSpacer="" %}}

```python

    import shutil
    import json
    import logging
    from pathlib import Path
    from asposepdfcloud import ApiClient, PdfApi, AttachmentsResponse, AttachmentResponse, Attachment

    # Configure logging
    logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")

    class Config:
        """Configuration parameters."""
        CREDENTIALS_FILE = Path(r"C:\\Projects\\ASPOSE\\Pdf.Cloud\\Credentials\\credentials.json")
        LOCAL_FOLDER = Path(r"C:\Samples")
        PDF_DOCUMENT_NAME = "sample_file_with_attachment.pdf"
        ATTACHMENT_PATH = ""

    class PdfAttachments:
        """Class for managing PDF attachments using Aspose PDF Cloud API."""
        def __init__(self, credentials_file: Path = Config.CREDENTIALS_FILE):
            self.pdf_api = None
            self._init_api(credentials_file)

        def _init_api(self, credentials_file: Path):
            """Initialize the API client."""
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
            """Upload a PDF document to the Aspose Cloud server."""
            if self.pdf_api:
                file_path = Config.LOCAL_FOLDER / Config.PDF_DOCUMENT_NAME
                try:
                    self.pdf_api.upload_file(Config.PDF_DOCUMENT_NAME, str(file_path))
                    logging.info(f"upload_document(): File {Config.PDF_DOCUMENT_NAME} uploaded successfully.")
                except Exception as e:
                    logging.error(f"upload_document(): Failed to upload file: {e}")

        def get_attachments(self):
            """Get attachments for the PDF document."""
            if self.pdf_api:
                try:
                    response : AttachmentsResponse = self.pdf_api.get_document_attachments(Config.PDF_DOCUMENT_NAME)
                    if response.code == 200:
                        logging.info(f"get_attachmnets(): attachments '{response.attachments}' for the document '{Config.PDF_DOCUMENT_NAME}'.")
                        Config.ATTACHMENT_PATH = response.attachments.list[0].links[0].href
                    else:
                        logging.error(f"get_attachmnets(): Failed to get attachments to the document. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"get_attachmnets(): Error while adding attachment: {e}")

        def get_attachment_by_id(self):
            """Get attachment by Id for the PDF document and save it to local file."""
            if self.pdf_api:
                try:
                    response : AttachmentResponse = self.pdf_api.get_document_attachment_by_index(Config.PDF_DOCUMENT_NAME, Config.ATTACHMENT_PATH)
                    if response.code == 200:
                        attachment: Attachment = response.attachment
                        temp_file = self.pdf_api.get_download_document_attachment_by_index(Config.PDF_DOCUMENT_NAME, Config.ATTACHMENT_PATH)
                        local_path = Config.LOCAL_FOLDER / attachment.name
                        shutil.copy(temp_file, local_path)
                        logging.info(f"get_attachment_by_id(): attachment '{local_path}' for the document '{Config.PDF_DOCUMENT_NAME}' successfuly saved.")
                    else:
                        logging.error(f"get_attachment_by_id(): Failed to get attachment for the document '{Config.PDF_DOCUMENT_NAME}'. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"get_attachment_by_id(): Error while get attachment: {e}")


    if __name__ == "__main__":
        pdf_attachments = PdfAttachments()
        pdf_attachments.upload_document()
        pdf_attachments.get_attachments()
        pdf_attachments.get_attachment_by_id()
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
