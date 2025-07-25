---
title: Apagar Links de PDF via Cloud Python SDK
url: python/links/delete/
description: Apague links de documentos PDF em Python usando Aspose.PDF Cloud SDK. Remova URLs quebradas ou desatualizadas.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Apagar Links de PDF no Python SDK" h2="Remova Links de um Documento PDF usando Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="para Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK para Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Como apagar Links de PDF via Cloud Python SDK " %}}

Para apagar links de PDF, usaremos
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). Este Cloud SDK auxilia programadores Python a desenvolver aplicações de criador, anotador, editor e conversor de PDF baseado em nuvem usando a API REST Aspose.PDF. Basta criar uma conta em [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) e obter informações da aplicação. Uma vez que tenha o App SID & chave, você está pronto para tentar o Aspose.PDF Cloud Python SDK. Se o pacote python estiver hospedado no Github, você pode instalar diretamente do Github:

{{% blocks/products/pf/agp/code-block title="Instalação do Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Comando de Gerenciador de Pacote" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Passos para apagar Links de PDF via Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

Desenvolvedores Aspose.PDF Cloud podem facilmente carregar & apagar links de PDF em apenas algumas linhas de código.

{{% /blocks/products/pf/agp/text %}}

1. Instale [Python SDK](https://pypi.org/project/asposepdfcloud/)
1. Faça upload de um documento PDF para o servidor Aspose Cloud
1. Baixe o documento PDF processado do servidor Aspose Cloud
1. Obtenha todas as anotações de hiperlinks para um documento PDF específico
1. Apague todos os Links

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Apagar Links de PDF usando Python" offSpacer="" %}}

```python

    import shutil
    import json
    import logging
    from pathlib import Path
    from asposepdfcloud import ApiClient, PdfApi, AsposeResponse

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

        def download_result(self):
            """Download the processed PDF document from the Aspose Cloud server."""
            if self.pdf_api:
                try:
                    temp_file = self.pdf_api.download_file(Config.PDF_DOCUMENT_NAME)
                    local_path = Config.LOCAL_FOLDER / Config.LOCAL_RESULT_DOCUMENT_NAME
                    shutil.move(temp_file, str(local_path))
                    logging.info(f"download_result(): File successfully downloaded: {local_path}")
                except Exception as e:
                    logging.error(f"download_result(): Failed to download file: {e}")

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
                    logging.error(f"Error while adding link: No links found - {e}")

        def remove_link_by_id(self):
            if self.pdf_api:
                response: AsposeResponse = self.pdf_api.delete_link_annotation(Config.PDF_DOCUMENT_NAME, Config.LINK_FIND_ID)

                if response.code == 200:
                    logging.info("Link annotation with ID " + Config.LINK_FIND_ID + " has been removed.")
                else:
                    logging.erro("Failed to remove link annotation with ID " + Config.LINK_FIND_ID)

    if __name__ == "__main__":
        pdf_links = PdfLinks()
        pdf_links.upload_document()
        pdf_links.get_all_links()
        pdf_links.remove_link_by_id()
        pdf_links.download_result()
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabalhe com links em PDF" %}}

Com o tempo, hiperlinks podem se tornar obsoletos ou levá-lo a páginas que não existem mais. Esses links quebrados podem frustrar os leitores e diminuir a credibilidade do documento. Remover esses links garante que o conteúdo permaneça acurado e confiável.​
Remova os links de documentos PDF com [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**Com nossa biblioteca Python você pode:**

+ Combine documentos PDF.
+ Divida Arquivos PDF.
+ Converta PDF para outros formatos e vice-versa.
+ Manipule Anotações.
+ Trabalhe com Imagens em PDF, etc.
+ Você pode experimentar nosso [App gratuito](https://products.aspose.app/pdf/family) para testar a funcionalidade online.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
