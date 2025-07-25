---
title: Giải mã PDF qua Cloud Python SDK
url: python/decrypt/
description: Aspose.PDF Cloud cho phép bạn giải mã Tài liệu PDF. Kiểm tra mã nguồn Python để giải mã tệp PDF.
lastmod: 2025-04-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Giải mã PDF trong Python SDK" h2="API để giải mã tài liệu PDF bằng cách sử dụng Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Cách giải mã PDF qua Cloud Python SDK " %}}

Để giải mã PDF, chúng ta sẽ sử dụng
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). SDK Cloud này hỗ trợ lập trình viên Python phát triển các ứng dụng tạo, chú thích, chỉnh sửa và chuyển đổi PDF trên nền tảng đám mây sử dụng ngôn ngữ lập trình Python qua Aspose.PDF REST API. Chỉ cần tạo một tài khoản tại [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) và lấy thông tin ứng dụng của bạn. Khi bạn đã có App SID & key, bạn sẵn sàng sử dụng Aspose.PDF Cloud Python SDK. Nếu gói python được lưu trữ trên Github, bạn có thể cài đặt trực tiếp từ Github:

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

{{% blocks/products/pf/agp/feature-section-col title="Các bước để giải mã PDF qua Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

Các nhà phát triển Aspose.PDF Cloud có thể dễ dàng tải & giải mã PDF chỉ trong vài dòng mã.

{{% /blocks/products/pf/agp/text %}}

1. Cài đặt [Python SDK](https://pypi.org/project/asposepdfcloud/).
1. Truy cập vào [Bảng điều khiển Aspose Cloud](https://dashboard.aspose.cloud/).
1. Tải lên một PDF đã mã hóa lên đám mây.
1. Giải mã tài liệu với mật khẩu đã chỉ định.
1. Tải tập tin đã giải mã về thư mục cục bộ.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Giải mã PDF sử dụng Python" offSpacer="" %}}

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
        PDF_DOCUMENT_NAME = "sample_encrypted.pdf"
        LOCAL_RESULT_DOCUMENT_NAME = "output_sample.pdf"
        DOCUMENT_PASSWORD = 'Owner-Password'
        
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

        def decrypt_document(self):
            """Decrypt the PDF document."""
            if self.pdf_api:
                try:
                    password_encoded = base64.b64encode(bytes(Config.DOCUMENT_PASSWORD, encoding='utf-8'))

                    response = self.pdf_api.post_decrypt_document_in_storage(Config.PDF_DOCUMENT_NAME, password_encoded)
                    if response.code == 200:
                        logging.info(f"decrypt_document(): Document #{Config.PDF_DOCUMENT_NAME} successfully decrypted.")
                    else:
                        logging.error(f"decrypt_document(): Failed to decrypt document #{Config.PDF_DOCUMENT_NAME}. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"decrypt_document(): Error while decrypted document: {e}")


    if __name__ == "__main__":
        pdf_encrypt = pdfEncryption()
        pdf_encrypt.upload_document()
        pdf_encrypt.decrypt_document()
        pdf_encrypt.download_result()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Giải mã PDF" %}}

Giải mã một tài liệu PDF là cần thiết khi quyền truy cập vào nội dung của nó bị hạn chế do mã hóa. Nó cho phép người dùng được ủy quyền lấy lại quyền kiểm soát hoàn toàn tập tin, cho phép chỉnh sửa, xem và trích xuất nội dung. Quá trình này đặc biệt quan trọng trong các quy trình làm việc nơi tài liệu bảo mật phải được truy cập theo chương trình hoặc tích hợp vào các hệ thống lớn hơn. Sử dụng các công cụ như Aspose.PDF Cloud, việc giải mã có thể được thực hiện dễ dàng và an toàn chỉ với mật khẩu chủ sở hữu hoặc người dùng chính xác. Điều này đảm bảo thông tin nhạy cảm vẫn được bảo vệ trong khi vẫn cho phép sự linh hoạt cho những người cần quyền truy cập hợp pháp.
Cuối cùng, giải mã PDF cho phép xử lý tài liệu trơn tru và củng cố tầm quan trọng của các thực hành bảo mật tài liệu mạnh mẽ nhưng có thể quản lý được.
Giải mã tài liệu PDF với [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**Với thư viện Python của chúng tôi, bạn có thể:**

+ Kết hợp tài liệu PDF.
+ Chia tệp PDF.
+ Chuyển đổi PDF sang định dạng khác, và ngược lại.
+ Thao tác với Chú thích.
+ Làm việc với Hình ảnh trong PDF, v.v.
+ Bạn có thể thử các [Ứng dụng miễn phí](https://products.aspose.app/pdf/family/) của chúng tôi để kiểm tra chức năng trực tuyến.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
