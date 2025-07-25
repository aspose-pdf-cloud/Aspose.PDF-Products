---
title: Extraer enlaces de PDF a través de Cloud Python SDK
url: python/links/extract/
description: Extraer hipervínculos de PDFs usando Python con Aspose.PDF Cloud SDK. Analizar referencias de documentos.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Extraer enlaces de PDF en Python SDK" h2="Extraer un enlace a un documento PDF usando Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Cómo extraer enlaces de PDF a través de Cloud Python SDK " %}}

Para obtener enlaces de PDF, usaremos
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). Este Cloud SDK ayuda a los programadores de Python a desarrollar aplicaciones de creación, anotación, edición y conversión de PDFs basadas en la nube usando el lenguaje de programación Python a través de Aspose.PDF REST API. Simplemente crea una cuenta en [Aspose para Cloud](https://dashboard.aspose.cloud/#/apps) y obtén la información de tu aplicación. Una vez que tengas el App SID y la clave, estás listo para usar el Aspose.PDF Cloud Python SDK. Si el paquete de Python está alojado en Github, puedes instalarlo directamente desde Github:

{{% blocks/products/pf/agp/code-block title="Instalación desde Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Comando de la consola del gestor de paquetes" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Pasos para extraer enlaces de PDF a través de Python" %}}

{{% blocks/products/pf/agp/text %}}

Los desarrolladores de Aspose.PDF Cloud pueden cargar y obtener enlaces de PDF fácilmente con solo unas pocas líneas de código.

{{% /blocks/products/pf/agp/text %}}

1. Instalar [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. Subir un documento PDF al servidor de Aspose Cloud
1. Descargar el documento PDF procesado desde el servidor de Aspose Cloud
1. Obtener todas las anotaciones de hipervínculo para un documento PDF específico
1. Obtener la anotación de hipervínculo usando el Id específico en el documento PDF

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Extraer enlaces de PDF usando Python" offSpacer="" %}}

```python

    import shutil
    import json
    import logging
    from pathlib import Path
    from asposepdfcloud import ApiClient, PdfApi

    # Configure logging
    logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")


    class Config:
        """Configuration parameters."""
        CREDENTIALS_FILE = Path(r"C:\\Projects\\ASPOSE\\Pdf.Cloud\\Credentials\\credentials.json")
        LOCAL_FOLDER = Path(r"C:\Samples")
        PDF_DOCUMENT_NAME = "sample.pdf"
        LOCAL_RESULT_DOCUMENT_NAME = "output_sample.pdf"
        PAGE_NUMBER = 2
        LINK_FIND_ID = "GI5UO32UN5KVESKBMN2GS33OHMZTEMJMGUYDQLBTGYYCYNJSGE"


    class PdfLinks:
        """Class for managing PDF links using Aspose PDF Cloud API."""

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
                        raise ValueError("Error: Missing API keys in the credentials file.")
                    self.pdf_api = PdfApi(ApiClient(api_key, app_id))
            except (FileNotFoundError, json.JSONDecodeError, ValueError) as e:
                logging.error(f"Failed to load credentials: {e}")

        def upload_document(self):
            """Upload a PDF document to the Aspose Cloud server."""
            if self.pdf_api:
                file_path = Config.LOCAL_FOLDER / Config.PDF_DOCUMENT_NAME
                try:
                    self.pdf_api.upload_file(Config.PDF_DOCUMENT_NAME, str(file_path))
                    logging.info(f"File {Config.PDF_DOCUMENT_NAME} uploaded successfully.")
                except Exception as e:
                    logging.error(f"Failed to upload file: {e}")

        def show_links_array(self, links, prefix):
            for item in links:
                logging.info(f"{prefix} Link ID: '{item.id}' - Link Action: '{item.action}'")

        def get_all_links(self):
            """Get all hyperlink annotations for a specific PDF document."""
            if self.pdf_api:
                try:
                    response = self.pdf_api.get_page_link_annotations( Config.PDF_DOCUMENT_NAME, Config.PAGE_NUMBER)
                    if response.code == 200:
                        self.show_links_array(response.links.list, "All: ")
                    else:
                        logging.error(f"Failed to add link to the page. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"Error while adding link: {e}")

        def get_link_by_id(self, link_id: str):
            """Get hyperlink annotation using the specific Id in PDF document."""
            if self.pdf_api:
                try:
                    result_link = self.pdf_api.get_link_annotation(Config.PDF_DOCUMENT_NAME, link_id)
                    if result_link.code == 200:
                        self.show_links_array([result_link.link], "Find: ")
                except Exception as e:
                    logging.error(f"Error while adding link: {e}")

    if __name__ == "__main__":
        pdf_links = PdfLinks()
        pdf_links.upload_document()
        pdf_links.get_all_links()
        pdf_links.get_link_by_id(Config.LINK_FIND_ID)
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabajar con enlaces en PDF" %}}

Al extraer enlaces, se puede verificar sistemáticamente la validez y relevancia de cada URL, asegurando que todas las referencias estén actualizadas y sean funcionales. Para tareas como descargar documentos vinculados o realizar análisis por lotes, extraer URLs permite la automatización, ahorrando tiempo y reduciendo el esfuerzo manual.
Obtén los enlaces de documentos PDF con [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**Con nuestra biblioteca de Python puedes:**

+ Combinar documentos PDF.
+ Dividir archivos PDF.
+ Convertir PDF a otros formatos, y viceversa.
+ Manipular anotaciones.
+ Trabajar con imágenes en PDF, etc.
+ Puedes probar nuestra [aplicación gratuita](https://products.aspose.app/pdf/family) para probar la funcionalidad en línea.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
