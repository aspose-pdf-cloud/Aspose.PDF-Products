---
title: Adicionar Carimbo de Imagem ao PDF via Cloud Node.js SDK
url: nodejs/stamp/image/
description: Adicione carimbos baseados em imagem a PDFs usando Node.js e o Aspose.PDF Cloud SDK.
lastmod: 2025-02-20
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Adicionar Carimbo de Imagem ao PDF no Node.js SDK" h2="Adicionar Carimbo de Imagem ao Documento PDF usando Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Como adicionar Carimbo via Node.js SDK" %}}

Para adicionar Carimbo de Imagem ao PDF, usaremos
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Este Cloud SDK auxilia programadores Node.js no desenvolvimento de aplicativos criadores, anotadores, editores e conversores de PDF na nuvem, usando a linguagem de programação Node.js via Aspose.PDF REST API. Basta criar uma conta em [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) e obter suas informações de aplicação. Uma vez que você tenha o App SID & key, estará pronto para usar o Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Comando do Console do Gerenciador de Pacotes" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Passos para adicionar Carimbos via Cloud Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Os desenvolvedores do Aspose.PDF Cloud podem facilmente adicionar Carimbo de Imagem ao PDF com apenas algumas linhas de código.

{{% /blocks/products/pf/agp/text %}}

1. Crie um objeto para conectar à API Pdf.Cloud
1. Carregue o arquivo do seu documento
1. Crie um novo carimbo de imagem para a página com as propriedades necessárias
1. Anexe o novo carimbo de imagem à página do documento usando a função putPageAddStamp()
1. Execute alguma ação após a adição bem-sucedida
1. Baixe o resultado se necessário

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Este código de exemplo mostra a adição de Carimbos usando Node.js" offSpacer="" %}}

```js

    import credentials from "./credentials.json"  with { type: "json" };
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "asposepdfcloud";
    import { Stamp } from "asposepdfcloud/src/models/stamp.js"; 

    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample.pdf",
        IMAGE_STAMP_FILE: "sample.png",
        LOCAL_RESULT_DOCUMENT_NAME: "output_sample.pdf",
        PAGE_NUMBER: 2,     // Your document page number...
        IMAGE_STAMP_LLY: 800,
        IMAGE_STAMP_WIDTH: 24,
        IMAGE_STAMP_HEIGHT: 24,
    };

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfPages = {
        async uploadFile (fileName) {
            const fileNamePath = path.join(configParams.LOCAL_FOLDER, fileName);
            const pdfFileData = await fs.readFile(fileNamePath);
            await pdfApi.uploadFile(fileName, pdfFileData);
        },
                        
        async downloadResult () {
            const changedPdfData = await pdfApi.downloadFile(configParams.PDF_DOCUMENT_NAME);
            const filePath = path.join(configParams.LOCAL_FOLDER, configParams.LOCAL_RESULT_DOCUMENT_NAME);
            await fs.writeFile(filePath, changedPdfData.body);
            console.log("Downloaded: " + filePath);
        },

        async uploadDocument () {
            await this.uploadFile(configParams.PDF_DOCUMENT_NAME);
        },

        async addPageImageStamp () {
            const pageStamp = new Stamp();
            pageStamp.type = "Image";
            pageStamp.background = true;
            pageStamp.horizontalAlignment = "Center";
            pageStamp.textAlignment = "Center";
            pageStamp.value = "NEW TEXT STAMP";
            pageStamp.pageIndex = configParams.PAGE_NUMBER;
            pageStamp.fileName = configParams.IMAGE_STAMP_FILE;
            pageStamp.yIndent = configParams.IMAGE_STAMP_LLY;
            pageStamp.width = configParams.IMAGE_STAMP_WIDTH;
            pageStamp.height = configParams.IMAGE_STAMP_HEIGHT;
            
            const resultPages = await pdfApi.putPageAddStamp(configParams.PDF_DOCUMENT_NAME, configParams.PAGE_NUMBER, pageStamp);

            if (resultPages.body.code == 200) {
                console.log("Image Stamp added!");
                return true;
            }
            else
                console.error("Unexpected error : can't get pages!!!");
        },
    }

    async function main() {
        try {
            await pdfPages.uploadDocument();
            await pdfPages.uploadFile(configParams.IMAGE_STAMP_FILE);
            await pdfPages.addPageImageStamp();
            await pdfPages.downloadResult();
        } catch (error) {
            console.error("Error:", error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabalhar com os Carimbos via Node.js SDK" %}}

Adicionar carimbos a documentos PDF serve a múltiplos propósitos, aprimorando tanto a funcionalidade quanto a segurança dos arquivos digitais. Como desenvolvedor, compreender esses benefícios pode informar a implementação de recursos que agilizam fluxos de trabalho de documentos e reforçam a integridade dos dados. Em ambientes colaborativos, documentos muitas vezes requerem várias revisões e aprovações. Os carimbos podem impedir a distribuição e modificação não autorizadas. A funcionalidade de carimbos em sistemas de gestão de PDF pode melhorar significativamente os fluxos de trabalho, segurança e conformidade dos documentos. Ao alavancar efetivamente os carimbos, as organizações podem garantir que seus documentos sejam profissionais e protegidos.
Adicione os Carimbos aos documentos PDF com [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**Com nossa biblioteca Node.js você pode**

+ Adicionar cabeçalho e rodapé do documento PDF em formato de texto ou imagem.
+ Adicionar tabelas e carimbos (texto ou imagem) a documentos PDF.
+ Anexar múltiplos documentos PDF a um arquivo existente.
+ Trabalhar com anexos de PDF, anotações e campos de formulário.
+ Aplicar criptografia ou descriptografia a documentos PDF e definir uma senha.
+ Excluir todos os carimbos e tabelas de uma página ou de todo o documento PDF.
+ Excluir um carimbo ou tabela específica do documento PDF pelo seu ID.
+ Substituir uma ou várias instâncias de texto em uma página PDF ou de todo o documento.
+ Suporte extenso para converter documentos PDF em vários outros formatos de arquivo.
+ Extrair vários elementos de arquivos PDF e otimizar documentos PDF.
+ Você pode experimentar nossos [Apps gratuitos](https://products.aspose.app/pdf/family/) para testar a funcionalidade online.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Recursos de Aprendizado" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentação" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Código Fonte" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="Referências de API" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Suporte ao Produto" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Suporte Gratuito" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Suporte Pago" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Por que Aspose.PDF Cloud para Node.js?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Lista de Clientes" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Segurança" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}



