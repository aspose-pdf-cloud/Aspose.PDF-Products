---
title: Obtenir une signature à partir d'un PDF via le Cloud Python SDK
url: python/signature/get/
description: Aspose.PDF Cloud vous permet d'extraire une signature d'un document PDF. Consultez le code source Python pour obtenir une signature à partir d'un fichier PDF.
lastmod: 2025-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Obtenir une signature à partir d'un PDF dans le SDK Python" h2="Extraire une signature d'un document PDF en utilisant le Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="pour Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK pour Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Comment obtenir une signature à partir d'un PDF via le Cloud Python SDK " %}}

Pour obtenir une signature à partir d'un PDF, nous utiliserons
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). Ce SDK Cloud aide les programmeurs Python à développer des applications créatrices, annotatrices, éditrices et convertisseuses de PDF basées sur le cloud en utilisant le langage de programmation Python via l'API REST Aspose.PDF. Créez simplement un compte sur [Aspose pour le Cloud](https://dashboard.aspose.cloud/#/apps) et obtenez les informations de votre application. Une fois que vous avez l'App SID & clé, vous êtes prêt à utiliser le Aspose.PDF Cloud Python SDK. Si le package python est hébergé sur Github, vous pouvez l'installer directement depuis Github :

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

{{% blocks/products/pf/agp/feature-section-col title="Étapes pour obtenir une signature à partir d'un PDF via le SDK Python" %}}

{{% blocks/products/pf/agp/text %}}

Les développeurs Aspose.PDF Cloud peuvent facilement charger et obtenir une signature d'un PDF en seulement quelques lignes de code.

{{% /blocks/products/pf/agp/text %}}

1. Installer [Python SDK](https://pypi.org/project/asposepdfcloud/).
1. Télécharger des documents PDF sur le cloud, et est configuré pour télécharger des documents traités.
1. Extraire les champs de signature dans le document PDF

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Extraire une signature d'un PDF en utilisant Python" offSpacer="" %}}

```python

    import json
    import logging
    from pathlib import Path
    from asposepdfcloud import ApiClient, PdfApi

    # Configure logging
    logging.basicConfig(level=logging.INFO, format="%(asctime)s - %(levelname)s - %(message)s")


    class Config:
        """Configuration parameters."""
        CREDENTIALS_FILE = Path(r".../../../credentials.json")
        LOCAL_FOLDER = Path(r"C:\Samples")
        PDF_DOCUMENT_NAME = "sample-signed.pdf"


    class PdfSignatures:
        """Class for managing PDF signatures using Aspose PDF Cloud API."""
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

        def upload_document(self):
            """Upload a PDF document to the Aspose Cloud server."""
            if self.pdf_api:
                file_path = Config.LOCAL_FOLDER / Config.PDF_DOCUMENT_NAME
                try:
                    self.pdf_api.upload_file(Config.PDF_DOCUMENT_NAME, str(file_path))
                    logging.info(f"File {Config.PDF_DOCUMENT_NAME} uploaded successfully.")
                except Exception as e:
                    logging.error(f"Failed to upload file: {e}")

        def _show_signature_fields_array(self, fields):
            if len(fields.list) == 0:
                logging.info(f"Signature fileds is empty!")
            else:
                for item in fields.list:
                    logging.info(f"Signature filed ID: '{item.signature.contact}'")

        def get_signature_fileds(self):
            """Extract signature fields in the PDF document."""
            if self.pdf_api:          
                try:
                    response = self.pdf_api.get_document_signature_fields(Config.PDF_DOCUMENT_NAME)
                    if response.code == 200:
                        logging.info(f"get_signature_fileds(): Signature fields successfully extracted in to the '{Config.PDF_DOCUMENT_NAME}' documen:")
                        self._show_signature_fields_array(response.fields)
                    else:
                        logging.error(f"get_signature_fileds(): Failed to extract signatures in the document. Response code: {response.code}")
                except Exception as e:
                    logging.error(f"get_signature_fileds(): Error while extrcting signature: {e}")


    if __name__ == "__main__":
        pdf_sign = PdfSignatures()
        pdf_sign.upload_document()
        pdf_sign.get_signature_fileds()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Travailler avec la signature dans un PDF" %}}

Extraire des signatures d'un PDF est essentiel pour vérifier l'authenticité du document, auditer les transactions numériques et assurer la conformité avec les normes légales ou réglementaires. En récupérant les champs de signature, les organisations peuvent confirmer qui a signé le document, quand il a été signé, et si le document a été modifié depuis. Ce processus aide à maintenir la confiance dans les flux de travail numériques et fournit une preuve traçable d'approbation ou d'accord.
Extraire une signature des documents PDF avec [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**Avec notre bibliothèque Python vous pouvez :**

+ Combiner des documents PDF.
+ Diviser des fichiers PDF.
+ Convertir des PDF en d'autres formats, et vice versa.
+ Manipuler les annotations.
+ Travailler avec des images dans le PDF, etc.
+ Vous pouvez essayer notre [application gratuite](https://products.aspose.app/pdf/family) pour tester la fonctionnalité en ligne.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
