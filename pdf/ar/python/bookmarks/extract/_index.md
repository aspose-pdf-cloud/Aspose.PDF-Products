---
title: استخراج العلامات المرجعية من PDF عبر Cloud Python SDK
url: python/bookmarks/extract/
description: استخرج جميع العلامات المرجعية من ملفات PDF باستخدام Python مع Aspose.PDF Cloud SDK. تحليل وتصدير هيكل الوثيقة.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="استخراج العلامات المرجعية من PDF في Python SDK" h2="استخرج العلامات المرجعية إلى مستند PDF باستخدام Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="كيفية استخراج العلامات المرجعية من PDF عبر Cloud Python SDK " %}}

لاستخراج العلامات المرجعية من PDF، سنستخدم [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). يساعد هذا SDK السحابي مبرمجي Python في تطوير تطبيقات إنشاء وتحرير وتحويل PDF قائمة على السحابة باستخدام لغة برمجة Python عبر Aspose.PDF REST API. ببساطة أنشئ حسابًا في [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) واحصل على معلومات تطبيقك. بمجرد أن يكون لديك App SID & key، ستكون جاهزًا لاستخدام Aspose.PDF Cloud Python SDK. إذا كان الحزمة البرمجية Python مستضافة على Github، يمكنك تثبيتها مباشرة من Github:

{{% blocks/products/pf/agp/code-block title="التثبيت من Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="أمر وحدة تحكم مدير الحزم" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="خطوات الحصول على العلامات المرجعية من PDF عبر Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

يمكن لمطوري Aspose.PDF Cloud بسهولة تحميل واستخراج العلامات المرجعية من PDF في بضع سطور من الكود.

{{% /blocks/products/pf/agp/text %}}

1. تثبيت [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. تحميل مستند PDF إلى خادم Aspose Cloud
1. الحصول على العلامة المرجعية لمستند PDF محدد باستخدام مسار العلامة المرجعية

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="استخراج العلامات المرجعية من PDF باستخدام Python" offSpacer="" %}}

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

{{% blocks/products/pf/agp/content h2="العمل مع العلامات المرجعية في PDF" %}}

استخراج العلامات المرجعية من PDF يحسن من قابلية استخدام الوثيقة، ويؤتمت معالجة المحتوى، ويعزز قابلية البحث. وهو مفيد بشكل خاص للشركات والباحثين والمحترفين الذين يتعاملون مع مستندات PDF كبيرة أو منظمة.
استخرج العلامات المرجعية من مستندات PDF باستخدام [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**مع مكتبتنا في Python يمكنك:**

+ دمج مستندات PDF.
+ تقسيم ملفات PDF.
+ تحويل PDF إلى صيغ أخرى، والعكس بالعكس.
+ معالجة التعليقات التوضيحية.
+ العمل مع الصور في PDF، إلخ.
+ يمكنك تجربة [تطبيقاتنا المجانية](https://products.aspose.app/pdf/family/) لاختبار الوظائف عبر الإنترنت.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
