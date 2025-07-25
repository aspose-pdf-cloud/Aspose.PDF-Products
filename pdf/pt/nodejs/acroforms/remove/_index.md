---
title: Remover Campos de Formulário de Documento PDF via Cloud Node.js SDK
url: nodejs/acroforms/remove/
description: Remova campos de formulário indesejados de PDFs com Node.js usando Aspose.PDF Cloud. Limpe e organize seus formulários.
lastmod: 2024-03-19
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Remover Formulários PDF no Node.js SDK" h2="Exclua todos os campos de formulário de um Documento PDF usando Node.js Cloud SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="Remover um AcroForms de documento PDF via Cloud Node.js SDK" %}}

Para excluir um AcroForms de um PDF, usaremos
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). Este SDK em nuvem auxilia programadores Node.js a desenvolver aplicativos em nuvem para criação, anotação, edição e conversão de PDFs usando a linguagem de programação Node.js via Aspose.PDF REST API. Basta criar uma conta em [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) e obter as informações do seu aplicativo. Uma vez que você tenha o App SID e a chave, você está pronto para usar o Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Comando do Console do Gerenciador de Pacotes" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Passos para remover AcroForms usando Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Desenvolvedores do Aspose.PDF Cloud podem facilmente carregar e excluir acroforms de um PDF em apenas algumas linhas de código.

{{% /blocks/products/pf/agp/text %}}

1. Carregue o arquivo PDF no serviço Aspose.PDF Cloud.
1. Exclua o campo de formulário especificado do arquivo carregado.
1. Baixe o resultado se necessário.

{{% /blocks/products/pf/agp/feature-section-col %}}


{{% blocks/products/pf/agp/code-block title="Este código de exemplo mostra a remoção de AcroForms de documentos PDF usando Node.js" offSpacer="" %}}

```js

    import credentials from "./credentials.json" with { type: "json" };
    import fs from 'node:fs/promises';
    import { PdfApi } from "asposepdfcloud";
    import { Border } from "asposepdfcloud/src/models/border";
    import { TextBoxField } from "asposepdfcloud/src/models/textBoxField";
    import { Dash } from "asposepdfcloud/src/models/dash";
    import { Rectangle } from "asposepdfcloud/src/models/rectangle";
    import { Field } from "asposepdfcloud/src/models/field";
    import { FieldType } from "asposepdfcloud/src/models/fieldType";
    import { Fields } from "asposepdfcloud/src/models/fields";

    async function removeFormField() {
        const localFileName = "C:\\Samples\\StudentInfoFormElectronic.pdf";
        const storageFileName = "StudentInfoFormElectronic.pdf";

        const pdfApi = new PdfApi(credentials.id, credentials.key);
        try {
            let fileData = await fs.readFile(localFileName);
            let uploadResult = await pdfApi.uploadFile(storageFileName, fileData);
            console.log(uploadResult.response.text);
        }
        catch (error) {
            console.error(error.message);
        }

        try {
            let response = await pdfApi.deleteField(storageFileName, "First Name");
            console.log(response.body.status);
        }
        catch (error) {
            console.log(error.message);
        }

    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Trabalhar com AcroForms via Node.js SDK" %}}

Se um formulário estiver desatualizado, irrelevante ou não for mais necessário, excluí-lo ajuda a simplificar o documento e manter a relevância. Remover formulários pode tornar um PDF mais simples e fácil de ler, especialmente se os formulários não forem mais destinados à interação. Elementos interativos como AcroForms podem aumentar o tamanho do arquivo PDF. Excluí-los pode otimizar o documento para um compartilhamento ou armazenamento mais rápido.
Remova um AcroForms de documentos PDF com [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**Com nossa biblioteca Node.js você pode**

+ Adicionar cabeçalho e rodapé ao documento PDF em formato de texto ou imagem.
+ Adicionar tabelas e carimbos (texto ou imagem) a documentos PDF.
+ Anexar vários documentos PDF a um arquivo existente.
+ Trabalhar com anexos, anotações e campos de formulário de PDF.
+ Aplicar criptografia ou descriptografia a documentos PDF e definir uma senha.
+ Excluir todos os carimbos e tabelas de uma página ou de todo o documento PDF.
+ Excluir um carimbo ou tabela específico do documento PDF pelo seu ID.
+ Substituir uma ou mais instâncias de texto em uma página PDF ou em todo o documento.
+ Suporte extensivo para converter documentos PDF em vários outros formatos de arquivo.
+ Extrair vários elementos de arquivos PDF e otimizar documentos PDF.
+ Você pode experimentar nosso [App gratuito](https://products.aspose.app/pdf/xfa) para excluir AcroForms de arquivos PDF online e testar a funcionalidade.

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



