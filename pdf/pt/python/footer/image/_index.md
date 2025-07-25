---
title: Adicionar Imagem no Rodapé de PDF via Cloud Python SDK
url: python/footer/image/
description: Adicione rodapés baseados em imagem às páginas de PDF em Python usando Aspose.PDF Cloud SDK. Automatize a marcação de rodapés.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Adicionar Imagem ao Rodapé de PDF no Python SDK" h2="API para trabalhar com Imagem no Rodapé de documentos PDF usando Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="para Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK para Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Como adicionar Imagem no Rodapé de PDF via Cloud Python SDK " %}}

Para adicionar Imagem no Rodapé de PDF, usaremos
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). Este Cloud SDK auxilia programadores Python no desenvolvimento de aplicativos criadores, anotadores, editores e conversores de PDF baseados em nuvem usando a linguagem de programação Python via Aspose.PDF REST API. Simplesmente crie uma conta no [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) e obtenha suas informações de aplicação. Uma vez que você tenha o App SID & key, você está pronto para usar o Aspose.PDF Cloud Python SDK. Se o pacote Python estiver hospedado no Github, você pode instalar diretamente do Github:

{{% blocks/products/pf/agp/code-block title="Instalação a partir do Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Comando do Console do Gerenciador de Pacotes" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Passos para adicionar Imagem no Rodapé via Python" %}}

{{% blocks/products/pf/agp/text %}}

Desenvolvedores do Aspose.PDF Cloud podem facilmente carregar e adicionar Imagem no Rodapé de PDF em apenas algumas linhas de código.

{{% /blocks/products/pf/agp/text %}}

1. Instale o [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. Carregue um documento PDF para o servidor Aspose Cloud
1. Baixe o documento PDF processado do servidor Aspose Cloud
1. Anexe um novo rodapé de imagem na página do documento PDF

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Adicionar Imagem no Rodapé de PDF usando Python" offSpacer="" %}}

```python

    import shutil
    import json
    import logging
    from pathlib import Path
    from asposepdfcloud import ApiClient, PdfApi, ImageFooter, HorizontalAlignment

    # Configure logging
    logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")

    class Config:
        """Configuration parameters."""
        CREDENTIALS_FILE = Path(r"C:\\Projects\\ASPOSE\\Pdf.Cloud\\Credentials\\credentials.json")
        LOCAL_FOLDER = Path(r"C:\Samples")
        PDF_DOCUMENT_NAME = "sample.pdf"
        LOCAL_RESULT_DOCUMENT_NAME = "output_sample.pdf"
        IMAGE_FOOTER_FILE = "sample.png"
        PAGE_NUMBER = 2     # Your document page number...
        

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

        def upload_file(self, fileName: str):
            """ Upload a local fileName to the Aspose Cloud server. """
            if self.pdf_api:
                file_path = Config.LOCAL_FOLDER / fileName
                try:
                    self.pdf_api.upload_file(fileName, str(file_path))
                    logging.info(f"upload_file(): File '{fileName}' uploaded successfully.")
                except Exception as e:
                    logging.error(f"upload_document(): Failed to upload file: {e}")

        def upload_document(self):
            """ Upload a PDF document to the Aspose Cloud server. """
            self.upload_file(Config.PDF_DOCUMENT_NAME)

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

        def append_image_footer(self):
            """Append a new image footer to the PDF document."""
            if self.pdf_api:
                new_footer = ImageFooter(
                    background = True,
                    horizontal_alignment = HorizontalAlignment.CENTER,
                    file_name = Config.IMAGE_FOOTER_FILE,
                    width = 24,
                    height = 24
                )

                try:
                    response = self.pdf_api.post_document_image_footer(
                        Config.PDF_DOCUMENT_NAME, new_footer
                    )
                    if response.code == 200:
                        logging.info(f"append_image_footer(): Footer '{new_footer.file_name}' added to the document #{Config.PDF_DOCUMENT_NAME}.")
                    else:
                        logging.error(f"append_image_footer(): Failed to add footer '{new_footer.file_name}' to the document #{Config.PDF_DOCUMENT_NAME}. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"append_image_footer(): Error while adding footer: {e}")

        def append_image_footer_page(self):
            """Append a new image footer on the page in PDF document."""
            if self.pdf_api:
                new_footer = ImageFooter(
                    background = True,
                    horizontal_alignment = HorizontalAlignment.RIGHT,
                    file_name = Config.IMAGE_FOOTER_FILE,
                    width = 24,
                    height = 24
                )

                try:
                    response = self.pdf_api.post_document_image_footer(
                        Config.PDF_DOCUMENT_NAME, new_footer, start_page_number=Config.PAGE_NUMBER, end_page_number=Config.PAGE_NUMBER
                    )
                    if response.code == 200:
                        logging.info(f"append_image_footer_page(): Footer '{new_footer.file_name}' added to the page #{Config.PAGE_NUMBER}.")
                    else:
                        logging.error(f"append_image_footer_page(): Failed to add footer '{new_footer.file_name}' to the document #{Config.PAGE_NUMBER}. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"append_image_footer_page(): Error while adding footer: {e}")


    if __name__ == "__main__":
        pdf_header_footer = pdfHederFooter()
        pdf_header_footer.upload_document()
        pdf_header_footer.upload_file(Config.IMAGE_FOOTER_FILE)
        pdf_header_footer.append_image_footer()
        pdf_header_footer.append_image_footer_page()
        pdf_header_footer.download_result()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabalhar com Rodapé em PDF" %}}

Adicionar uma imagem ao rodapé de um PDF melhora a marcação, segurança, estética e funcionalidade do documento. É especialmente valioso para documentos empresariais, relatórios, documentos legais e materiais de marketing, garantindo uma apresentação profissional e bem estruturada.
Adicione o Rodapé em documentos PDF com [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**Com nossa biblioteca Python você pode:**

+ Combinar documentos PDF.
+ Dividir arquivos PDF.
+ Converter PDF para outros formatos, e vice-versa.
+ Manipular Anotações.
+ Trabalhar com Imagens em PDF, etc.
+ Você pode experimentar nossos [aplicativos gratuitos](https://products.aspose.app/pdf/family/) para testar a funcionalidade online.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
