---
title: Encrypt PDF via Cloud PHP SDK 
url: /python/encrypt/
description: Aspose.PDF Cloud allows you to encrypt PDF Document. Check the Python source code to encrypt PDF file.
lastmod: "2025-04-19"
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Password Protect PDF in Python SDK" h2="API for encrypting PDF documents using Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="How to encrypt PDF via Cloud Python SDK " %}}

To encrypt PDF, we'll use
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). This Cloud SDK assists Python programmers in developing cloud-based PDF creator, annotator, editor, and converter apps using Python programming language via Aspose.PDF REST API. Simply create an account at [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) and get your application information. Once you have the App SID & key, you are ready to give the Aspose.PDF Cloud Python SDK. If the python package is hosted on Github, you can install directly from Github:

{{% blocks/products/pf/agp/code-block title="Installation from Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Package Manager Console Command" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Steps to encrypt PDF via Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud developers can easily load & encrypt PDF in just a few lines of code.

{{% /blocks/products/pf/agp/text %}}

1. Install [Python SDK](https://pypi.org/project/asposepdfcloud/).
1. Go to the [Aspose Cloud Dashboard](https://dashboard.aspose.cloud/).
1. Encrypt the file with AES-256 using base64-encoded passwords.
1. Download the secured PDF back to a local folder.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Encrypt PDF using Python" offSpacer="" %}}

```python

    import shutil
    import json
    import logging
    from pathlib import Path
    import base64
    from asposepdfcloud import ApiClient, PdfApi, CryptoAlgorithm

    # Configure logging
    logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")

    class Config:
        """Configuration parameters."""
        CREDENTIALS_FILE = Path(r"C:\\Projects\\ASPOSE\\Pdf.Cloud\\Credentials\\credentials.json")
        LOCAL_FOLDER = Path(r"C:\Samples")
        PDF_DOCUMENT_NAME = "sample.pdf"
        LOCAL_RESULT_DOCUMENT_NAME = "output_sample.pdf"
        ENCRYPT_ALGORITHM = CryptoAlgorithm.AESX256
        USER_PASSWORD = 'User-Password'
        OWNER_PASSWORD = 'Owner-Password'
        
    class pdfEncryption:
        """Class for managing PDF encryption using Aspose PDF Cloud API."""
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
            """ Upload a PDF document to the Aspose Cloud server. """
            if self.pdf_api:
                file_path = Config.LOCAL_FOLDER / Config.PDF_DOCUMENT_NAME
                try:
                    self.pdf_api.upload_file(Config.PDF_DOCUMENT_NAME, str(file_path))
                    logging.info(f"upload_file(): File '{Config.PDF_DOCUMENT_NAME}' uploaded successfully.")
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

        def encrypt_document(self):
            """Encrypt the PDF document."""
            if self.pdf_api:
                try:
                    user_password_encoded = base64.b64encode(bytes(Config.USER_PASSWORD, encoding='utf-8'))

                    owner_password_encoded = base64.b64encode(bytes(Config.OWNER_PASSWORD, encoding='utf-8'))

                    response = self.pdf_api.post_encrypt_document_in_storage(Config.PDF_DOCUMENT_NAME, user_password_encoded, owner_password_encoded, Config.ENCRYPT_ALGORITHM)
                    if response.code == 200:
                        logging.info(f"encrypt_document(): Document #{Config.PDF_DOCUMENT_NAME} successfully encrypted.")
                    else:
                        logging.error(f"encrypt_document(): Failed to encrypt document #{Config.PDF_DOCUMENT_NAME}. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"aencrypt_document(): Error while encrypted document: {e}")


    if __name__ == "__main__":
        pdf_encrypt = pdfEncryption()
        pdf_encrypt.upload_document()
        pdf_encrypt.encrypt_document()
        pdf_encrypt.download_result()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Encrypt PDF" %}}

Encrypting a PDF document is a simple yet powerful way to protect sensitive content, ensure privacy, and maintain control over how the document is used. Whether you're sharing business contracts, financial reports, or personal records, encryption helps safeguard your information from unauthorized access, tampering, or misuse.
By applying encryption and setting appropriate permissions, you enhance the document's security, ensure compliance with industry regulations, and build trust with your audience. In today's digital world, PDF encryption is not just a feature—it's a necessity for responsible data handling.
Encrypt PDF documents with [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**With our Python library you can:**

+ Combine PDF documents.
+ Split PDF Files.
+ Convert PDF to other formats, and vice versa.
+ Manipulate Annotations.
+ Work with Images in PDF, etc.
+ You can try out our [free Apps](https://products.aspose.app/pdf/family/) to test the functionality online.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}