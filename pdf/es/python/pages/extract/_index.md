---
title: Extraer páginas de PDF mediante Cloud Python SDK
url: python/pages/extract/
description: Extraer páginas específicas de documentos PDF utilizando Python con Aspose.PDF Cloud SDK.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Extraer páginas de PDF en Python SDK" h2="Extraer páginas de un documento PDF utilizando Cloud utilizando Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Cómo obtener páginas de PDF mediante Cloud Python SDK " %}}

Para extraer páginas de PDF, utilizaremos 
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). Este Cloud SDK ayuda a los programadores de Python a desarrollar aplicaciones basadas en la nube para crear, anotar, editar y convertir archivos PDF utilizando el lenguaje de programación Python a través de Aspose.PDF REST API. Simplemente, cree una cuenta en [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) y obtenga su información de la aplicación. Una vez que tenga el App SID y la clave, está listo para usar Aspose.PDF Cloud Python SDK. Si el paquete de Python está alojado en Github, puede instalarlo directamente desde Github:

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

{{% blocks/products/pf/agp/feature-section-col title="Paso a paso para obtener páginas de PDF mediante Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

Los desarrolladores de Aspose.PDF Cloud pueden cargar y extraer fácilmente páginas de PDF en solo unas pocas líneas de código.

{{% /blocks/products/pf/agp/text %}}

1. Instale [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. Cargue un documento PDF en el servidor de Aspose Cloud
1. Descargue el documento PDF procesado desde el servidor de Aspose Cloud
1. Obtenga la información de página del documento PDF

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Extraer páginas de PDF utilizando Python" offSpacer="" %}}

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
        LOCAL_RESULT_DOCUMENT_NAME = "output_sample.png"
        PAGE_NUMBER = 2

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

        def get_page_info(self):
            """ Get page information of the PDF document. """
            if self.pdf_api:
                result_pages: DocumentPagesResponse = self.pdf_api.get_page(Config.PDF_DOCUMENT_NAME, Config.PAGE_NUMBER)

                if result_pages.code == 200:
                    logging.info(f"Page #{Config.PAGE_NUMBER} information: {result_pages.page}")
                else:
                    logging.error(f"Failed to get the page #{Config.PAGE_NUMBER}.")

        def get_page_as_png(self):
            """ Get page information of the PDF document. """
            if self.pdf_api:
                try:
                    result_pages = self.pdf_api.get_page_convert_to_png(Config.PDF_DOCUMENT_NAME, Config.PAGE_NUMBER)
                    local_path = Config.LOCAL_FOLDER / Config.LOCAL_RESULT_DOCUMENT_NAME
                    shutil.move(result_pages, str(local_path))
                    logging.info(f"download_result(): File successfully downloaded: {local_path}")
                except Exception as e:
                    logging.error(f"download_result(): Failed to download file: {e}")

    if __name__ == "__main__":
        pdf_pages = PdfPages()
        pdf_pages.upload_document()
        pdf_pages.get_page_info()
        pdf_pages.get_page_as_png()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabajar con páginas en PDF" %}}

Extraer páginas de un PDF es una tarea común que sirve para diversos propósitos en diferentes contextos. Este proceso implica seleccionar páginas específicas de un documento más grande para crear un nuevo archivo PDF separado. Comprender las razones detrás de esta práctica puede ayudar a gestionar y utilizar los documentos PDF de manera efectiva. Los archivos PDF grandes pueden ser incómodos de compartir o almacenar. Al extraer solo las páginas necesarias, los usuarios pueden crear archivos más pequeños y manejables. Esto es especialmente útil cuando solo una parte del documento es relevante para un propósito específico. Por ejemplo, eliminar páginas innecesarias puede reducir significativamente el tamaño del archivo, facilitando su manejo y distribución. 
Extraer páginas permite a los usuarios reutilizar el contenido para diferentes aplicaciones. Por ejemplo, uno podría extraer páginas de un informe comprehensivo para crear un resumen independiente o aislar datos específicos para el análisis. Esto permite la reutilización del contenido existente sin necesidad de crear información desde cero. Extraiga las páginas de los documentos PDF con [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**Con nuestra biblioteca de Python puede:**

+ Combinar documentos PDF.
+ Dividir archivos PDF.
+ Convertir PDF a otros formatos, y viceversa.
+ Manipular anotaciones.
+ Trabajar con imágenes en PDF, etc.
+ Puede probar nuestra [aplicación gratuita](https://products.aspose.app/pdf/family) para probar la funcionalidad en línea.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
