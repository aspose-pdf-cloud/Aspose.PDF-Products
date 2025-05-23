---
title: Add Signature to PDF via Cloud Python SDK 
url: /python/signature/add/
description: Aspose.PDF Cloud allows you to add a Signature to a PDF Document. Check the Python source code to add a Signature into PDF file.
lastmod: "2025-03-19"
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Sign PDF in Python SDK" h2="Add a Signature to a PDF Document using Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="How to add Signature to PDF via Cloud Python SDK " %}}

To add signature into PDF, we'll use
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

{{% blocks/products/pf/agp/feature-section-col title="Steps to add signature into PDF via Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud developers can easily load & add signature to PDF in just a few lines of code.

{{% /blocks/products/pf/agp/text %}}

1. Install [Python SDK](https://pypi.org/project/asposepdfcloud/).
1. Uploads PDF documents to the cloud, and is set up to download processed documents.
1. Append a new signature to the PDF document.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Add Signature to PDF using Python" offSpacer="" %}}

```python

    import shutil
    import json
    import logging
    from pathlib import Path
    from asposepdfcloud import ApiClient, PdfApi, Signature, SignatureType, SignatureField, Rectangle

    # Configure logging
    logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")


    class Config:
        """Configuration parameters."""
        CREDENTIALS_FILE = Path(r".../../../credentials.json")
        LOCAL_FOLDER = Path(r"C:\Samples")
        PDF_DOCUMENT_NAME = "sample.pdf"
        LOCAL_RESULT_DOCUMENT_NAME = "output_sample.pdf"
        LOCAL_SIGNATURE_PATH = Path(r"C:\Samples\Signatures\3")
        SIGNATURE_PFX = "signature.pfx"
        SIGNATURE_FORM_FIELD = 'Signature_1'
        SIGNATURE_PASSWORD='Password'
        SIGNATURE_CONTACT='Contact'
        SIGNATURE_LOCATION='Location'
        SIGNATURE_AUTHORITY='Issuer'
        SIGNATURE_DATE='04/19/2025 12:15:00.000 PM'
        SIGNATURE_RECT = Rectangle(100, 100, 500, 500)


    class PdfSignatures:
        """Class for managing PDF signatures using Aspose PDF Cloud API."""
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

        def upload_file(self, local_path: Path, fileName: str):
            """ Upload a local fileName to the Aspose Cloud server. """
            if self.pdf_api:
                file_path = local_path / fileName
                try:
                    self.pdf_api.upload_file(fileName, str(file_path))
                    logging.info(f"upload_file(): File '{fileName}' uploaded successfully.")
                except Exception as e:
                    logging.error(f"upload_document(): Failed to upload file: {e}")

        def upload_document(self):
            """ Upload a PDF document to the Aspose Cloud server. """
            self.upload_file(Config.LOCAL_FOLDER, Config.PDF_DOCUMENT_NAME)


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

        def append_signature(self):
            """Append a new signature to the PDF document."""
            if self.pdf_api:
                
                signature = Signature(
                    signature_path=Config.SIGNATURE_PFX,
                    signature_type=SignatureType.PKCS7,
                    password=Config.SIGNATURE_PASSWORD,
                    contact=Config.SIGNATURE_CONTACT,
                    location=Config.SIGNATURE_LOCATION,
                    visible=True,
                    rectangle=Config.SIGNATURE_RECT,
                    form_field_name=Config.SIGNATURE_FORM_FIELD,
                    authority=Config.SIGNATURE_AUTHORITY,
                    date=Config.SIGNATURE_DATE,
                    show_properties=False)
                
                field = SignatureField(page_index=1)
                field.signature = signature
                field.partial_name = 'sign1'
                field.rect = Config.SIGNATURE_RECT

                try:
                    response = self.pdf_api.post_signature_field(Config.PDF_DOCUMENT_NAME, field)
                    if response.code == 200:
                        logging.info(f"append_signature(): Signature '{Config.SIGNATURE_CONTACT}' successfully added to the document.")
                    else:
                        logging.error(f"append_signature(): Failed to add signature to the document. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"append_signature(): Error while adding signature: {e}")


    if __name__ == "__main__":
        pdf_sign = PdfSignatures()
        pdf_sign.upload_document()
        pdf_sign.upload_file(Config.LOCAL_SIGNATURE_PATH, Config.SIGNATURE_PFX)
        pdf_sign.append_signature()
        pdf_sign.download_result()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Work with Signature in PDF" %}}

Digitally signing a PDF ensures the authenticity, integrity, and legitimacy of a document. It verifies that the content has not been altered since the signature was applied and confirms the identity of the signer. This is especially important in legal, financial, and professional settings where document trust and security are critical. Digital signatures also help meet compliance standards and streamline approval workflows in a secure, verifiable manner.
Add the Signature into PDF documents with [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**With our Python library you can:**

+ Combine PDF documents.
+ Split PDF Files.
+ Convert PDF to other formats, and vice versa.
+ Manipulate Annotations.
+ Work with Images in PDF, etc.
+ You can try out our [free App](https://products.aspose.app/pdf/family) to test the functionality online.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}