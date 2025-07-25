---
title: Adicionar Texto ao PDF via Cloud Python SDK
url: python/text/add/
description: Insira novo texto em documentos PDF usando Python e Aspose.PDF Cloud SDK.
lastmod: 2024-10-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Adicionar Texto ao PDF no Python SDK" h2="Adicionar um Texto a um Documento PDF usando Cloud Python SDK" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" sourceAdditionalConversionTag="" additionalConversionTag="" pfName="Aspose.PDF" subTitlepfName="para Python" downloadUrl="" fileiconsmall1="PNG" fileiconsmall2="JPG" fileiconsmall3="BMP" fileiconsmall4="TIFF" fileiconsmall5="PDF" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud " subTitlepfName="SDK para Python" >}}
{{< blocks/products/pf/sub-menu autoGeneratedVersion="true" logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-python.svg" apiHomeLink="" codeSamplesLink="https://github.com/aspose-pdf-cloud" liveDemosLink="https://products.aspose.cloud/pdf/" docsLink="https://docs.aspose.cloud/pdf/" installationsDocsLink="https://docs.aspose.cloud/pdf/" nugetLink="https://www.nuget.org/packages/Aspose.Pdf-Cloud" nugetPackageName="" downloadAsLink="https://releases.aspose.cloud/pdf/python/" learnAsLink="https://docs.aspose.cloud/pdf/" apiReference="" mavenRepoLink="https://reference.aspose.cloud/pdf/" >}}

{{% blocks/products/pf/agp/content h2="Como adicionar Texto ao PDF via Cloud Python SDK " %}}

O seguinte trecho de código, do Aspose.PDF, carrega um arquivo PDF e uma fonte personalizada, define o item com o estilo personalizado (cor do texto, cor de fundo, fonte, rotação, alinhamento e espaçamento) e especifica o retângulo no qual o parágrafo deve ser colocado na página. Isso é útil para adicionar texto estilizado a uma certa área da página PDF.
Para adicionar texto ao PDF, usaremos
[Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/). Este Cloud SDK auxilia programadores Python no desenvolvimento de aplicativos de criação, anotação, edição e conversão de PDF baseados em nuvem usando a linguagem de programação Python via Aspose.PDF REST API. Basta criar uma conta em [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) e obter as informações do seu aplicativo. Assim que você tiver o App SID & key, você está pronto para usar o Aspose.PDF Cloud Python SDK. Se o pacote python estiver hospedado no Github, você pode instalar diretamente do Github:

{{% blocks/products/pf/agp/code-block title="Instalação a partir do Github" offSpacer="true" %}}

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

{{% blocks/products/pf/agp/feature-section-col title="Etapas para adicionar Texto ao PDF via Python SDK" %}}

{{% blocks/products/pf/agp/text %}}

Os desenvolvedores do Aspose.PDF Cloud podem facilmente carregar e adicionar Texto ao PDF em apenas algumas linhas de código.

{{% /blocks/products/pf/agp/text %}}

1. Instale [Python SDK](https://pypi.org/project/asposepdfcloud/).
1. Vá ao [Painel da Aspose Cloud](https://dashboard.aspose.cloud/).
1. Crie uma nova [Conta](https://docs.aspose.cloud/display/storagecloud/Creating+and+Managing+Account) para acessar todos os aplicativos e serviços ou faça login na sua conta.
1. Clique em Aplicativos no menu à esquerda para obter o Id do Cliente e o Segredo do Cliente.
1. Confira o [Guia do Desenvolvedor](https://docs.aspose.cloud/pdf/developer-guide/) para adicionar Texto ao PDF via Python.
1. Confira nosso [repositório GitHub](https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-python/) para uma lista completa de APIs junto com exemplos funcionais.
1. Confira a [página de Referência da API](https://reference.aspose.cloud/pdf/#/Document) para a descrição dos parâmetros das APIs.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Adicionar Texto ao PDF usando Python" offSpacer="" %}}

```python

    file_name = 'pages.pdf'
    self.uploadFile(file_name)

    # Upload font file
    font_file = 'Righteous-Regular.ttf'
    self.uploadFile(font_file)

    # Specify the page number and define the text area (rectangle)
    page_number = 1
    rectangle = asposepdfcloud.models.Rectangle(100, 100, 300, 300)

    # Define colors for text foreground and background
    foreground_color = asposepdfcloud.models.Color(a=0x00, r=0x00, g=0xFF, b=0x00)  # Blue foreground
    background_color = asposepdfcloud.models.Color(a=0x00, r=0xFF, g=0x00, b=0x00)  # Green background

    # Define text properties using TextState
    text_state = asposepdfcloud.models.TextState(
        font_size=10,
        font='Righteous',
        foreground_color=foreground_color,
        background_color=background_color,
        font_style=asposepdfcloud.models.FontStyles.REGULAR,
        font_file=self.temp_folder + '/' + font_file
    )

    # Create a text segment with specified text and text state
    segment = asposepdfcloud.models.Segment(value='segment 1', text_state=text_state)

    # Add the segment to a text line with right horizontal alignment
    text_line = asposepdfcloud.models.TextLine(
        horizontal_alignment=asposepdfcloud.models.TextHorizontalAlignment.RIGHT,
        segments=[segment]
    )

    # Create a paragraph with the text line and set additional properties
    paragraph = asposepdfcloud.models.Paragraph(lines=[text_line])
    paragraph.rectangle = rectangle
    paragraph.left_margin = 10
    paragraph.right_margin = 10
    paragraph.top_margin = 20
    paragraph.bottom_margin = 20
    paragraph.horizontal_alignment = asposepdfcloud.models.TextHorizontalAlignment.FULLJUSTIFY
    paragraph.line_spacing = asposepdfcloud.models.LineSpacing.FONTSIZE
    paragraph.rotation = 10
    paragraph.subsequent_lines_indent = 20
    paragraph.vertical_alignment = asposepdfcloud.models.VerticalAlignment.CENTER
    paragraph.wrap_mode = asposepdfcloud.models.WrapMode.BYWORDS

    # Set the options for adding the paragraph
    opts = {
        "paragraph": paragraph,
        "folder": self.temp_folder
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabalhar com Texto em PDF" %}}

O texto pode ser adicionado dinamicamente para personalizar um PDF para um usuário específico, como adicionar seu nome ou mensagem personalizada. Isso é frequentemente usado em materiais de marketing ou para relatórios personalizados. Adicionar texto em fontes, cores e alinhamentos específicos pode tornar certas seções mais legíveis e visualmente atraentes, criando uma melhor experiência para o usuário. Adições de texto podem ajudar a manter informações consistentes em diferentes versões de PDF, evitando edições manuais e garantindo que as informações essenciais permaneçam no lugar.
Adicione o Texto em documentos PDF com [Aspose.PDF Cloud Python SDK](https://products.aspose.cloud/pdf/python/).

**Com nossa biblioteca Python você pode:**

+ Combinar documentos PDF.
+ Dividir arquivos PDF.
+ Converter PDF para outros formatos, e vice-versa.
+ Manipular Anotações.
+ Trabalhar com Imagens em PDF, etc.
+ Você pode experimentar nosso [App gratuito](https://products.aspose.app/pdf/editor) para adicionar o texto em arquivos PDF online e testar a funcionalidade.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
