---
title: 通过云端 Python SDK 从 PDF 中提取书签
url: python/bookmarks/extract/
description: 使用 Python 和 Aspose.PDF Cloud SDK 从 PDF 中提取所有书签。分析并导出文档结构。
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="通过 Python SDK 从 PDF 中提取书签" h2="使用云端 Python SDK 将书签提取到 PDF 文档中。" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="如何通过云端 Python SDK 从 PDF 中提取书签" %}}

要从 PDF 中提取书签，我们将使用 [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/)。此云端 SDK 帮助 Python 程序员使用 Aspose.PDF REST API 开发基于云的 PDF 创建、注释、编辑和转换应用程序。只需在 [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) 创建一个帐户并获取您的应用程序信息。一旦您拥有 App SID 和密钥，您就可以开始使用 Aspose.PDF Cloud Python SDK。如果 python 包托管在 Github 上，您可以直接从 Github 安装：

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

{{% blocks/products/pf/agp/feature-section-col title="通过 Python SDK 从 PDF 获取书签的步骤" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud 开发者可以轻松加载和提取 PDF 中的书签，只需几行代码。

{{% /blocks/products/pf/agp/text %}}

1. 安装 [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. 将 PDF 文档上传到 Aspose 云服务器
1. 使用书签路径获取特定 PDF 文档的书签

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="使用 Python 从 PDF 提取书签" offSpacer="" %}}

```python

    import shutil
    import json
    import logging
    from pathlib import Path
    from asposepdfcloud import ApiClient, PdfApi, BookmarkResponse

    # Configure logging
    logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")


    class Config:
        """Configuration parameters."""
        CREDENTIALS_FILE = Path(r"C:\\Projects\\ASPOSE\\Pdf.Cloud\\Credentials\\credentials.json")
        LOCAL_FOLDER = Path(r"C:\Samples")
        PDF_DOCUMENT_NAME = "sample.pdf"
        BOOKMARK_PATH = "/5"

    class PdfBookmarks:
        """Class for managing PDF bookmarks using Aspose PDF Cloud API."""

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
                        raise ValueError("Error: Missing API keys in the credentials file.")
                    self.pdf_api = PdfApi(ApiClient(api_key, app_id))
            except (FileNotFoundError, json.JSONDecodeError, ValueError) as e:
                logging.error(f"Failed to load credentials: {e}")

        def upload_document(self):
            """Upload a PDF document to the Aspose Cloud server."""
            if self.pdf_api:
                file_path = Config.LOCAL_FOLDER / Config.PDF_DOCUMENT_NAME
                try:
                    self.pdf_api.upload_file(Config.PDF_DOCUMENT_NAME, str(file_path))
                    logging.info(f"File {Config.PDF_DOCUMENT_NAME} uploaded successfully.")
                except Exception as e:
                    logging.error(f"Failed to upload file: {e}")

        def get_bookmark(self):
            """Get bookmark for a specific PDF document using bookmark path."""    
            if self.pdf_api:
                try:
                    response : BookmarkResponse = self.pdf_api.get_bookmark( Config.PDF_DOCUMENT_NAME, Config.BOOKMARK_PATH)
                    if response.code == 200:
                        logging.info(f"Found bookmark => level: '{response.bookmark.level}' - action: '{response.bookmark.action}' - title: '{response.bookmark.title}'")
                    else:
                        logging.error(f"Failed to find bookmark for the document. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"Error while find bookmark: {e}")

    if __name__ == "__main__":
        pdf_bookmarks = PdfBookmarks()
        pdf_bookmarks.upload_document()
        pdf_bookmarks.get_bookmark()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="在 PDF 中处理书签" %}}

从 PDF 中提取书签可以提高文档的可用性、自动化内容处理并增强可搜索性。对于处理大型或结构化 PDF 文档的企业、研究人员和专业人士尤其有用。
使用 [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/) 从 PDF 文档中提取书签。

**使用我们的 Python 库，您可以：**

+ 合并 PDF 文档。
+ 拆分 PDF 文件。
+ 将 PDF 转换为其他格式，反之亦然。
+ 操作注释。
+ 处理 PDF 中的图像等。
+ 您可以试用我们的 [免费应用程序](https://products.aspose.app/pdf/family/) 在线测试功能。

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
