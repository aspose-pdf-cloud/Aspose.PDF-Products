---
title: إضافة ختم نص إلى PDF عبر Cloud Python SDK
url: python/stamp/text/
description: أضف الأختام المعتمدة على النص إلى ملفات PDF في Python باستخدام Aspose.PDF Cloud SDK. أتمتة تسمية المستندات.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="إضافة ختم إلى PDF في Python SDK" h2="API للعمل مع الأختام في مستندات PDF باستخدام Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="كيفية إضافة ختم نص إلى PDF عبر Cloud Python SDK " %}}

لإضافة الأختام إلى PDF، سنستخدم
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). يساعد هذا Cloud SDK مبرمجي Python في تطوير تطبيقات إنشاء، تعليق، تحرير، وتحويل PDF المستندة إلى السحابة باستخدام لغة برمجة Python عبر Aspose.PDF REST API. ببساطة أنشئ حسابًا في [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) واحصل على معلومات التطبيق الخاص بك. بمجرد حصولك على App SID & key، تكون جاهزًا لاستخدام Aspose.PDF Cloud Python SDK. إذا كانت حزمة python مستضافة على Github، يمكنك التثبيت مباشرة من Github:

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

{{% blocks/products/pf/agp/feature-section-col title="خطوات إضافة الأختام إلى PDF عبر Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

يمكن لمطوري Aspose.PDF Cloud بسهولة تحميل وإضافة الأختام إلى PDF في بضع خطوط من الكود.

{{% /blocks/products/pf/agp/text %}}

1. تثبيت [Python SDK](https://pypi.org/project/asposepdfcloud/)
2. تحميل مستند PDF إلى خادم Aspose Cloud
3. تنزيل مستند PDF المعالج من خادم Aspose Cloud
4. إضافة ختم نص إلى صفحة معينة في مستند PDF

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="إضافة الأختام إلى PDF باستخدام Python" offSpacer="" %}}

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

{{% blocks/products/pf/agp/content h2="العمل مع الأختام في PDF" %}}

يخدم إضافة الأختام إلى مستندات PDF أغراضًا متعددة، مما يعزز كل من وظائف وأمان الملفات الرقمية. كمطور، يمكن لفهم هذه الفوائد أن يوجه تنفيذ الميزات التي تبسط تدفقات العمل للمستند وتعزز سلامة البيانات.​ في البيئات التعاونية، غالبًا ما تتطلب المستندات مراجعات وموافقات متعددة. يمكن أن تردع الأختام التوزيع غير المصرح به والتعديل. يمكن أن يعزز تضمين وظيفة الأختام في أنظمة إدارة PDF بشكل كبير تدفقات عمل المستندات والأمان والامتثال. من خلال الاستفادة الفعالة من الأختام، يمكن للمنظمات ضمان أن تكون مستنداتها احترافية ومحفوظة.
أضف الأختام إلى مستندات PDF باستخدام [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**مع مكتبتنا في Python يمكنك:**

+ دمج مستندات PDF.
+ تقسيم ملفات PDF.
+ تحويل PDF إلى صيغ أخرى، والعكس صحيح.
+ التعامل مع التعليقات التوضيحية.
+ العمل مع الصور في PDF، إلخ.
+ يمكنك تجربة [تطبيقنا المجاني](https://products.aspose.app/pdf/family) لاختبار الوظائف عبر الإنترنت.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
