---
title: Get Tables from PDF via Cloud Node.js SDK 
url: /nodejs/table/get/
description: Aspose.PDF Cloud allows you to get Tables from PDF Document. Check the Node.js source code to get Tables from PDF file.
lastmod: "2024-11-19"
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Extract Tables from PDF in Node.js SDK" h2="API for working with Tables in PDF documents using Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="How to get Tables from PDF via Node.js SDK" %}}

To get Tables from PDF, we'll use
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). This Cloud SDK assists Node.js programmers in developing cloud-based PDF creator, annotator, editor, and converter apps using Node.js programming language via Aspose.PDF REST API. Simply create an account at [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) and get your application information. Once you have the App SID & key, you are ready to give the Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Package Manager Console Command" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Steps to get Tables from PDF via Cloud Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud developers can easily load & get Tables from PDF in just a few lines of code.

{{% /blocks/products/pf/agp/text %}}

1. Read the local PDF file.
1. Upload a local PDF to Aspose Cloud.
1. Retrieve and display all detected tables.
1. Retrieve and display one table by its ID.
1. Downloads the updated PDF file from the Aspose PDF Cloud storage.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Get Tables from PDF using Node.js" offSpacer="" %}}

```js

    import credentials from "../../../../Credentials/credentials.json"  with { type: "json" };
    import fs from 'node:fs/promises';
    import path from 'node:path';
    import { PdfApi } from "../../../src/api/api.js";

    const configParams = {
        LOCAL_FOLDER: "C:\\Samples\\",
        PDF_DOCUMENT_NAME: "sample.pdf",
        PAGE_NUMBER: 2,                                 // Your document page number...
        TABLE_ID: "GE5TCOZSGAYCYNRQGUWDINZVFQ3DGMA",    // Your table id...
    };

    const pdfApi = new PdfApi(credentials.id, credentials.key);

    const pdfTables = {
        async uploadDocument () {
            const fileNamePath = path.join(configParams.LOCAL_FOLDER, configParams.PDF_DOCUMENT_NAME);
            const pdfFileData = await fs.readFile(fileNamePath);
            await pdfApi.uploadFile(configParams.PDF_DOCUMENT_NAME, pdfFileData);
        },
                            
        async getAllTables () {
            const resultTabs = await pdfApi.getDocumentTables(configParams.PDF_DOCUMENT_NAME);

            if (resultTabs.body.code == 200 && resultTabs.body.tables) {
                if (!Array.isArray(resultTabs.body.tables.list) || resultTabs.body.tables.list.length === 0) {
                    throw new Error("Unexpected error : tables is null or empty!!!");
                }
                this.showTablesInfo(resultTabs.body.tables.list, "All tables");
                return resultTabs.body.tables.list;
            }
            else
                console.error("Unexpected error : can't get links!!!");
        },

        async getTableById () {
            const resultTabs = await pdfApi.getTable(configParams.PDF_DOCUMENT_NAME, configParams.TABLE_ID);

            if (resultTabs.body.code == 200 && resultTabs.body.table) {
                this.showTablesInfo( [ resultTabs.body.table ], "Table by Id");
                return resultTabs.body.table;
            }
            else
                console.error("Unexpected error : can't get links!!!");
        },

        showTablesInfo(tables, prefix) {
            if (Array.isArray(tables) && tables.length > 0)
            {
                tables.forEach(function(table) {
                    console.log(prefix +" => id: '" + table.id + "', page: '" + table.pageNum + "', rows: '" + table.rowList.length + "', columns: '" + table.rowList[0].cellList.length + "'");
                });
            }
            else
                console.error("showBoormarks() error: array of tables is empty!")
        },
    }

    async function main() {
        try {
            await pdfTables.uploadDocument();
            await pdfTables.getAllTables();
            await pdfTables.getTableById();
        } catch (error) {
            console.error("Error:", error.message);
        }
    }
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Get Tables from PDF" %}}

Extracting tables from PDF documents is essential for transforming static, unstructured content into usable, structured data. It enables efficient data analysis, automation, integration with business systems, and digital transformation. This process saves time, improves accuracy, supports large-scale document processing, and allows for easy reuse of data in reports, applications, and audits.
Extract Tables from PDF documents with [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

**With our Node.js library you can:**

+ Add PDF document's header & footer in text or image format.
+ Add tables & stamps (text or image) to PDF documents.
+ Append multiple PDF documents to an existing file.
+ Work with PDF attachments, annotations, & form fields.
+ Apply encryption or decryption to PDF documents & set a password.
+ Delete all stamps & tables from a page or entire PDF document.
+ Delete a specific stamp or table from the PDF document by its ID.
+ Replace single or multiple instances of text on a PDF page or from the entire document.
+ Extensive support for converting PDF documents to various other file formats.
+ Extract various elements of PDF files & make PDF documents optimized.
+ You can try out our [free App](https://products.aspose.app/pdf/table-extraction) to extract Table into PDF files online and test the functionality.

{{% /blocks/products/pf/agp/content %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/support-learning-resources >}}
{{< blocks/products/pf/slr-tab tabTitle="Learning Resources" tabId="resources" >}}
{{< blocks/products/pf/slr-element name="Documentation" href="https://docs.aspose.cloud/pdf" >}}
{{< blocks/products/pf/slr-element name="Source Code" href="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-nodejs" >}}
{{< blocks/products/pf/slr-element name="API References" href="https://reference.aspose.cloud/pdf/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Product Support" tabId="support" >}}
{{< blocks/products/pf/slr-element name="Free Support" href="https://forum.aspose.cloud/c/pdf/13" >}}
{{< blocks/products/pf/slr-element name="Paid Support" href="https://helpdesk.aspose.cloud" >}}
{{< blocks/products/pf/slr-element name="Blog" href="https://blog.aspose.cloud/categories/aspose.pdf-cloud-product-family/" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< blocks/products/pf/slr-tab tabTitle="Why Aspose.PDF Cloud for Node.js?" tabId="success-stories" >}}
{{< blocks/products/pf/slr-element name="Customers List" href="https://company.aspose.cloud/customers" >}}
{{< blocks/products/pf/slr-element name="Security" href="https://company.aspose.cloud/legal/security" >}}
{{< /blocks/products/pf/slr-tab >}}

{{< /blocks/products/pf/support-learning-resources >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}


