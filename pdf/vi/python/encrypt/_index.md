---
title: Mã hóa PDF qua Cloud PHP SDK
url: python/encrypt/
description: Aspose.PDF Cloud cho phép bạn mã hóa Tài liệu PDF. Kiểm tra mã nguồn Python để mã hóa tệp PDF.
lastmod: 2025-04-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Bảo vệ bằng mật khẩu PDF trong Python SDK" h2="API để mã hóa tài liệu PDF bằng Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Cách mã hóa PDF qua Cloud Python SDK " %}}

Để mã hóa PDF, chúng ta sẽ sử dụng
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). SDK Cloud này hỗ trợ các lập trình viên Python phát triển ứng dụng tạo, chú thích, chỉnh sửa và chuyển đổi PDF dựa trên đám mây bằng ngôn ngữ lập trình Python qua Aspose.PDF REST API. Chỉ cần tạo một tài khoản tại [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) và lấy thông tin ứng dụng của bạn. Khi đã có App SID & key, bạn đã sẵn sàng sử dụng Aspose.PDF Cloud Python SDK. Nếu gói python được lưu trữ trên Github, bạn có thể cài đặt trực tiếp từ Github:

{{% blocks/products/pf/agp/code-block title="Cài đặt từ Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Lệnh trong Package Manager Console" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Các bước để mã hóa PDF qua Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

Các nhà phát triển Aspose.PDF Cloud có thể dễ dàng tải & mã hóa PDF chỉ trong vài dòng mã.

{{% /blocks/products/pf/agp/text %}}

1. Cài đặt [Python SDK](https://pypi.org/project/asposepdfcloud/).
1. Truy cập [Bảng điều khiển Aspose Cloud](https://dashboard.aspose.cloud/).
1. Mã hóa tệp bằng AES-256 sử dụng mật khẩu mã hóa base64.
1. Tải lại PDF đã được bảo mật về thư mục cục bộ.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Mã hóa PDF bằng Python" offSpacer="" %}}

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

{{% blocks/products/pf/agp/content h2="Mã hóa PDF" %}}

Mã hóa tài liệu PDF là một cách đơn giản nhưng mạnh mẽ để bảo vệ nội dung nhạy cảm, đảm bảo quyền riêng tư và kiểm soát cách sử dụng tài liệu. Cho dù bạn đang chia sẻ hợp đồng kinh doanh, báo cáo tài chính hay hồ sơ cá nhân, mã hóa giúp bảo vệ thông tin của bạn khỏi truy cập trái phép, giả mạo hoặc sử dụng sai mục đích.
Bằng cách áp dụng mã hóa và thiết lập các quyền phù hợp, bạn nâng cao bảo mật của tài liệu, đảm bảo tuân thủ các quy định của ngành và xây dựng lòng tin với khán giả của bạn. Trong thế giới kỹ thuật số ngày nay, mã hóa PDF không chỉ là một tính năng—nó là một điều cần thiết để xử lý dữ liệu một cách có trách nhiệm.
Mã hóa tài liệu PDF với [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**Với thư viện Python của chúng tôi, bạn có thể:**

+ Kết hợp các tài liệu PDF.
+ Tách các tệp PDF.
+ Chuyển đổi PDF sang các định dạng khác và ngược lại.
+ Thao tác với Chú thích.
+ Làm việc với Hình ảnh trong PDF, v.v.
+ Bạn có thể thử các [Ứng dụng miễn phí](https://products.aspose.app/pdf/family/) của chúng tôi để kiểm tra chức năng trực tuyến.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
