---
title: إضافة الروابط إلى PDF عبر Cloud Python SDK
url: python/links/add/
description: أضف الروابط التشعبية إلى ملفات PDF باستخدام بايثون عبر Aspose.PDF Cloud SDK. اجعل المستندات تفاعلية ومتصلة.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="إضافة الروابط إلى PDF في Python SDK" h2="إضافة الروابط إلى مستند PDF باستخدام Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="كيفية إضافة الروابط إلى PDF عبر Cloud Python SDK " %}}

لإضافة الروابط إلى PDF، سنستخدم
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). هذا SDK السحابي يساعد مبرمجي بايثون في تطوير تطبيقات إنشاء، تعليق، تحرير، وتحويل PDF المستندة إلى السحابة باستخدام لغة البرمجة بايثون عبر Aspose.PDF REST API. ببساطة قم بإنشاء حساب في [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) واحصل على معلومات تطبيقك. بمجرد حصولك على App SID & key، أنت جاهز لاستخدام Aspose.PDF Cloud Python SDK. إذا كان حزمة بايثون موجودة على Github، يمكنك تثبيتها مباشرة من Github:

{{% blocks/products/pf/agp/code-block title="التثبيت من Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="أمر في وحدة إدارة الحزم" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="خطوات إضافة الروابط إلى PDF عبر Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

يمكن لمطوري Aspose.PDF Cloud تحميل وإضافة الروابط إلى PDF بسهولة في بضعة أسطر من التعليمات البرمجية.

{{% /blocks/products/pf/agp/text %}}

1. تثبيت [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. تحميل مستند PDF إلى خادم Aspose Cloud
1. تنزيل مستند PDF المعالج من خادم Aspose Cloud
1. إلحاق تعليق تشعبي جديد إلى صفحة محددة في مستند PDF

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="إضافة الروابط إلى PDF باستخدام بايثون" offSpacer="" %}}

```python

    import shutil
    import json
    import logging
    from pathlib import Path
    from asposepdfcloud import ApiClient, PdfApi, LinkAnnotation, LinkActionType, LinkHighlightingMode, Color, Link, Rectangle

    # Configure logging
    logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")


    class Config:
        """Configuration parameters."""
        CREDENTIALS_FILE = Path(r"C:\\Projects\\ASPOSE\\Pdf.Cloud\\Credentials\\credentials.json")
        LOCAL_FOLDER = Path(r"C:\Samples")
        PDF_DOCUMENT_NAME = "sample.pdf"
        LOCAL_RESULT_DOCUMENT_NAME = "output_sample.pdf"
        NEW_LINK_ACTION = "https://reference.aspose.cloud/pdf/"
        PAGE_NUMBER = 2
        LINK_RECT = Rectangle(llx=244.914, lly=488.622, urx=284.776, ury=498.588)


    class PdfLinks:
        """Class for managing PDF links using Aspose PDF Cloud API."""
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

        def download_result(self):
            """Download the processed PDF document from the Aspose Cloud server."""
            if self.pdf_api:
                try:
                    temp_file = self.pdf_api.download_file(Config.PDF_DOCUMENT_NAME)
                    local_path = Config.LOCAL_FOLDER / Config.LOCAL_RESULT_DOCUMENT_NAME
                    shutil.move(temp_file, str(local_path))
                    logging.info(f"download_result(): File successfully downloaded: {local_path}")
                except Exception as e:
                    logging.error(f"download_result(): Failed to download file: {e}")

        def append_link(self):
            """Append a new hyperlink annotation to a specific page in the PDF document."""
            if self.pdf_api:
                link_annotation = LinkAnnotation(
                    links=[Link(href=Config.NEW_LINK_ACTION)],
                    action_type= LinkActionType.GOTOURIACTION,
                    action=Config.NEW_LINK_ACTION,
                    highlighting=LinkHighlightingMode.INVERT,
                    color=Color(a=255, r=0, g=255, b=0),
                    rect=Config.LINK_RECT,
                )

                try:
                    response = self.pdf_api.post_page_link_annotations(
                        Config.PDF_DOCUMENT_NAME, Config.PAGE_NUMBER, [link_annotation]
                    )
                    if response.code == 200:
                        logging.info(f"append_link(): Link '{Config.NEW_LINK_ACTION}' added to page #{Config.PAGE_NUMBER}.")
                    else:
                        logging.error(f"append_link(): Failed to add link to the page. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"append_link(): Error while adding link: {e}")


    if __name__ == "__main__":
        pdf_links = PdfLinks()
        pdf_links.upload_document()
        pdf_links.append_link()
        pdf_links.download_result()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="العمل مع الروابط في PDF" %}}

إضافة الروابط إلى PDF يعزز من سهولة الاستخدام، التفاعل، وإمكانية الوصول. سواء كان للتنقل، التسويق، أو الإشارة المتقاطعة، الروابط التشعبية تحسن من فعالية المستند، مما يسهل على المستخدمين العثور على المحتوى المناسب واتخاذ الإجراءات.
أضف الروابط إلى مستندات PDF باستخدام [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**مع مكتبة بايثون الخاصة بنا يمكنك:**

+ دمج مستندات PDF.
+ تقسيم ملفات PDF.
+ تحويل PDF إلى صيغ أخرى، والعكس بالعكس.
+ معالجة التعليقات التوضيحية.
+ العمل مع الصور في PDF، إلخ.
+ يمكنك تجربة [التطبيق المجاني](https://products.aspose.app/pdf/family) لاختبار الوظائف عبر الإنترنت.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
