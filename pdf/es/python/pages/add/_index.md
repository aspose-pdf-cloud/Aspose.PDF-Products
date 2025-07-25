---
title: Agregar Páginas a PDF mediante Cloud Python SDK
url: python/pages/add/
description: Insertar nuevas páginas en archivos PDF con Python y Aspose.PDF Cloud SDK. Expanda dinámicamente el contenido.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Agregar Páginas a PDF en Python SDK" h2="Agregar Páginas al Documento PDF usando Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Cómo agregar Páginas a PDF mediante Cloud Python SDK " %}}

Para agregar Páginas a un PDF, usaremos
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). Este Cloud SDK ayuda a los programadores de Python a desarrollar aplicaciones basadas en la nube para crear, anotar, editar y convertir PDF usando el lenguaje de programación Python a través de Aspose.PDF REST API. Simplemente cree una cuenta en [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) y obtenga la información de su aplicación. Una vez que tenga el App SID y la clave, estará listo para usar Aspose.PDF Cloud Python SDK. Si el paquete de Python está alojado en Github, puede instalarlo directamente desde Github:

{{% blocks/products/pf/agp/code-block title="Instalación desde Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Comando de la Consola del Administrador de Paquetes" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Pasos para agregar Páginas a PDF mediante Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

Los desarrolladores de Aspose.PDF Cloud pueden cargar y agregar páginas a PDF fácilmente en solo unas pocas líneas de código.

{{% /blocks/products/pf/agp/text %}}

1. Instale [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. Suba un documento PDF al servidor de Aspose Cloud
1. Descargue el documento PDF procesado desde el servidor de Aspose Cloud
1. Agregue una nueva página al final del documento PDF

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Agregar Páginas a PDF usando Python" offSpacer="" %}}

```python

    import shutil
    import json
    import logging
    from pathlib import Path
    from asposepdfcloud import ApiClient, PdfApi, DocumentPagesResponse

    # Configure logging
    logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")


    class Config:
        """Configuration parameters."""
        CREDENTIALS_FILE = Path(r"C:\\Projects\\ASPOSE\\Pdf.Cloud\\Credentials\\credentials.json")
        LOCAL_FOLDER = Path(r"C:\Samples")
        PDF_DOCUMENT_NAME = "sample.pdf"
        LOCAL_RESULT_DOCUMENT_NAME = "output_sample.pdf"

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

        def add_new_page(self):
            """ Add new page to end of the PDF document. """
            if self.pdf_api:
                result_pages: DocumentPagesResponse = self.pdf_api.put_add_new_page(Config.PDF_DOCUMENT_NAME)

                if result_pages.code == 200 and result_pages.pages:
                    logging.info(f"Added a new page: {result_pages.pages.list[-1]}")
                else:
                    logging.error("Failed to add a new page.")

    if __name__ == "__main__":
        pdf_pages = PdfPages()
        pdf_pages.upload_document()
        pdf_pages.add_new_page()
        pdf_pages.download_result()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabajar con Páginas en PDF" %}}

Agregar páginas a un documento PDF es una tarea común que sirve para varios propósitos, mejorando la funcionalidad, organización y exhaustividad del documento. A menudo, es necesario incluir contenido adicional como apéndices, referencias o datos actualizados que no estaban disponibles durante la creación original del documento. Agregar nuevas páginas permite la integración fluida de esta información complementaria, asegurando que el documento se mantenga actual y completo. Agregar páginas a un PDF es una práctica versátil que aborda múltiples necesidades, desde mejorar el contenido y la estructura hasta asegurar el cumplimiento y facilitar la colaboración. Al comprender los requisitos específicos y utilizar herramientas adecuadas, los usuarios pueden gestionar y modificar eficazmente sus documentos PDF para adaptarse a diversos propósitos.
Agregue las Páginas a documentos PDF con [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**Con nuestra biblioteca de Python puedes:**

+ Combinar documentos PDF.
+ Dividir archivos PDF.
+ Convertir PDF a otros formatos, y viceversa.
+ Manipular Anotaciones.
+ Trabajar con Imágenes en PDF, etc.
+ Puede probar nuestra [App gratuita](https://products.aspose.app/pdf/family) para probar la funcionalidad en línea.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
