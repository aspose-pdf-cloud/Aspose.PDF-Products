---
title: Extraer Marcadores de PDF a través de Cloud Python SDK
url: python/bookmarks/extract/
description: Extrae todos los marcadores de los PDFs usando Python con Aspose.PDF Cloud SDK. Analiza y exporta la estructura del documento.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Extraer Marcadores de PDF en Python SDK" h2="Extraer Marcadores a un Documento PDF usando Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Cómo extraer Marcadores de PDF a través de Cloud Python SDK " %}}

Para extraer Marcadores de PDF, utilizaremos [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). Este Cloud SDK ayuda a los programadores de Python a desarrollar aplicaciones basadas en la nube para crear, anotar, editar y convertir PDFs usando el lenguaje de programación Python a través de Aspose.PDF REST API. Simplemente crea una cuenta en [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) y obtén la información de tu aplicación. Una vez que tengas el App SID y la clave, estás listo para usar Aspose.PDF Cloud Python SDK. Si el paquete de python está alojado en Github, puedes instalar directamente desde Github:

{{% blocks/products/pf/agp/code-block title="Instalación desde Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Comando de Consola del Administrador de Paquetes" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Pasos para obtener Marcadores de PDF a través de Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

Los desarrolladores de Aspose.PDF Cloud pueden cargar y extraer fácilmente Marcadores de PDF en solo unas pocas líneas de código.

{{% /blocks/products/pf/agp/text %}}

1. Instalar [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. Subir un documento PDF al servidor de Aspose Cloud
1. Obtener el marcador para un documento PDF específico usando la ruta del marcador

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Extraer Marcadores de PDF usando Python" offSpacer="" %}}

```python

    import shutil
    import json
    import logging
    from pathlib import Path
    from asposepdfcloud import ApiClient, PdfApi, BookmarkResponse

    # Configure logging
    logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")


    class Config:
        """Configuration parameters."""
        CREDENTIALS_FILE = Path(r"C:\\Projects\\ASPOSE\\Pdf.Cloud\\Credentials\\credentials.json")
        LOCAL_FOLDER = Path(r"C:\Samples")
        PDF_DOCUMENT_NAME = "sample.pdf"
        BOOKMARK_PATH = "/5"

    class PdfBookmarks:
        """Class for managing PDF bookmarks using Aspose PDF Cloud API."""

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

        def get_bookmark(self):
            """Get bookmark for a specific PDF document using bookmark path."""    
            if self.pdf_api:
                try:
                    response : BookmarkResponse = self.pdf_api.get_bookmark( Config.PDF_DOCUMENT_NAME, Config.BOOKMARK_PATH)
                    if response.code == 200:
                        logging.info(f"Found bookmark => level: '{response.bookmark.level}' - action: '{response.bookmark.action}' - title: '{response.bookmark.title}'")
                    else:
                        logging.error(f"Failed to find bookmark for the document. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"Error while find bookmark: {e}")

    if __name__ == "__main__":
        pdf_bookmarks = PdfBookmarks()
        pdf_bookmarks.upload_document()
        pdf_bookmarks.get_bookmark()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabajar con Marcadores en PDF" %}}

Extraer marcadores de un PDF mejora la usabilidad del documento, automatiza el procesamiento de contenido y mejora la capacidad de búsqueda. Es especialmente útil para empresas, investigadores y profesionales que manejan documentos PDF grandes o estructurados.
Extrae los Marcadores de documentos PDF con [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**Con nuestra biblioteca de Python puedes:**

+ Combinar documentos PDF.
+ Dividir archivos PDF.
+ Convertir PDF a otros formatos y viceversa.
+ Manipular Anotaciones.
+ Trabajar con Imágenes en PDF, etc.
+ Puedes probar nuestras [aplicaciones gratuitas](https://products.aspose.app/pdf/family/) para testar la funcionalidad en línea.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
