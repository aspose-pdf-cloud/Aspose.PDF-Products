---
title: Extrair anexos de documentos PDF via Aspose.Pdf Cloud Node.js SDK
url: nodejs/attachments/get/
description: Extraia anexos de PDF usando Node.js e Aspose.PDF Cloud SDK. Acesse conteúdo incorporado via API.
lastmod: 2024-10-29
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Extrair Anexos de PDF em Node.js SDK" h2="API para extrair anexos em documentos PDF com Aspose.PDF Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Como extrair anexos de documentos PDF usando Cloud Node.js SDK" %}}

Para trabalhar com anexos em documentos PDF, usaremos
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)
Este SDK Cloud auxilia programadores Node.js a desenvolver aplicativos na nuvem para criar, anotar, editar e converter PDFs usando a linguagem de programação Node.js via Aspose.PDF REST API. Abra
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

{{% blocks/products/pf/agp/feature-section-col title="Passos para extrair anexos usando Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Desenvolvedores do Aspose.PDF Cloud Node.js podem facilmente extrair, anexar e substituir anexos em documentos PDF. Os desenvolvedores precisam de apenas algumas linhas de código.

{{% /blocks/products/pf/agp/text %}}

1. Carregue seu Application Secret e Key do arquivo JSON ou configure as credenciais de outra forma
1. Crie um objeto para conectar-se à API da nuvem
1. Carregue seu arquivo de documento
1. Realize as ações de extração de anexos para o documento PDF
1. Baixe o resultado, se necessário

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Este código de exemplo mostra a extração de anexos de documento PDF usando PDF Cloud Node.js SDK" offSpacer="" %}}

```js

    import credentials from "./credentials.json" with { type: "json" };
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "asposepdfcloud";
    import { AttachmentInfo } from "asposepdfcloud/src/models/attachmentInfo.js";

    async function getAllAttachments() {
        const LOCAL_PATH = "C:\\Samples\\";
        const LOCAL_FILE_NAME = "C:\\Samples\\Attachments\\sample_attachment.pdf";
        const STORAGE_FILE_NAME = "sample_attachment.pdf";
        try {
            const pdfApi = new PdfApi(credentials.id, credentials.key);
            const pdfData = await fs.readFile(LOCAL_FILE_NAME);
            await pdfApi.uploadFile(STORAGE_FILE_NAME, pdfData);

            const result = await pdfApi.getDocumentAttachments(STORAGE_FILE_NAME);

            if (result.body.code === 200 && result.body.attachments) {
                const attachmentList = result.body.attachments.list || [];
                if (!attachmentList.length) {
                    console.error("No attachments found.");
                    return;
                }

                const downloadTasks = attachmentList.map(async (attachment) => {
                    try {
                        const attachmentUrl = attachment.links[0].href;
                        const info = await pdfApi.getDocumentAttachmentByIndex(STORAGE_FILE_NAME, attachmentUrl);
                        const download = await pdfApi.getDownloadDocumentAttachmentByIndex(STORAGE_FILE_NAME, attachmentUrl);
                        await fs.writeFile(path.join(LOCAL_PATH, info.body.attachment.name), download.body);
                    } catch (error) {
                        console.error("Failed to download attachment:", error);
                    }
                });

                await Promise.all(downloadTasks);
            } else {
                console.error("Failed to retrieve attachments. Status:", result.statusCode);
            }
        } catch (error) {
            console.error("Error processing PDF attachments:", error);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabalhar com Anexos em PDF via Node.js SDK" %}}

Obter anexos de um PDF é essencial para acessar conteúdo suplementar, melhorar a eficiência do fluxo de trabalho, garantir conformidade e aumentar a segurança. Ajuda os usuários a recuperar arquivos críticos, automatizar o processamento de documentos e otimizar o gerenciamento de documentos em aplicações empresariais, jurídicas e técnicas.
Obtenha os Anexos de documentos PDF com [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**Com nossa biblioteca Node.js você pode**

+ Adicionar cabeçalho e rodapé de documento PDF em formato de texto ou imagem.
+ Adicionar tabelas e carimbos (texto ou imagem) a documentos PDF.
+ Anexar múltiplos documentos PDF a um arquivo existente.
+ Trabalhar com anexos, anotações e campos de formulário de PDF.
+ Aplicar criptografia ou descriptografia a documentos PDF e definir uma senha.
+ Excluir todos os carimbos e tabelas de uma página ou de todo o documento PDF.
+ Excluir um carimbo ou tabela específico do documento PDF pelo seu ID.
+ Substituir uma ou várias instâncias de texto em uma página PDF ou em todo o documento.
+ Suporte extensivo para converter documentos PDF para vários outros formatos de arquivo.
+ Extrair vários elementos de arquivos PDF e otimizar documentos PDF.
+ Você pode experimentar nosso [App gratuito](https://products.aspose.app/pdf/xfa) para adicionar AcroForms em arquivos PDF online e testar a funcionalidade.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
