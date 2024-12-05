---
title: Add Table to PDF via Cloud Node.js SDK 
url: /nodejs/table/add/
description: Aspose.PDF Cloud allows you to add a Table to a PDF Document. Check the Node.js source code to add a Table into PDF file.
lastmod: "2024-11-19"
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Add Table to PDF document via Node.js Cloud API" h2="Build your own Node.js apps to create Fillable document files using server-side APIs." logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-node.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-node.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="How to add Table to PDF via Node.js SDK" %}}

To add Table into PDF, we'll use
[Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/). This Cloud SDK assists Node.js programmers in developing cloud-based PDF creator, annotator, editor, and converter apps using Node.js programming language via Aspose.PDF REST API. Simply create an account at [Aspose for Cloud](https://dashboard.aspose.cloud/#/apps) and get your application information. Once you have the App SID & key, you are ready to give the Aspose.PDF Cloud Node.js SDK.

{{% blocks/products/pf/agp/code-block title="Package Manager Console Command" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Steps to add Table into PDF via Cloud Node.js" %}}

{{% blocks/products/pf/agp/text %}}

Aspose.PDF Cloud developers can easily load & add Table to PDF in just a few lines of code.

{{% /blocks/products/pf/agp/text %}}

1. Read the local PDF file.
1. Uploads the PDF file to the Aspose PDF Cloud storage.
1. Creates a table with two cells and adds it to the PDF file.
1. Downloads the updated PDF file from the Aspose PDF Cloud storage.

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/feature-section-col title="System Requirements" %}}

{{% blocks/products/pf/agp/text %}}

It is easy to get started with Aspose.PDF Cloud Node.js SDK and there is nothing to install. Simply create an account at Aspose for Cloud and get your application information. Once you have the App SID & key, you are ready to give the Aspose.PDF Cloud Node.js SDK.

* CPU: 1GHz
* RAM: 512Mb
* Free space on disk: 20Mb
* Any OS Microsoft Windows, Mac OS, Linux x32/x64
* node.js v4.8 or higher

{{% /blocks/products/pf/agp/text %}}

{{% /blocks/products/pf/agp/feature-section-col %}}

{{% blocks/products/pf/agp/code-block title="Add Table to PDF - Node.js" offSpacer="" %}}

```js

import credentials from "./credentials.json"  with { type: "json" };
import fs from 'node:fs/promises';
import { PdfApi } from "asposepdfcloud";
import { Color } from "asposepdfcloud/src/models/color.js";
import { FontStyles } from "asposepdfcloud/src/models/fontStyles.js";
import { LineSpacing } from "asposepdfcloud/src/models/lineSpacing.js";
import { Paragraph } from "asposepdfcloud/src/models/paragraph.js";
import { TextHorizontalAlignment } from "asposepdfcloud/src/models/textHorizontalAlignment.js";
import { VerticalAlignment } from "asposepdfcloud/src/models/verticalAlignment.js";
import { WrapMode } from "asposepdfcloud/src/models/wrapMode.js";
import { TextLine } from "asposepdfcloud/src/models/textLine.js";
import { Segment } from "asposepdfcloud/src/models/segment.js";
import { Rectangle } from "asposepdfcloud/src/models/rectangle.js";
import { TextState } from "asposepdfcloud/src/models/textState.js";
import { Row } from "asposepdfcloud/src/models/row.js";
import { Cell } from "asposepdfcloud/src/models/cell.js";

const LOCAL_FILE_NAME = "c:\\Samples\\sample.pdf";
const STORAGE_FILENAME = "sample.pdf";
const PAGE_NUMBER = 1;
const TEXT_CONTENT = "Lorem ipsum dolor sit amet, consectetur adipiscing elit.";

async function add() {
    const pdfApi = new PdfApi(credentials.id, credentials.key);
    try {

        const fileBuffer = await fs.readFile(LOCAL_FILE_NAME);
        await pdfApi.uploadFile(STORAGE_FILENAME, fileBuffer);

        const decor = new GraphInfo();
        decor.Color = Object.assign(new Color(), { a: 255, r: 0, g: 0, b: 255 });
        decor.LineWidth = 2;
        decor.IsDoubled = true;

        const cells = [Object.assign(new Cell(), { HtmlFragment: "<strong>Cell 1</strong>" }),
        Object.assign(new Cell(), { HtmlFragment: "<strong>Cell 2</strong>" })];

        const rows = [Object.assign(new Row(), { Cells: cells })];

        const demoTable = new Table();
        demoTable.Rows = rows;
        demoTable.Top = 600;
        demoTable.Left = 10;
        demoTable.Border = new BorderInfo(decor, decor, decor, decor);
        demoTable.ColumnWidths = "150 300";

        const tables = [demoTable];
        await pdfApi.postPageTables(STORAGE_FILENAME, PAGE_NUMBER, tables);
        const buffer = await pdfApi.downloadFile(STORAGE_FILENAME)


        console.log(result.body.status);
    } catch (error) {
        console.error("Error adding text to PDF:", error.message);
    }
}
```

{{% /blocks/products/pf/agp/code-block %}}

{{% blocks/products/pf/agp/content h2="Work with Table in PDF" %}}

Tables provide a structured format for presenting data systematically, making it easier for readers to understand and analyze information. They also enhance the visual appeal of a document, adding professionalism and organization. When dealing with numerical or comparative data, tables improve clarity by grouping related information in an easy-to-read format. Additionally, tables can incorporate real-time or dynamically generated content, such as data from databases or analytics dashboards.
Add the Table into PDF documents with [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/).

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

<!-- aboutfile Starts -->

{{% blocks/products/pf/agp/content h2="About Aspose.PDF Cloud Node.js SDK" %}}

[Aspose.PDF Cloud](https://products.aspose.cloud/pdf) is a true REST API that enables you to perform a wide range of document processing operations including creation, manipulation, conversion and rendering of PDF documents in the cloud.

Our Cloud SDKs are wrappers around REST API in various programming languages, allowing you to process documents in language of your choice quickly and easily, gaining all benefits of strong types and IDE highlights. This repository contains new generation SDKs for Aspose.PDF Cloud and examples.

These SDKs are now fully supported. If you have any questions, see any bugs or have enhancement request, feel free to reach out to us at Free [Support Forums](https://forum.aspose.cloud/c/pdf).

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/about-file-section >}}

{{< blocks/products/pf/agp/demobox sectionTitle="Extract table from PDF" sectionDescription="Add Table into PDF by visiting our [Live Demos website](https://products.aspose.app/pdf/table-extraction). The live demo has the following benefits" >}}

{{< blocks/products/pf/agp/democard icon="fa-cogs" text=" No need to download or setup anything" >}}
{{< blocks/products/pf/agp/democard icon="fa-edit" text=" No need to write any code" >}}
{{< blocks/products/pf/agp/democard icon="fa-file-text" text="Click the button. Your PDF files will be uploaded and will be added." >}}
{{< blocks/products/pf/agp/democard icon="fa-download" text=" Instantly get the download link for the resultant file" >}}

{{< blocks/products/pf/agp/about-file-text fileFormat="PDF" readMoreLink="https://docs.fileformat.com/view/pdf/" >}}
Portable Document Format (PDF) is a type of document created by Adobe back in 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins. Most of the commercially available software suites also offer conversion of their documents to PDF file format without the requirement of any additional software component. Thus, PDF file format has full capability to contain information like text, images, hyperlinks, form-fields, rich media, digital signatures, attachments, metadata, Geospatial features and 3D objects in it that can become as part of source document.

{{< /blocks/products/pf/agp/about-file-text >}}

{{< /blocks/products/pf/agp/about-file-section >}}

{{< /blocks/products/pf/agp/demobox >}}

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

