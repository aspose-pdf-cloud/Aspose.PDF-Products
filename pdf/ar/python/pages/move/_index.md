---
title: تحريك الصفحات في PDF عبر Cloud Python SDK
url: python/pages/move/
description: تحريك أو إعادة ترتيب الصفحات في ملفات PDF باستخدام Python وAspose.PDF Cloud SDK.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="تحريك الصفحات في PDF في Python SDK" h2="تحريك الصفحات في مستند PDF باستخدام Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="كيفية تحريك الصفحات في PDF عبر Cloud Python SDK " %}}

لتحريك الصفحات في PDF، سنستخدم
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). هذا SDK السحابي يساعد مبرمجي Python في تطوير تطبيقات إنشاء وتحرير وتعليق وتحويل PDF القائمة على السحابة باستخدام لغة برمجة Python عبر Aspose.PDF REST API. ببساطة قم بإنشاء حساب في [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) واحصل على معلومات التطبيق الخاصة بك. بمجرد حصولك على App SID & key، فأنت جاهز لاستخدام Aspose.PDF Cloud Python SDK. إذا كان حزمة Python مستضافة على Github، يمكنك التثبيت مباشرة من Github:

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

{{% blocks/products/pf/agp/feature-section-col title="خطوات تحريك الصفحات في PDF عبر Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

يمكن لمطوري Aspose.PDF Cloud تحميل وتحريك الصفحات في PDF بسهولة في بضعة أسطر من التعليمات البرمجية.

{{% /blocks/products/pf/agp/text %}}

1. تثبيت [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. تحميل مستند PDF إلى خادم Aspose Cloud
1. تنزيل مستند PDF المعالج من خادم Aspose Cloud
1. نقل صفحة إلى موقع جديد في مستند PDF

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="تحريك الصفحات في PDF باستخدام Python" offSpacer="" %}}

```python

    import shutil
    import json
    import logging
    from pathlib import Path
    from asposepdfcloud import ApiClient, PdfApi, AsposeResponse

    # Configure logging
    logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")

    class Config:
        """Configuration parameters."""
        CREDENTIALS_FILE = Path(r"C:\\Projects\\ASPOSE\\Pdf.Cloud\\Credentials\\credentials.json")
        LOCAL_FOLDER = Path(r"C:\Samples")
        PDF_DOCUMENT_NAME = "sample.pdf"
        LOCAL_RESULT_DOCUMENT_NAME = "output_sample.pdf"
        PAGE_NUMBER = 2

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

        def move_page(self):
            """ Moves a page to a new location in the PDF document. """
            if self.pdf_api:
                response: AsposeResponse = self.pdf_api.post_move_page(Config.PDF_DOCUMENT_NAME, Config.PAGE_NUMBER, Config.PAGE_NUMBER + 1)

                if response.code == 200:
                    logging.info(f"Page #{Config.PAGE_NUMBER} has been moved to position #{Config.PAGE_NUMBER + 1}.")
                else:
                    logging.error("Failed to move a new page.")

    if __name__ == "__main__":
        pdf_pages = PdfPages()
        pdf_pages.upload_document()
        pdf_pages.move_page()
        pdf_pages.download_result()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="العمل مع الصفحات في PDF" %}}

استبدال الصفحات داخل مستند PDF هو مهمة شائعة للمطورين والمحترفين الذين يحتاجون إلى الحفاظ على محتوى دقيق ومحدث. تضمن هذه العملية أن المستندات تعكس أحدث المعلومات دون الحاجة إلى إعادة إنشاء الملف بالكامل. الأخطاء في مستند، مثل الأخطاء المطبعية، أو المعلومات القديمة، أو مشكلات التنسيق، تستدعي استبدال الصفحات. بدلاً من إعادة إنشاء PDF بالكامل، يسمح استبدال صفحات معينة بإجراء تصحيحات فعالة. هذه الطريقة مفيدة بشكل خاص عندما تحتوي عدد قليل من الصفحات على أخطاء، مما يوفر الوقت والموارد. على سبيل المثال، إذا كانت صفحة تحتوي على بيانات غير صحيحة أو رسومات قديمة، فإن استبدال تلك الصفحة يضمن بقاء المستند دقيقًا واحترافيًا.
قم بتحريك الصفحات في مستندات PDF باستخدام [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**مع مكتبة Python الخاصة بنا يمكنك:**

+ دمج مستندات PDF.
+ تقسيم ملفات PDF.
+ تحويل PDF إلى صيغ أخرى، والعكس صحيح.
+ معالجة التعليقات التوضيحية.
+ العمل مع الصور في PDF، إلخ.
+ يمكنك تجربة [تطبيقنا المجاني](https://products.aspose.app/pdf/family) لاختبار الوظائف عبر الإنترنت.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
