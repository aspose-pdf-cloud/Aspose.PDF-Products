---
title: Ajouter des pages au PDF via Cloud Python SDK
url: python/pages/add/
description: Insérez de nouvelles pages dans les fichiers PDF avec Python et Aspose.PDF Cloud SDK. Élargissez dynamiquement le contenu.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Ajouter des pages au PDF dans Python SDK" h2="Ajouter des pages au document PDF en utilisant Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="for Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK for Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Comment ajouter des pages au PDF via Cloud Python SDK " %}}

Pour ajouter des pages dans un PDF, nous utiliserons
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). Ce Cloud SDK aide les programmeurs Python à développer des applications de création, d'annotation, d'édition et de conversion de PDF basées sur le cloud en utilisant le langage de programmation Python via Aspose.PDF REST API. Créez simplement un compte sur [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) et obtenez les informations de votre application. Une fois que vous avez l'App SID & clé, vous êtes prêt à utiliser Aspose.PDF Cloud Python SDK. Si le package python est hébergé sur Github, vous pouvez l'installer directement depuis Github :

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

{{% blocks/products/pf/agp/feature-section-col title="Étapes pour ajouter des pages dans un PDF via Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

Les développeurs Aspose.PDF Cloud peuvent facilement charger et ajouter des pages à un PDF en seulement quelques lignes de code.

{{% /blocks/products/pf/agp/text %}}

1. Installez [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. Téléchargez un document PDF sur le serveur Aspose Cloud
1. Téléchargez le document PDF traité depuis le serveur Aspose Cloud
1. Ajoutez une nouvelle page à la fin du document PDF

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Ajouter des pages au PDF en utilisant Python" offSpacer="" %}}

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

{{% blocks/products/pf/agp/content h2="Travailler avec les pages dans un PDF" %}}

L'ajout de pages à un document PDF est une tâche courante qui sert divers objectifs, améliorant la fonctionnalité, l'organisation et la compréhension du document. Souvent, il est nécessaire d'inclure des contenus supplémentaires tels que des annexes, des références ou des données mises à jour qui n'étaient pas disponibles lors de la création initiale du document. Ajouter de nouvelles pages permet l'intégration harmonieuse de ces informations supplémentaires, garantissant que le document reste actuel et complet. Ajouter des pages à un PDF est une pratique polyvalente qui répond à plusieurs besoins, de l'amélioration du contenu et de la structure à la garantie de la conformité et à la facilitation de la collaboration. En comprenant les exigences spécifiques et en utilisant les outils appropriés, les utilisateurs peuvent gérer et modifier efficacement leurs documents PDF pour répondre à divers objectifs.
Ajoutez les pages aux documents PDF avec [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**Avec notre bibliothèque Python, vous pouvez :**

+ Combiner des documents PDF.
+ Diviser des fichiers PDF.
+ Convertir des PDF en d'autres formats, et vice versa.
+ Manipuler les annotations.
+ Travailler avec les images dans un PDF, etc.
+ Vous pouvez essayer notre [application gratuite](https://products.aspose.app/pdf/family) pour tester la fonctionnalité en ligne.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
