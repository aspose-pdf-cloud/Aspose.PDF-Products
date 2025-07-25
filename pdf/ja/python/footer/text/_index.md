---
title: Cloud Python SDKを介してPDFのフッターにテキストを追加
url: python/footer/text/
description: PythonとAspose.PDF Cloud SDKを使用してPDFにテキストフッターを挿入します。フッターを動的にカスタマイズします。
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Python SDKでPDFのフッターにテキストを追加" h2="Cloud Python SDKを使用してPDF文書のフッター内でテキストを操作するためのAPI。" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Cloud Python SDKを介してPDFのフッターにテキストを追加する方法" %}}

PDFのフッターにテキストを追加するために、
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/)を使用します。このCloud SDKは、PythonプログラマーがPythonプログラミング言語を介してAspose.PDF REST APIを使用してクラウドベースのPDF作成、注釈、編集、および変換アプリを開発するのを支援します。[Aspose for Cloud](https://dashboard.aspose.cloud/#/apps)でアカウントを作成し、アプリケーション情報を取得してください。App SIDとキーを取得したら、Aspose.PDF Cloud Python SDKを試す準備が整います。PythonパッケージがGithubにホストされている場合は、Githubから直接インストールできます:

{{% blocks/products/pf/agp/code-block title="Githubからのインストール" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="パッケージマネージャコンソールコマンド" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Pythonを介してフッターにテキストを追加する手順" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud開発者は、わずか数行のコードでPDFのフッターにテキストを簡単に読み込んで追加できます。

{{% /blocks/products/pf/agp/text %}}

1. [Python SDK](https://pypi.org/project/asposepdfcloud/)をインストール
1. PDF文書をAspose Cloudサーバーにアップロード
1. Aspose Cloudサーバーから処理済みのPDF文書をダウンロード
1. PDF文書のページに新しいテキストフッターを追加

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Pythonを使用してPDFのフッターにテキストを追加" offSpacer="" %}}

```python

    import shutil
    import json
    import logging
    from pathlib import Path
    from asposepdfcloud import ApiClient, PdfApi, TextFooter, HorizontalAlignment, TextHorizontalAlignment

    # Configure logging
    logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")

    class Config:
        """Configuration parameters."""
        CREDENTIALS_FILE = Path(r"C:\\Projects\\ASPOSE\\Pdf.Cloud\\Credentials\\credentials.json")
        LOCAL_FOLDER = Path(r"C:\Samples")
        PDF_DOCUMENT_NAME = "sample.pdf"
        LOCAL_RESULT_DOCUMENT_NAME = "output_sample.pdf"
        FOOTER_VALUE = "New Footer Value"
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

        def append_text_footer(self):
            """Append a new text footer to the PDF document."""
            if self.pdf_api:
                new_footer = TextFooter(
                    background = True,
                    horizontal_alignment = HorizontalAlignment.CENTER,
                    text_alignment = TextHorizontalAlignment.CENTER,
                    value = Config.FOOTER_VALUE
                )

                try:
                    response = self.pdf_api.post_document_text_footer(
                        Config.PDF_DOCUMENT_NAME, new_footer
                    )
                    if response.code == 200:
                        logging.info(f"append_text_footer(): Footer '{new_footer.value}' added to the document '{Config.PDF_DOCUMENT_NAME}'.")
                    else:
                        logging.error(f"append_text_footer(): Failed to add footer '{new_footer.value}' to the document '{Config.PDF_DOCUMENT_NAME}'. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"append_text_footer(): Error while adding footer: {e}")

        def append_text_footer(self):
            """Append a new text footer to the PDF document."""
            if self.pdf_api:
                new_footer = TextFooter(
                    background = True,
                    horizontal_alignment = HorizontalAlignment.CENTER,
                    text_alignment = TextHorizontalAlignment.CENTER,
                    value = Config.FOOTER_VALUE
                )

                try:
                    response = self.pdf_api.post_document_text_footer(
                        Config.PDF_DOCUMENT_NAME, new_footer
                    )
                    if response.code == 200:
                        logging.info(f"append_text_footer(): Footer '{new_footer.value}' added to the document '{Config.PDF_DOCUMENT_NAME}'.")
                    else:
                        logging.error(f"append_text_footer(): Failed to add footer '{new_footer.value}' to the document '{Config.PDF_DOCUMENT_NAME}'. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"append_text_footer(): Error while adding footer: {e}")

        def append_text_footer_page(self):
            """Append a new text footer to the page on PDF document."""
            if self.pdf_api:
                new_footer = TextFooter(
                    background = True,
                    horizontal_alignment = HorizontalAlignment.RIGHT,
                    text_alignment = TextHorizontalAlignment.CENTER,
                    value = Config.FOOTER_VALUE
                )

                try:
                    response = self.pdf_api.post_document_text_footer(
                        Config.PDF_DOCUMENT_NAME, new_footer, start_page_number=Config.PAGE_NUMBER, end_page_number=Config.PAGE_NUMBER
                    )
                    if response.code == 200:
                        logging.info(f"append_text_footer_page(): Footer '{new_footer.value}' added to the page #{Config.PAGE_NUMBER}.")
                    else:
                        logging.error(f"append_text_footer_page(): Failed to add footer '{new_footer.value}' to the document #{Config.PAGE_NUMBER}. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"append_text_footer_page(): Error while adding footer: {e}")

    if __name__ == "__main__":
        pdf_header_footer = pdfHederFooter()
        pdf_header_footer.upload_document()
        pdf_header_footer.append_text_footer()
        pdf_header_footer.append_text_footer_page()
        pdf_header_footer.download_result()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="PDFのフッターで作業" %}}

PDFのフッターにテキストを追加することで、ドキュメントの整理、プロフェッショナリズム、および使いやすさが向上します。ブランディング、法令遵守、ナビゲーション、およびセキュリティに不可欠であり、ビジネス、学術、および公式文書にとって価値のある機能です。
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/)を使用してPDF文書にフッターを追加します。

**Pythonライブラリを使用してできること:**

+ PDF文書を結合します。
+ PDFファイルを分割します。
+ PDFを他の形式に変換し、その逆も可能です。
+ 注釈を操作します。
+ PDF内の画像を操作します、など。
+ 機能をオンラインでテストするために、[無料のアプリ](https://products.aspose.app/pdf/family/)をお試しください。

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
