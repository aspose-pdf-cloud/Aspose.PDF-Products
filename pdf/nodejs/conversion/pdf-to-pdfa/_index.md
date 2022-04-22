---
title: Convert PDF to PDF/A via Cloud Node.js SDK
url: /nodejs/conversion/pdf-to-pdfa/
description: Sample code for PDF to PDF/A Cloud Node.js SDK conversion. Use API example code for batch PDF files to PDF/A conversion with Aspose.PDF Cloud.
lastmod: "2022-03-17"
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/upper-banner h1="Convert PDF to PDF/A via Cloud Node.js SDK" h2="Export PDF documents to multiple formats including PDF/A with Aspose.PDF Cloud Node.js SDK" logoImageSrc="https://products.aspose.cloud/headers/aspose_pdf-for-net.svg" sourceAdditionalConversionTag="" additionalConversionTag="PDF" pfName="" subTitlepfName="" downloadUrl="" fileiconsmall1="HTML" fileiconsmall2="JPG" fileiconsmall3="PDF" fileiconsmall4="XML" fileiconsmall5="DOCX" >}}

{{< blocks/products/pf/main-container pfName="Aspose.PDF Cloud" subTitlepfName="Node.js SDK" >}}
{{< blocks/products/pf/sub-menu logoImageSrc="https://products.aspose.cloud/sdk/aspose_pdf-for-net.svg"
autoGeneratedVersion="true"
liveDemosLink="https://products.aspose.app/pdf/family/" PricingLink="https://purchase.aspose.cloud/pricing" buyLink="" docsLink="https://docs.aspose.cloud/pdf"  directDownloadLink="https://github.com/aspose-pdf-cloud/aspose-pdf-cloud-node.js" >}}

{{% blocks/products/pf/agp/content h2="How to Convert PDF to PDF/A Using Node.js SDK" %}}

 To convert PDF to PDF/A, we'll use
 [Aspose.PDF Cloud Node.js SDK](https://products.aspose.cloud/pdf/nodejs/)
 This Cloud SDK SDK assists Node.js programmers in developing cloud-based PDF creator, annotator, editor, and converter apps using Node.js programming language via Aspose.PDF REST API. Open
 [NPM](https://www.npmjs.com/package/asposepdfcloud)
 package manager, search for
 Aspose.PDF Cloud,
 and install. You may also use the following command from the Package Manager Console.

{{% blocks/products/pf/agp/code-block title="Package Manager Console Command" offSpacer="true" %}}

```bash

     
    npm install asposepdfcloud --save
     
     

```

{{% /blocks/products/pf/agp/code-block %}}

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/feature-section isGrey="true" >}}

{{% blocks/products/pf/agp/feature-section-col title="Steps to Convert PDF to PDF/A via Node.js" %}}

{{% blocks/products/pf/agp/text %}}

 Aspose.PDF Cloud Node.js developers can easily load & convert PDF files to PDF/A in just a few lines of code.

{{% /blocks/products/pf/agp/text %}}

1. Load your Application Secret and Key from the JSON file or set credentials in another way
1. Create an object to connect to the Cloud API
1. Upload your document file
1. Perform the conversion using getPdfInStorageToPdfA
1. Download the result if need it

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

{{% blocks/products/pf/agp/code-block title="This sample code shows PDF to PDF/A Cloud Node.js SDK Conversion" offSpacer="" %}}

```js
const fs = require("fs");
const credentials = require("./credentials.json");
const { PdfApi } = require("asposepdfcloud");

// Load your Application Secret and Key from the JSON file or set credentials in another way
async function convertPDFtoPDFA() {
    const localFileName = "C:\\Samples\\sample.pdf";
    const storageFileName = "sample.pdf";
    const pdfApi = new PdfApi(credentials.id, credentials.key);
    let fileData = fs.readFileSync(localFileName);
    try {
        let uploadResult = await pdfApi.uploadFile(storageFileName, fileData);
        console.log(uploadResult.response.text);
    }
    catch (error) {
        console.error(error.response.text);
    }

    try {
        let convertResult = await pdfApi.getPdfInStorageToPdfA(storageFileName,"PDFA1A");
        fs.writeFileSync("sample-pdfa.pdf", convertResult.body);
    } catch (error) {
        console.error(error);
    }
}
```

{{% /blocks/products/pf/agp/code-block %}}

{{< /blocks/products/pf/agp/feature-section >}}

{{< blocks/products/pf/agp/faq-item question="" answer="" >}}

<!-- aboutfile Starts -->

{{< blocks/products/pf/agp/demobox sectionTitle="Free App to Convert PDF/A to PDF" sectionDescription="Check our live demos for [PDF/A to PDF conversion](https://products.aspose.app/pdf/conversion/pdf-to-pdfa1a) with following benefits." >}}
{{< blocks/products/pf/agp/democard icon="fa-cogs" text=" No need to download or setup anything." >}}
{{< blocks/products/pf/agp/democard icon="fa-edit" text=" No need to write any code." >}}
{{< blocks/products/pf/agp/democard icon="fa-file-text" text=" Just upload your PDF/A file and hit the \"Convert\" button." >}}
{{< blocks/products/pf/agp/democard icon="fa-download" text=" You will instantly receive a link to download the result."  >}}

{{% blocks/products/pf/agp/content h2="" %}}

A PDF Processing Library to create cross-platform applications with the ability to generate, modify, convert, render, secure and print documents without using Adobe Acrobat. .NET PDF API offers compression, table creation, graph & image functions, hyperlinks, stamp and watermarking tasks, extended security controls & custom font handling.

{{% /blocks/products/pf/agp/content %}}

{{< blocks/products/pf/agp/about-file-section >}}

{{< blocks/products/pf/agp/about-file-text fileFormat="PDF" readMoreLink="https://docs.fileformat.com/pdf/" >}}
Portable Document Format (PDF) is a type of document created by Adobe back in 1990s. The purpose of this file format was to introduce a standard for representation of documents and other reference material in a format that is independent of application software, hardware as well as Operating System. PDF files can be opened in Adobe Acrobat Reader/Writer as well in most modern browsers like Chrome, Safari, Firefox via extensions/plug-ins. Most of the commercially available software suites also offer conversion of their documents to PDF file format without the requirement of any additional software component. Thus, PDF file format has full capability to contain information like text, images, hyperlinks, form-fields, rich media, digital signatures, attachments, metadata, Geospatial features and 3D objects in it that can become as part of source document.


{{< /blocks/products/pf/agp/about-file-text >}}

{{< blocks/products/pf/agp/about-file-text fileFormat="PDF/A" readMoreLink="https://docs.fileformat.com/pdf/a/" >}}
PDF/A is an ISO standard format for archiving of electronic documents in PDF format. Its primary reason for coming into being was to meet the requirements of long term archiving. The standard ensures the opening of archived files even after long time by imposing certain limitations on document integral parts to achieve conformance. The format is now widely adopted across all industries . PDFA/A viewers like Adobe Acrobat Reader, ensure that files saved with this format can be opened even in future in accordance with the information shared by this Standard.

{{< /blocks/products/pf/agp/about-file-text >}}

{{< /blocks/products/pf/agp/about-file-section >}}

{{< /blocks/products/pf/agp/demobox >}}

<!-- aboutfile Ends -->

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}