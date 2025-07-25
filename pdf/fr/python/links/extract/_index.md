---
title: Extraire des liens d'un PDF via Cloud Python SDK
url: python/links/extract/
description: Extraire des hyperliens de PDF en utilisant Python avec Aspose.PDF Cloud SDK. Analyser les références du document.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Extraire des liens d'un PDF dans Python SDK" h2="Extraire un lien vers un document PDF en utilisant Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="pour Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK pour Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Comment extraire des liens d'un PDF via Cloud Python SDK " %}}

Pour obtenir des liens à partir de PDF, nous utiliserons
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). Ce SDK Cloud aide les programmeurs Python à développer des applications de création, d'annotation, d'édition et de conversion de PDF basées sur le cloud en utilisant le langage de programmation Python via Aspose.PDF REST API. Créez simplement un compte sur [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) et obtenez les informations de votre application. Une fois que vous avez l'App SID et la clé, vous êtes prêt à utiliser le Aspose.PDF Cloud Python SDK. Si le package python est hébergé sur Github, vous pouvez l'installer directement depuis Github :

{{% blocks/products/pf/agp/code-block title="Installation depuis Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Commande Console du Gestionnaire de Paquets" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Étapes pour extraire des liens d'un PDF via Python" %}}

{{% blocks/products/pf/agp/text %}}

Les développeurs Aspose.PDF Cloud peuvent facilement charger et obtenir des liens à partir d'un PDF en seulement quelques lignes de code.

{{% /blocks/products/pf/agp/text %}}

1. Installer [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. Téléchargez un document PDF sur le serveur Aspose Cloud
1. Téléchargez le document PDF traité depuis le serveur Aspose Cloud
1. Obtenez toutes les annotations d'hyperlien pour un document PDF spécifique
1. Obtenez l'annotation d'hyperlien en utilisant l'Id spécifique dans le document PDF

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Extraire des liens d'un PDF en utilisant Python" offSpacer="" %}}

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

{{% blocks/products/pf/agp/content h2="Travailler avec des liens dans un PDF" %}}

En extrayant des liens, on peut systématiquement vérifier la validité et la pertinence de chaque URL, en s'assurant que toutes les références sont à jour et fonctionnelles. Pour des tâches telles que le téléchargement de documents liés ou la réalisation d'analyses par lots, l'extraction des URL permet l'automatisation, économisant du temps et réduisant l'effort manuel.
Obtenez les liens à partir de documents PDF avec [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**Avec notre bibliothèque Python, vous pouvez :**

+ Combiner des documents PDF.
+ Diviser des fichiers PDF.
+ Convertir des PDF vers d'autres formats, et vice versa.
+ Manipuler les annotations.
+ Travailler avec des images dans un PDF, etc.
+ Vous pouvez essayer notre [application gratuite](https://products.aspose.app/pdf/family) pour tester la fonctionnalité en ligne.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
