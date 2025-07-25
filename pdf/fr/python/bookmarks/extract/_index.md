---
title: Extraire des signets d'un PDF via Cloud Python SDK
url: python/bookmarks/extract/
description: Extraire tous les signets des PDF en utilisant Python avec Aspose.PDF Cloud SDK. Analyser et exporter la structure du document.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Extraire des signets d'un PDF dans Python SDK" h2="Extraire des signets vers un document PDF en utilisant Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="pour Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK pour Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Comment extraire des signets d'un PDF via Cloud Python SDK " %}}

Pour extraire des signets d'un PDF, nous utiliserons [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). Ce Cloud SDK aide les programmeurs Python à développer des applications de création, annotation, édition et conversion de PDF basées sur le cloud en utilisant le langage de programmation Python via Aspose.PDF REST API. Créez simplement un compte sur [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) et obtenez les informations de votre application. Une fois que vous avez l'App SID & la clé, vous êtes prêt à essayer Aspose.PDF Cloud Python SDK. Si le package Python est hébergé sur Github, vous pouvez l'installer directement depuis Github:

{{% blocks/products/pf/agp/code-block title="Installation depuis Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Commande de la console du gestionnaire de packages" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Étapes pour obtenir des signets d'un PDF via Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

Les développeurs Aspose.PDF Cloud peuvent facilement charger et extraire des signets d'un PDF en quelques lignes de code.

{{% /blocks/products/pf/agp/text %}}

1. Installez [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. Téléchargez un document PDF sur le serveur Aspose Cloud
1. Obtenez un signet pour un document PDF spécifique en utilisant le chemin du signet

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Extraire des signets d'un PDF en utilisant Python" offSpacer="" %}}

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

{{% blocks/products/pf/agp/content h2="Travailler avec des signets dans un PDF" %}}

Extraire des signets d'un PDF améliore l'utilisabilité du document, automatise le traitement du contenu et améliore la recherchabilité. C'est particulièrement utile pour les entreprises, les chercheurs et les professionnels traitant de documents PDF volumineux ou structurés.
Extrayez les signets des documents PDF avec [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**Avec notre bibliothèque Python, vous pouvez :**

+ Combiner des documents PDF.
+ Diviser des fichiers PDF.
+ Convertir des PDF en d'autres formats, et vice versa.
+ Manipuler des annotations.
+ Travailler avec des images dans un PDF, etc.
+ Vous pouvez essayer nos [applications gratuites](https://products.aspose.app/pdf/family/) pour tester la fonctionnalité en ligne.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
