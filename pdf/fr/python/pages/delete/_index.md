---
title: Supprimer des Pages du PDF via Cloud Python SDK
url: python/pages/delete/
description: Supprimer des pages de fichiers PDF en Python en utilisant Aspose.PDF Cloud SDK. Automatisez le nettoyage de documents.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Supprimer des Pages d'un PDF dans Python SDK" h2="Retirer des Pages d'un Document PDF en utilisant Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="pour Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK pour Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Comment retirer des Pages du PDF via Cloud Python SDK " %}}

Pour supprimer des Pages du PDF, nous utiliserons
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). Ce Cloud SDK aide les programmeurs Python à développer des applications de création, annotation, édition et conversion de PDF basées sur le cloud en utilisant le langage de programmation Python via Aspose.PDF REST API. Créez simplement un compte sur [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) et obtenez vos informations d'application. Une fois que vous avez le SID de l'application et la clé, vous êtes prêt à utiliser Aspose.PDF Cloud Python SDK. Si le package python est hébergé sur Github, vous pouvez l'installer directement depuis Github :

{{% blocks/products/pf/agp/code-block title="Installation depuis Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Commande de la Console du Gestionnaire de Paquets" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Étapes pour supprimer des Pages du PDF via Python" %}}

{{% blocks/products/pf/agp/text %}}

Les développeurs d'Aspose.PDF Cloud peuvent facilement charger et supprimer des pages de PDF en quelques lignes de code.

{{% /blocks/products/pf/agp/text %}}

1. Installez le [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. Téléchargez un document PDF sur le serveur Aspose Cloud
1. Téléchargez le document PDF traité depuis le serveur Aspose Cloud
1. Supprime une page spécifique d'un document PDF

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Retirer des Pages du PDF en utilisant Python" offSpacer="" %}}

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

        def delete_page(self):
            """ Deletes a specific page from a PDF document. """
            if self.pdf_api:
                result = self.pdf_api.delete_page(Config.PDF_DOCUMENT_NAME, Config.PAGE_NUMBER)
                if result.code == 200:
                    logging.info(f"Page #{Config.PAGE_NUMBER} deleted.")
                else:
                    logging.error(f"Failed to delete page #{Config.PAGE_NUMBER}.")

    if __name__ == "__main__":
        pdf_pages = PdfPages()
        pdf_pages.upload_document()
        pdf_pages.delete_page()
        pdf_pages.download_result()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Travailler avec les Pages dans le PDF" %}}

​​Supprimer des pages d'un PDF est une tâche courante qui sert plusieurs objectifs, améliorant à la fois la fonctionnalité et la sécurité du document. Les PDF peuvent devenir ingérables lorsqu'ils contiennent des pages inutiles ou redondantes, entraînant des tailles de fichiers plus grandes. En supprimant ces pages superflues, la taille globale du fichier est réduite, rendant le document plus facile à gérer pour le stockage et plus rapide à télécharger ou à téléverser. Au fil du temps, les documents peuvent accumuler des informations obsolètes ou non pertinentes. Supprimer ces pages garantit que le contenu reste actuel et pertinent pour le public visé. Supprimer des pages d'un PDF est une approche pratique pour optimiser la taille du document, améliorer sa pertinence, protéger les informations sensibles, améliorer la navigation, maintenir la précision et faciliter la collaboration. Retirez les Pages des documents PDF avec [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**Avec notre bibliothèque Python, vous pouvez :**

+ Combiner des documents PDF.
+ Diviser des fichiers PDF.
+ Convertir des PDF vers d'autres formats, et vice versa.
+ Manipuler les annotations.
+ Travailler avec des images dans le PDF, etc.
+ Vous pouvez essayer notre [application gratuite](https://products.aspose.app/pdf/family) pour tester la fonctionnalité en ligne.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
