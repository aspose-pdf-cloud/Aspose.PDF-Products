---
title: Thêm Văn Bản vào Tiêu Đề của PDF qua Cloud Python SDK
url: python/header/text/
description: Chèn văn bản tiêu đề vào PDF bằng Python và Aspose.PDF Cloud SDK. Tự động hóa việc tạo báo cáo.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Thêm Văn Bản vào Tiêu Đề của PDF trong Python SDK" h2="API để làm việc với Văn Bản trong Tiêu Đề của tài liệu PDF sử dụng Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Cách thêm Văn Bản vào Tiêu Đề của PDF qua Cloud Python SDK " %}}

Để thêm Văn Bản vào Tiêu Đề của PDF, chúng ta sẽ sử dụng
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). Cloud SDK này hỗ trợ các lập trình viên Python phát triển ứng dụng tạo, chú thích, chỉnh sửa và chuyển đổi PDF dựa trên đám mây sử dụng ngôn ngữ lập trình Python qua Aspose.PDF REST API. Chỉ cần tạo tài khoản tại [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) và nhận thông tin ứng dụng của bạn. Khi bạn có App SID & key, bạn đã sẵn sàng sử dụng Aspose.PDF Cloud Python SDK. Nếu gói python được lưu trữ trên Github, bạn có thể cài đặt trực tiếp từ Github:

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

{{% blocks/products/pf/agp/feature-section-col title="Các bước để thêm Văn Bản vào Tiêu Đề bằng Python" %}}

{{% blocks/products/pf/agp/text %}}

Các nhà phát triển Aspose.PDF Cloud có thể dễ dàng tải lên & thêm Văn Bản vào Tiêu Đề của PDF chỉ với vài dòng mã.

{{% /blocks/products/pf/agp/text %}}

1. Cài đặt [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. Tải lên tài liệu PDF lên máy chủ Aspose Cloud
1. Tải xuống tài liệu PDF đã xử lý từ máy chủ Aspose Cloud
1. Thêm một tiêu đề văn bản mới vào trang trên tài liệu PDF

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Thêm Văn Bản vào Tiêu Đề của PDF bằng Python" offSpacer="" %}}

```python

    import shutil
    import json
    import logging
    from pathlib import Path
    from asposepdfcloud import ApiClient, PdfApi, TextHeader, HorizontalAlignment, TextHorizontalAlignment

    # Configure logging
    logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")

    class Config:
        """Configuration parameters."""
        CREDENTIALS_FILE = Path(r"C:\\Projects\\ASPOSE\\Pdf.Cloud\\Credentials\\credentials.json")
        LOCAL_FOLDER = Path(r"C:\Samples")
        PDF_DOCUMENT_NAME = "sample.pdf"
        LOCAL_RESULT_DOCUMENT_NAME = "output_sample.pdf"
        HEADER_VALUE = "New header Value"
        PAGE_NUMBER = 2

    class pdfHederFooter:
        """Class for managing PDF headers and footers using Aspose PDF Cloud API."""
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

        def append_text_header(self):
            """Append a new text header to the PDF document."""
            if self.pdf_api:
                new_header = TextHeader(
                    background = True,
                    horizontal_alignment = HorizontalAlignment.CENTER,
                    text_alignment = TextHorizontalAlignment.CENTER,
                    value = Config.HEADER_VALUE
                )

                try:
                    response = self.pdf_api.post_document_text_header(
                        Config.PDF_DOCUMENT_NAME, new_header
                    )
                    if response.code == 200:
                        logging.info(f"append_text_header(): Header '{new_header.value}' added to the document '{Config.PDF_DOCUMENT_NAME}'.")
                    else:
                        logging.error(f"append_text_header(): Failed to add header '{new_header.value}' to the document '{Config.PDF_DOCUMENT_NAME}'. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"append_text_header(): Error while adding header: {e}")

        def append_text_header_page(self):
            """Append a new text header to the page on PDF document."""
            if self.pdf_api:
                new_header = TextHeader(
                    background = True,
                    horizontal_alignment = HorizontalAlignment.LEFT,
                    text_alignment = TextHorizontalAlignment.CENTER,
                    value = Config.HEADER_VALUE
                )

                try:
                    response = self.pdf_api.post_document_text_header(
                        Config.PDF_DOCUMENT_NAME, new_header, start_page_number=Config.PAGE_NUMBER, end_page_number=Config.PAGE_NUMBER
                    )
                    if response.code == 200:
                        logging.info(f"append_text_header_page(): Header '{new_header.value}' added to the page #{Config.PAGE_NUMBER}.")
                    else:
                        logging.error(f"append_text_header_page(): Failed to add header '{new_header.value}' to the document #{Config.PAGE_NUMBER}. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"append_text_header_page(): Error while adding header: {e}")


    if __name__ == "__main__":
        pdf_header_footer = pdfHederFooter()
        pdf_header_footer.upload_document()
        pdf_header_footer.append_text_header()
        pdf_header_footer.append_text_header_page()
        pdf_header_footer.download_result()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Làm việc với Tiêu Đề trong PDF" %}}

Thêm văn bản vào tiêu đề của PDF nâng cao thương hiệu, điều hướng, bảo mật và tính chuyên nghiệp. Nó giúp tổ chức tài liệu, duy trì tuân thủ và đảm bảo sự nhất quán, làm cho nó trở thành một tính năng có giá trị cho tài liệu kinh doanh, pháp lý, học thuật và kỹ thuật.
Thêm Tiêu Đề vào tài liệu PDF với [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**Với thư viện Python của chúng tôi, bạn có thể:**

+ Kết hợp tài liệu PDF.
+ Tách tệp PDF.
+ Chuyển đổi PDF sang các định dạng khác, và ngược lại.
+ Thao tác Chú Thích.
+ Làm việc với Hình Ảnh trong PDF, v.v.
+ Bạn có thể thử nghiệm [ứng dụng miễn phí](https://products.aspose.app/pdf/family/) của chúng tôi để kiểm tra chức năng trực tuyến.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
