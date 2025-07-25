---
title: Converter PDF para XLSX via Python Cloud SDK
url: python/conversion/pdf-to-xlsx/
description: Exporte dados de PDF para o formato Excel (XLSX) usando Python e Aspose.PDF Cloud SDK. Extraia dados estruturados.
lastmod: 2024-10-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Converter PDF para XLSX no Python SDK" h2="Exporte documentos PDF para vários formatos, incluindo XLSX, com Aspose.PDF Cloud Python SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOC" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Python SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" DocsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python" >}}

{{% blocks/products/pf/agp/content h2="Como Converter PDF para XLSX Usando Python SDK" %}}

Para converter PDF para XLSX, usaremos
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/)
Este Cloud SDK auxilia programadores Python no desenvolvimento de aplicativos de criação, anotação, edição e conversão de PDFs baseados em nuvem usando a linguagem de programação Python via Aspose.PDF REST API. Basta criar uma conta no [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) e obter as informações do seu aplicativo. Uma vez que você tenha o App SID e a chave, estará pronto para usar o Aspose.PDF Cloud Python SDK. Se o pacote Python estiver hospedado no Github, você pode instalá-lo diretamente de lá:

{{% blocks/products/pf/agp/code-block title="Instalação do Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Comando do Console do Gerenciador de Pacotes" offSpacer="true" %}}

```bash

     
    pip install asposepdfcloud
       

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Passos para Converter PDF para XLSX via Python" %}}

{{% blocks/products/pf/agp/text %}}

Desenvolvedores do Aspose.PDF Cloud Python podem facilmente carregar e converter arquivos PDF para XLSX com apenas algumas linhas de código.

{{% /blocks/products/pf/agp/text %}}

1. Definir Nome do Arquivo de Entrada
1. Definir Nome do Arquivo de Saída
1. Criar Dicionário de Opções
1. Chamar Método da API

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="Requisitos do Sistema" %}}

{{% blocks/products/pf/agp/text %}}

É fácil começar com o Aspose.PDF Cloud Python SDK:

* Python 2.7 e 3.4+

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Este código de exemplo mostra a conversão de PDF para XLSX no Cloud Python SDK" offSpacer="" %}}

```python

    file_name = 'pages.pdf'
    result_file_name = "result.xls"

    opts = {
        "file": test_data_path + file_name
    }

    response = pdf_api.put_pdf_in_request_to_xls(
        temp_folder + '/' + result_file_name, **opts)
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="Outras Conversões Suportadas" subTitle="Você também pode converter PDF em muitos outros formatos de arquivo, incluindo alguns listados abaixo." >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/python/conversion/pdf-to-word/" name="PDF PARA WORD" description="Microsoft Word DOC & DOC" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/python/conversion/pdf-to-excel/" name="PDF PARA EXCEL" description="Microsoft Excel" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/python/conversion/pdf-to-jpeg/" name="PDF PARA JPEG" description="Imagem JPEG" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/python/conversion/pdf-to-png/" name="PDF PARA PNG" description="Gráficos de Rede Portáteis" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/python/conversion/pdf-to-pptx/" name="PDF PARA PPTX" description="Formato de Apresentação Open XML" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}


