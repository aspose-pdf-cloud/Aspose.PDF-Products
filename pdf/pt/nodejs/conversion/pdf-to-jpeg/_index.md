---
title: Converter PDF para JPEG via Cloud Node.js SDK
url: nodejs/conversion/pdf-to-jpeg/
description: Transforme arquivos PDF em imagens JPEG com Aspose.PDF Cloud SDK para Node.js. Fácil compartilhamento e publicação.
lastmod: 2022-03-17
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Converter PDF para JPEG no Node.js SDK" h2="Exporte documentos PDF para múltiplos formatos, incluindo JPEG, com Aspose.PDF Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Como Converter PDF para JPEG Usando Node.js SDK" %}}

Para converter PDF para JPEG, usaremos
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)
Este Cloud SDK auxilia programadores Node.js a desenvolver aplicativos de criação, anotação, edição e conversão de PDF baseados em nuvem usando a linguagem de programação Node.js via Aspose.PDF REST API. Abra
[NPM](https://www.npmjs.com/package/asposepdfcloud)
gerenciador de pacotes, procure por
Aspose.PDF Cloud,
e instale. Você também pode usar o seguinte comando do Console do Gerenciador de Pacotes.

{{% blocks/products/pf/agp/code-block title="Comando do Console do Gerenciador de Pacotes" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Passos para Converter PDF para JPEG via Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Desenvolvedores Aspose.PDF Cloud Node.js podem facilmente carregar e converter arquivos PDF para JPEG em apenas algumas linhas de código.

{{% /blocks/products/pf/agp/text %}}

1. Carregue seu Segredo e Chave da Aplicação a partir do arquivo JSON ou configure as credenciais de outra forma
1. Crie um objeto para conectar-se à API Cloud
1. Faça o upload do seu arquivo de documento
1. Realize a conversão usando getPageConvertToJpeg
1. Baixe o resultado se necessário

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Este código de exemplo mostra a Conversão de PDF para JPEG Cloud Node.js SDK" offSpacer="" %}}

```js

    const fs = require("fs");
    const credentials = require("./credentials.json");
    const { PdfApi } = require("asposepdfcloud");

    // Load your Application Secret and Key from the JSON file or set credentials in another way
    async function convertPDFtoJPEG() {
        const localFileName = "C:\\Samples\\sample.pdf";
        const storageFileName = "sample.pdf";
        const pdfApi = new PdfApi(credentials.id, credentials.key);

        try {
            let fileData = await fs.readFile(localImageFileName);
            let uploadResult = await pdfApi.uploadFile(storageFileName, fileData);
            console.log(uploadResult.response.text);
        }
        catch (error) {
            console.error(error.response.text);
        }

        try {
            let convertResult = await pdfApi.getPageConvertToJpeg(storageFileName, 1);
            fs.writeFileSync("sample.jpg", convertResult.body);
            const buffer = await pdfApi.downloadFile(STORAGE_FILENAME);
        } catch (error) {
            console.error(error.response.text);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< blocks/products/pf/agp/other-supported-section title="Outras Conversões Suportadas" subTitle="Você também pode converter MD em muitos outros formatos de arquivo, incluindo alguns listados abaixo." >}}

{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/bmp-to-pdf/" name="BMP PARA PDF" description="Imagem Bitmap" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/cgm-to-pdf/" name="CGM PARA PDF" description="Formato Binário do Microsoft Word" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/emf-to-pdf/" name="EMF PARA PDF" description="Documento do Office 2007+ Words" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/epub-to-pdf/" name="EPUB PARA PDF" description="Formato de Metarquivo Aprimorado" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/gif-to-pdf/" name="GIF PARA PDF" description="Formato de Intercâmbio Gráfico" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/html-to-pdf/" name="HTML PARA PDF" description="Linguagem de Marcação de Hipertexto" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/jpeg-to-pdf/" name="JPEG PARA PDF" description="Grupo de Especialistas em Fotografia" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/latex-to-pdf/" name="LATEX PARA PDF" description="Texto de Saída LaTeX" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pcl-to-pdf/" name="PCL PARA PDF" description="Linguagem de Comando de Impressora" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/md-to-pdf/" name="MD PARA PDF" description="Markdown" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-bmp/" name="PDF PARA BMP" description="Imagem Bitmap" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-epub/" name="PDF PARA EPUB" description="Formato de E-book" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-gif/" name="PDF PARA GIF" description="Formato de Intercâmbio Gráfico" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-html/" name="PDF PARA HTML" description="Linguagem de Marcação de Hipertexto" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-jpeg/" name="PDF PARA JPEG" description="Grupo Conjunto de Peritos em Fotografia" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-pdfa/" name="PDF PARA PDF/A" description="Formato de Documento Portátil" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-png/" name="PDF PARA PNG" description="Gráficos de Rede Portáteis" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-pptx/" name="PDF PARA PPTX" description="Microsoft PowerPoint" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-svg/" name="PDF PARA SVG" description="Gráficos Vetoriais Escaláveis" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-tex/" name="PDF PARA TEX" description="Sistema de Gráficos Computacionais" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-tiff/" name="PDF PARA TIFF" description="Formato de Imagem Etiquetado" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-word/" name="PDF PARA WORD" description="Formato Binário do Microsoft Word" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-xlsx/" name="PDF PARA XLSX" description="Arquivo de Formato de Planilha do Microsoft Excel Open XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/pdf-to-xps/" name="PDF PARA XPS" description="Especificações de Papel XML" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/png-to-pdf/" name="PNG PARA PDF" description="Gráficos de Rede Portáteis" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/ps-to-pdf/" name="PS PARA PDF" description="PostScript" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/svg-to-pdf/" name="SVG PARA PDF" description="Gráficos Vetoriais Escaláveis" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/text-to-pdf/" name="TEXTO PARA PDF" description="Documento de Texto" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/tiff-to-pdf/" name="TIFF PARA PDF" description="Formato de Imagem Etiquetado" >}}
{{< blocks/products/pf/agp/other-supported-section-item href="https://products.aspose.cloud/pdf/nodejs/conversion/xps-to-pdf/" name="XPS PARA PDF" description="Especificações de Papel XML" >}}

{{< /blocks/products/pf/agp/other-supported-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}


