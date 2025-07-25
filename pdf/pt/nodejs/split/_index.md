---
title: Dividir Documentos PDF Únicos | Node.js
description: Divida PDF em vários arquivos no Node.js usando o Aspose.PDF Cloud SDK. Automatize a segmentação de documentos.
weight: 40
url: nodejs/split/
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Dividir PDF no Node.js SDK" h2="Dividir arquivos PDF no Node.js Cloud SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Como Dividir Arquivos PDF Usando o Node.js SDK" %}}

**Por que preciso dividir documentos PDF?** Dividir PDFs com PHP pode ser necessário ao gerenciar e organizar documentos grandes ou trabalhar em um ambiente de processamento de dados. Às vezes, um documento maior requer apenas uma seção separada ou conjunto de páginas. A divisão de PDF permite que você destaque e extraia as páginas correspondentes sem o restante do documento.

Além disso, enviar ou compartilhar todos os PDFs pode ser ineficiente, especialmente se o documento for grande e contiver mais informações do que o necessário. Ao dividir PDFs, você só precisa separar as páginas correspondentes, o que torna o processo mais rápido e economiza largura de banda.

Dividir PDF em seções menores pode reduzir o tamanho do arquivo, o que é útil quando você tem problemas de armazenamento ou está carregando documentos em sistemas com restrições de tamanho.

{{% blocks/products/pf/agp/code-block title="Comando do Console do Gerenciador de Pacotes" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Passos para Dividir PDF via Cloud Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Um programa básico para dividir pdfs programaticamente com
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)
APIs podem ser feitos com apenas algumas linhas de código.

{{% /blocks/products/pf/agp/text %}}

1. Carregue seu Segredo e Chave de Aplicação do arquivo JSON ou configure as credenciais de outra forma
1. Crie um objeto para conectar à API Cloud
1. Faça o upload do arquivo do seu documento
1. Divide o documento PDF carregado usando a API PDF.
1. Baixe cada página dividida como um arquivo PDF separado e salve-os localmente.

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Dividir arquivos PDF únicos usando Node.js" offSpacer="" %}}

```js


    import credentials from "./credentials.json" with { type: "json" };
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "asposepdfcloud";

    async function splitSingle() {
        try {
            // The initialization assumes that the necessary credentials (Application ID and Application Key) from https://dashboard.aspose.cloud/
            const pdfApi = new PdfApi(credentials.id, credentials.key);

            const buffer = await fs.readFile(LOCAL_FILE_NAME);
            await pdfApi.uploadFile(STORAGE_FILENAME, buffer);
            const result = await pdfApi.postSplitDocument(STORAGE_FILENAME);

            console.log(result.body.status);
            await Promise.all(
                result.body.result.documents.map(async (document, index) => {
                    const downloadRes = await pdfApi.downloadFile(document.href);
                    await fs.writeFile(`page${index + 1}.pdf`, downloadRes.body);
                })
            );
        } catch (error) {
            console.error(error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Com nossa ferramenta Node.js você pode:" %}}

+ Adicionar cabeçalho e rodapé do documento PDF em formato de texto ou imagem.
+ Adicionar tabelas e selos (texto ou imagem) a documentos PDF.
+ Anexar vários documentos PDF a um arquivo existente.
+ Trabalhar com anexos, anotações e campos de formulário de PDF.
+ Aplicar criptografia ou descriptografia a documentos PDF e definir uma senha.
+ Excluir todos os selos e tabelas de uma página ou de todo o documento PDF.
+ Excluir um selo ou tabela específico do documento PDF por seu ID.
+ Substituir instâncias únicas ou múltiplas de texto em uma página PDF ou em todo o documento.
+ Suporte extensivo para converter documentos PDF em vários outros formatos de arquivo.
+ Extrair vários elementos de arquivos PDF e otimizar documentos PDF.
+ Você pode experimentar nosso [App gratuito](https://products.aspose.app/pdf/split-pdf) para dividir arquivos PDF online e testar a funcionalidade.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Recursos de Aprendizado" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentação" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Código Fonte" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="Referências da API" href="https://reference.aspose.cloud/pdf/" >}}
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



