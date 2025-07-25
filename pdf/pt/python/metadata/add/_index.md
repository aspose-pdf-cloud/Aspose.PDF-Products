---
title: Adicionar Metadados via Cloud Python SDK
url: python/metadata/add/
description: Adicione metadados aos PDFs no Python usando o Aspose.PDF Cloud SDK. Melhore a organização e a localização de documentos.
lastmod: 2024-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Adicionar Metadados a PDF no Python SDK" h2="Adiciona um Metadados a um Documento PDF usando Cloud Python SDK." logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="para Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK para Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Como criar Metadados via Cloud Python SDK" %}}

Para criar Metadados, usaremos
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/)
Este Cloud SDK auxilia programadores Python no desenvolvimento de apps baseados em nuvem para criação, anotação, edição e conversão de PDFs usando a linguagem de programação Python via Aspose.PDF REST API. Simplesmente crie uma conta no [Aspose para Cloud](https://dashboard.aspose.cloud/#/apps) e obter suas informações de aplicação. Uma vez que você tenha o App SID e a chave, você está pronto para usar o Aspose.PDF Cloud Python SDK. Se o pacote Python estiver hospedado no Github, você pode instalá-lo diretamente do Github:

{{% blocks/products/pf/agp/code-block title="Instalação a partir do Github" offSpacer="true" %}}

```bash

     
    pip install git+https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python.git


```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/code-block title="Comando Fidelidade Console" offSpacer="true" %}}

```bash
     
    pip install asposepdfcloud

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Passos para criar um Metadados via Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

Os desenvolvedores do Aspose.PDF Cloud podem facilmente carregar e criar metadados em PDF com apenas algumas linhas de código.

{{% /blocks/products/pf/agp/text %}}

1. Instale [Python SDK](https://pypi.org/project/asposepdfcloud/).
1. Vá ao [Painel do Aspose Cloud](https://dashboard.aspose.cloud/).
1. Crie uma nova [Conta](https://docs.aspose.cloud/display/storagecloud/Creating+and+Managing+Account) para acessar todas as aplicações e serviços ou faça login na sua conta.
1. Clique em Aplicações no menu à esquerda para obter ID e Segredo do Cliente.
1. Consulte o [Guia do Desenvolvedor](https://docs.aspose.cloud/pdf/developer-guide/) para adicionar metadados em PDF via Python.
1. Consulte nosso [repositório GitHub](https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python/) para obter uma lista completa de APIs juntamente com exemplos funcionais.
1. Consulte a [página de Referência da API](https://reference.aspose.cloud/pdf/#/Document) para a descrição dos parâmetros de API.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Criar Propriedades de Metadados XMP em PDF usando Python" offSpacer="" %}}

```python

    file_name = 'pages.pdf'
    self.uploadFile(file_name)

    date = '2024-10-27T09:59:52+02:00'
    metadata = asposepdfcloud.models.XmpMetadata(properties=[
        # Add Default property
        asposepdfcloud.models.XmpMetadataProperty(key = "BaseURL", value = "http://www.somename.com/path"),
        # Add user defined property
        asposepdfcloud.models.XmpMetadataProperty(key = "pdf:Prop", value = "PropValue", namespace_uri = "http://ns.adobe.com/pdf/1.3/"),
    ])
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabalhar com Metadados em PDF" %}}

Trabalhar com metadados em arquivos PDF é importante. Metadados como o campo título, autor e tema ajudam a classificar documentos, tornando mais fácil gerenciar grandes coleções de documentos ao fornecer uma visão rápida do conteúdo sem abrir arquivos.
Os metadados também melhoram a pesquisa de arquivos permitindo que você pesquise por palavras-chave e atributos. Isso é particularmente valioso em sistemas onde a recuperação rápida de documentos é essencial.

**Com nossa biblioteca Python você pode:**

+ Combinar documentos PDF.
+ Dividir arquivos PDF.
+ Converter PDF para outros formatos e vice-versa.
+ Manipular Anotações.
+ Trabalhar com Imagens em PDF, etc.
+ Você pode testar nossa [aplicação gratuita](https://products.aspose.app/pdf/metadata) para adicionar metadados a arquivos PDF online e testar a funcionalidade.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}


{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
