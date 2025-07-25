---
title: Agregar imagen en el pie de página de PDF a través de Cloud Python SDK
url: python/footer/image/
description: Agregue pies de página basados en imágenes a las páginas PDF en Python usando Aspose.PDF Cloud SDK. Automatice el branding del pie de página.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Agregar imagen al pie de página de PDF en Python SDK" h2="API para trabajar con imágenes en el pie de página de documentos PDF usando Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Cómo agregar imagen en el pie de página de PDF a través de Cloud Python SDK " %}}

Para agregar una imagen en el pie de página de PDF, usaremos
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). Este Cloud SDK ayuda a los programadores de Python a desarrollar aplicaciones basadas en la nube para crear, anotar, editar y convertir PDF usando el lenguaje de programación Python a través de Aspose.PDF REST API. Simplemente cree una cuenta en [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) y obtenga la información de su aplicación. Una vez que tenga el App SID y la clave, estará listo para usar Aspose.PDF Cloud Python SDK. Si el paquete de Python está alojado en Github, puede instalarlo directamente desde Github:

{{% blocks/products/pf/agp/code-block title="Instalación desde Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Comando de consola del administrador de paquetes" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Pasos para agregar imagen en el pie de página a través de Python" %}}

{{% blocks/products/pf/agp/text %}}

Los desarrolladores de Aspose.PDF Cloud pueden cargar y agregar fácilmente una imagen en el pie de página de un PDF con solo unas pocas líneas de código.

{{% /blocks/products/pf/agp/text %}}

1. Instalar [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. Subir un documento PDF al servidor de Aspose Cloud
1. Descargar el documento PDF procesado desde el servidor de Aspose Cloud
1. Añadir un nuevo pie de página con imagen en la página del documento PDF

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Agregar imagen en el pie de página de PDF usando Python" offSpacer="" %}}

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

{{% blocks/products/pf/agp/content h2="Trabajar con el pie de página en PDF" %}}

Agregar una imagen al pie de página de un PDF mejora el branding del documento, la seguridad, la estética y la funcionalidad. Es especialmente valioso para documentos empresariales, informes, documentos legales y materiales de marketing, asegurando una presentación profesional y bien estructurada.
Agregue el pie de página en documentos PDF con [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**Con nuestra biblioteca de Python, puedes:**

+ Combinar documentos PDF.
+ Dividir archivos PDF.
+ Convertir PDF a otros formatos, y viceversa.
+ Manipular anotaciones.
+ Trabajar con imágenes en PDF, etc.
+ Puedes probar nuestras [aplicaciones gratuitas](https://products.aspose.app/pdf/family/) para probar la funcionalidad en línea.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
